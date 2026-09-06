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

Global installation can cause package conflicts between Odoo, the operating system, and other Python projects.

A virtual environment isolates Odoo's packages.

$$ \text{Odoo Packages} \rightarrow \text{Dedicated Environment} $$

is safer than:

$$ \text{Everything} \rightarrow \text{Global Python} $$

### QUESTION 2: BEFORE DEPENDENCIES

A Python virtual environment.

Example:

```bash
python3 -m venv .venv
```

Then activate it before:

```bash
pip install -r requirements.txt
```

### QUESTION 3: POSTGRESQL INSTALLED

We still need to know:

- is the server running?
- what version is installed?
- which role Odoo will use?
- can that role authenticate?
- can it create or access the required database?
- how will Odoo connect to it?

Installation alone does not guarantee usable connectivity.

### QUESTION 4: GIT VERSUS ZIP

Git clone gives source files, branch information, commit history, ability to pull updates, ability to compare changes, and a proper version-control workflow.

A ZIP gives mostly a snapshot of files.

### QUESTION 5: DESKTOP MODULE

Because Odoo only searches directories listed in `addons_path`.

An arbitrary folder elsewhere on the machine is invisible to Odoo unless its parent addon directory is configured.

### QUESTION 6: MODULE DISCOVERY CONFIG

`addons_path`.

Example:

```ini
addons_path = /path/to/odoo/addons,/path/to/custom_addons
```

The custom module should live under one of those addon directories.

### QUESTION 7: IDE INTERPRETER

If the terminal uses `.venv` but VS Code uses system Python, then the editor may report missing imports, use the wrong debugger environment, and load different dependencies.

Both should normally point to the same project virtual environment.

### QUESTION 8: PRODUCTION DATABASE NAME

It creates ambiguity.

A developer may accidentally think they are working with a real production database, or accidentally use commands intended for development against the wrong environment.

Better:

```text
odoo19_dev
```

or:

```text
sales_training
```

### QUESTION 9: PASSWORD IN GIT

Git history is persistent.

Even if the password is later removed from the file, it may remain in previous commits.

Secrets should be managed separately and not exposed in a public repository.

### QUESTION 10: CORRECTED ENVIRONMENT

A good structure is:

```text
odoo-development/
├── odoo/
├── custom_addons/
├── .venv/
└── odoo.conf
```

Then:

1. Use supported Python for Odoo 19.
2. Create `.venv`.
3. Activate it.
4. Clone Odoo branch `19.0`.
5. Install `requirements.txt`.
6. Install and start supported PostgreSQL.
7. Configure an Odoo DB role.
8. Add both standard and custom directories to `addons_path`.
9. Create a clearly named development database.
10. Configure VS Code or PyCharm to use `.venv`.
11. Keep secrets out of Git.
12. Enable Developer Mode as needed.
13. Configure logging and debugger.

That gives a reproducible development environment.
