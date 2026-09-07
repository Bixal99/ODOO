# UNIT II EXERCISE

Answer before scrolling to the solution. For each response, give the concept, scenario evidence, and a reason. Self-score each original numbered question or named part: 0 = missing/incorrect, 1 = correct label without reasoning, 2 = correct explanation using evidence. Rework every answer below 2. The solution is one defensible model, not wording to memorize; clearly stated alternative assumptions can support a different answer.

This exercise covers all of Unit II: Chapters 4, 5, and 6.

Try answering without looking back first. Work through the scenario in your own words, then compare with the complete solution below.

---

## TABLE OF CONTENTS

- [Case Study: Broken Customization Investigation](#case-study-broken-customization-investigation)
- [Question 1: Likely Layer](#question-1-likely-layer)
- [Question 2: addons_path](#question-2-addons_path)
- [Question 3: Module Installed](#question-3-module-installed)
- [Question 4: Manifest](#question-4-manifest)
- [Question 5: Import Chain](#question-5-import-chain)
- [Question 6: Unimported File](#question-6-unimported-file)
- [Question 7: Field Exists UI Missing](#question-7-field-exists-ui-missing)
- [Question 8: sale.view_order_form](#question-8-saleview_order_form)
- [Question 9: action_confirm Never Runs](#question-9-action_confirm-never-runs)
- [Question 10: Debugger Evidence](#question-10-debugger-evidence)
- [Question 11: Editing Standard sale_order.py](#question-11-editing-standard-sale_orderpy)
- [Question 12: Full Investigation Flow](#question-12-full-investigation-flow)
- [Complete Solution](#unit-ii-exercise-complete-solution)

---

## CASE STUDY: BROKEN CUSTOMIZATION INVESTIGATION

Your team installs a custom module:

`nova_sale_extension`

The requirements were:

- add `approval_reason` to Sales Order,
- display it on the Sales Order form,
- perform extra logic when Sales Order is confirmed.

After installation on `odoo19_dev`:

- the module is visible in Apps,
- `approval_reason` does not appear,
- no error is displayed,
- the confirmation behavior also appears unchanged.

Rami owns the investigation. Lina asks for evidence, not guesses. Noor still needs Meridian Supplies orders such as `SO0052` to confirm correctly.

Diagnose the problem using everything from Unit II (architecture, environment, source navigation).

---

## QUESTION 1: LIKELY LAYER

Which architectural layer is most likely involved if the Odoo web client loads normally but the custom field is missing?

---

## QUESTION 2: ADDONS_PATH

Why should you check `addons_path`?

---

## QUESTION 3: MODULE INSTALLED

Why should you check whether the module is installed in the current database?

---

## QUESTION 4: MANIFEST

Why should you inspect `__manifest__.py`?

---

## QUESTION 5: IMPORT CHAIN

Why should you inspect `__init__.py` and `models/__init__.py`?

---

## QUESTION 6: UNIMPORTED FILE

Suppose:

```python
class SaleOrder(models.Model):
    _inherit = "sale.order"

    approval_reason = fields.Char()
```

exists, but `sale_order.py` is not imported.

What happens conceptually?

---

## QUESTION 7: FIELD EXISTS UI MISSING

Suppose the Python field works but the UI still does not display it. Which area should you inspect?

---

## QUESTION 8: SALE.VIEW_ORDER_FORM

Suppose your XML inherits `sale.view_order_form`. What is that value?

---

## QUESTION 9: ACTION_CONFIRM NEVER RUNS

Your custom `action_confirm()` never runs. List at least five things to investigate.

---

## QUESTION 10: DEBUGGER EVIDENCE

How would a debugger help you determine whether the override participates in runtime execution?

---

## QUESTION 11: EDITING STANDARD SALE_ORDER.PY

Why is editing `addons/sale/models/sale_order.py` directly a bad solution?

---

## QUESTION 12: FULL INVESTIGATION FLOW

Construct a complete investigation flow from symptom to root cause.

---

# UNIT II EXERCISE: COMPLETE SOLUTION

Work through the questions above first. The solution below combines Chapters 4–6 into one investigation habit.

---

## QUESTION 1

**Concept:** Layer isolation.

**Evidence:** Browser and web client load normally, so the whole stack is not down.

**Reason:** Investigation should move toward module loading, registry, model definition, view definition, and addon configuration. Do not immediately blame PostgreSQL or the browser.

---

## QUESTION 2

**Concept:** Module discovery.

**Evidence:** Odoo discovers modules through directories listed in `addons_path`.

**Reason:** If the parent directory of `nova_sale_extension` is missing from `addons_path`, Odoo cannot properly discover the module even when the folder exists on disk.

---

## QUESTION 3

**Concept:** Disk versus database state.

**Evidence:** A source directory existing on disk does not mean its code is active in `odoo19_dev`.

**Reason:**

$$ \text{Module Source} + \text{Installed Module State} + \text{Registry Loading} $$

Confirm installation for the database under test.

---

## QUESTION 4

**Concept:** Manifest completeness.

**Evidence:** The manifest declares dependencies, data files, installability, and metadata.

**Reason:** If the view XML is missing from `"data": [...]`, it may never load. If `"depends"` omits `sale`, inheritance may be invalid or incomplete.

---

## QUESTION 5

**Concept:** Python package imports.

**Evidence:** Model files must be imported through the package hierarchy.

**Reason:** Typical chain:

```text
module/__init__.py
→ models
→ models/__init__.py
→ sale_order.py
```

Missing imports prevent model classes from executing.

---

## QUESTION 6

**Concept:** Present versus loaded.

**Evidence:** The file exists, but the class is never imported into the module package.

**Reason:** `approval_reason` would not become part of the effective model. This is the difference between source present and source loaded.

---

## QUESTION 7

**Concept:** View layer after model layer.

**Evidence:** Model field existence does not automatically display the field on every form.

**Reason:** Inspect the XML view: inherited view, XML ID, XPath/location, manifest loading, and whether the module was upgraded after view changes.

---

## QUESTION 8

**Concept:** External / XML ID.

**Evidence:** `sale.view_order_form` splits into module `sale` and record id `view_order_form`.

**Reason:** It identifies the Sales Order form view defined by the `sale` module and is the portable target for inheritance.

---

## QUESTION 9

**Concept:** Method-chain investigation.

**Evidence / Reason:** Investigate at least:

1. Is the custom file imported?
2. Is the module installed?
3. Is `_inherit = "sale.order"` correct?
4. Is the method name exactly `action_confirm`?
5. Was the module upgraded after code changes?
6. Is the request hitting `odoo19_dev`?
7. Are multiple Odoo processes running?
8. Is the debugger attached to the right process?
9. Do other overrides affect execution?
10. Does the custom override call `super()` properly?

---

## QUESTION 10

**Concept:** Runtime evidence.

**Evidence:** Place a breakpoint inside `def action_confirm(self):` then confirm a Sales Order.

**Reason:** If execution pauses there, the override is active. If it does not, investigate loading, registry, and method chain. The call stack shows where execution came from.

---

## QUESTION 11

**Concept:** Customization ownership.

**Evidence:** Editing standard `sale_order.py` mixes vendor and custom code.

**Reason:** It creates upgrade conflicts, hides ownership, makes maintenance harder, and risks losing changes when source updates. Prefer:

```text
custom_addons/
└── nova_sale_extension/
```

using inheritance.

---

## QUESTION 12

**Concept:** Unit II investigation pyramid.

**Reason:** A disciplined flow is:

$$ \text{Observe Symptom} $$

↓

$$ \text{Identify Model / View / Method} $$

↓

$$ \text{Confirm Module Discovery} $$

↓

$$ \text{Confirm Module Installed} $$

↓

$$ \text{Check Manifest} $$

↓

$$ \text{Check Imports} $$

↓

$$ \text{Check Registry / Upgrade} $$

↓

$$ \text{Trace XML ID} $$

↓

$$ \text{Trace Method Overrides} $$

↓

$$ \text{Use Logs / Debugger} $$

↓

$$ \text{Verify Root Cause} $$

That is the systematic thinking Unit II was designed to develop.
