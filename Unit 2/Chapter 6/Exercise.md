# CHAPTER 6 EXERCISE

Answer before scrolling to the solution. For each response, give the concept, scenario evidence, and a reason. Self-score each original numbered question or named part: 0 = missing/incorrect, 1 = correct label without reasoning, 2 = correct explanation using evidence. Rework every answer below 2. The solution is one defensible model, not wording to memorize; clearly stated alternative assumptions can support a different answer.

Try answering these without looking back at Content.md first. Answer in your own words, then compare with the complete solution at the bottom of this file.

For verified source-navigation materials, see [Resources.md](Resources.md).

---

## TABLE OF CONTENTS

- [Case Study: Where Does This Feature Come From?](#case-study-where-does-this-feature-come-from)
- [Question 1: odoo/ Versus addons/](#question-1-odoo-versus-addons)
- [Question 2: One sale_order.py File](#question-2-one-sale_orderpy-file)
- [Question 3: opportunity_id Extension](#question-3-opportunity_id-extension)
- [Question 4: Manifest First](#question-4-manifest-first)
- [Question 5: models/__init__.py](#question-5-models__init__py)
- [Question 6: _name Versus _inherit](#question-6-_name-versus-_inherit)
- [Question 7: sale.view_order_form](#question-7-saleview_order_form)
- [Question 8: XML IDs Versus Database IDs](#question-8-xml-ids-versus-database-ids)
- [Question 9: Multiple action_confirm](#question-9-multiple-action_confirm)
- [Question 10: super()](#question-10-super)
- [Question 11: Where To Look](#question-11-where-to-look)
- [Question 12: Source Exists But Missing In Database](#question-12-source-exists-but-missing-in-database)
- [Complete Solution](#chapter-6-exercise-complete-solution)

---

## CASE STUDY: WHERE DOES THIS FEATURE COME FROM?

You join Nova Retail Group's Odoo project.

A Sales Order for Meridian Supplies (`SO0052`) contains:

- a customer,
- an opportunity link,
- a Delivery smart button,
- a Margin field.

Noor asks:

> Are all of these features actually part of the core Sales module?

You must investigate the source instead of guessing.

---

## QUESTION 1: ODOO/ VERSUS ADDONS/

What is the conceptual difference between the top-level `odoo/` directory and top-level `addons/`?

---

## QUESTION 2: ONE SALE_ORDER.PY FILE

Why is searching only `addons/sale/models/sale_order.py` insufficient to understand the complete runtime `sale.order` model?

---

## QUESTION 3: OPPORTUNITY_ID EXTENSION

A field is defined as:

```python
opportunity_id = fields.Many2one(...)
```

inside a class with:

```python
_inherit = "sale.order"
```

What does that tell you?

---

## QUESTION 4: MANIFEST FIRST

Why should you inspect a module's `__manifest__.py` before deeply reading its code?

---

## QUESTION 5: MODELS/__INIT__.PY

What role does `models/__init__.py` play?

---

## QUESTION 6: _NAME VERSUS _INHERIT

What is the difference between:

```python
_name = "sale.order"
```

and:

```python
_inherit = "sale.order"
```

at a high level?

---

## QUESTION 7: SALE.VIEW_ORDER_FORM

You encounter:

```xml
inherit_id ref="sale.view_order_form"
```

Explain what `sale.view_order_form` represents.

---

## QUESTION 8: XML IDS VERSUS DATABASE IDS

Why are XML IDs more useful than raw PostgreSQL record IDs for module development?

---

## QUESTION 9: MULTIPLE ACTION_CONFIRM

You find three different implementations of:

```python
def action_confirm(self):
```

What should you inspect before deciding which one actually executes?

---

## QUESTION 10: SUPER()

Why is `super()` important when tracing Odoo methods?

---

## QUESTION 11: WHERE TO LOOK

Where would you primarily look for:

1. HTTP routing?
2. model declarations?
3. reusable framework utilities?
4. module loading?
5. runtime model registry?

---

## QUESTION 12: SOURCE EXISTS BUT MISSING IN DATABASE

Why might a field exist in the source code but not appear in a particular database's model?

---

# CHAPTER 6 EXERCISE: COMPLETE SOLUTION

Work through the questions above first. The solution below is one defensible model using Chapter 6 evidence.

---

## QUESTION 1

**Concept:** Framework versus business modules.

**Evidence:** Top-level `odoo/` holds runtime/framework packages. Top-level `addons/` holds functional modules such as Sales, CRM, Accounting, and HR.

**Reason:**

$$ \texttt{odoo/} = \text{Framework} $$

$$ \texttt{addons/} = \text{Business Modules} $$

Without that split, every investigation starts in the wrong shelf.

---

## QUESTION 2

**Concept:** Extensible models.

**Evidence:** Other installed modules can contain `_inherit = "sale.order"` and add fields, methods, and constraints.

**Reason:**

$$ \text{Effective sale.order} \neq \text{One Python File} $$

$$ \text{Effective Model} = \text{Base Definition} + \text{Loaded Extensions} $$

Reading only `sale_order.py` describes the base contribution, not the full registry model on `odoo19_dev`.

---

## QUESTION 3

**Concept:** Model inheritance / field contribution.

**Evidence:** `_inherit = "sale.order"` plus a new field means the module extends Sales Order rather than creating an unrelated model.

**Reason:** In current Odoo 19, `sale_crm` does this with `opportunity_id`. CRM linkage is contributed by an integration module, not necessarily invented inside base `sale`.

---

## QUESTION 4

**Concept:** Manifest as module context.

**Evidence:** `__manifest__.py` declares dependencies, data files, metadata, and installability.

**Reason:** It answers "What must exist before this module?" and "Which XML/CSV files does it load?" Reading code without the dependency graph is guessing.

---

## QUESTION 5

**Concept:** Python import chain.

**Evidence:** `models/__init__.py` imports model files into the module package (for Sales, files such as `sale_order`).

**Reason:**

$$ \text{Python File Exists} \neq \text{Python File Loaded} $$

If `sale_order.py` is never imported, its classes do not participate in module loading.

---

## QUESTION 6

**Concept:** Define versus extend (beginner mental model).

**Evidence:** `_name = "sale.order"` introduces model identity. `_inherit = "sale.order"` commonly extends an existing model.

**Reason:**

$$ \texttt{\_name} \approx \text{Define} $$

$$ \texttt{\_inherit} \approx \text{Extend} $$

Later chapters refine inheritance nuances. This high-level map is enough for Chapter 6 tracing.

---

## QUESTION 7

**Concept:** XML / external ID.

**Evidence:** Split `sale.view_order_form` into module `sale` and record id `view_order_form`.

**Reason:** It identifies the standard Sales Order form view. Another module can reference it to inherit that view, which is how Delivery UI can attach without editing base Sales XML.

---

## QUESTION 8

**Concept:** Portability of identifiers.

**Evidence:** Integer IDs differ across databases (542 vs 887). XML IDs such as `sale.view_order_form` stay stable as module-scoped names.

**Reason:** Module development needs portable references across environments. Raw PostgreSQL IDs do not travel safely.

---

## QUESTION 9

**Concept:** Inheritance chain / installed state.

**Evidence:** Multiple `action_confirm` definitions can exist across `sale`, `sale_crm`, custom modules such as `nova_sale_approval`, and others.

**Reason:** Inspect which model each class extends, which module owns it, whether that module is installed, dependency relationships, `super()` calls, and runtime behavior (debugger) before claiming one file is "the" implementation.

---

## QUESTION 10

**Concept:** Extending versus replacing.

**Evidence:** An override that calls `super().action_confirm()` continues the chain into parent/next implementations.

**Reason:** Without `super()`, an override may drop expected Sales or CRM behavior. With `super()`, the typical goal is existing behavior plus new behavior.

---

## QUESTION 11

**Concept:** Source shelf literacy.

**Evidence / Reason:**

| Need | Primary place |
| --- | --- |
| HTTP routing | `odoo/http.py` plus module `controllers/` |
| Model declarations | module `models/` using `odoo.models` |
| Reusable utilities | `odoo/tools/` |
| Module loading | `odoo/modules/` |
| Runtime model registry | registry-related code under `odoo/modules/` |

---

## QUESTION 12

**Concept:** Disk presence versus runtime state.

**Evidence:** A field can live in source while its module is not installed on the current database.

**Reason:**

$$ \text{Source Available} + \text{Module Installed} + \text{Dependencies Resolved} + \text{Registry Loaded} $$

So:

$$ \text{File on Disk} \neq \text{Active Runtime Feature} $$

At Nova Retail, `odoo19_dev` and another database can disagree even when the same checkout is shared.
