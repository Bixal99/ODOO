# UNIT II CONCLUSION: HOW ODOO ACTUALLY WORKS

You've finished the three teaching chapters of Unit II. Before we go into Unit III and your first module, pause here: check that the full unit landed, then pull the whole picture together in one place.

---

## TABLE OF CONTENTS

- [Did We Cover Everything?](#did-we-cover-everything)
- [Unit II Learning Model](#unit-ii-learning-model)
- [Unit II Key Mental Model](#unit-ii-key-mental-model)
- [The Whole Unit In One Picture](#the-whole-unit-in-one-picture)
- [Transition Toward Unit III](#transition-toward-unit-iii)

---

## DID WE COVER EVERYTHING?

Knowing folder names is only the starting point. A learner should also be able to explain request flow, environment evidence, source ownership, and inheritance chains. Topic coverage by itself does not demonstrate mastery.

Chapter 6 was the last teaching chapter in Unit II. The roadmap defines this unit as Chapters 4 through 6, then **Unit III: Your First Odoo Module**. So this is a good moment to ask: did we actually cover what we needed before building addons?

### CHAPTER 4: ODOO ARCHITECTURE

We covered:

- Three-tier architecture
- Browser
- Web client
- HTTP request
- Application server
- Python runtime
- ORM
- PostgreSQL
- Filestore
- Addons
- Registry
- HTTP layer
- Sessions
- Workers
- Cron workers
- Long-polling / WebSocket concepts

Exercise and project are in place.

This chapter gave you the system map: presentation, logic, and data, plus the runtime vocabulary that makes later debugging possible.

### CHAPTER 5: DEVELOPMENT ENVIRONMENT

We covered:

- Python environment
- Virtual environments
- Dependencies
- PostgreSQL setup
- PostgreSQL user
- Odoo source
- Git clone
- Configuration file
- `addons_path`
- Custom addons directory
- Database creation
- Developer mode
- Developer mode with assets
- Logging
- IDE setup
- Debugger setup

Exercise and project are in place.

This chapter gave you a workshop you can trust: a coherent local Odoo 19.0 workspace rather than a lucky one-time login screen.

### CHAPTER 6: ODOO SOURCE CODE STRUCTURE

We covered:

- `odoo/`
- `addons/`
- Core framework
- `api.py` concepts
- `fields.py` concepts
- `models.py` concepts
- HTTP
- Services
- Tools
- Registry
- Modules loader
- Reading official addons
- Tracing model definitions
- Tracing XML IDs
- Tracing methods

Exercise and project are in place.

This chapter gave you source literacy: question-driven navigation from UI symptom to module, model, XML ID, method, and runtime evidence.

**No important Unit II gap detected.**

---

## UNIT II LEARNING MODEL

Unit II progressed through three levels.

### LEVEL 1: ARCHITECTURE

$$ \text{Browser} \rightarrow \text{Server} \rightarrow \text{ORM} \rightarrow \text{Database} $$

### LEVEL 2: DEVELOPMENT ENVIRONMENT

$$ \text{Python} + \text{PostgreSQL} + \text{Odoo Source} + \text{Config} + \text{IDE} $$

### LEVEL 3: SOURCE NAVIGATION

$$ \text{Repository} \rightarrow \text{Module} \rightarrow \text{Model} \rightarrow \text{View} \rightarrow \text{Method} $$

---

## UNIT II KEY MENTAL MODEL

You should now be capable of thinking:

User clicks something in the browser.

Then:

$$ \text{Web Client} $$

↓

$$ \text{HTTP} $$

↓

$$ \text{Odoo Server} $$

↓

$$ \text{Loaded Module / Registry} $$

↓

$$ \text{Model Method} $$

↓

$$ \text{ORM} $$

↓

$$ \text{PostgreSQL} $$

And when debugging it:

$$ \text{UI} \rightarrow \text{XML View} \rightarrow \text{Model} \rightarrow \text{Method} \rightarrow \text{Inheritance} \rightarrow \text{Debugger} $$

At Nova Retail, that habit turns a vague report about `SO0052` into an evidence trail Rami, Lina, and Noor can share.

---

## THE WHOLE UNIT IN ONE PICTURE

```text
                         USER
                          │
                          ▼
                       Browser
                          │
                          ▼
                    Odoo Web Client
                          │
                          ▼
                       HTTP/RPC
                          │
                          ▼
                    Odoo Server
                          │
                          ▼
                    Python Runtime
                          │
                    ┌─────┴─────┐
                    │ Registry  │
                    └─────┬─────┘
                          │
             ┌────────────┼────────────┐
             │            │            │
             ▼            ▼            ▼
           sale        sale_crm     sale_stock
             │            │            │
             └────────────┼────────────┘
                          │
                          ▼
                     sale.order
                          │
                          ▼
                    action_confirm
                          │
                          ▼
                         ORM
                          │
                          ▼
                     PostgreSQL
```

Surrounding workspace from Chapter 5:

```text
Python venv
+ Odoo 19.0 source
+ addons_path
+ custom_addons
+ odoo.conf
+ IDE / debugger
+ named database (odoo19_dev)
```

---

## TRANSITION TOWARD UNIT III

Unit II answered:

How does Odoo actually work internally?

You now understand:

- the architecture,
- development environment,
- repository structure,
- framework versus addons,
- model loading,
- registry,
- source tracing,
- XML IDs,
- method inheritance.

But we have still not properly created our own Odoo module.

That is intentional.

We first needed to understand the machine before adding to it.

The next roadmap unit is:

**UNIT III: YOUR FIRST ODOO MODULE**

with:

**Chapter 7: Module Anatomy**

followed by:

**Chapter 8: Module Lifecycle**

The learning progression is now:

$$ \text{Understand Business} $$

↓

$$ \text{Understand Odoo Internals} $$

↓

$$ \text{Build Your Own Addon} $$

Chapter 7 will finally let us create and dissect a module containing concepts such as:

- addon directory,
- `__manifest__.py`,
- `__init__.py`,
- `models/`,
- `views/`,
- `security/`,
- `data/`,
- `demo/`,
- `static/`,
- `controllers/`,
- `wizard/`,
- `report/`,
- `i18n/`,
- `tests/`,
- README,
- coding conventions.

Unit II is complete under the current roadmap rules: chapter summaries, case-based exercises and dedicated solutions, justified projects and worked solutions, unit completeness check, unit exercise and solutions, unit project and solution, and transition are all in place.

**Continue:** [Unit II Exercise](../Exercise/Exercise.md) → [Unit II Project](../Project/Project.md) → Unit III Chapter 7
