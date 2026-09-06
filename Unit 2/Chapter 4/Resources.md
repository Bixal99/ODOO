# UNIT II: FREE LEARNING RESOURCES

## CHAPTER 4: ODOO ARCHITECTURE

Chapter 4 is **architectural**, so the best resources are official Odoo 19.0 developer and deployment documentation, plus verified technical videos that reinforce layer boundaries from [Chapter 4 Content](Content.md).

These resources map to three-tier design, browser and web client, HTTP, application server, Python, ORM, PostgreSQL, filestore, addons, registry, sessions, workers, cron, and WebSocket concepts.

Primary sources support the key concepts in this chapter. Videos and repository listings are supplementary and may change over time. Odoo-specific references use version **19.0** unless a video title states an older teaching version.

> **Verification note:** YouTube video IDs and GitHub repository links below were checked via Composio (YouTube Search + video details batch + GitHub API). Official documentation links target Odoo 19.0.

---

## CHAPTER 4 RESOURCES TABLE OF CONTENTS

- [YouTube: Architecture Overview](#youtube-architecture-overview)
- [YouTube: Framework and Application Server](#youtube-framework-and-application-server)
- [YouTube: ORM](#youtube-orm)
- [YouTube: Addons and Manifest](#youtube-addons-and-manifest)
- [YouTube: Web Client / OWL](#youtube-web-client--owl)
- [YouTube: Cron / Scheduled Actions](#youtube-cron--scheduled-actions)
- [YouTube: Database Backup / Filestore Context](#youtube-database-backup--filestore-context)
- [Official Documentation](#official-documentation)
- [Repositories](#repositories)
- [Practice / Hands-On](#practice--hands-on)
- [Best Resource Order for Chapter 4](#best-resource-order-for-chapter-4)

---

## YOUTUBE: ARCHITECTURE OVERVIEW


### 1. ODOO ARCHITECTURE EXPLAINED: THREE-TIERS (ODOO 19)

| | |
|---|---|
| **Relevant to** | [4.1 Three-Tiers Architecture](Content.md#41-three-tiers-architecture) |
| **Source** | Community technical channel (Odoo with Vinay) |
| **Reinforces** | **Presentation → Logic → Data** |

<div align="center">

[![Odoo Architecture Explained | Three-Tiers Architecture in Odoo 19](https://img.youtube.com/vi/PKMgbCSneyg/hqdefault.jpg)](https://www.youtube.com/watch?v=PKMgbCSneyg)

**Watch on YouTube:** [Odoo Architecture Explained | Three-Tiers Architecture in Odoo 19](https://www.youtube.com/watch?v=PKMgbCSneyg)

</div>

---

### 2. ODOO TECHNICAL TRAINING PART 1: ARCHITECTURE AND EDITIONS

| | |
|---|---|
| **Relevant to** | [4.1 Three-Tiers Architecture](Content.md#41-three-tiers-architecture), chapter overview |
| **Source** | Community technical channel (Odoo Tech) |
| **Why use it** | Broad intro to architecture and editions before deeper layer topics |
| **Version note** | Titled for Odoo 18; use with Odoo 19.0 official docs as the authority |

<div align="center">

[![Odoo 18 Technical Training Part 1 | Architecture | Editions](https://img.youtube.com/vi/O8ij3ZF-UyQ/hqdefault.jpg)](https://www.youtube.com/watch?v=O8ij3ZF-UyQ)

**Watch on YouTube:** [Odoo 18 Technical Training Part 1 | Architecture | Editions](https://www.youtube.com/watch?v=O8ij3ZF-UyQ)

</div>

---

## YOUTUBE: FRAMEWORK AND APPLICATION SERVER

### ODOO FRAMEWORK EXPLAINED

| | |
|---|---|
| **Relevant to** | [4.5 Odoo Application Server](Content.md#45-odoo-application-server), [4.6 Python Runtime](Content.md#46-python-runtime) |
| **Source** | Community technical channel (EasyDev) |
| **Reinforces** | Odoo as a modular application framework, not only an ERP UI |

<div align="center">

[![Odoo Framework Explained](https://img.youtube.com/vi/Ru2cz7l0g5k/hqdefault.jpg)](https://www.youtube.com/watch?v=Ru2cz7l0g5k)

**Watch on YouTube:** [Odoo Framework Explained](https://www.youtube.com/watch?v=Ru2cz7l0g5k)

</div>

---

## YOUTUBE: ORM

### 1. ORM IN ODOO (OBJECT RELATIONAL MAPPING)

| | |
|---|---|
| **Relevant to** | [4.7 ORM](Content.md#47-orm) |
| **Source** | Cybrosys Technologies |
| **Reinforces** | **Python model ↔ PostgreSQL table** via the ORM |
| **Version note** | Titled for Odoo 16; pair with the Odoo 19 ORM API reference |

<div align="center">

[![ORM (Object Relational Mapping) in Odoo 16](https://img.youtube.com/vi/A8MEl4BfqyY/hqdefault.jpg)](https://www.youtube.com/watch?v=A8MEl4BfqyY)

**Watch on YouTube:** [ORM (Object Relational Mapping) in Odoo 16](https://www.youtube.com/watch?v=A8MEl4BfqyY)

</div>

---

### 2. ODOO ORM METHODS (PART 1)

| | |
|---|---|
| **Relevant to** | [4.7 ORM](Content.md#47-orm) |
| **Source** | Odoo Mates |
| **Why use it** | Practical method-level view of how the ORM is used from Python |

<div align="center">

[![Odoo ORM Methods - Part1](https://img.youtube.com/vi/8V-uOG8KkKA/hqdefault.jpg)](https://www.youtube.com/watch?v=8V-uOG8KkKA)

**Watch on YouTube:** [Odoo ORM Methods - Part1](https://www.youtube.com/watch?v=8V-uOG8KkKA)

</div>

---

## YOUTUBE: ADDONS AND MANIFEST

### 1. ODOO MODULES EXPLAINED

| | |
|---|---|
| **Relevant to** | [4.10 Addons](Content.md#410-addons) |
| **Source** | EasyDev |
| **Reinforces** | Modules as the packaging unit for business features |

<div align="center">

[![Odoo Modules Explained](https://img.youtube.com/vi/uJPjmS5Arug/hqdefault.jpg)](https://www.youtube.com/watch?v=uJPjmS5Arug)

**Watch on YouTube:** [Odoo Modules Explained](https://www.youtube.com/watch?v=uJPjmS5Arug)

</div>

---

### 2. ODOO MODULE STRUCTURE: MODELS, VIEWS, SECURITY

| | |
|---|---|
| **Relevant to** | [4.10 Addons](Content.md#410-addons), [4.11 Registry](Content.md#411-registry) |
| **Source** | EasyDev |

<div align="center">

[![Odoo Module Structure Explained](https://img.youtube.com/vi/ov-ReGkIxIg/hqdefault.jpg)](https://www.youtube.com/watch?v=ov-ReGkIxIg)

**Watch on YouTube:** [Odoo Module Structure Explained](https://www.youtube.com/watch?v=ov-ReGkIxIg)

</div>

---

### 3. MANIFEST FILE IN ODOO 19

| | |
|---|---|
| **Relevant to** | [4.10 Addons](Content.md#410-addons) |
| **Source** | Cybrosys Technologies |
| **Reinforces** | `__manifest__.py` as module declaration metadata |

<div align="center">

[![What is the Manifest File in Odoo?](https://img.youtube.com/vi/n7OXja3UBVw/hqdefault.jpg)](https://www.youtube.com/watch?v=n7OXja3UBVw)

**Watch on YouTube:** [What is the Manifest File in Odoo?](https://www.youtube.com/watch?v=n7OXja3UBVw)

</div>

---

### 4. ODOO MANIFEST FIELDS EXPLAINED

| | |
|---|---|
| **Relevant to** | [4.10 Addons](Content.md#410-addons) |
| **Source** | EasyDev |

<div align="center">

[![Odoo Manifest Explained](https://img.youtube.com/vi/brTqE3bxzVY/hqdefault.jpg)](https://www.youtube.com/watch?v=brTqE3bxzVY)

**Watch on YouTube:** [Odoo Manifest Explained](https://www.youtube.com/watch?v=brTqE3bxzVY)

</div>

---

### 5. CREATE A BASIC MODULE

| | |
|---|---|
| **Relevant to** | [4.10 Addons](Content.md#410-addons), preparation for Chapter 5 |
| **Source** | Cybrosys Technologies |
| **Version note** | Titled for Odoo 17; still useful for structure intuition before local setup |

<div align="center">

[![How to Create a Basic Module in Odoo 17](https://img.youtube.com/vi/mT43V3twcyE/hqdefault.jpg)](https://www.youtube.com/watch?v=mT43V3twcyE)

**Watch on YouTube:** [How to Create a Basic Module in Odoo 17](https://www.youtube.com/watch?v=mT43V3twcyE)

</div>

---

### 6. MODULE LIFECYCLE: INSTALL, UPGRADE, UNINSTALL

| | |
|---|---|
| **Relevant to** | [4.10 Addons](Content.md#410-addons), [4.11 Registry](Content.md#411-registry) |
| **Source** | EasyDev |

<div align="center">

[![Odoo Module Lifecycle Explained](https://img.youtube.com/vi/lyUGD4reCys/hqdefault.jpg)](https://www.youtube.com/watch?v=lyUGD4reCys)

**Watch on YouTube:** [Odoo Module Lifecycle Explained](https://www.youtube.com/watch?v=lyUGD4reCys)

</div>

---

## YOUTUBE: WEB CLIENT / OWL

### 1. ODOO SERVICES USING OWL

| | |
|---|---|
| **Relevant to** | [4.3 Odoo Web Client](Content.md#43-odoo-web-client) |
| **Source** | AJScript Media |
| **Reinforces** | Browser-side services that talk to the server |

<div align="center">

[![Odoo Services Using OWL Javascript Framework](https://img.youtube.com/vi/jl9husDIX2o/hqdefault.jpg)](https://www.youtube.com/watch?v=jl9husDIX2o)

**Watch on YouTube:** [Odoo Services Using OWL Javascript Framework](https://www.youtube.com/watch?v=jl9husDIX2o)

</div>

---

### 2. ODOO 19 CLIENT ACTION WITH OWL

| | |
|---|---|
| **Relevant to** | [4.3 Odoo Web Client](Content.md#43-odoo-web-client) |
| **Source** | Odoo with Vinay |
| **Why use it** | Shows a client-side action still depending on server models and routes |

<div align="center">

[![Odoo 19 Client Action Explained with JavaScript (OWL)](https://img.youtube.com/vi/bF4aao2DbS8/hqdefault.jpg)](https://www.youtube.com/watch?v=bF4aao2DbS8)

**Watch on YouTube:** [Odoo 19 Client Action Explained with JavaScript (OWL)](https://www.youtube.com/watch?v=bF4aao2DbS8)

</div>

---

## YOUTUBE: CRON / SCHEDULED ACTIONS

### 1. SCHEDULED ACTIONS IN ODOO 18

| | |
|---|---|
| **Relevant to** | [4.15 Cron Workers](Content.md#415-cron-workers) |
| **Source** | Cybrosys Technologies |
| **Reinforces** | Scheduled work is server-side, not browser-driven |

<div align="center">

[![What are Scheduled Actions in Odoo 18](https://img.youtube.com/vi/9HMwSNPww_c/hqdefault.jpg)](https://www.youtube.com/watch?v=9HMwSNPww_c)

**Watch on YouTube:** [What are Scheduled Actions in Odoo 18](https://www.youtube.com/watch?v=9HMwSNPww_c)

</div>

---

### 2. CRON JOBS AND SCHEDULED ACTIONS

| | |
|---|---|
| **Relevant to** | [4.15 Cron Workers](Content.md#415-cron-workers) |
| **Source** | Odooistic |

<div align="center">

[![Automate Tasks with Cron Jobs and Scheduled Actions](https://img.youtube.com/vi/HQ4XLCw-2tM/hqdefault.jpg)](https://www.youtube.com/watch?v=HQ4XLCw-2tM)

**Watch on YouTube:** [Automate Tasks with Cron Jobs and Scheduled Actions](https://www.youtube.com/watch?v=HQ4XLCw-2tM)

</div>

---

## YOUTUBE: DATABASE BACKUP / FILESTORE CONTEXT

### HOW TO RESTORE YOUR ODOO DATABASE FROM BACKUP

| | |
|---|---|
| **Relevant to** | [4.8 PostgreSQL](Content.md#48-postgresql), [4.9 Filestore](Content.md#49-filestore) |
| **Source** | Cybrosys Technologies |
| **Why use it** | Makes durable state visible: database dump versus file attachments |
| **Caution** | Pair with official backup guidance; do not treat restore demos as production runbooks without reading deploy docs |

<div align="center">

[![How to Restore your Odoo Database from Backup?](https://img.youtube.com/vi/kebK_7_ezD8/hqdefault.jpg)](https://www.youtube.com/watch?v=kebK_7_ezD8)

**Watch on YouTube:** [How to Restore your Odoo Database from Backup?](https://www.youtube.com/watch?v=kebK_7_ezD8)

</div>

---

## OFFICIAL DOCUMENTATION

Use the architecture overview for the three-tier story, the ORM API for model persistence, HTTP controllers for request routing, module manifests for addons, deployment for workers and WebSockets, and the CLI for `data-dir` (filestore and sessions). These references support the corresponding lesson explanations and project decisions.

All links below target **Odoo 19.0** documentation.

| Topic | Relevant sections | Documentation |
|---|---|---|
| **Architecture overview** | [4.1](Content.md#41-three-tiers-architecture), [4.10](Content.md#410-addons) | [Chapter 1: Architecture Overview](https://www.odoo.com/documentation/19.0/developer/tutorials/server_framework_101/01_architecture.html) |
| **ORM API** | [4.7 ORM](Content.md#47-orm), [4.11 Registry](Content.md#411-registry) | [ORM API](https://www.odoo.com/documentation/19.0/developer/reference/backend/orm.html) |
| **Web controllers / HTTP** | [4.4 HTTP Request](Content.md#44-http-request), [4.12 HTTP Layer](Content.md#412-http-layer) | [Web Controllers](https://www.odoo.com/documentation/19.0/developer/reference/backend/http.html) |
| **Module manifests / addons** | [4.10 Addons](Content.md#410-addons) | [Module Manifests](https://www.odoo.com/documentation/19.0/developer/reference/backend/module.html) |
| **Building a module** | [4.10](Content.md#410-addons), prep for Chapter 5 | [Building a Module](https://www.odoo.com/documentation/19.0/developer/tutorials/backend.html) |
| **JavaScript / web client** | [4.2 Browser](Content.md#42-browser), [4.3 Web Client](Content.md#43-odoo-web-client) | [Javascript Reference](https://www.odoo.com/documentation/19.0/developer/reference/frontend/javascript_reference.html) |
| **Scheduled actions (cron)** | [4.15 Cron Workers](Content.md#415-cron-workers) | [Actions (Scheduled Actions / ir.cron)](https://www.odoo.com/documentation/19.0/developer/reference/backend/actions.html) |
| **Deployment: workers, WebSocket, filestore serving** | [4.5](Content.md#45-odoo-application-server), [4.9](Content.md#49-filestore), [4.14](Content.md#414-workers), [4.16](Content.md#416-long-polling--websocket-concepts) | [System configuration / Deploy](https://www.odoo.com/documentation/19.0/administration/on_premise/deploy.html) |
| **CLI: data-dir, workers, gevent-port, db dump** | [4.9](Content.md#49-filestore), [4.13 Sessions](Content.md#413-sessions), [4.14](Content.md#414-workers) | [Command-line interface (CLI)](https://www.odoo.com/documentation/19.0/developer/reference/cli.html) |
| **Odoo.sh container layout (filestore / sessions)** | [4.9](Content.md#49-filestore), [4.13](Content.md#413-sessions) | [Containers](https://www.odoo.com/documentation/19.0/administration/odoo_sh/advanced/containers.html) |

---

## REPOSITORIES

You do **not** need to read all of this source yet. For Chapter 4, repositories help you see where architecture claims live in real trees.

### OFFICIAL ODOO

| Repository | Relevant to | Link |
|---|---|---|
| **odoo/odoo** | Application server, ORM, addons, HTTP, bus; default branch tracks 19.0 | [GitHub: odoo/odoo](https://github.com/odoo/odoo) |
| **odoo/documentation** | Source of the official docs linked above; default branch 19.0 | [GitHub: odoo/documentation](https://github.com/odoo/documentation) |
| **odoo/tutorials** | Official tutorial bases and solutions aligned with developer docs | [GitHub: odoo/tutorials](https://github.com/odoo/tutorials) |
| **odoo/technical-training** | Official technical training materials | [GitHub: odoo/technical-training](https://github.com/odoo/technical-training) |

### OCA (ODOO COMMUNITY ASSOCIATION)

| Repository | Domain | Link |
|---|---|---|
| **server-tools** | Server-side technical utilities and admin-oriented modules | [GitHub: OCA/server-tools](https://github.com/OCA/server-tools) |

---

## PRACTICE / HANDS-ON

Chapter 4 stays conceptual. Practice means **inspecting evidence**, not shipping custom modules yet.

In any available Odoo 19 environment (trial, education, runbot, or a later local install from Chapter 5), observe:

1. A browser Network tab while opening a sales order: count HTTP/RPC calls.
2. That attachments require both database metadata and filestore files (backup mental model).
3. That scheduled actions exist under Technical menus when developer mode is on.
4. That production worker / WebSocket settings are described in deploy docs, not guessed from the UI alone.

### ENVIRONMENTS TO USE

| Environment | Best for | Link |
|---|---|---|
| **Odoo Education** | Free educational practice (when eligible) | [Odoo Education](https://www.odoo.com/education/odoo-online) |
| **Odoo Trial** | Temporary free trial for experimentation | [Odoo Trial](https://www.odoo.com/trial) |
| **Odoo Runbot** | Developer/test sandbox (not for permanent work) | [Odoo Runbot](https://runbot.odoo.com/) |

---

## BEST RESOURCE ORDER FOR CHAPTER 4

If you do not want to consume everything, use this sequence:

| Step | Focus | Resources |
|---|---|---|
| 1 | Three-tier map | Architecture Overview doc → Three-Tiers video (`PKMgbCSneyg`) |
| 2 | Request path | Web Controllers doc → Javascript Reference |
| 3 | Persistence | ORM API doc → ORM videos |
| 4 | Packaging | Module Manifests doc → Modules / Manifest videos |
| 5 | Runtime shape | Deploy doc (workers, WebSocket, filestore) → CLI `data-dir` |
| 6 | Background work | Actions / ir.cron section → Scheduled Actions videos |
| 7 | Source orientation | Browse `odoo/odoo` and `odoo/documentation` lightly |

That combination gives you:

**Official layer map + Request evidence + Persistence rules + Packaging + Runtime/ops vocabulary + Source orientation**

which is much better than relying on random YouTube tutorials alone.

---

**Back to content:** [Chapter 4 Content](Content.md) | **Continue:** [Chapter 4 Exercise](Exercise.md) → [Chapter 4 Project](Project.md)
