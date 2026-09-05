# ODOO DEVELOPMENT & ENGINEERING STUDY GUIDE

> **From Zero to Odoo Engineer** — A structured, chapter-by-chapter roadmap for learning ERP fundamentals, Odoo development, production engineering, and real-world Odoo engineering practice.

[![Repository](https://img.shields.io/badge/GitHub-Bixal99%2FODOO-blue?logo=github)](https://github.com/Bixal99/ODOO)
[![Odoo](https://img.shields.io/badge/Odoo-Development-875A7B?logo=odoo&logoColor=white)](https://www.odoo.com/)
[![Python](https://img.shields.io/badge/Python-Required-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Required-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)

---

## TABLE OF CONTENTS

- [About](#about)
- [Learning Path](#learning-path)
- [Who Is This For?](#who-is-this-for)
- [Prerequisites](#prerequisites)
- [Repository Structure](#repository-structure)
- [Curriculum Overview](#curriculum-overview)
- [How to Use This Guide](#how-to-use-this-guide)
- [Recommended Study Order](#recommended-study-order)
- [Technologies Covered](#technologies-covered)
- [Official Resources](#official-resources)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## ABOUT

This repository is a **comprehensive Odoo study guide** designed to take learners from no prior ERP or Odoo knowledge to production-ready **Odoo Engineer** competency. It is organized as a detailed roadmap with **24 units**, **96 chapters**, and hundreds of granular topics covering business fundamentals, backend development, frontend (OWL), integrations, deployment, and professional engineering practices.

Unlike scattered tutorials, this guide follows a deliberate progression:

```
Zero Knowledge → ERP Understanding → Odoo Development
→ Full-Stack Odoo → Production Engineering → Odoo Engineer
```

Each unit builds on the previous one — starting with *why* businesses use ERP systems before diving into *how* Odoo works under the hood, and ending with capstone projects, code review practices, and interview readiness.

---

## LEARNING PATH

| Phase | Units | Focus |
|-------|-------|-------|
| **Foundation** | I–III | ERP concepts, Odoo ecosystem, first module |
| **Core Development** | IV–X | Models, ORM, UI, security, extensions, advanced features |
| **Full-Stack** | XI–XV | i18n, web/portal, APIs, OWL frontend, attachments |
| **Production Skills** | XVI–XX | PostgreSQL, testing, CLI, deployment, upgrades |
| **Professional Engineering** | XXI–XXIV | Functional depth, solution architecture, capstone, interviews |

---

## WHO IS THIS FOR?

- **Beginners** who want a clear, structured path into Odoo development
- **Python developers** transitioning into ERP and Odoo customization
- **Functional consultants** who want to understand the technical side
- **Junior Odoo developers** looking to fill gaps and reach senior-level breadth
- **Self-learners** preparing for Odoo developer roles or certifications

---

## PREREQUISITES

| Area | Minimum Level |
|------|---------------|
| **Python** | Basic syntax, functions, classes, and OOP |
| **SQL** | Basic SELECT, WHERE, JOIN (deep PostgreSQL covered in Unit XVI) |
| **Linux / CLI** | Comfortable with terminal commands (deployment units) |
| **Git** | Basic clone, commit, branch (collaboration covered in Unit XXII) |
| **Web basics** | HTML, HTTP, JSON (frontend units build from here) |

No prior ERP or Odoo experience is required — Unit I starts from business process fundamentals.

---

## REPOSITORY STRUCTURE

Each unit follows the same organizational pattern: **chapters** for teaching content, then **conclusion**, **unit exercise**, and **unit project** at the unit level.

Per chapter, the intended order is: **Content → Exercise → Project**. Resources are embedded inside `Content.md` at the end of each topic; `Resources.md` remains as the full chapter reference index.

**Final template (all units):** read theory in `Content.md`, then scroll to **Relevant Resources** on the same page — thumbnails, videos, docs, and links appear inline. No jumping between files while studying.

```
Read topic theory in Content.md
        ↓
### RELEVANT RESOURCES  (same file, end of section)
        ↓
YouTube thumbnails + docs + practice links (topic-relevant only)
        ↓
Scroll down to next topic in Content.md
```

**Content.md (end of each topic section):**

```markdown
### RELEVANT RESOURCES

Here are the relevant resources for **3.2 CRM**:

### 1. CRM BASICS: PIPELINES AND OPPORTUNITIES

| | |
|---|---|
| **Source** | Official Odoo |
| **Reinforces** | **Lead/Opportunity → Pipeline** |

<div align="center">

[![CRM Basics: Pipelines and Opportunities](https://img.youtube.com/vi/RpPKOl85kuc/hqdefault.jpg)](https://www.youtube.com/watch?v=RpPKOl85kuc)

**Watch on YouTube:** [CRM Basics: Pipelines and Opportunities](https://www.youtube.com/watch?v=RpPKOl85kuc)

</div>

### OFFICIAL DOCUMENTATION

| Application | Documentation |
|---|---|
| **CRM** | [Odoo 19 CRM Documentation](https://www.odoo.com/documentation/19.0/applications/sales/crm.html) |
```

**Resources.md:** kept as the complete chapter resource library (same content, organized by type). Used for reference and when building future units — not required during linear reading.

Rules for future units:

- Every teachable topic section in `Content.md` gets a `### RELEVANT RESOURCES` block with **full embedded resources** copied from `Resources.md` (thumbnails, tables, links) — only items relevant to that topic.
- Include the GitHub thumbnail note once per chapter (first topic section).
- Keep `Resources.md` in sync as the master resource index for the chapter.
- ALL HEADINGS UPPERCASE; no em dashes in chapter content; conversational closings.

```
ODOO/
├── README.md                              # Project overview (this file)
└── Unit 1/                                # Unit I: Understand the Business Before the Code
    ├── Table of Content/
    │   └── Roadmap.md                     # Full curriculum table of contents
    ├── Chapter 1/                         # What Is ERP?
    │   ├── Content.md                     # Chapter teaching material
    │   ├── Exercise.md                    # Chapter exercise + complete solution
    │   ├── Project.md                     # Chapter project + complete solution
    │   └── Resources.md                   # Supplementary references
    ├── Chapter 2/                         # Understanding Odoo
    │   ├── Content.md
    │   ├── Exercise.md
    │   ├── Project.md
    │   └── Resources.md
    ├── Chapter 3/                         # Core Business Applications
    │   ├── Content.md
    │   ├── Exercise.md
    │   ├── Project.md
    │   └── Resources.md
    ├── Conclusion/
    │   └── Summary.md                     # Unit completeness check + unit summary
    ├── Exercise/
    │   └── Exercise.md                    # Unit capstone exercise + solution
    └── Project/
        └── Project.md                     # Unit capstone project + solution + next-unit transition
```

### UNIT I STUDY ORDER

Work through Unit I in this sequence:

1. **Chapter 1** → [Content](Unit%201/Chapter%201/Content.md), then [Exercise](Unit%201/Chapter%201/Exercise.md), then [Project](Unit%201/Chapter%201/Project.md) · [Resources index](Unit%201/Chapter%201/Resources.md)  
2. **Chapter 2** → [Content](Unit%201/Chapter%202/Content.md), then [Exercise](Unit%201/Chapter%202/Exercise.md), then [Project](Unit%201/Chapter%202/Project.md) · [Resources index](Unit%201/Chapter%202/Resources.md)  
3. **Chapter 3** → [Content](Unit%201/Chapter%203/Content.md), then [Exercise](Unit%201/Chapter%203/Exercise.md), then [Project](Unit%201/Chapter%203/Project.md) · [Resources index](Unit%201/Chapter%203/Resources.md)  

**After Chapter 3, start here:**

4. **Conclusion** → [Summary.md](Unit%201/Conclusion/Summary.md): completeness check and unit recap  
5. **Unit Exercise** → [Exercise/Exercise.md](Unit%201/Exercise/Exercise.md)  
6. **Unit Project** → [Project/Project.md](Unit%201/Project/Project.md)  
7. **Unit II** → begins with Chapter 4 (Odoo Architecture)

Future units (`Unit 2/`, `Unit 3/`, etc.) will follow the same chapter pattern: Content, Resources, Exercise, Project, then unit Conclusion, Exercise, and Project.

The master roadmap lives at:

📄 [Table of Content/Roadmap.md](Table%20of%20Content/Roadmap.md)

---

## CURRICULUM OVERVIEW

### UNIT I: UNDERSTAND THE BUSINESS BEFORE THE CODE
Chapters 1–3 · ERP fundamentals, Odoo ecosystem, core business applications

Learn business processes, departments, master data, and how Odoo apps (CRM, Sales, Inventory, Accounting, etc.) fit together before writing any code.

**Status:** Complete: all three chapters, resources, unit conclusion, exercise, and project.

| Chapter | Topic | Content |
|---------|-------|---------|
| 1 | What Is ERP? | [Content](Unit%201/Chapter%201/Content.md) · [Resources](Unit%201/Chapter%201/Resources.md) · [Exercise](Unit%201/Chapter%201/Exercise.md) · [Project](Unit%201/Chapter%201/Project.md) |
| 2 | Understanding Odoo | [Content](Unit%201/Chapter%202/Content.md) · [Resources](Unit%201/Chapter%202/Resources.md) · [Exercise](Unit%201/Chapter%202/Exercise.md) · [Project](Unit%201/Chapter%202/Project.md) |
| 3 | Core Business Applications | [Content](Unit%201/Chapter%203/Content.md) · [Resources](Unit%201/Chapter%203/Resources.md) · [Exercise](Unit%201/Chapter%203/Exercise.md) · [Project](Unit%201/Chapter%203/Project.md) |

Unit-level capstone (**start here after Chapter 3**): [Conclusion](Unit%201/Conclusion/Summary.md) · [Exercise](Unit%201/Exercise/Exercise.md) · [Project](Unit%201/Project/Project.md)

---

### UNIT II: HOW ODOO ACTUALLY WORKS
Chapters 4–6 · Architecture, dev environment, source code structure

Three-tier architecture, ORM, PostgreSQL, filestore, workers, Python/PostgreSQL setup, and navigating the Odoo source tree.

---

### UNIT III: YOUR FIRST ODOO MODULE
Chapters 7–8 · Module anatomy and lifecycle

`__manifest__.py`, models, views, security, installation, upgrades, and module flags.

---

### UNIT IV: MODELING BUSINESS DATA
Chapters 9–12 · Models, fields, relationships, computed fields

`models.Model`, field types, Many2one/One2many/Many2many, `@api.depends`, stored vs non-stored computations.

---

### UNIT V: MASTERING THE ODOO ORM
Chapters 13–17 · Environment, CRUD, domains, recordsets, performance

`env`, `search()`, domains, recordset operations, prefetching, N+1 queries, `read_group()`, and ORM internals.

---

### UNIT VI: BUSINESS RULES & WORKFLOWS
Chapters 18–21 · Methods, constraints, onchange, state machines

Method overrides, `@api.constrains`, `@api.onchange`, draft/confirmed/done workflows, and auditability.

---

### UNIT VII: BUILDING THE USER INTERFACE
Chapters 22–26 · XML, views, actions, inheritance

Form/list/kanban/search views, window actions, menus, XPath inheritance, and upgrade-safe view extensions.

---

### UNIT VIII: SECURITY & MULTI-COMPANY
Chapters 27–31 · Users, ACLs, record rules, multi-company

Groups, `ir.model.access`, `ir.rule`, `sudo()`, field security, `company_id`, and cross-company patterns.

---

### UNIT IX: EXTENDING EXISTING ODOO
Chapters 32–35 · Inheritance, mixins, real module extensions

`_inherit`, `_inherits`, `mail.thread`, extending `sale.order`, `stock.picking`, `account.move`, and more.

---

### UNIT X: ADVANCED BUSINESS FEATURES
Chapters 36–42 · Wizards, cron, automation, mail, reports, data

TransientModel wizards, `ir.sequence`, `ir.cron`, server actions, QWeb reports, import/export, and demo data.

---

### UNIT XI: INTERNATIONALIZATION & LOCALIZATION
Chapter 43 · Translations and locale

`_()` translation function, `.po` files, translatable fields, and localization modules.

---

### UNIT XII: WEB DEVELOPMENT WITH ODOO
Chapters 44–46 · Controllers, website, portal

`@http.route`, QWeb pages, website forms, portal users, and customer-facing security.

---

### UNIT XIII: APIS & INTEGRATIONS
Chapters 47–52 · External API, webhooks, payments

JSON-RPC/XML-RPC, custom REST endpoints, webhook security, third-party sync, and payment provider integration.

---

### UNIT XIV: MODERN ODOO FRONTEND
Chapters 53–58 · JavaScript, OWL, assets, client actions

OWL components, services, registries, `patch()`, custom field widgets, and client actions.

---

### UNIT XV: FILES, ATTACHMENTS & MEDIA
Chapter 59 · Filestore and attachments

`ir.attachment`, binary/image fields, upload security, and access tokens.

---

### UNIT XVI: POSTGRESQL & PERFORMANCE
Chapters 60–65 · Database structure, SQL, transactions, optimization

Schema inspection, EXPLAIN ANALYZE, indexes, ORM performance, profiling, and benchmarking.

---

### UNIT XVII: TESTING & DEBUGGING
Chapters 66–71 · Logging, unit tests, security tests, frontend tests

`TransactionCase`, test tours, HOOT, query count tests, and root cause analysis.

---

### UNIT XVIII: CLI & DEVELOPER TOOLING
Chapter 72 · Odoo command-line interface

`odoo-bin`, install/upgrade flags, `--dev`, shell, scaffold, and test tags.

---

### UNIT XIX: DEPLOYMENT & OPERATIONS
Chapters 73–81 · Config, Linux, Nginx, workers, Docker, monitoring

Production configuration, systemd, HTTPS, backups, Odoo.sh, Docker Compose, and incident diagnosis.

---

### UNIT XX: UPGRADES, MIGRATIONS & MAINTENANCE
Chapters 82–88 · Versioning, schema changes, hooks, legacy code

Migration scripts, `pre_init_hook` / `post_init_hook`, upgrade-safe customization, and technical debt.

---

### UNIT XXI: FUNCTIONAL ODOO FOR DEVELOPERS
Chapter 89 · End-to-end business flows

Deep functional coverage of Sales, Purchase, Inventory, Accounting, MRP, eCommerce, POS, and document flows.

---

### UNIT XXII: REAL ODOO ENGINEERING
Chapters 90–94 · Requirements, architecture, maintainability, Git

ERP solution design, configuration vs customization decisions, code quality, and team collaboration workflows.

---

### UNIT XXIII: GRAND ODOO ENGINEERING CAPSTONE
Chapter 95 · Production ERP project

Full-stack capstone: requirements → models → security → UI → API → tests → deployment → documentation.

---

### UNIT XXIV: INTERVIEW & ODOO ENGINEER READINESS
Chapter 96 · Knowledge review, live engineering, final assessment

Structured review of all topics, live coding/debugging exercises, mock interviews, and portfolio defense.

---

## HOW TO USE THIS GUIDE

1. **Start at Unit I** — Even experienced developers benefit from the business context in early units.
2. **Follow the roadmap sequentially** — Later units assume knowledge from earlier chapters.
3. **Use the per-chapter structure** — Read each topic in `Content.md` (theory plus embedded **Relevant Resources** at the bottom of each section), then complete `Exercise.md` and `Project.md`. Use `Resources.md` as a chapter-wide reference when needed.
4. **Finish each unit** — Complete the unit `Conclusion/`, `Exercise/`, and `Project/` before starting the next unit.
5. **Use the table of contents** — Open [Roadmap.md](Table%20of%20Content/Roadmap.md) to jump to specific topics.
6. **Practice alongside reading** — Set up a local Odoo dev environment (Unit II, Chapter 5) and build modules as you learn.
7. **Track your progress** — Check off chapters as you complete them; revisit ORM and security units before interviews.
8. **Build the capstone** — Unit XXIII is designed as a portfolio-worthy production project.

---

## RECOMMENDED STUDY ORDER

```mermaid
flowchart TD
    A[Unit I: Business & ERP] --> B[Unit II: Architecture & Setup]
    B --> C[Unit III: First Module]
    C --> D[Units IV–VI: Models, ORM, Workflows]
    D --> E[Units VII–IX: UI, Security, Extensions]
    E --> F[Units X–XV: Advanced Features & Full-Stack]
    F --> G[Units XVI–XX: Performance, Testing, Deployment]
    G --> H[Units XXI–XXIII: Engineering & Capstone]
    H --> I[Unit XXIV: Interview Readiness]
    I --> J[Odoo Engineer]
```

---

## TECHNOLOGIES COVERED

| Category | Technologies & Concepts |
|----------|-------------------------|
| **Backend** | Python, Odoo ORM, PostgreSQL |
| **Frontend** | OWL, JavaScript, SCSS, QWeb |
| **Web** | HTTP controllers, Website, Portal |
| **Integration** | JSON-RPC, REST, Webhooks, OAuth |
| **DevOps** | Linux, Nginx, systemd, Docker, Odoo.sh |
| **Quality** | Unit tests, tours, profiling, CI concepts |
| **Business** | CRM, Sales, Inventory, Accounting, MRP, HR |

---

## OFFICIAL RESOURCES

Use these alongside this study guide:

| Resource | URL |
|----------|-----|
| Odoo Documentation | https://www.odoo.com/documentation |
| Odoo Developer Docs | https://www.odoo.com/documentation/master/developer.html |
| Odoo GitHub (Community) | https://github.com/odoo/odoo |
| OWL Framework | https://github.com/odoo/owl |
| PostgreSQL Documentation | https://www.postgresql.org/docs/ |

---

## CONTRIBUTING

Contributions are welcome! This guide grows best with community input.

1. **Fork** the repository
2. **Create a branch** for your changes (`feature/unit-4-chapter-9-notes`)
3. **Follow the existing structure** — organize content by unit and chapter
4. **Submit a pull request** with a clear description of what you added or improved

Suggestions for contributions:

- Chapter notes, examples, and exercises
- Code samples and module templates
- Corrections and clarifications to the roadmap
- Translations of study material

---

## LICENSE

This study guide is provided as an open educational resource. Please refer to the repository for license details. When sharing or adapting content, credit the original repository and respect Odoo's own licensing terms for Odoo source code and trademarks.

---

## AUTHOR

**Repository:** [github.com/Bixal99/ODOO](https://github.com/Bixal99/ODOO)

---

<p align="center">
  <strong>Zero Knowledge → ERP Understanding → Odoo Development → Full-Stack Odoo → Production Engineering → Odoo Engineer</strong>
</p>
