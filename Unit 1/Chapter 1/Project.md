# Chapter 1 Project: Map a Small Company Before Building It in Odoo

## Project Goal

Create an ERP business analysis for a fictional company called **Bilal Office Supplies**.

The company sells:

- laptops,
- monitors,
- keyboards,
- office chairs.

It purchases these products from suppliers and sells them to business customers.

This is **business modeling**, not Odoo configuration yet. Do not build records in Odoo until you have mapped the business first.

For supplementary ERP videos and process-mapping tools, see [Resources.md](Resources.md).

---

## Table of Contents

- [Part 1: Define the Departments](#part-1-define-the-departments)
- [Part 2: Define Master Data](#part-2-define-master-data)
- [Part 3: Map Order-to-Cash](#part-3-map-order-to-cash)
- [Part 4: Add an Inventory Shortage](#part-4-add-an-inventory-shortage)
- [Part 5: Identify the Source of Truth](#part-5-identify-the-source-of-truth)
- [Part 6: As-Is vs To-Be](#part-6-as-is-vs-to-be)
- [Complete Solution](#chapter-1-project-complete-solution)

---

## Part 1: Define the Departments

Document responsibilities for:

- Sales
- Purchasing
- Warehouse
- Finance
- HR
- Operations

For each department, describe its purpose, key responsibilities, and likely process owner.

---

## Part 2: Define Master Data

Create sample master records for:

- 3 customers,
- 2 vendors,
- 4 products,
- 3 employees,
- basic financial accounts.

Do not build them in Odoo yet. This is business modeling.

---

## Part 3: Map Order-to-Cash

Create the flow from customer request through payment.

<div align="center">

```mermaid
flowchart LR
    CR["Customer Request"] --> Q["Quotation"] --> SO["Sales Order"] --> DEL["Delivery"] --> INV["Invoice"] --> PAY["Payment"]
```

</div>

For every stage identify:

- department,
- input,
- activity,
- output,
- responsible role.

---

## Part 4: Add an Inventory Shortage

Assume:

- **Customer demand:** 50 units
- **Available stock:** 20 units
- **Shortage:** 30 units (50 − 20)

Extend the process to include purchasing and receipt before delivery.

<div align="center">

```mermaid
flowchart LR
    SAL["Sales"] --> IC["Inventory Check"] --> PUR["Purchase"] --> REC["Receipt"] --> DEL["Delivery"] --> INV["Invoice"]
```

</div>

Document how the departments interact.

---

## Part 5: Identify the Source of Truth

For each item, decide where the authoritative information should conceptually live:

- customer address,
- product price,
- stock quantity,
- employee department,
- invoice status.

Then explain why maintaining multiple unrelated copies would cause problems.

---

## Part 6: As-Is vs To-Be

Design a deliberately inefficient manual process. For example:

Sales uses Excel → warehouse receives email → Purchasing uses another spreadsheet → Finance receives paper documents.

Label this **As-Is**.

Then design an integrated process. Label it **To-Be**.

This exercise will make the need for an ERP system very concrete.

---

# Chapter 1 Project: Complete Solution

The solution below shows what a strong Chapter 1 project submission looks like. Use it to check your own work, not to skip the analysis.

---

## Bilal Office Supplies: Company Description

Bilal Office Supplies is a fictional business-to-business company selling laptops, monitors, keyboards, and office chairs.

The company purchases products from suppliers, stores them in inventory, sells them to business customers, delivers customer orders, and receives customer payments.

The company will eventually use an ERP such as Odoo to integrate these activities.

---

## Part 1: Define the Departments

### 1. Sales Department

**Main purpose:** Convert customer demand into confirmed orders and revenue.

**Responsibilities:**

- maintain customer relationships,
- receive customer inquiries,
- prepare quotations,
- negotiate prices where permitted,
- confirm Sales Orders,
- communicate delivery expectations,
- monitor customer orders.

**Example:** A customer asks for **10 laptops**. Sales checks pricing and availability and creates a quotation. If the customer accepts, the quotation becomes a Sales Order.

**Process owner:** Sales Manager

---

### 2. Purchasing Department

**Main purpose:** Obtain products and services required by the company.

**Responsibilities:**

- identify purchasing requirements,
- select suppliers,
- request supplier quotations,
- compare prices,
- create Purchase Orders,
- communicate with suppliers,
- track expected deliveries.

**Example:** Customer demand is **50 monitors**, stock is **20**, shortage is **30**. Purchasing must obtain approximately 30 additional monitors if the company wants to fulfill the sale.

**Process owner:** Purchasing Manager

---

### 3. Warehouse Department

**Main purpose:** Control physical product movement and storage.

**Responsibilities:**

- receive supplier deliveries,
- inspect received goods,
- store products,
- maintain stock records,
- pick products for customer orders,
- pack goods,
- deliver or prepare shipments,
- perform inventory counts.

**Example:** A supplier delivers 30 monitors. Warehouse receives them and updates available stock.

**Process owner:** Warehouse Manager

---

### 4. Finance Department

**Main purpose:** Manage financial records and monetary consequences of business activities.

**Responsibilities:**

- create customer invoices,
- record vendor bills,
- track customer payments,
- track supplier payments,
- manage receivables and payables,
- record accounting transactions,
- prepare financial reports.

**Example:** A customer receives **10 laptops** at **3,000 QAR each**. Invoice amount: **30,000 QAR**. Finance records the customer invoice.

**Process owner:** Finance Manager

---

### 5. HR Department

**Main purpose:** Manage employees and employee-related processes.

**Responsibilities:**

- maintain employee information,
- manage recruitment,
- manage leave,
- maintain organizational structure,
- coordinate employee records,
- support policies and HR procedures.

**Example:** A warehouse employee requests annual leave. HR manages the overall policy while the employee's manager may approve the request.

**Process owner:** HR Manager

---

### 6. Operations Department

**Main purpose:** Ensure the company's day-to-day business activities operate effectively.

**Responsibilities:**

- coordinate operational workflows,
- monitor order fulfillment,
- identify bottlenecks,
- improve processes,
- coordinate departments when required,
- monitor service quality.

For Bilal Office Supplies, Operations may monitor whether Order → Purchase → Receipt → Delivery happens efficiently.

**Process owner:** Operations Manager

---

## Part 2: Define Master Data

### A. Customers

**Customer 1: Doha Business Solutions**

| Field | Value |
| --- | --- |
| Customer Name | Doha Business Solutions |
| City | Doha |
| Country | Qatar |
| Type | Business Customer |
| Payment Terms | 30 Days |
| Currency | QAR |

**Customer 2: Gulf Engineering Services**

| Field | Value |
| --- | --- |
| Customer Name | Gulf Engineering Services |
| City | Al Wakrah |
| Country | Qatar |
| Type | Business Customer |
| Payment Terms | 15 Days |
| Currency | QAR |

**Customer 3: Qatar Modern Offices**

| Field | Value |
| --- | --- |
| Customer Name | Qatar Modern Offices |
| City | Doha |
| Country | Qatar |
| Type | Business Customer |
| Payment Terms | Immediate |
| Currency | QAR |

---

### B. Vendors

**Vendor 1: TechSource Distribution** (supplies laptops, monitors, keyboards)

| Field | Value |
| --- | --- |
| Vendor | TechSource Distribution |
| Supplier Category | Electronics |
| Currency | QAR |
| Payment Terms | 30 Days |

**Vendor 2: Gulf Furniture Trading** (supplies office chairs)

| Field | Value |
| --- | --- |
| Vendor | Gulf Furniture Trading |
| Supplier Category | Office Furniture |
| Currency | QAR |
| Payment Terms | 30 Days |

---

### C. Products

| Product | Selling Price | Cost | Type / Category |
| --- | --- | --- | --- |
| Business Laptop | 3,000 QAR | 2,400 QAR | Stocked / Computers |
| 27-inch Monitor | 1,000 QAR | 750 QAR | Stocked / Displays |
| Wireless Keyboard | 200 QAR | 130 QAR | Stocked / Accessories |
| Ergonomic Office Chair | 700 QAR | 450 QAR | Stocked / Furniture |

---

### D. Employees

| Employee | Role | Department | Manager |
| --- | --- | --- | --- |
| Ahmed Khan | Sales Executive | Sales | Sales Manager |
| Sara Ali | Purchasing Officer | Purchasing | Purchasing Manager |
| Omar Hassan | Warehouse Officer | Warehouse | Warehouse Manager |

---

### E. Basic Financial Accounts

| Account | Type | Purpose |
| --- | --- | --- |
| Cash | Asset | Physical cash |
| Bank | Asset | Company bank balance |
| Accounts Receivable | Asset | Money customers owe |
| Inventory | Asset | Value of stock |
| Accounts Payable | Liability | Money owed to vendors |
| Sales Revenue | Revenue | Income from customer sales |
| Cost of Goods Sold | Expense | Cost associated with sold products |
| Operating Expenses | Expense | General company expenses |

These account records are relatively stable. Individual journal entries against them are transactions.

---

## Part 3: Map Order-to-Cash

<div align="center">

```mermaid
flowchart LR
    CR["Customer Request"] --> Q["Quotation"] --> SO["Sales Order"] --> DEL["Delivery"] --> INV["Invoice"] --> PAY["Payment"]
```

</div>

### Stage 1: Customer Request

| | |
| --- | --- |
| **Department** | Sales |
| **Input** | Customer requirement (e.g., Doha Business Solutions needs 10 laptops) |
| **Activity** | Sales employee gathers product, quantity, customer, expected date, pricing requirements |
| **Output** | A sufficiently defined customer requirement that can become a quotation |
| **Responsible role** | Sales Executive |

### Stage 2: Quotation

| | |
| --- | --- |
| **Department** | Sales |
| **Input** | Customer request |
| **Activity** | Create quotation containing customer, product, quantity, price, terms (e.g., 10 × 3,000 = 30,000 QAR) |
| **Output** | Customer quotation |
| **Responsible role** | Sales Executive |

### Stage 3: Sales Order

| | |
| --- | --- |
| **Department** | Sales |
| **Input** | Accepted quotation |
| **Activity** | Customer confirms; company converts commercial proposal into confirmed order |
| **Output** | Sales Order |
| **Responsible role** | Sales Executive / Sales Manager |

### Stage 4: Delivery

| | |
| --- | --- |
| **Department** | Warehouse |
| **Input** | Confirmed Sales Order |
| **Activity** | Check stock, reserve products, pick items, pack, send to customer |
| **Output** | Completed delivery |
| **Responsible role** | Warehouse Officer / Warehouse Manager |

### Stage 5: Invoice

| | |
| --- | --- |
| **Department** | Finance |
| **Input** | Confirmed sale and relevant delivery information |
| **Activity** | Create customer invoice (e.g., 10 laptops × 3,000 = 30,000 QAR) |
| **Output** | Customer invoice |
| **Responsible role** | Accountant |

### Stage 6: Payment

| | |
| --- | --- |
| **Department** | Finance |
| **Input** | Customer payment |
| **Activity** | Record payment, match with invoice, update outstanding receivable |
| **Output** | Paid or partially paid invoice |
| **Responsible role** | Accountant / Finance Officer |

### Order-to-Cash summary

| Stage | Department | Input | Activity | Output | Responsible role |
| --- | --- | --- | --- | --- | --- |
| Customer Request | Sales | Customer need | Capture requirement | Defined request | Sales Executive |
| Quotation | Sales | Request | Prepare commercial offer | Quotation | Sales Executive |
| Sales Order | Sales | Accepted quote | Confirm sale | Sales Order | Sales Executive |
| Delivery | Warehouse | Sales Order | Pick, pack, deliver | Completed delivery | Warehouse Officer |
| Invoice | Finance | Sale / Delivery | Bill customer | Invoice | Accountant |
| Payment | Finance | Customer funds | Record / reconcile payment | Paid invoice | Accountant |

---

## Part 4: Inventory Shortage

**Given:** Customer demand = **50**, Available stock = **20**, Shortage = **30** (50 − 20).

<div align="center">

```mermaid
flowchart LR
    SAL["Sales"] --> IC["Inventory Check"] --> PUR["Purchase"] --> REC["Receipt"] --> DEL["Delivery"] --> INV["Invoice"]
```

</div>

Suppose the product is **27-inch Monitor**.

### Step 1: Sales

Customer requests **50 monitors**. Sales creates and confirms the order. Sales demand becomes an inventory requirement.

### Step 2: Inventory check

Warehouse sees **20 available** but **50 required**. **30 missing**. The shortage must be communicated to Purchasing.

### Step 3: Purchasing

Purchasing receives the requirement for **30 monitors** and creates a Purchase Order with **TechSource Distribution**. Output: **PO for 30 Monitors**.

### Step 4: Supplier receipt

TechSource Distribution sends the 30 monitors. Warehouse receives them. Stock becomes **50** (20 + 30). Now the complete customer order can be fulfilled.

### Step 5: Delivery

Warehouse reserves **50 monitors** for the customer, picks, packs, and delivers them. Stock movement is recorded.

### Step 6: Invoice

Selling price: **1,000 QAR per monitor**. Invoice total: **50,000 QAR** (50 × 1,000). Finance creates the customer invoice.

### How the departments interact

- **Sales** tells **Warehouse:** the customer requires 50 units.
- **Warehouse** tells **Purchasing:** we only have 20; we need 30 more.
- **Purchasing** tells **Vendor:** supply 30 units.
- **Vendor** supplies **Warehouse**.
- **Warehouse** tells the process: 50 units are now available and can be delivered.
- **Delivery** information supports **Finance:** the customer order has been fulfilled; invoice according to business rules.

That is a cross-department ERP workflow.

---

## Part 5: Identify the Source of Truth

### 1. Customer address

**Authoritative location:** Customer master record.

Sales, Warehouse, and Finance should reference the same customer address rather than keeping unrelated copies. If each department stores a different street, the company may deliver to the wrong address, invoice incorrectly, and maintain inconsistent customer data.

### 2. Product price

**Authoritative location:** Product / pricing master data.

There must be an authoritative pricing rule rather than independent departmental spreadsheets. Otherwise Sales could quote **900 QAR** while Finance invoices **1,000 QAR**, creating disputes.

### 3. Stock quantity

**Authoritative location:** Inventory / Warehouse system records.

Inventory quantities should come from recorded stock movements and warehouse data. Sales should not maintain an unrelated Excel sheet saying **50 available** while Warehouse knows actual stock is **20**.

### 4. Employee department

**Authoritative location:** Employee / HR master record.

Example: **Ahmed Khan → Sales Department**. Other applications should refer to that organizational information where appropriate.

### 5. Invoice status

**Authoritative location:** Accounting / Finance transaction record.

The invoice itself should represent its status: Draft, Posted, Partially Paid, Paid. Sales should not maintain an unrelated spreadsheet manually saying an invoice is paid.

### Why multiple unrelated copies are dangerous

Suppose the same information exists in four systems. A change must then be made four times. If someone forgets one system, the organization has multiple conflicting versions of "truth."

This causes:

- data inconsistency,
- customer disputes,
- reporting problems,
- incorrect decisions,
- duplicate work,
- operational delays.

---

## Part 6: As-Is vs To-Be

### As-Is: Inefficient manual process

Bilal Office Supplies currently operates without an integrated ERP.

| Step | What happens |
| --- | --- |
| **1. Customer order** | Customer emails Sales. Sales records the order in **Sales.xlsx** |
| **2. Inventory check** | Sales emails Warehouse. Warehouse opens **Stock.xlsx**, sees only 20 available, replies by email |
| **3. Purchasing** | Sales or Warehouse emails Purchasing. Purchasing opens **Purchases.xlsx** and manually creates information for 30 missing monitors. PO may be created separately in Word or PDF |
| **4. Vendor receipt** | Vendor delivers goods. Warehouse manually changes Stock.xlsx from 20 to 50. Sales.xlsx does not know this happened. Warehouse sends another email |
| **5. Delivery** | Warehouse ships 50 monitors. Delivery details may be written on paper |
| **6. Finance** | Sales sends order information to Finance. Warehouse separately sends delivery proof. Finance manually enters information into accounting software |

**Problems with the As-Is process:**

- **Duplicate entry:** same customer and product information entered repeatedly
- **No real-time visibility:** Sales may not know current stock without contacting Warehouse
- **Data inconsistency:** Sales.xlsx may say 50 available while Stock.xlsx says 20
- **Slow communication:** email, calls, spreadsheets, paper
- **Weak audit trail:** difficult to reconstruct who changed what
- **Higher error risk:** forgotten emails, old spreadsheets, wrong quantities, wrong invoice amounts

---

### To-Be: Integrated ERP process

Now imagine Bilal Office Supplies operates through an integrated ERP.

| Step | What happens |
| --- | --- |
| **1. Sales Order** | Sales creates one customer order referencing master data: Customer, Product, Quantity, Price |
| **2. Inventory visibility** | ERP shows demand 50, available 20, shortage 30 |
| **3. Purchasing** | Purchasing creates a PO for 30 units referencing the same product master data |
| **4. Supplier receipt** | Warehouse receives 30 monitors; inventory records stock increase (20 + 30 = 50) |
| **5. Customer delivery** | Delivery references the Sales Order; Warehouse delivers all 50 units |
| **6. Finance** | Finance generates the customer invoice from connected business records |

<div align="center">

```mermaid
flowchart LR
    C["Customer"] --> SAL["Sales"] --> INV["Inventory"] --> PUR["Purchase"] --> REC["Receipt"] --> DEL["Delivery"] --> FIN["Finance"]
```

</div>

All activities operate around connected records.

### As-Is vs To-Be comparison

| As-Is | To-Be |
| --- | --- |
| Separate spreadsheets | Integrated system |
| Repeated data entry | Shared master data |
| Manual emails | Connected workflows |
| Delayed stock visibility | Shared inventory information |
| Duplicate customer records | Authoritative customer record |
| Manual reconciliation | Related business transactions |
| Difficult traceability | Better transaction history |
| Higher inconsistency risk | Stronger data consistency |

---

## Final Chapter 1 Project Conclusion

Bilal Office Supplies demonstrates the basic reason ERP systems exist.

The business contains separate departments (Sales, Purchase, Warehouse, Finance, HR, Operations), but those departments do not exist in isolation. They participate in shared processes.

The business uses reusable **master data** (customers, vendors, products, employees, accounts) and generates **transactions** (Sales Orders, Purchase Orders, receipts, deliveries, invoices, payments).

An integrated ERP attempts to connect these into coherent workflows and provide authoritative business information.

The most important lesson from the project is therefore:

**ERP is not mainly about screens or software modules.** It is about representing and coordinating **Business Data + Business Processes + Business Rules** across the organization.

With the exercise and project solution completed, Chapter 1 can now be considered complete from both the theory and practical-analysis side.
