# CHAPTER 5 EXERCISE

Answer before scrolling to the solution. For each response, give the concept, scenario evidence, and a reason. Self-score each original numbered question or named part: 0 = missing/incorrect, 1 = correct label without reasoning, 2 = correct explanation using evidence. Rework every answer below 2. The solution is one defensible model, not wording to memorize; clearly stated alternative assumptions can support a different answer.

Try answering these without looking back at Content.md first. Answer in your own words, then compare with the complete solution at the bottom of this file.

For source-install docs and verified setup materials when added, see [Resources.md](Resources.md).

---

## TABLE OF CONTENTS

- [Case Study: Broken New Developer Setup](#case-study-broken-new-developer-setup)
- [Question 1: Global Packages](#question-1-global-packages)
- [Question 2: Before Dependencies](#question-2-before-dependencies)
- [Question 3: PostgreSQL Installed](#question-3-postgresql-installed)
- [Question 4: Git Versus ZIP](#question-4-git-versus-zip)
- [Question 5: Desktop Module](#question-5-desktop-module)
- [Question 6: Module Discovery Config](#question-6-module-discovery-config)
- [Question 7: IDE Interpreter](#question-7-ide-interpreter)
- [Question 8: Production Database Name](#question-8-production-database-name)
- [Question 9: Password in Git](#question-9-password-in-git)
- [Question 10: Corrected Environment](#question-10-corrected-environment)
- [Complete Solution](#chapter-5-exercise-complete-solution)

---

## CASE STUDY: BROKEN NEW DEVELOPER SETUP

A junior developer joins Nova Retail Group's Odoo team.

They report:

> Odoo doesn't work on my machine.

You investigate and discover:

- Python 3 is installed.
- They installed packages globally.
- PostgreSQL is installed but they don't know which account Odoo uses.
- They downloaded Odoo as a ZIP.
- Their custom module is inside `Desktop/my_module`.
- Odoo cannot find the module.
- VS Code uses a different Python interpreter than their terminal.
- They are testing directly against a copy named `production`.
- They have `db_password` committed to Git.

Answer the following.

---

## QUESTION 1: GLOBAL PACKAGES

What is wrong with installing all Odoo dependencies globally?

---

## QUESTION 2: BEFORE DEPENDENCIES

What should be created before installing Python dependencies?

---

## QUESTION 3: POSTGRESQL INSTALLED

Why is "PostgreSQL is installed" not enough information?

---

## QUESTION 4: GIT VERSUS ZIP

Why is Git clone preferable to downloading an Odoo ZIP for development?

---

## QUESTION 5: DESKTOP MODULE

Why can't Odoo automatically discover `Desktop/my_module`?

---

## QUESTION 6: MODULE DISCOVERY CONFIG

What configuration should be checked for module discovery?

---

## QUESTION 7: IDE INTERPRETER

Why does it matter that VS Code and the terminal use the same Python interpreter?

---

## QUESTION 8: PRODUCTION DATABASE NAME

Why is a database named `production` dangerous for development experiments?

---

## QUESTION 9: PASSWORD IN GIT

Why is committing `db_password` to Git a problem?

---

## QUESTION 10: CORRECTED ENVIRONMENT

Describe a corrected development environment for this developer.

---

## CHAPTER 5 EXERCISE COMPLETE SOLUTION

### QUESTION 1: GLOBAL PACKAGES

**Concept:** dependency isolation.

**Scenario evidence:** packages were installed globally; Odoo "doesn't work," and other Python projects or the OS may already rely on different package versions.

**Reason:** Global installation can cause package conflicts between Odoo, the operating system, and other Python projects. Odoo needs a controlled set of libraries. The OS may need a different set. Another project may need a third set. Mixing them in one global Python turns every upgrade into a possible breakage.

A virtual environment isolates Odoo's packages:

$$ \text{Odoo Packages} \rightarrow \text{Dedicated Environment} $$

is safer than:

$$ \text{Everything} \rightarrow \text{Global Python} $$

A full-credit answer names both the conflict risk and the isolation remedy, not only "use venv."

### QUESTION 2: BEFORE DEPENDENCIES

**Concept:** create the container before filling it.

**Scenario evidence:** they installed packages globally, which means they skipped the isolation step.

**Reason:** Create and activate a Python virtual environment before installing Odoo dependencies.

Example:

```bash
python3 -m venv .venv
```

Then activate it, confirm the interpreter path points into `.venv`, and only then run:

```bash
pip install -r requirements.txt
```

If you install first and create `.venv` later, the packages are still in the wrong place. Order matters.

### QUESTION 3: POSTGRESQL INSTALLED

**Concept:** installation ≠ usable connectivity.

**Scenario evidence:** PostgreSQL is installed, but nobody knows which account Odoo uses.

**Reason:** "Installed" answers only one question. For Odoo you still need evidence for:

- is the server process running?
- what version is installed (Odoo 19 expects PostgreSQL 13+)?
- which role will Odoo use?
- can that role authenticate?
- can it create or access the required database?
- which host/port/auth method will Odoo use?

Without those answers, Rami can spend hours debugging Odoo when the real gap is a stopped service or an unknown role.

### QUESTION 4: GIT VERSUS ZIP

**Concept:** reproducible source control vs a static snapshot.

**Scenario evidence:** they downloaded Odoo as a ZIP.

**Reason:** Git clone gives source files plus branch information, commit history, update ability, comparison tools, and a normal development workflow. For Odoo 19 study you can clone branch `19.0` deliberately.

A ZIP mostly gives a file snapshot. You can open it, but you lose the easy path to "which branch is this?" and "how do I pull a fix?"

ZIP can be acceptable for a quick look. It is a weak foundation for ongoing development.

### QUESTION 5: DESKTOP MODULE

**Concept:** discovery is path-based, not machine-wide search.

**Scenario evidence:** custom module lives in `Desktop/my_module`; Odoo cannot find it.

**Reason:** Odoo only searches directories listed in `addons_path`. An arbitrary folder on the Desktop is invisible unless its parent addon directory is configured into that path.

The module can be perfect Python and still never appear in Apps. Presence on disk is not the same as discovery.

### QUESTION 6: MODULE DISCOVERY CONFIG

**Concept:** `addons_path` is the discovery map.

**Scenario evidence:** module cannot be found despite existing on disk.

**Reason:** Check `addons_path` in the configuration (or equivalent CLI flags).

Example:

```ini
addons_path = /path/to/odoo/addons,/path/to/custom_addons
```

Then place the custom module under one of those directories, for example:

```text
custom_addons/nova_order_gate/
```

not:

```text
Desktop/my_module/
```

unless Desktop itself is intentionally configured as an addon root, which is a poor professional habit.

### QUESTION 7: IDE INTERPRETER

**Concept:** one project, one interpreter.

**Scenario evidence:** VS Code uses a different Python interpreter than the terminal.

**Reason:** If the terminal uses `.venv` but VS Code uses system Python, the editor may report missing imports, launch the wrong debugger environment, and resolve different dependency versions.

Then the developer hears:

> But it runs in the terminal.

and also:

> But the IDE says the package is missing.

Both can be true. Align:

$$ \text{IDE Interpreter} = \text{Terminal Virtual Environment Interpreter} $$

### QUESTION 8: PRODUCTION DATABASE NAME

**Concept:** naming is a safety control.

**Scenario evidence:** experiments run against a copy named `production`.

**Reason:** The name creates ambiguity. A tired developer may treat it as real production, run destructive commands, or apply experimental modules without the mental brake that `odoo19_dev` provides.

Better names communicate purpose:

```text
odoo19_dev
sales_training
```

Even a restored production dump used for testing should be renamed to something that says "safe to break."

### QUESTION 9: PASSWORD IN GIT

**Concept:** Git history persists secrets.

**Scenario evidence:** `db_password` was committed.

**Reason:** Git history is durable. Removing the password from the current file does not erase earlier commits. Public or shared repositories can leak credentials long after the "fix."

Secrets belong outside public history: local ignored config, secret managers, or environment-specific private files. Treat a leaked password as compromised until rotated.

### QUESTION 10: CORRECTED ENVIRONMENT

**Concept:** reproducible, isolated, inspectable, safe workspace.

**Scenario evidence:** every failure above maps to a missing environment piece.

**Reason:** A corrected layout could be:

```text
odoo-development/
├── odoo/                 # Git clone of branch 19.0
├── custom_addons/        # team modules such as nova_order_gate
├── .venv/                # isolated Python
├── config/odoo.conf      # repeatable settings, no public secrets
└── logs/
```

Then, in order:

1. Use supported Python for Odoo 19 (3.10+).
2. Create and activate `.venv`; verify interpreter path.
3. Clone Odoo branch `19.0` with Git.
4. Install `requirements.txt` into the venv.
5. Install and start supported PostgreSQL (13+); create role `odoo_dev`.
6. Put official and custom directories in `addons_path`.
7. Create a clearly named development database such as `odoo19_dev`.
8. Point VS Code or PyCharm at `.venv`.
9. Keep secrets out of Git.
10. Enable Developer Mode when inspecting; use logging and debugger when diagnosing.

That environment does not merely "open Odoo." It makes failures inspectable and experiments recoverable.
