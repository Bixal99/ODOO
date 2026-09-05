# CHAPTER 3 PROJECT: BILAL OFFICE SUPPLIES INTEGRATED ODOO FLOW

> **Added working assumptions:** This remains a conceptual project; an optional practice database is not required. Use one company and warehouse, usable unreserved opening stock, manual replenishment, a single full delivery, and billing after delivery. The 24,000 QAR total excludes tax, discounts, and freight. Use illustrative references CUST-ABC, SO001, PO001, REC001, DEL001, INV001, and TKT001 throughout your existing parts so each link can be traced.

We extend the same fictional company from Chapters 1 and 2.

This project connects CRM, Sales, Purchase, Inventory, Accounting, and Helpdesk into one integrated document flow.

For app-specific Odoo videos, documentation, and hands-on environments, see [Resources.md](Resources.md).

---

## TABLE OF CONTENTS

- [Part 1: Master Data](#part-1-master-data)
- [Part 2: CRM](#part-2-crm)
- [Part 3: Sales](#part-3-sales)
- [Part 4: Inventory](#part-4-inventory)
- [Part 5: Purchase](#part-5-purchase)
- [Part 6: Receipt](#part-6-receipt)
- [Part 7: Delivery](#part-7-delivery)
- [Part 8: Accounting](#part-8-accounting)
- [Part 9: Helpdesk](#part-9-helpdesk)
- [Part 10: Final Document Map](#part-10-final-document-map)
- [Complete Solution](#chapter-3-project-complete-solution)

---

## PART 1: MASTER DATA

> **Added prompt:** Give monitors and keyboards distinct product references and unit “unit.” Reuse ABC Trading across the opportunity, order, shipment, invoice, and ticket. Identify its invoice and delivery addresses separately. Explain which employee roles need user access to perform the later actions; an employee record alone does not authorize those actions.

Define:

**Customers**

- ABC Trading
- Doha Tech
- Gulf Office Solutions

**Vendors**

- Global Displays
- Qatar Hardware Supply

**Products**

- Laptop
- Monitor
- Keyboard
- Office Chair

**Employees**

- Ahmed — Sales
- Sara — Purchasing
- Ali — Warehouse
- Fatima — Finance

---

## PART 2: CRM

> **Added prompt:** Record Ahmed as opportunity owner, a proposed next activity, and the evidence needed to qualify the deal. Explain why 24,000 QAR is an estimate here rather than a posted receivable. The opportunity remains as sales history when a linked quotation is created.

Create this conceptual opportunity:

**ABC Trading — New Office Equipment**

Potential requirement:

- 20 monitors
- 20 keyboards

Expected value:

**20(1,000) + 20(200) = 20,000 + 4,000 = 24,000 QAR**

---

## PART 3: SALES

> **Added prompt:** Record two quotation lines, their units, quantities, agreed prices, and customer acceptance. Confirm the existing quotation as an order. Show that confirmation records demand and may plan a delivery, while on-hand stock and payment received remain unchanged at this moment.

**Enhanced:** Create a quotation linked to the opportunity; the opportunity remains a distinct CRM record.

Customer accepts.

Quotation becomes a confirmed Sales Order.

Demand:

- 20 monitors
- 20 keyboards

---

## PART 4: INVENTORY

> **Added prompt:** Maintain separate monitor and keyboard balances after confirmation, reservation, receipt, and delivery. If the eight monitors are reserved, they remain on hand but unavailable to another order. Explain why treating reservation as a delivery would subtract the same goods twice.

Available stock:

| Product | Required | Available |
| --- | --- | --- |
| Monitor | 20 | 8 |
| Keyboard | 20 | 50 |

Monitor shortage: **20 − 8 = 12**

**Enhanced:** Keyboard shortage: **max(0, 20 − 50) = 0**; thirty keyboards remain beyond this order’s demand.

Therefore monitors are not sufficient, but keyboards are.

---

## PART 5: PURCHASE

> **Added prompt:** Use PO001 for twelve monitors and identify Global Displays as vendor. The scenario gives a selling price but no vendor price; obtain or explicitly assume a purchase price before calculating a vendor bill. Do not reuse the 1,000 QAR selling price as supplier cost without evidence.

Purchase **12 monitors** from Global Displays.

Document conceptual flow:

**RFQ → Purchase Order**

---

## PART 6: RECEIPT

> **Added exception:** Record the actual receipt against PO001. If only ten monitors arrive, calculate available stock and the remaining supply obligation. Do not record twelve received simply because twelve were ordered. State who informs Sales about any effect on the promised delivery.

Vendor delivers **12 monitors**.

New monitor stock: **8 + 12 = 20**

---

## PART 7: DELIVERY

> **Added prompt:** Show ending stock after DEL001 and verify it against the two ordered product lines. If part is held back, record an actual partial delivery and outstanding demand. Never use a new customer order merely to represent the unfulfilled part of the same order.

Deliver **20 monitors** and **20 keyboards** to ABC Trading.

---

## PART 8: ACCOUNTING

> **Added prompt:** Distinguish draft invoice, posted invoice, payment activity, and completed settlement. Use the 24,000 QAR customer charge to calculate what remains due after a 10,000 QAR partial settlement and after the final 14,000 QAR. Record a vendor bill/payment as a related procurement branch if that cycle is in scope; no vendor amount is supplied.

Suppose:

- Monitor: **1,000 QAR**
- Keyboard: **200 QAR**

Invoice:

**20(1,000) + 20(200) = 24,000 QAR**

Customer pays **24,000 QAR**.

Outstanding: **0**

---

## PART 9: HELPDESK

> **Added prompt:** Open the ticket when the damage is reported, whether or not the invoice is paid. Add an investigation step and an explicit proposed remedy: repair, replacement, or credit/refund. Name which later record would prove the remedy happened. Ticket references are business requirements; structured links and after-sales buttons depend on installed features and configuration.

After delivery, customer reports:

Two keyboards are damaged.

Create a conceptual Helpdesk ticket containing:

- customer,
- Sales Order reference,
- delivery reference,
- problem,
- responsible support person,
- status.

Explain why connecting this ticket to existing records is better than treating it as an isolated email.

---

## PART 10: FINAL DOCUMENT MAP

> **Added completion criteria:** Connect the contact to multiple transactions, include receipt between purchasing and delivery, and branch the ticket from the post-delivery complaint independently of payment. For every arrow explain whether it means a shared reference, an action, or an optional dependency. Check quantities and amounts against Parts 4–8. The diagram is complete only when another learner can locate an unfinished shipment or payment from your explanation.

Your project should end with the complete conceptual flow from contact through payment and, if needed, Helpdesk.

That diagram demonstrates the core goal of Unit I:

**Understand the Business Before the Code**

---

# CHAPTER 3 PROJECT: COMPLETE SOLUTION

---

## PART 1: MASTER DATA

### CUSTOMERS

| Customer | Role in this project |
| --- | --- |
| **ABC Trading** | Main customer for the integrated flow |
| **Doha Tech** | Additional customer master record |
| **Gulf Office Solutions** | Additional customer master record |

These are reusable contact records, not transactions.

### VENDORS

| Vendor | Role in this project |
| --- | --- |
| **Global Displays** | Supplier used to replenish monitors |
| **Qatar Hardware Supply** | Additional vendor master record |

### PRODUCTS

| Product | Typical use |
| --- | --- |
| Laptop | General catalog product |
| Monitor | Used in ABC Trading order |
| Keyboard | Used in ABC Trading order |
| Office Chair | General catalog product |

### EMPLOYEES

| Employee | Department / role |
| --- | --- |
| Ahmed | Sales |
| Sara | Purchasing |
| Ali | Warehouse |
| Fatima | Finance |

Each employee is master data. Only some will also be Odoo users with app access.

---

## PART 2: CRM

**Opportunity:** ABC Trading — New Office Equipment

**Customer:** ABC Trading

**Potential requirement:**

- 20 monitors
- 20 keyboards

**Expected value:**

- Monitors: 20 × 1,000 = **20,000 QAR**
- Keyboards: 20 × 200 = **4,000 QAR**
- Total expected value: **24,000 QAR**

**Purpose at this stage:** track potential business before a formal quotation exists.

Ahmed may record notes, activities, stage, and expected close information while the deal is still being qualified.

---

## PART 3: SALES

**Enhanced:** Once requirements are clear, Ahmed creates a **quotation** linked to the opportunity for ABC Trading:

- 20 monitors at 1,000 QAR
- 20 keyboards at 200 QAR

When ABC Trading accepts, the quotation becomes a confirmed **Sales Order**.

**Confirmed demand:**

- 20 monitors
- 20 keyboards

This Sales Order now triggers operational consequences in Inventory and eventually Accounting.

---

## PART 4: INVENTORY

> **Added worked balances:** Before receipt there are eight monitors and fifty keyboards on hand. After receiving twelve monitors: twenty monitors and fifty keyboards. After the full delivery: zero monitors and thirty keyboards. If only ten monitors arrive, eighteen are available and two are still missing; agree a partial shipment or wait for the outstanding two.

| Product | Required | Available | Result |
| --- | --- | --- | --- |
| Monitor | 20 | 8 | Shortage of **12** |
| Keyboard | 20 | 50 | Sufficient stock |

Inventory analysis:

- Monitors: need 20, have 8, short **12**
- Keyboards: need 20, have 50, no purchase required

Ali sees outgoing delivery demand for both products, but only monitors require replenishment before full fulfillment.

---

## PART 5: PURCHASE

Sara creates procurement for **12 monitors** from **Global Displays**.

Conceptual flow:

<div align="center">

```mermaid
flowchart LR
    RFQ["RFQ"] --> PO["Purchase Order"]
```

</div>

The Purchase Order represents the commercial commitment to buy 12 monitors.

It does **not** by itself mean the monitors are already in stock.

---

## PART 6: RECEIPT

Global Displays delivers **12 monitors**.

Ali processes the receipt in Inventory.

Updated monitor stock:

**8 + 12 = 20 monitors**

Now the warehouse can fulfill the full Sales Order quantity for monitors. Keyboards were already sufficient.

---

## PART 7: DELIVERY

Ali delivers to ABC Trading:

- 20 monitors
- 20 keyboards

This is the physical fulfillment stage.

The Sales Order recorded the commercial promise.

The delivery records the actual movement of goods to the customer.

---

## PART 8: ACCOUNTING

> **Added worked settlement:** Against 24,000 QAR, a matched 10,000 QAR partial settlement leaves 14,000 QAR due; settling the remaining 14,000 leaves zero. The solution’s zero balance assumes the appropriate matching/reconciliation is complete. A payment button or standalone payment entry alone is not sufficient completion evidence.

**Pricing:**

- Monitor: 1,000 QAR
- Keyboard: 200 QAR

**Invoice calculation:**

- Monitors: 20 × 1,000 = 20,000 QAR
- Keyboards: 20 × 200 = 4,000 QAR
- Total invoice: **24,000 QAR**

Fatima creates and posts the customer invoice.

ABC Trading later pays **24,000 QAR**.

Outstanding balance becomes **0**.

The invoice represents what the customer owes.

**Enhanced:** The completed settlement in this example is supported by received funds and matching financial records; a payment entry alone does not prove settlement.

---

## PART 9: HELPDESK

> **Added worked remedy:** Suppose the agreed remedy is to inspect the two returned keyboards and replace them. Receiving two damaged returns does not make them saleable automatically; keep their condition/location explicit. Sending two good replacements from the thirty remaining good keyboards leaves twenty-eight good keyboards. A refund would instead need the appropriate financial correction and payment evidence. The complaint alone changes neither stock nor the invoice.

**Problem reported:** Two keyboards arrived damaged.

**Conceptual Helpdesk ticket:**

| Field | Value |
| --- | --- |
| Customer | ABC Trading |
| Sales Order reference | Linked to the original confirmed order |
| Delivery reference | Linked to the delivery that contained the keyboards |
| Problem | Two keyboards damaged on arrival |
| Responsible support person | Assigned support agent or team |
| Status | Example: New, In Progress, Waiting Customer, Resolved |

**Why integration is better than an isolated email:**

If the ticket stands alone, support must manually ask who the customer is, what was ordered, when delivery happened, and which invoice or order is involved.

Because the ticket links to existing Odoo records, support can immediately see:

- the customer contact,
- the Sales Order,
- the products delivered,
- the delivery document,
- prior commercial history.

That reduces delay, duplication, and error. It also preserves the customer lifecycle from CRM and Sales through fulfillment to after-sales support.

---

## PART 10: FINAL DOCUMENT MAP

> **Correction:** The support branch below starts from the post-delivery complaint, not from payment. The purchase step supplies this example’s shortage; it is not required for a fully stocked order. Separate references may need to be followed through the originating order rather than assumed to be direct links on every screen.

<div align="center">

```mermaid
flowchart TD
    CON["Contact: ABC Trading"] --> CRM["CRM Opportunity"]
    CRM --> QUO["Quotation"]
    QUO --> SO["Sales Order"]
    SO --> PO["Purchase Order for 12 monitors"]
    PO --> REC["Receipt"]
    REC --> DEL["Delivery"]
    DEL --> INV["Invoice: 24,000 QAR"]
    INV --> PAY["Payment"]
    DEL -->|"Damage complaint, independent of payment"| HD["Helpdesk Ticket if support issue"]
```

</div>

**Complete sequence:**

1. **Contact** — ABC Trading exists as reusable master data.
2. **CRM Opportunity** — potential deal for office equipment.
3. **Quotation** — formal commercial offer.
4. **Sales Order** — confirmed sale for 20 monitors and 20 keyboards.
5. **Purchase Order** — procurement of 12 missing monitors.
6. **Receipt** — vendor delivery increases stock to 20 monitors.
7. **Delivery** — warehouse ships all goods to ABC Trading.
8. **Invoice** — Finance bills 24,000 QAR.
9. **Payment** — customer settles the invoice.
10. **Helpdesk Ticket** — support handles damaged keyboards with full business context.

This demonstrates the core goal of Unit I:

**Understand the Business Before the Code**

Before writing Odoo Python, a developer should be able to explain which business records exist, which application owns each stage, and how one customer journey crosses application boundaries.
