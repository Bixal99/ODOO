# CHAPTER 6 PROJECT: TRACE A REAL ODOO FEATURE FROM UI TO SOURCE

This is a source-investigation project. You are not required to modify Odoo code. Every answer must be specific enough that another developer could follow the same trail on an Odoo 19.0 checkout without guessing. Complete all eight tasks with named modules, files, evidence, and one verification step where relevant. Self-score each task: 0 = missing/incorrect, 1 = correct label without reasoning, 2 = correct explanation using evidence. Rework every answer below 2.

A project is justified for this chapter because source ownership is learned by tracing a real feature, not by memorizing folder names.

For verified materials, see [Resources.md](Resources.md).

---

## TABLE OF CONTENTS

- [Case Study](#case-study)
- [Objectives](#objectives)
- [Constraints](#constraints)
- [Task 1: Base Model](#task-1-base-model)
- [Task 2: CRM Extension](#task-2-crm-extension)
- [Task 3: Delivery Extension](#task-3-delivery-extension)
- [Task 4: Method Trace](#task-4-method-trace)
- [Task 5: Manifest Analysis](#task-5-manifest-analysis)
- [Task 6: Future Customization Decision](#task-6-future-customization-decision)
- [Task 7: Delivery-Dependent Custom Feature](#task-7-delivery-dependent-custom-feature)
- [Task 8: Final Architecture Map](#task-8-final-architecture-map)
- [Complete Solution](#chapter-6-project-complete-solution)

---

## CASE STUDY

Nova Retail Group uses Odoo Sales, CRM, and Inventory.

The Sales team reports:

> On a Sales Order we can see CRM information and a Delivery button. We want to customize both, but we do not know which modules own those features.

You are not allowed to modify any code yet.

Your job is to produce a source ownership and execution trace before development begins. Use Sales Order `SO0052` for Meridian Supplies as the mental example.

---

## OBJECTIVES

You must determine:

- which module owns the base Sales Order,
- which modules extend it,
- where CRM integration comes from,
- where Delivery integration comes from,
- which XML view is being extended,
- how method overrides participate,
- what dependencies a future custom module such as `nova_sale_approval` may require.

---

## CONSTRAINTS

You must not:

- edit official Odoo source,
- guess module ownership,
- make database changes for this project,
- disable integrations,
- start writing the custom feature before understanding the existing execution flow.

---

## TASK 1: BASE MODEL

Locate the original `sale.order` model.

Document:

- module,
- file,
- model name.

---

## TASK 2: CRM EXTENSION

Find where `opportunity_id` is added to Sales Order.

Document:

- addon name,
- inherited model,
- field type,
- relevant method override.

---

## TASK 3: DELIVERY EXTENSION

Find which addon modifies the Sales Order form to add Delivery-related UI.

Document:

- addon,
- XML file,
- inherited view XML ID,
- button/method involved.

---

## TASK 4: METHOD TRACE

Trace `action_confirm` through at least:

- base Sales,
- one integration addon.

Explain why `super()` matters.

---

## TASK 5: MANIFEST ANALYSIS

Explain why the integration modules should depend on the functional modules they connect.

---

## TASK 6: FUTURE CUSTOMIZATION DECISION

Suppose your custom feature needs:

- base Sales Order only,
- no CRM,
- no Inventory.

Should the module depend on `sale`, `sale_crm`, or `sale_stock`? Explain.

---

## TASK 7: DELIVERY-DEPENDENT CUSTOM FEATURE

Suppose the custom feature needs the Delivery button / stock behavior.

Which dependency becomes relevant? Explain why depending only on `sale` may not be sufficient.

---

## TASK 8: FINAL ARCHITECTURE MAP

Create a conceptual diagram showing how `sale`, `crm`, `sale_crm`, `stock`, and `sale_stock` relate.

---

# CHAPTER 6 PROJECT: COMPLETE SOLUTION

Complete the tasks above first. The solution below is one defensible ownership map for Odoo 19.0-style Community source.

---

## TASK 1: BASE MODEL

The base Sales Order belongs to the `sale` module.

A core source location is:

```text
addons/sale/models/sale_order.py
```

Conceptually:

```text
sale
└── models
    └── sale_order.py
        └── sale.order
```

**Verification:** search for `_name = "sale.order"` (or single quotes) and confirm the declaring module is `sale`.

---

## TASK 2: CRM EXTENSION

CRM-Sales integration is provided by `sale_crm`.

Current Odoo 19-style layout includes:

```text
addons/sale_crm/models/sale_order.py
```

where the class uses `_inherit = "sale.order"`, adds `opportunity_id = fields.Many2one(...)`, and overrides `action_confirm()` before applying CRM-related behavior.

Therefore:

$$ \text{CRM Link on Sales Order} \rightarrow \text{sale\_crm} $$

not purely:

$$ \text{sale} $$

**Verification:** search `opportunity_id =` and confirm the owning addon is `sale_crm`.

---

## TASK 3: DELIVERY EXTENSION

Sales + Inventory integration is represented by `sale_stock`.

Current Odoo 19-style layout includes:

```text
addons/sale_stock/views/sale_order_views.xml
```

which inherits `sale.view_order_form` and introduces Delivery-related UI, often including a button referencing `action_view_delivery`.

Therefore:

$$ \text{Sales Delivery UI} \rightarrow \text{Sales/Stock Integration} $$

**Verification:** search `inherit_id` references to `sale.view_order_form` inside `sale_stock` views.

---

## TASK 4: METHOD TRACE

Base Sales provides primary Sales Order confirmation behavior.

An integration addon such as `sale_crm` can override `action_confirm()` and call `super().action_confirm()` before or after its own logic.

Conceptually:

$$ \text{sale\_crm.action\_confirm} \rightarrow \text{super()} \rightarrow \text{next implementation} \rightarrow \text{base Sales confirmation} $$

The exact runtime chain can involve more installed modules on `odoo19_dev`.

**Why `super()` matters:** without it, an override may replace expected existing behavior rather than extend it. The typical goal is:

$$ \text{Existing Behavior} + \text{New Behavior} $$

not accidental deletion of existing behavior.

---

## TASK 5: MANIFEST ANALYSIS

`sale_crm` extends Sales and CRM, so it logically needs both. The integration only makes sense if Sales and CRM are available.

Similarly, `sale_stock` exists because Sales and Inventory need integration.

Manifests encode those dependency edges so the module loader can order loading correctly.

---

## TASK 6: FUTURE CUSTOMIZATION DECISION

Requirement: add a Sales Order approval description field. No CRM. No stock.

The appropriate base dependency is normally `sale`, not `sale_crm` or `sale_stock`.

Principle:

$$ \text{Minimal Necessary Dependencies} $$

reduces coupling. A future `nova_sale_approval` should not drag CRM into every Sales database that only needs approval text.

---

## TASK 7: DELIVERY-DEPENDENT CUSTOM FEATURE

If the custom module directly depends on features provided by Sales/Inventory integration, then `sale_stock` is the relevant dependency.

Depending only on `sale` would not guarantee that stock-specific Sales behavior exists in the registry for that database.

---

## TASK 8: FINAL ARCHITECTURE MAP

```text
           ┌───────────┐
           │   sale    │
           └─────┬─────┘
                 │
       ┌─────────┴─────────┐
       │                   │
┌──────▼──────┐     ┌──────▼──────┐
│  sale_crm   │     │ sale_stock  │
└──────┬──────┘     └──────┬──────┘
       │                   │
┌──────▼──────┐     ┌──────▼──────┐
│    crm      │     │    stock    │
└─────────────┘     └─────────────┘
```

Conceptually:

$$ \text{sale\_crm} = \text{Sales/CRM Bridge} $$

$$ \text{sale\_stock} = \text{Sales/Inventory Bridge} $$

This bridge-module pattern is one of the most important structures to recognize when reading Odoo source at Nova Retail or anywhere else.
