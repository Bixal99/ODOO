# UNIT II PROJECT: DIAGNOSE AND MAP A REAL ODOO FEATURE

A Unit Project is justified here because Chapters 4–6 naturally combine into one engineering workflow: architecture, environment, and source navigation.

Complete all ten tasks with named components, evidence, and one verification step where relevant. Self-score each task: 0 = missing/incorrect, 1 = correct label without reasoning, 2 = correct explanation using evidence. Rework every answer below 2.

---

## TABLE OF CONTENTS

- [Case Study](#case-study)
- [Constraints](#constraints)
- [Task 1: Architecture Flow](#task-1-architecture-flow)
- [Task 2: Environment Map](#task-2-environment-map)
- [Task 3: Source Ownership](#task-3-source-ownership)
- [Task 4: Field Trace](#task-4-field-trace)
- [Task 5: View Trace](#task-5-view-trace)
- [Task 6: Method Trace](#task-6-method-trace)
- [Task 7: Custom Module Placement](#task-7-custom-module-placement)
- [Task 8: Dependency Decision](#task-8-dependency-decision)
- [Task 9: Debugging Strategy](#task-9-debugging-strategy)
- [Task 10: Final Engineering Diagram](#task-10-final-engineering-diagram)
- [Complete Solution](#unit-ii-project-complete-solution)

---

## CASE STUDY

Nova Retail Group has an Odoo 19 development server.

Users report:

> When we confirm a Sales Order, CRM values change and a Delivery button appears. We want to add an approval process, but the developers do not understand where existing behavior comes from.

You must produce a technical investigation before writing the custom module `nova_sale_approval`.

Use Sales Order `SO0052` for Meridian Supplies as the running example.

---

## CONSTRAINTS

You must not:

- edit official Odoo source,
- guess module ownership,
- make production database changes,
- disable integrations,
- start writing the custom feature before understanding the existing execution flow.

---

## TASK 1: ARCHITECTURE FLOW

Trace:

Salesperson clicks Confirm.

From Browser to PostgreSQL.

---

## TASK 2: ENVIRONMENT MAP

Document:

- Python environment,
- Odoo source,
- PostgreSQL,
- config,
- addons path,
- custom addons path,
- development database.

---

## TASK 3: SOURCE OWNERSHIP

Identify:

- base Sales Order module,
- CRM integration module,
- stock integration module.

---

## TASK 4: FIELD TRACE

Find `opportunity_id` and explain which module contributes it.

---

## TASK 5: VIEW TRACE

Find the Delivery-related Sales Order view extension and explain its inherited XML ID.

---

## TASK 6: METHOD TRACE

Explain how `action_confirm()` can be extended by multiple modules.

---

## TASK 7: CUSTOM MODULE PLACEMENT

Design `custom_addons/nova_sale_approval/` conceptually.

Do not implement the complete module yet.

---

## TASK 8: DEPENDENCY DECISION

If approval requires only Sales, choose the dependency.

If approval logic also directly uses Delivery data, explain what additional dependency may be required.

---

## TASK 9: DEBUGGING STRATEGY

Explain where to place breakpoints to observe confirmation behavior.

---

## TASK 10: FINAL ENGINEERING DIAGRAM

Create one diagram joining architecture, environment, source structure, and runtime method execution.

---

# UNIT II PROJECT: COMPLETE SOLUTION

Complete the tasks above first. The solution below is one defensible Unit II end-to-end map.

---

## TASK 1: ARCHITECTURE FLOW

A Sales Order confirmation request conceptually follows:

```text
User
↓
Browser
↓
Odoo Web Client
↓
HTTP/RPC
↓
Odoo HTTP Layer
↓
Worker
↓
Python Runtime
↓
Registry
↓
sale.order
↓
action_confirm()
↓
ORM
↓
PostgreSQL
```

Additional addons may extend `sale.order` inside the registry before the method runs.

---

## TASK 2: ENVIRONMENT MAP

A clean development environment could be:

```text
odoo19-development/
├── odoo/
├── custom_addons/
├── .venv/
├── config/
│   └── odoo.conf
└── logs/
```

Configuration contains addon paths including `odoo/addons` (or Community `addons`) and `custom_addons`, and the server targets a clearly named database such as `odoo19_dev`.

---

## TASK 3: SOURCE OWNERSHIP

| Concern | Module |
| --- | --- |
| Base Sales | `sale` |
| CRM integration | `sale_crm` |
| Inventory / Delivery integration | `sale_stock` |

---

## TASK 4: FIELD TRACE

Current Odoo 19 places `opportunity_id = fields.Many2one(...)` inside `sale_crm/models/sale_order.py` on `_inherit = "sale.order"`.

CRM linkage is modularly added rather than requiring base Sales to own CRM functionality.

---

## TASK 5: VIEW TRACE

`sale_stock/views/sale_order_views.xml` inherits `sale.view_order_form` and introduces Delivery-related UI.

So:

$$ \text{Base Form} + \text{Stock View Extension} = \text{Final UI} $$

---

## TASK 6: METHOD TRACE

Potential runtime chain:

```text
custom approval override
↓ super()
sale_crm override
↓ super()
other installed integration override
↓ super()
base sale action_confirm
```

The exact chain depends on installed modules and inheritance resolution.

Important point:

$$ \text{Runtime Method} \neq \text{One Source File} $$

---

## TASK 7: CUSTOM MODULE PLACEMENT

Conceptual structure:

```text
custom_addons/
└── nova_sale_approval/
    ├── __init__.py
    ├── __manifest__.py
    ├── models/
    │   ├── __init__.py
    │   └── sale_order.py
    └── views/
        └── sale_order_views.xml
```

Unit III teaches module anatomy and lifecycle in depth. This project only places the module correctly.

---

## TASK 8: DEPENDENCY DECISION

If approval requires only Sales:

```python
"depends": ["sale"]
```

is conceptually appropriate.

If it directly relies on stock/delivery behavior provided by Sales-Inventory integration, then `sale_stock` may need to be included.

Principle:

$$ \text{Depend on the module that owns the functionality you use} $$

---

## TASK 9: DEBUGGING STRATEGY

Useful breakpoints include:

- custom `action_confirm`,
- CRM's `action_confirm`,
- relevant base Sales confirmation method,
- any method responsible for approval logic.

Then:

```text
Browser Confirm
↓
Debugger pauses
↓
Call Stack
↓
Inspect self
↓
Inspect model / runtime chain
```

This converts assumptions into evidence on `SO0052`.

---

## TASK 10: FINAL ENGINEERING DIAGRAM

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

Development environment surrounding it:

```text
Python venv
+ Odoo source
+ addons_path
+ custom_addons
+ odoo.conf
+ IDE/debugger
```

This is the complete mental model of Unit II.
