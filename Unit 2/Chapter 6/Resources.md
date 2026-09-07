# UNIT II: FREE LEARNING RESOURCES

## CHAPTER 6: ODOO SOURCE CODE STRUCTURE

Chapter 6 is **navigational**, so the best resources are official Odoo 19.0 module and ORM documentation, the `odoo/odoo` source tree, plus verified technical videos that reinforce folder literacy from [Chapter 6 Content](Content.md).

These resources map to `odoo/` versus `addons/`, framework packages (`api`, `fields`, `models`), HTTP, services, tools, registry, module loading, reading official addons, and tracing models, XML IDs, and methods.

Primary sources support the key concepts in this chapter. Videos and repository listings are supplementary and may change over time. Odoo-specific references use version **19.0** unless a video title states an older teaching version.

> **Verification note:** YouTube video IDs and GitHub repository links below were checked via Composio (YouTube Search + video details batch). Official documentation links target Odoo 19.0.

---

## CHAPTER 6 RESOURCES TABLE OF CONTENTS

- [YouTube: Folder and Project Structure](#youtube-folder-and-project-structure)
- [YouTube: Module Structure and Manifest](#youtube-module-structure-and-manifest)
- [YouTube: Official Addons Orientation](#youtube-official-addons-orientation)
- [YouTube: XML IDs / External Identifiers](#youtube-xml-ids--external-identifiers)
- [Official Documentation](#official-documentation)
- [Repositories](#repositories)
- [Practice / Hands-On](#practice--hands-on)
- [Best Resource Order for Chapter 6](#best-resource-order-for-chapter-6)

---

## YOUTUBE: FOLDER AND PROJECT STRUCTURE

### 1. ODOO FOLDER STRUCTURE (BEGINNERS)

| | |
|---|---|
| **Relevant to** | [6.1 odoo/](Content.md#61-odoo), [6.2 addons/](Content.md#62-addons), [Before We Start](Content.md#before-we-start-reading-the-repository-root) |
| **Source** | Community technical channel (Odoo Tech) |
| **Reinforces** | Top-level repository landmarks before diving into one addon |
| **Version note** | Titled for Odoo 18; pair with an Odoo 19.0 checkout as the authority |

<div align="center">

[![Understanding Odoo Folder Structure | Beginners Guide to Odoo Development](https://img.youtube.com/vi/hqg2DRO8Rw4/hqdefault.jpg)](https://www.youtube.com/watch?v=hqg2DRO8Rw4)

**Watch on YouTube:** [Understanding Odoo Folder Structure | Beginners Guide to Odoo Development](https://www.youtube.com/watch?v=hqg2DRO8Rw4)

</div>

---

### 2. ODOO FOLDER STRUCTURE EXPLAINED

| | |
|---|---|
| **Relevant to** | [6.1](Content.md#61-odoo), [6.2](Content.md#62-addons) |
| **Source** | Community technical channel (OdooVerse) |

<div align="center">

[![Odoo Folder Structure Explained | Beginner Friendly Guide](https://img.youtube.com/vi/drZxPJIRUmo/hqdefault.jpg)](https://www.youtube.com/watch?v=drZxPJIRUmo)

**Watch on YouTube:** [Odoo Folder Structure Explained | Beginner Friendly Guide](https://www.youtube.com/watch?v=drZxPJIRUmo)

</div>

---

### 3. ODOO PROJECT STRUCTURE EXPLAINED

| | |
|---|---|
| **Relevant to** | [6.3 Core Framework](Content.md#63-core-framework), chapter overview |
| **Source** | EasyDev |
| **Why use it** | Project-level mental model before package-level reading |

<div align="center">

[![Odoo Project Structure Explained](https://img.youtube.com/vi/9_I-U5eYKL8/hqdefault.jpg)](https://www.youtube.com/watch?v=9_I-U5eYKL8)

**Watch on YouTube:** [Odoo Project Structure Explained](https://www.youtube.com/watch?v=9_I-U5eYKL8)

</div>

---

## YOUTUBE: MODULE STRUCTURE AND MANIFEST

### 1. ODOO MODULE STRUCTURE: MODELS, VIEWS, SECURITY

| | |
|---|---|
| **Relevant to** | [6.2 addons/](Content.md#62-addons), [6.12 Reading Official Addons](Content.md#612-reading-official-addons) |
| **Source** | EasyDev |
| **Reinforces** | Module directory anatomy before tracing inheritance |

<div align="center">

[![Odoo Module Structure Explained](https://img.youtube.com/vi/ov-ReGkIxIg/hqdefault.jpg)](https://www.youtube.com/watch?v=ov-ReGkIxIg)

**Watch on YouTube:** [Odoo Module Structure Explained](https://www.youtube.com/watch?v=ov-ReGkIxIg)

</div>

---

### 2. UNDERSTANDING ODOO MODULE STRUCTURE

| | |
|---|---|
| **Relevant to** | [6.2](Content.md#62-addons), [6.12](Content.md#612-reading-official-addons) |
| **Source** | Odoo Tech |

<div align="center">

[![Understanding Odoo Module Structure](https://img.youtube.com/vi/44IcOa9ZM9Q/hqdefault.jpg)](https://www.youtube.com/watch?v=44IcOa9ZM9Q)

**Watch on YouTube:** [Understanding Odoo Module Structure](https://www.youtube.com/watch?v=44IcOa9ZM9Q)

</div>

---

### 3. MANIFEST FILE IN ODOO

| | |
|---|---|
| **Relevant to** | [6.12](Content.md#612-reading-official-addons), [6.11 Modules Loader](Content.md#611-modules-loader) |
| **Source** | Cybrosys Technologies |
| **Reinforces** | `__manifest__.py` as the first file to open in an addon |

<div align="center">

[![What is the Manifest File in Odoo?](https://img.youtube.com/vi/n7OXja3UBVw/hqdefault.jpg)](https://www.youtube.com/watch?v=n7OXja3UBVw)

**Watch on YouTube:** [What is the Manifest File in Odoo?](https://www.youtube.com/watch?v=n7OXja3UBVw)

</div>

---

### 4. ODOO MODULES EXPLAINED

| | |
|---|---|
| **Relevant to** | [6.2](Content.md#62-addons), [6.3](Content.md#63-core-framework) |
| **Source** | EasyDev |

<div align="center">

[![Odoo Modules Explained](https://img.youtube.com/vi/uJPjmS5Arug/hqdefault.jpg)](https://www.youtube.com/watch?v=uJPjmS5Arug)

**Watch on YouTube:** [Odoo Modules Explained](https://www.youtube.com/watch?v=uJPjmS5Arug)

</div>

---

### 5. MODULE LIFECYCLE: INSTALL, UPGRADE, UNINSTALL

| | |
|---|---|
| **Relevant to** | [6.10 Registry](Content.md#610-registry), [6.11 Modules Loader](Content.md#611-modules-loader) |
| **Source** | EasyDev |
| **Why use it** | Connects filesystem modules to runtime installed state |

<div align="center">

[![Odoo Module Lifecycle Explained](https://img.youtube.com/vi/lyUGD4reCys/hqdefault.jpg)](https://www.youtube.com/watch?v=lyUGD4reCys)

**Watch on YouTube:** [Odoo Module Lifecycle Explained](https://www.youtube.com/watch?v=lyUGD4reCys)

</div>

---

## YOUTUBE: OFFICIAL ADDONS ORIENTATION

### 1. CREATE A CUSTOM MODULE (ODOO 19)

| | |
|---|---|
| **Relevant to** | [6.12](Content.md#612-reading-official-addons), prep for Unit III |
| **Source** | Odoo Hub |
| **Why use it** | Shows module scaffolding after you understand where official addons live |

<div align="center">

[![Odoo 19 Tutorial | How to Create a Custom Module (App) From Scratch](https://img.youtube.com/vi/l9uoxgmS6ig/hqdefault.jpg)](https://www.youtube.com/watch?v=l9uoxgmS6ig)

**Watch on YouTube:** [Odoo 19 Tutorial | How to Create a Custom Module (App) From Scratch](https://www.youtube.com/watch?v=l9uoxgmS6ig)

</div>

---

### 2. CREATE A BASIC MODULE (ODOO 17)

| | |
|---|---|
| **Relevant to** | [6.12](Content.md#612-reading-official-addons) |
| **Source** | Cybrosys Technologies |
| **Version note** | Titled for Odoo 17; still useful for structure intuition |

<div align="center">

[![How to Create a Basic Module in Odoo 17](https://img.youtube.com/vi/mT43V3twcyE/hqdefault.jpg)](https://www.youtube.com/watch?v=mT43V3twcyE)

**Watch on YouTube:** [How to Create a Basic Module in Odoo 17](https://www.youtube.com/watch?v=mT43V3twcyE)

</div>

---

## YOUTUBE: XML IDS / EXTERNAL IDENTIFIERS

### 1. FIND XML ID IN PYCHARM

| | |
|---|---|
| **Relevant to** | [6.14 Tracing XML IDs](Content.md#614-tracing-xml-ids) |
| **Source** | Odoo Discussions |
| **Reinforces** | Locating external IDs during custom-module work |

<div align="center">

[![Easily find XML ID in PyCharm | Odoo custom module development](https://img.youtube.com/vi/0e9UcOh92PI/hqdefault.jpg)](https://www.youtube.com/watch?v=0e9UcOh92PI)

**Watch on YouTube:** [Easily find XML ID in PyCharm | Odoo custom module development](https://www.youtube.com/watch?v=0e9UcOh92PI)

</div>

---

### 2. GENERATE EXTERNAL ID FOR UI-CREATED RECORDS

| | |
|---|---|
| **Relevant to** | [6.14](Content.md#614-tracing-xml-ids) |
| **Source** | Odoo Mates |
| **Why use it** | Clarifies that external IDs are not only for views authored in XML files |

<div align="center">

[![How To Generate External ID For The Records Created From User Interface Odoo](https://img.youtube.com/vi/VKpepIjraMs/hqdefault.jpg)](https://www.youtube.com/watch?v=VKpepIjraMs)

**Watch on YouTube:** [How To Generate External ID For The Records Created From User Interface Odoo](https://www.youtube.com/watch?v=VKpepIjraMs)

</div>

---

## OFFICIAL DOCUMENTATION

Use module docs for manifests and package layout, ORM for models/fields/api concepts, HTTP controllers for routes, and architecture overview for the three-tier map that Chapter 4 already taught. These references support the corresponding lesson explanations and project decisions.

All links below target **Odoo 19.0** documentation.

| Topic | Relevant sections | Documentation |
|---|---|---|
| **Module manifests / addon packages** | [6.2](Content.md#62-addons), [6.11](Content.md#611-modules-loader), [6.12](Content.md#612-reading-official-addons) | [Module Manifests](https://www.odoo.com/documentation/19.0/developer/reference/backend/module.html) |
| **Building a module** | [6.12](Content.md#612-reading-official-addons), prep for Unit III | [Building a Module](https://www.odoo.com/documentation/19.0/developer/tutorials/backend.html) |
| **ORM API (models, fields, decorators, Environment)** | [6.4](Content.md#64-apipy-concepts)–[6.6](Content.md#66-modelspy-concepts), [6.10](Content.md#610-registry) | [ORM API](https://www.odoo.com/documentation/19.0/developer/reference/backend/orm.html) |
| **Web controllers / HTTP** | [6.7 HTTP](Content.md#67-http) | [Web Controllers](https://www.odoo.com/documentation/19.0/developer/reference/backend/http.html) |
| **Architecture overview** | [6.1](Content.md#61-odoo), [6.3](Content.md#63-core-framework) | [Chapter 1: Architecture Overview](https://www.odoo.com/documentation/19.0/developer/tutorials/server_framework_101/01_architecture.html) |
| **CLI (runtime discovery context)** | [6.10](Content.md#610-registry), [6.11](Content.md#611-modules-loader) | [Command-line interface (CLI)](https://www.odoo.com/documentation/19.0/developer/reference/cli.html) |

---

## REPOSITORIES

For Chapter 6, repositories are the primary laboratory. Prefer browsing the **19.0** branch.

### OFFICIAL ODOO

| Repository | Relevant to | Link |
|---|---|---|
| **odoo/odoo** | Framework under `odoo/`, business addons under `addons/`, including `sale`, `sale_crm`, `sale_stock` | [GitHub: odoo/odoo](https://github.com/odoo/odoo) |
| **odoo/documentation** | Source of the official docs linked above | [GitHub: odoo/documentation](https://github.com/odoo/documentation) |
| **odoo/tutorials** | Official tutorial bases aligned with developer docs | [GitHub: odoo/tutorials](https://github.com/odoo/tutorials) |
| **odoo/technical-training** | Official technical training materials | [GitHub: odoo/technical-training](https://github.com/odoo/technical-training) |

### PRACTICE TARGETS INSIDE ODOO/ODOO

| Path idea | Why open it |
|---|---|
| `addons/sale/__manifest__.py` | Manifest-first habit |
| `addons/sale/models/sale_order.py` | Base model definition |
| `addons/sale_crm/models/sale_order.py` | `_inherit` + field + method override |
| `addons/sale_stock/views/sale_order_views.xml` | XML ID inheritance of `sale.view_order_form` |
| `odoo/api/`, `odoo/fields/`, `odoo/models/` | Developer-facing framework packages in Odoo 19 |

---

## PRACTICE / HANDS-ON

Chapter 6 practice means **question-driven investigation**, not reading `sale_order.py` from line 1 to the end.

On a local Odoo 19.0 checkout (from Chapter 5), verify:

1. You can point to `odoo/` versus top-level `addons/` without hesitation.
2. Searching `_name = "sale.order"` finds the base definition in `sale`.
3. Searching `_inherit = "sale.order"` finds multiple extensions.
4. Searching `id="view_order_form"` inside `addons/sale/` explains `sale.view_order_form`.
5. Searching `def action_confirm` shows more than one relevant override when CRM/Stock modules are present.
6. A module on disk that is not installed does not contribute to that database's registry.

### ENVIRONMENTS TO USE

| Environment | Best for | Link |
|---|---|---|
| **Local Odoo 19.0 source** | Primary Chapter 6 goal | [Installing Odoo from source](https://www.odoo.com/documentation/19.0/administration/on_premise/source.html) |
| **GitHub odoo/odoo @ 19.0** | Read-only browsing when your laptop is offline for installs | [odoo/odoo](https://github.com/odoo/odoo/tree/19.0) |
| **Odoo Runbot** | Compare installed-module effects without owning the server | [Odoo Runbot](https://runbot.odoo.com/) |

---

## BEST RESOURCE ORDER FOR CHAPTER 6

If you do not want to consume everything, use this sequence:

| Step | Focus | Resources |
|---|---|---|
| 1 | Root map | Architecture Overview doc → Folder Structure videos |
| 2 | Module anatomy | Module Manifests doc → Module Structure videos |
| 3 | Framework APIs | ORM API doc → skim `odoo/api`, `odoo/fields`, `odoo/models` |
| 4 | HTTP shelf | Web Controllers doc → glance at `odoo/http.py` |
| 5 | Official addon reading | Open `sale` manifest → models → one view file |
| 6 | Tracing drills | Trace `opportunity_id`, `sale.view_order_form`, `action_confirm` |
| 7 | Runtime check | Module Lifecycle video + confirm installed modules on `odoo19_dev` |

That combination gives you:

**Official maps + Folder literacy + Addon anatomy + Tracing drills + Runtime confirmation**

which is much better than randomly browsing thousands of files.

---

**Back to content:** [Chapter 6 Content](Content.md) | **Continue:** [Chapter 6 Exercise](Exercise.md) → [Chapter 6 Project](Project.md) | **Unit wrap-up:** [Unit II Exercise](../Exercise/Exercise.md) → [Unit II Project](../Project/Project.md) → [Unit II Conclusion](../Conclusion/Summary.md)
