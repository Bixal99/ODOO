# CHAPTER 5 PROJECT: BUILD A CLEAN ODOO DEVELOPMENT WORKSPACE

This is a workspace-design project. You are not required to install Odoo on a real machine to complete it, but every answer must be specific enough that another developer could follow it without guessing. Complete all ten tasks with named components, evidence of purpose, and one verification step where relevant. Self-score each task: 0 = missing/incorrect, 1 = correct label without reasoning, 2 = correct explanation using evidence. Rework every answer below 2.

A project is justified for this chapter because environment design is best learned by assembling a repeatable workspace rather than memorizing tool names.

For source-install docs and verified setup materials when added, see [Resources.md](Resources.md).

---

## TABLE OF CONTENTS

- [Case Study](#case-study)
- [Requirements](#requirements)
- [Constraints](#constraints)
- [Task 1: Directory Structure](#task-1-directory-structure)
- [Task 2: Setup Sequence](#task-2-setup-sequence)
- [Task 3: Sample Configuration](#task-3-sample-configuration)
- [Task 4: addons_path](#task-4-addons_path)
- [Task 5: Naming](#task-5-naming)
- [Task 6: Verify Startup](#task-6-verify-startup)
- [Task 7: Developer Modes](#task-7-developer-modes)
- [Task 8: IDE Setup](#task-8-ide-setup)
- [Task 9: Debugger Verification](#task-9-debugger-verification)
- [Task 10: Startup Troubleshooting Checklist](#task-10-startup-troubleshooting-checklist)
- [Complete Solution](#chapter-5-project-complete-solution)

---

## CASE STUDY

You have joined Nova Retail Group's small Odoo development team.

The current developers each set up Odoo differently.

- One developer uses global Python packages.
- Another modifies standard Odoo files directly.
- Another keeps custom addons in Downloads.
- No one knows which PostgreSQL user is being used.
- New developers need two days just to get Odoo running.

Your task is to design a repeatable local Odoo 19 development environment.

---

## REQUIREMENTS

Your environment must include:

- supported Python,
- virtual environment,
- Odoo 19 Community source,
- Python dependencies,
- PostgreSQL,
- dedicated PostgreSQL role,
- separate custom addons directory,
- configuration file,
- dedicated development database,
- Developer Mode,
- logging,
- IDE integration,
- debugger capability.

---

## CONSTRAINTS

You are not allowed to:

- modify standard Odoo code,
- store custom modules inside random folders,
- use a production DB,
- commit passwords publicly,
- install project dependencies globally unless absolutely required.

This is a workspace-design project.

---

## TASK 1: DIRECTORY STRUCTURE

Design the directory structure. Show official Odoo, custom addons, virtual environment, and configuration as separate concerns.

---

## TASK 2: SETUP SEQUENCE

List the installation and setup sequence in correct order. Include Python, Git, PostgreSQL, clone, venv, dependencies, role, config, database, IDE, and debugger.

---

## TASK 3: SAMPLE CONFIGURATION

Create a sample `odoo.conf` suitable for local development. Mark anything that must be machine-specific.

---

## TASK 4: ADDONS_PATH

Explain the required `addons_path` and what fails if custom addons are omitted.

---

## TASK 5: NAMING

Define database and user naming for:

- PostgreSQL role,
- Odoo database,
- custom addon directory.

Explain why the names communicate purpose.

---

## TASK 6: VERIFY STARTUP

Explain how to verify Odoo starts successfully. Include command shape, log evidence, and browser check.

---

## TASK 7: DEVELOPER MODES

Explain how to activate Developer Mode and Developer Mode with Assets, and when each is appropriate.

---

## TASK 8: IDE SETUP

Explain how to configure the IDE for this workspace. Emphasize interpreter alignment.

---

## TASK 9: DEBUGGER VERIFICATION

Explain how you would verify the debugger works against a real Odoo request.

---

## TASK 10: STARTUP TROUBLESHOOTING CHECKLIST

Create a troubleshooting checklist for a developer whose Odoo does not start. Order the checks so evidence comes before destructive changes.

---

## CHAPTER 5 PROJECT COMPLETE SOLUTION

### TASK 1: DIRECTORY STRUCTURE

A clean structure could be:

```text
odoo19-development/
├── odoo/
│   ├── odoo/
│   ├── addons/
│   ├── odoo-bin
│   └── requirements.txt
│
├── custom_addons/
│
├── .venv/
│
├── config/
│   └── odoo.conf
│
└── logs/
```

The important separation is:

$$ \text{Official Odoo} \neq \text{Custom Addons} $$

### TASK 2: SETUP SEQUENCE

A logical sequence is:

1. Install supported Python for Odoo 19: $$ \text{Python} \geq 3.10 $$
2. Install Git.
3. Install PostgreSQL for Odoo 19: $$ \text{PostgreSQL} \geq 13 $$
4. Create project directory:

```bash
mkdir odoo19-development
cd odoo19-development
```

5. Clone Odoo:

```bash
git clone --branch 19.0 https://github.com/odoo/odoo.git
```

6. Create virtual environment:

```bash
python3 -m venv .venv
```

7. Activate it.

Linux/macOS:

```bash
source .venv/bin/activate
```

Windows:

```powershell
.venv\Scripts\Activate.ps1
```

8. Install dependencies:

```bash
pip install -r odoo/requirements.txt
```

9. Create custom addons:

```bash
mkdir custom_addons
```

10. Configure PostgreSQL role, for example `odoo_dev`.
11. Create configuration file.
12. Run Odoo.
13. Create development database, for example `odoo19_dev`.
14. Configure IDE.
15. Verify debugger.

### TASK 3: SAMPLE CONFIGURATION

Example:

```ini
[options]

db_host = False
db_port = False
db_user = odoo_dev
db_password = False

addons_path = /absolute/path/odoo19-development/odoo/addons,/absolute/path/odoo19-development/custom_addons

http_port = 8069

log_level = info
logfile = /absolute/path/odoo19-development/logs/odoo.log
```

This is a development example, not a universal production configuration. Absolute paths and authentication settings must match the machine.

### TASK 4: ADDONS_PATH

It must contain at least:

- official Odoo addons,
- custom addons.

Conceptually:

**`addons_path`** = Standard + Custom

If custom addons are absent:

$$ \text{Odoo} \not\rightarrow \text{Custom Modules} $$

because they cannot be discovered.

### TASK 5: NAMING

| Item | Example name | Why |
| --- | --- | --- |
| **PostgreSQL role** | `odoo_dev` | Communicates development DB access, not Odoo login |
| **Odoo database** | `odoo19_dev` | Communicates Odoo 19 + development purpose |
| **Custom addon directory** | `custom_addons` | Separates team modules from vendor source |

Names should communicate purpose clearly and reduce accidental production confusion.

### TASK 6: VERIFY STARTUP

Run:

```bash
cd odoo
python odoo-bin -c ../config/odoo.conf
```

Then inspect logs.

You want to see normal startup and module-loading activity rather than Python exceptions.

Official documentation notes that, once module loading is complete, the server can be accessed through the browser, usually on localhost port 8069 in a basic setup.

Open:

```text
http://localhost:8069
```

### TASK 7: DEVELOPER MODES

**Developer Mode**

Use:

```text
?debug=1
```

or activate it through Odoo settings when you need technical menus, model metadata, external IDs, and related inspection tools.

**Assets Mode**

Use:

```text
?debug=assets
```

when frontend asset debugging is required.

### TASK 8: IDE SETUP

Configure the workspace to include:

```text
odoo/
custom_addons/
```

Select the `.venv` Python interpreter.

Enable Python, XML, JavaScript, Git, and debugger support as appropriate.

The most important point is:

$$ \text{IDE Python} = \text{Environment Python} $$

### TASK 9: DEBUGGER VERIFICATION

Create or select Python code that will execute during an Odoo request, for example a method in `nova_order_gate`.

Place a breakpoint.

Launch Odoo through the IDE debugger.

Trigger the relevant operation in the browser.

Expected result:

$$ \text{Browser Action} \rightarrow \text{Odoo Request} \rightarrow \text{Breakpoint Hit} $$

Then inspect local variables, call stack, `self`, and recordsets when applicable.

That confirms the debugger is attached to the correct Odoo process.

### TASK 10: STARTUP TROUBLESHOOTING CHECKLIST

If Odoo does not start, investigate systematically:

1. Is the intended Python version running?
2. Is the virtual environment activated?
3. Were `requirements.txt` dependencies installed successfully?
4. Is PostgreSQL installed?
5. Is PostgreSQL running?
6. Does the configured DB user exist?
7. Can Odoo authenticate to PostgreSQL?
8. Is `odoo-bin` being run from the correct repository?
9. Does `odoo.conf` point to valid paths?
10. Is `addons_path` correct?
11. Is the configured port already in use?
12. What does the traceback or log say?
13. Is the IDE launching the same interpreter as the terminal?
14. Was an incompatible package version manually installed?

Always begin with:

$$ \text{Read the Error} $$

before:

$$ \text{Change Things} $$

---

## CHAPTER 5 PROJECT HANDOFF

This project was workspace design: isolate Python, obtain Odoo 19 source, configure PostgreSQL correctly, separate custom addons, and make the environment inspectable with logs, IDE, and debugger.

At this point Odoo should be conceptually runnable:

$$ \text{Python} + \text{Odoo Source} + \text{PostgreSQL} + \text{Configuration} + \text{Custom Addons} + \text{Debugger} $$

What remains is source navigation:

**Where exactly does everything live inside the Odoo tree?**

That is where Chapter 6 begins: `odoo/`, `addons/`, core framework files, HTTP, services, registry, module loading, official addons, model definitions, XML IDs, and method tracing.

If you still need chapter review before that, return to [Content.md](Content.md), then the [Exercise](Exercise.md). Use [Resources.md](Resources.md) later when verified links are added.
