# UNIT II: FREE LEARNING RESOURCES

## CHAPTER 5: DEVELOPMENT ENVIRONMENT

Chapter 5 is **practical setup**, so the best resources are official Odoo 19.0 source-install and CLI documentation, plus verified technical videos that reinforce a clean local workspace from [Chapter 5 Content](Content.md).

These resources map to Python, virtual environments, dependencies, PostgreSQL, Odoo source, Git clone, configuration, `addons_path`, custom addons, database creation, developer modes, logging, IDE, and debugger setup.

Primary sources support the key concepts in this chapter. Videos and repository listings are supplementary and may change over time. Odoo-specific references use version **19.0** unless a video title states an older teaching version.

> **Verification note:** YouTube video IDs and GitHub repository links below were checked via Composio (YouTube Search + video details batch + GitHub API). Official documentation links target Odoo 19.0.

---

## CHAPTER 5 RESOURCES TABLE OF CONTENTS

- [YouTube: Full Local Setup](#youtube-full-local-setup)
- [YouTube: Virtual Environments](#youtube-virtual-environments)
- [YouTube: Configuration and Addons Path](#youtube-configuration-and-addons-path)
- [YouTube: Custom Modules / Custom Addons](#youtube-custom-modules--custom-addons)
- [YouTube: Developer Mode](#youtube-developer-mode)
- [YouTube: IDE and Debugger](#youtube-ide-and-debugger)
- [Official Documentation](#official-documentation)
- [Repositories](#repositories)
- [Practice / Hands-On](#practice--hands-on)
- [Best Resource Order for Chapter 5](#best-resource-order-for-chapter-5)

---

## YOUTUBE: FULL LOCAL SETUP

### 1. ODOO 19 FULL INSTALLATION ON WINDOWS (VS CODE + POSTGRESQL)

| | |
|---|---|
| **Relevant to** | [5.1 Python Environment](Content.md#51-python-environment), [5.4 PostgreSQL Setup](Content.md#54-postgresql-setup), [5.6 Odoo Source](Content.md#56-odoo-source), [5.15 IDE Setup](Content.md#515-ide-setup) |
| **Source** | Community technical channel (Odooistic) |
| **Reinforces** | End-to-end Windows workspace: Python, PostgreSQL, VS Code, Odoo 19 |

<div align="center">

[![Odoo 19 Full Installation on Windows | VS Code + PostgreSQL + Setup Explained!](https://img.youtube.com/vi/b6HEu5WQ2s8/hqdefault.jpg)](https://www.youtube.com/watch?v=b6HEu5WQ2s8)

**Watch on YouTube:** [Odoo 19 Full Installation on Windows | VS Code + PostgreSQL + Setup Explained!](https://www.youtube.com/watch?v=b6HEu5WQ2s8)

</div>

---

### 2. SET UP ODOO ENVIRONMENT: POSTGRESQL, GITHUB, VS CODE

| | |
|---|---|
| **Relevant to** | [5.1](Content.md#51-python-environment), [5.4](Content.md#54-postgresql-setup), [5.7 Git Clone](Content.md#57-git-clone), [5.15](Content.md#515-ide-setup) |
| **Source** | Community technical channel (Logic Works) |
| **Why use it** | Environment-first framing before module or web-framework work |
| **Version note** | Pair with Odoo 19.0 source-install docs as the authority |

<div align="center">

[![Odoo Web Framework Tutorial | Set Up Odoo Environment | PostgreSQL, GitHub & VS Code](https://img.youtube.com/vi/a2ovPreTqAA/hqdefault.jpg)](https://www.youtube.com/watch?v=a2ovPreTqAA)

**Watch on YouTube:** [Odoo Web Framework Tutorial | Set Up Odoo Environment | PostgreSQL, GitHub & VS Code](https://www.youtube.com/watch?v=a2ovPreTqAA)

</div>

---

### 3. INSTALL ODOO 19 ON UBUNTU

| | |
|---|---|
| **Relevant to** | [5.1](Content.md#51-python-environment), [5.4](Content.md#54-postgresql-setup), [5.6](Content.md#56-odoo-source) |
| **Source** | Community technical channel (Odoo Hub) |
| **Why use it** | Linux path parallel to the Windows install videos |

<div align="center">

[![How to Install Odoo 19 on Ubuntu | Step by Step](https://img.youtube.com/vi/NDnX9k6jyTw/hqdefault.jpg)](https://www.youtube.com/watch?v=NDnX9k6jyTw)

**Watch on YouTube:** [How to Install Odoo 19 on Ubuntu | Step by Step](https://www.youtube.com/watch?v=NDnX9k6jyTw)

</div>

---

### 4. DEVELOPMENT SETUP ON WINDOWS 11 WITH VS CODE

| | |
|---|---|
| **Relevant to** | [5.15 IDE Setup](Content.md#515-ide-setup), full local workspace orientation |
| **Source** | Community technical channel (Exploring Odoo) |
| **Version note** | Older than Odoo 19; keep for IDE layout intuition, then verify against 19.0 docs |

<div align="center">

[![Odoo Tutorial: Development Setup On Windows 11 with VS Code](https://img.youtube.com/vi/wWnZu7-63jU/hqdefault.jpg)](https://www.youtube.com/watch?v=wWnZu7-63jU)

**Watch on YouTube:** [Odoo Tutorial: Development Setup On Windows 11 with VS Code](https://www.youtube.com/watch?v=wWnZu7-63jU)

</div>

---

## YOUTUBE: VIRTUAL ENVIRONMENTS

### 1. VIRTUAL ENVIRONMENTS ON WINDOWS

| | |
|---|---|
| **Relevant to** | [5.2 Python Virtual Environments](Content.md#52-python-virtual-environments) |
| **Source** | Odooistic |
| **Reinforces** | Isolate project packages from the global Python install |

<div align="center">

[![How to use Virtual Environments on the Windows](https://img.youtube.com/vi/PpDCWg_Kb8M/hqdefault.jpg)](https://www.youtube.com/watch?v=PpDCWg_Kb8M)

**Watch on YouTube:** [How to use Virtual Environments on the Windows](https://www.youtube.com/watch?v=PpDCWg_Kb8M)

</div>

---

### 2. PYTHON VENV FOR ODOO 19 AND CONFIG FILE (UBUNTU)

| | |
|---|---|
| **Relevant to** | [5.2](Content.md#52-python-virtual-environments), [5.3 Python Dependencies](Content.md#53-python-dependencies), [5.8 Odoo Configuration File](Content.md#58-odoo-configuration-file) |
| **Source** | Community technical channel (ROYTEK) |
| **Reinforces** | venv + config file as a paired setup habit |

<div align="center">

[![Create Python Virtual Environment for Odoo 19 on Ubuntu and the Odoo Configuration File](https://img.youtube.com/vi/yLcO2A1LA64/hqdefault.jpg)](https://www.youtube.com/watch?v=yLcO2A1LA64)

**Watch on YouTube:** [Create Python Virtual Environment for Odoo 19 on Ubuntu and the Odoo Configuration File](https://www.youtube.com/watch?v=yLcO2A1LA64)

</div>

---

### 3. PYTHON VIRTUAL ENVIRONMENT IN VS CODE

| | |
|---|---|
| **Relevant to** | [5.2](Content.md#52-python-virtual-environments), [5.15](Content.md#515-ide-setup) |
| **Source** | BytePage |
| **Why use it** | Generic VS Code interpreter selection; apply the same habit to Odoo |

<div align="center">

[![How to Set Up a Python Virtual Environment in VS Code](https://img.youtube.com/vi/hvDjgDjKtSU/hqdefault.jpg)](https://www.youtube.com/watch?v=hvDjgDjKtSU)

**Watch on YouTube:** [How to Set Up a Python Virtual Environment in VS Code](https://www.youtube.com/watch?v=hvDjgDjKtSU)

</div>

---

## YOUTUBE: CONFIGURATION AND ADDONS PATH

### 1. UNDERSTANDING THE ODOO CONFIGURATION FILE

| | |
|---|---|
| **Relevant to** | [5.8 Odoo Configuration File](Content.md#58-odoo-configuration-file) |
| **Source** | The Mighty Administrator |
| **Reinforces** | Config as the durable control surface for db, paths, and runtime flags |

<div align="center">

[![Understanding the Odoo Configuration File](https://img.youtube.com/vi/BOX4saaIZ7g/hqdefault.jpg)](https://www.youtube.com/watch?v=BOX4saaIZ7g)

**Watch on YouTube:** [Understanding the Odoo Configuration File](https://www.youtube.com/watch?v=BOX4saaIZ7g)

</div>

---

### 2. CREATE A CONFIGURATION FILE (ODOO 17)

| | |
|---|---|
| **Relevant to** | [5.8](Content.md#58-odoo-configuration-file) |
| **Source** | WebLearns |
| **Version note** | Titled for Odoo 17; pair with Odoo 19.0 CLI / source-install docs |

<div align="center">

[![How to Create a Configuration File for Odoo 17](https://img.youtube.com/vi/DRFn7Rb9uuA/hqdefault.jpg)](https://www.youtube.com/watch?v=DRFn7Rb9uuA)

**Watch on YouTube:** [How to Create a Configuration File for Odoo 17](https://www.youtube.com/watch?v=DRFn7Rb9uuA)

</div>

---

### 3. MULTIPLE ADDONS USING ADDONS-PATH

| | |
|---|---|
| **Relevant to** | [5.9 addons_path](Content.md#59-addons_path), [5.10 Custom Addons Directory](Content.md#510-custom-addons-directory) |
| **Source** | WebLearns |
| **Reinforces** | Core addons and custom addons as separate path entries |

<div align="center">

[![How to add multiple addons using addons-path in Odoo](https://img.youtube.com/vi/TfYvao3hDNU/hqdefault.jpg)](https://www.youtube.com/watch?v=TfYvao3hDNU)

**Watch on YouTube:** [How to add multiple addons using addons-path in Odoo](https://www.youtube.com/watch?v=TfYvao3hDNU)

</div>

---

## YOUTUBE: CUSTOM MODULES / CUSTOM ADDONS

### 1. CREATE A CUSTOM MODULE FROM SCRATCH (ODOO 19)

| | |
|---|---|
| **Relevant to** | [5.10 Custom Addons Directory](Content.md#510-custom-addons-directory) |
| **Source** | Odoo Hub |
| **Reinforces** | Custom code lives outside core; module scaffolding starts after paths are correct |

<div align="center">

[![Odoo 19 Tutorial | How to Create a Custom Module (App) From Scratch](https://img.youtube.com/vi/l9uoxgmS6ig/hqdefault.jpg)](https://www.youtube.com/watch?v=l9uoxgmS6ig)

**Watch on YouTube:** [Odoo 19 Tutorial | How to Create a Custom Module (App) From Scratch](https://www.youtube.com/watch?v=l9uoxgmS6ig)

</div>

---

### 2. CREATE A BASIC MODULE (ODOO 17)

| | |
|---|---|
| **Relevant to** | [5.10](Content.md#510-custom-addons-directory) |
| **Source** | Cybrosys Technologies |
| **Version note** | Titled for Odoo 17; still useful for structure intuition after Chapter 5 paths are set |

<div align="center">

[![How to Create a Basic Module in Odoo 17](https://img.youtube.com/vi/mT43V3twcyE/hqdefault.jpg)](https://www.youtube.com/watch?v=mT43V3twcyE)

**Watch on YouTube:** [How to Create a Basic Module in Odoo 17](https://www.youtube.com/watch?v=mT43V3twcyE)

</div>

---

## YOUTUBE: DEVELOPER MODE

### ACTIVATE DEVELOPER MODE

| | |
|---|---|
| **Relevant to** | [5.12 Developer Mode](Content.md#512-developer-mode) |
| **Source** | TechMoodly |
| **Language note** | Hindi narration; UI steps still map to the official developer mode path |
| **Pair with** | Official [Developer mode (Odoo 19)](https://www.odoo.com/documentation/19.0/applications/general/developer_mode.html) |

<div align="center">

[![How to Activate developer mode in Odoo](https://img.youtube.com/vi/uhVJ7RoaIuM/hqdefault.jpg)](https://www.youtube.com/watch?v=uhVJ7RoaIuM)

**Watch on YouTube:** [How to Activate developer mode in Odoo](https://www.youtube.com/watch?v=uhVJ7RoaIuM)

</div>

---

## YOUTUBE: IDE AND DEBUGGER

### 1. CONFIGURE ODOO 19 WITH PYCHARM

| | |
|---|---|
| **Relevant to** | [5.15 IDE Setup](Content.md#515-ide-setup) |
| **Source** | Odoo Hub |
| **Why use it** | Alternate IDE path (PyCharm) beside VS Code videos |

<div align="center">

[![How to Configure Odoo 19 with PyCharm](https://img.youtube.com/vi/i3V1stWh8fE/hqdefault.jpg)](https://www.youtube.com/watch?v=i3V1stWh8fE)

**Watch on YouTube:** [How to Configure Odoo 19 with PyCharm](https://www.youtube.com/watch?v=i3V1stWh8fE)

</div>

---

### 2. RUN ODOO IN VS CODE DEBUG

| | |
|---|---|
| **Relevant to** | [5.16 Debugger Setup](Content.md#516-debugger-setup) |
| **Source** | Open Source Hustle |
| **Reinforces** | Debugger launch args, restart habit, useful CLI flags |

<div align="center">

[![Run Odoo in VSCode using the Debug feature](https://img.youtube.com/vi/gq4ISuGO8xo/hqdefault.jpg)](https://www.youtube.com/watch?v=gq4ISuGO8xo)

**Watch on YouTube:** [Run Odoo in VSCode using the Debug feature](https://www.youtube.com/watch?v=gq4ISuGO8xo)

</div>

---

### 3. DEBUG ODOO IN VISUAL STUDIO CODE

| | |
|---|---|
| **Relevant to** | [5.16 Debugger Setup](Content.md#516-debugger-setup) |
| **Source** | Community technical channel (Đông Chí) |
| **Version note** | Older Python / launch.json style; treat as pattern, then match your Odoo 19.0 venv and paths |

<div align="center">

[![How to debug Odoo in Visual Studio Code?](https://img.youtube.com/vi/w2t9YKQV7w8/hqdefault.jpg)](https://www.youtube.com/watch?v=w2t9YKQV7w8)

**Watch on YouTube:** [How to debug Odoo in Visual Studio Code?](https://www.youtube.com/watch?v=w2t9YKQV7w8)

</div>

---

## OFFICIAL DOCUMENTATION

Use source install for Python/PostgreSQL/clone/requirements, CLI for config flags and logging, developer mode for Technical menus, and the Javascript reference for debug assets. These references support the corresponding lesson explanations and project decisions.

All links below target **Odoo 19.0** documentation.

| Topic | Relevant sections | Documentation |
|---|---|---|
| **Source installation (Python, PostgreSQL, clone, requirements)** | [5.1](Content.md#51-python-environment)–[5.7](Content.md#57-git-clone), [5.3](Content.md#53-python-dependencies) | [Installing Odoo from source](https://www.odoo.com/documentation/19.0/administration/on_premise/source.html) |
| **Command-line interface (config, db, logging, paths)** | [5.8](Content.md#58-odoo-configuration-file), [5.9](Content.md#59-addons_path), [5.11](Content.md#511-database-creation), [5.14](Content.md#514-logging) | [Command-line interface (CLI)](https://www.odoo.com/documentation/19.0/developer/reference/cli.html) |
| **Developer mode** | [5.12 Developer Mode](Content.md#512-developer-mode) | [Developer mode](https://www.odoo.com/documentation/19.0/applications/general/developer_mode.html) |
| **Javascript / debug assets context** | [5.13 Developer Mode with Assets](Content.md#513-developer-mode-with-assets) | [Javascript Reference](https://www.odoo.com/documentation/19.0/developer/reference/frontend/javascript_reference.html) |
| **Module manifests (after custom path is ready)** | [5.10 Custom Addons Directory](Content.md#510-custom-addons-directory) | [Module Manifests](https://www.odoo.com/documentation/19.0/developer/reference/backend/module.html) |
| **Building a module** | [5.10](Content.md#510-custom-addons-directory), prep for later units | [Building a Module](https://www.odoo.com/documentation/19.0/developer/tutorials/backend.html) |
| **Deploy / data-dir context (sessions, filestore)** | [5.8](Content.md#58-odoo-configuration-file), [5.11](Content.md#511-database-creation) | [System configuration / Deploy](https://www.odoo.com/documentation/19.0/administration/on_premise/deploy.html) |
| **Containers layout (filestore / sessions example)** | [5.8](Content.md#58-odoo-configuration-file) | [Containers](https://www.odoo.com/documentation/19.0/administration/odoo_sh/advanced/containers.html) |

---

## REPOSITORIES

You do **not** need to read all of this source yet. For Chapter 5, repositories help you clone the correct branch and see where setup claims live in real trees.

### OFFICIAL ODOO

| Repository | Relevant to | Link |
|---|---|---|
| **odoo/odoo** | Source tree to clone for local development; default branch tracks 19.0 | [GitHub: odoo/odoo](https://github.com/odoo/odoo) |
| **odoo/documentation** | Source of the official docs linked above; default branch 19.0 | [GitHub: odoo/documentation](https://github.com/odoo/documentation) |
| **odoo/tutorials** | Official tutorial bases aligned with developer docs | [GitHub: odoo/tutorials](https://github.com/odoo/tutorials) |
| **odoo/technical-training** | Official technical training materials | [GitHub: odoo/technical-training](https://github.com/odoo/technical-training) |

### OCA (ODOO COMMUNITY ASSOCIATION)

| Repository | Domain | Link |
|---|---|---|
| **server-tools** | Server-side technical utilities useful after a local env exists | [GitHub: OCA/server-tools](https://github.com/OCA/server-tools) |

---

## PRACTICE / HANDS-ON

Chapter 5 is where practice becomes a **working local Odoo 19.0 environment**. Prefer evidence over screenshots of someone else's machine.

On your workstation, verify:

1. A dedicated Python version matching the source-install docs, used inside a virtual environment.
2. PostgreSQL running, with a dedicated role/user for Odoo (not your personal OS login as a shortcut forever).
3. `odoo/odoo` cloned on the **19.0** branch, with dependencies installed into the venv.
4. A config file that points `addons_path` at core addons **and** a separate custom addons directory.
5. A database you created deliberately (name + master password known), not a mystery leftover.
6. Developer mode reachable from Settings, and logs readable when something fails.
7. IDE interpreter = the same venv; debugger can stop inside a Python method and continue.

### ENVIRONMENTS TO USE

| Environment | Best for | Link |
|---|---|---|
| **Local source install** | Primary Chapter 5 goal | [Installing Odoo from source](https://www.odoo.com/documentation/19.0/administration/on_premise/source.html) |
| **Odoo Education** | UI exploration while local setup is incomplete | [Odoo Education](https://www.odoo.com/education/odoo-online) |
| **Odoo Trial** | Temporary free trial for experimentation | [Odoo Trial](https://www.odoo.com/trial) |
| **Odoo Runbot** | Compare behavior without owning the server | [Odoo Runbot](https://runbot.odoo.com/) |

---

## BEST RESOURCE ORDER FOR CHAPTER 5

If you do not want to consume everything, use this sequence:

| Step | Focus | Resources |
|---|---|---|
| 1 | Official install map | Source installation doc |
| 2 | OS-matched walkthrough | Windows (`b6HEu5WQ2s8`) or Ubuntu (`NDnX9k6jyTw`) |
| 3 | Isolation | venv videos (`PpDCWg_Kb8M` / `yLcO2A1LA64`) + requirements from source doc |
| 4 | Source + Git | Clone `odoo/odoo` 19.0 → Environment setup video (`a2ovPreTqAA`) |
| 5 | Config + paths | Config videos → `addons_path` video (`TfYvao3hDNU`) → CLI doc |
| 6 | Database + developer tools | CLI db options → Developer mode doc → optional activate video |
| 7 | IDE + debugger | VS Code / PyCharm setup → Debug videos (`gq4ISuGO8xo`, `w2t9YKQV7w8`) |

That combination gives you:

**Official install authority + OS walkthrough + Isolation + Paths + Runtime evidence + Debug loop**

which is much better than relying on random YouTube tutorials alone.

---

**Back to content:** [Chapter 5 Content](Content.md) | **Continue:** [Chapter 5 Exercise](Exercise.md) → [Chapter 5 Project](Project.md)
