# CHAPTER 2 EXERCISE

> **Added study method:** Answer before scrolling to the solution. For each response, give the concept, scenario evidence, and a reason. Self-score each original numbered question or named part: 0 = missing/incorrect, 1 = correct label without reasoning, 2 = correct explanation using evidence. Rework every answer below 2. The solution is one defensible model, not wording to memorize; clearly stated alternative assumptions can support a different answer.

Try answering these without looking back at Content.md first. Answer in your own words, then compare with the complete solution at the bottom of this file.

These solutions apply Chapter 2 concepts from the Odoo roadmap rather than simply repeating the lesson.

For Odoo docs, hosting comparisons, GitHub repos, and practice environments, see [Resources.md](Resources.md).

---

## TABLE OF CONTENTS

- [Part A: Understanding](#part-a-understanding)
- [Practical Classification Exercise](#practical-classification-exercise)
- [Complete Solution](#chapter-2-exercise-complete-solution)
  - [Part A Solutions](#part-a-understanding-1)
  - [Classification Solutions](#practical-classification-exercise-solutions)

---

## PART A: UNDERSTANDING

> **Added response guidance:** In the hosting comparison, use two scenarios: standard workflows with no technical operator, and a custom Python integration requiring maintenance. For users and companies, give one allowed action and one forbidden action. For Studio versus code, state the missing requirement detail that could change your choice. Distinguish release number from edition and hosting.

1. Explain Odoo in your own words without using only the phrase "ERP software."

2. Why is Odoo considered both an ERP system and a development framework?

3. What does the term **Odoo ecosystem** include?

4. Explain the conceptual relationship:

   **Community → Enterprise**

5. Why doesn't "open source" mean there is no operational cost?

6. What is the difference between **edition** and **hosting**?

7. Compare **Odoo Online**, **Odoo.sh**, and **self-hosted Odoo**.

8. Why is Odoo Online normally inappropriate for arbitrary custom Python modules?

9. Explain the difference between **app**, **module**, and **addon**.

10. Explain why **Apps ⊆ Modules** is a useful mental model.

11. Explain why an **employee** and an **Odoo user** are not necessarily the same concept.

12. Why would an organization use multiple companies in one Odoo database?

13. Give two examples of potentially shared records and two examples of normally company-specific transactional records.

14. Explain when **Studio** may be preferable to custom development.

15. Explain when **custom development** may be preferable to Studio.

---

## PRACTICAL CLASSIFICATION EXERCISE

> **Added success criteria:** For A–E, provide your first option, one reason, and one condition that would change it. “Custom module” without explaining the reliability or maintenance requirement is incomplete. A missing Studio subscription, an existing standard field, or a proven connector can change the investigation path. No code or live installation is required.

Classify each request as the first solution you would investigate:

- Standard functionality
- Configuration
- Studio
- Custom module

The exact answer sometimes depends on details. That itself is an ERP lesson: you investigate the requirement before choosing the implementation.

**A.** "Add an additional text field to Customer."

**B.** "Automatically synchronize Odoo orders with a proprietary external API using signed HTTP requests."

**C.** "Enable standard Purchase functionality."

**D.** "Change a standard business setting already available in Settings."

**E.** "Create a complicated custom pricing algorithm involving multiple external systems."

---

# CHAPTER 2 EXERCISE: COMPLETE SOLUTION

Work through the questions above first. The solutions below explain the reasoning Chapter 2 expects you to demonstrate.

---

## PART A: UNDERSTANDING

### 1. WHAT IS ODOO?

Odoo is an integrated business application platform used to manage different parts of an organization through connected applications and shared business data.

Instead of having completely separate software for Sales, Inventory, Purchasing, Accounting, HR, and other departments, Odoo allows these areas to work inside the same overall system.

For example:

<div align="center">

```mermaid
flowchart LR
    SO["Sales Order"] --> DEL["Inventory Delivery"] --> INV["Customer Invoice"] --> PAY["Payment"]
```

</div>

The important point is that these are not unrelated applications. The records can participate in the same business workflow.

For developers, Odoo is also a framework on which new business functionality can be built.

So a strong definition is:

**Odoo = Integrated Business Applications + Shared Business Data + ERP Workflows + Development Framework**

---

### 2. WHY IS ODOO BOTH AN ERP SYSTEM AND A DEVELOPMENT FRAMEWORK?

It is an ERP system because it manages and connects business functions such as Sales, Purchase, Inventory, Accounting, HR, Manufacturing, and Projects.

It is a development framework because developers can extend that system.

For example, Odoo already provides Sales functionality. A developer might add:

- an approval workflow,
- an additional field,
- a new business rule,
- a custom report,
- an external API integration.

Therefore:

- **Odoo ERP** = ready business functionality
- **Odoo Framework** = tools for building and extending functionality

The same platform provides both.

---

### 3. WHAT DOES THE ODOO ECOSYSTEM INCLUDE?

The Odoo ecosystem is everything surrounding and supporting the Odoo platform.

It includes:

- Odoo SA
- Community Edition
- Enterprise Edition
- official Odoo applications
- third-party modules
- Odoo developers
- implementation partners
- consultants
- community contributors
- hosting platforms
- Odoo Apps marketplace
- customers and businesses using Odoo

A useful model is:

**Odoo Ecosystem = Software + Developers + Partners + Community + Hosting + Extensions + Businesses**

---

### 4. COMMUNITY → ENTERPRISE RELATIONSHIP

The correct mental model is not that Community and Enterprise are completely unrelated products.

Instead:

**Enterprise = Community Foundation + Additional Enterprise Functionality**

Community provides the open-source foundation of Odoo.

Enterprise builds upon that foundation and adds commercially licensed functionality and services.

Therefore the arrow **Community → Enterprise** means that Enterprise grows from the Community foundation rather than being an entirely unrelated ERP product.

---

### 5. WHY DOESN'T OPEN SOURCE MEAN ZERO OPERATIONAL COST?

Open-source software can be free to obtain while still costing money to operate.

Suppose a company self-hosts Odoo Community. It may still need:

- servers,
- cloud resources,
- backups,
- system administrators,
- developers,
- security maintenance,
- monitoring,
- database administration,
- upgrades,
- disaster recovery.

Therefore **License Cost = 0** does not imply **Total Cost = 0**.

A better equation is:

**Total Cost = Infrastructure + People + Maintenance + Development + Operations**

---

### 6. EDITION VS HOSTING

These answer different questions.

**Enhanced:** **Edition** answers which software/license family is used (Community or Enterprise). **Release** answers which numbered generation, such as 19.0. These are separate from the hosting choice.

Examples: Community, Enterprise.

**Hosting** answers: where and how is Odoo running?

Examples: Odoo Online, Odoo.sh, self-hosted.

Therefore **Edition ≠ Hosting**.

You should never treat "Enterprise" and "Odoo.sh" as equivalent concepts. One concerns software and licensing. The other concerns deployment.

---

### 7. ODOO ONLINE VS ODOO.SH VS SELF-HOSTED

> **Added worked reasoning:** A firm needing supported standard settings and no custom addon can evaluate Online. A firm requiring a Python addon with managed infrastructure can evaluate Odoo.sh. A firm with a capable operations team and infrastructure constraints can evaluate self-hosting. These are conditional fits, not a universal ranking of quality. Confirm the [Online restriction](https://www.odoo.com/documentation/19.0/administration/odoo_online.html) and [Odoo.sh service terms](https://www.odoo.sh/faq) when defending the decision.

| Area | Odoo Online | Odoo.sh | Self-Hosted |
| --- | --- | --- | --- |
| Infrastructure management | Mostly Odoo | Mostly managed by Odoo platform | Your responsibility |
| Ease of operation | Highest | High | Lowest |
| Custom Python modules | Generally not supported | Yes | Yes |
| Development control | Limited | High | Highest |
| Server control | Very limited | Moderate | Full |
| Best suited for | Standard or simple deployments | Custom Odoo projects | Maximum control or custom infrastructure |
| Operations burden | Low | Medium | High |

**Odoo Online** is best when the organization mainly needs standard Odoo and does not require arbitrary server-side custom modules.

**Odoo.sh** is best when the organization wants custom development but does not want to manage every infrastructure component itself.

**Self-hosted** is best when maximum infrastructure and software control are required and the organization can operate the environment properly.

---

### 8. WHY IS ODOO ONLINE INAPPROPRIATE FOR ARBITRARY CUSTOM PYTHON MODULES?

Because Odoo Online is a managed SaaS environment.

Users do not receive the same level of filesystem or server control they would have on Odoo.sh or a self-hosted installation.

A custom Python addon may require:

- source code deployment,
- Python libraries,
- server configuration,
- filesystem access,
- custom runtime behavior.

Those requirements conflict with the highly managed nature of Odoo Online.

Therefore, if you require significant Python development, the likely candidates become **Odoo.sh or Self-Hosted**.

---

### 9. APP VS MODULE VS ADDON

**App**

An app represents a major user-facing business capability.

Examples: Sales, Purchase, Inventory.

**Module**

A module is a technical package of Odoo functionality.

A module may contain models, fields, views, security, reports, data, and Python logic.

**Addon**

Addon is commonly used as another term for an installable Odoo module, especially when discussing extensions.

For example, "We created a custom addon" normally means "We created a custom Odoo module."

---

### 10. WHY IS APPS ⊆ MODULES USEFUL?

Because an Odoo app is implemented as a module, but many modules are not major standalone applications.

For example, a technical integration module may extend Sales without appearing as its own major app in the app launcher.

Therefore:

- **Every app is a module**
- **Not every module is a major app**

---

### 11. EMPLOYEE VS ODOO USER

An employee represents someone from the business or HR perspective.

A user represents someone from the system-access perspective.

Example: Ahmed works for the company, so **Ahmed = Employee**.

If Ahmed must log into Odoo: **Ahmed = Employee + User**.

But another employee might never use Odoo directly. Then **Employee ≠ User**.

Also, some users may not be employees. For example, portal users might be customers.

---

### 12. WHY USE MULTIPLE COMPANIES IN ONE DATABASE?

Suppose Bilal Office Supplies expands to Qatar, Pakistan, and UAE.

Management may want one overall Odoo environment while maintaining separate legal entities.

Multi-company support can allow:

- selected shared master data,
- centralized management,
- users working across multiple companies,
- separate company transactions,
- separate accounting contexts.

Conceptually, **one Odoo database** can contain multiple companies while still separating company-specific operations.

---

### 13. SHARED VS COMPANY-SPECIFIC RECORDS

> **Added reasoning check:** Sharing a product identity does not pool the Qatar and Pakistan companies’ stock. Likewise, a user allowed into both companies must still create each invoice in the correct company. To test your explanation, name a shared fact, such as product reference, and a company-context fact, such as the stock held by that company.

**Potentially shared**

- **Customer / Contact:** ABC Trading could do business with both Qatar and Pakistan companies.
- **Product:** "Logitech MX Keys" might be used by both companies.

**Normally company-specific transactional records**

- **Sales Order:** should belong to the company actually selling the product.
- **Invoice:** belongs to a specific legal or accounting entity.

Other examples include vendor bills, Purchase Orders, and journal entries.

A useful distinction is **Shared Master Data** versus **Company-Specific Transactions**.

---

### 14. WHEN IS STUDIO PREFERABLE?

Studio is attractive when the customization is:

- small,
- visual,
- straightforward,
- mostly configuration-oriented,
- achievable without complicated Python logic.

Examples: adding a field, rearranging a form, adding a simple approval, modifying a view, simple automation.

For such requirements, **Studio convenience > custom development cost**.

---

### 15. WHEN IS CUSTOM DEVELOPMENT PREFERABLE?

Custom modules become more suitable when requirements involve:

- complicated business logic,
- APIs,
- advanced validation,
- reusable technical architecture,
- scheduled jobs,
- complex workflows,
- large integrations,
- advanced reporting,
- maintainability requirements.

Example: send each delivery to an external logistics API, retry failures, maintain synchronization state, and provide audit logs.

That is clearly becoming an engineering problem rather than a simple visual customization.

---

## PRACTICAL CLASSIFICATION EXERCISE: SOLUTIONS

### A. ADD AN ADDITIONAL TEXT FIELD TO CUSTOMER

> **Added alternative:** If the required information fits an existing standard field, use it instead of creating a duplicate. If Studio is unavailable, a small custom extension can be reasonable. Full credit depends on this reasoning, not on always selecting Studio.

**First investigate: Studio**

Assuming standard Odoo does not already provide the required field, this is a simple model and view customization and does not justify complex Python development.

### B. SYNCHRONIZE ORDERS WITH PROPRIETARY API USING SIGNED HTTP REQUESTS

> **Added alternative:** First check for a supported connector that demonstrably meets the signing, retry, and duplicate-prevention requirements. External middleware can also own the integration when supported interfaces allow it. A custom Odoo addon is one implementation location, not the definition of integration itself.

**First investigate: Custom Module**

Because this likely requires HTTP requests, authentication, signatures, error handling, logging, retry logic, and synchronization status. That is software integration work.

### C. ENABLE STANDARD PURCHASE FUNCTIONALITY

**Answer: Standard Functionality**

Install or enable the existing Purchase application. There is no reason to build something Odoo already provides.

### D. CHANGE A BUSINESS SETTING ALREADY AVAILABLE IN SETTINGS

**Answer: Configuration**

If the system already provides the setting, configure it. Do not customize the platform unnecessarily.

### E. COMPLICATED CUSTOM PRICING ALGORITHM USING MULTIPLE EXTERNAL SYSTEMS

> **Added reasoning:** Ask whether the systems supply periodic prices that standard pricelists can consume, or whether each quotation requires live calculations. A cached price import and a live pricing call have different failure behavior. The latter needs a decision about what the salesperson sees if an external service is unavailable.

**Answer: Custom Module**

Because the requirement includes complex logic and external integration.

### THE PROFESSIONAL DECISION SEQUENCE

The broader lesson is:

<div align="center">

```mermaid
flowchart LR
    STD["Standard"] --> CFG["Configuration"] --> STU["Studio"] --> DEV["Custom Development"]
```

</div>

Move further right only when necessary.
