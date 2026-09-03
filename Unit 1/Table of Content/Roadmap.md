# ODOO DEVELOPMENT & ENGINEERING
> Zero Knowledge → ERP Understanding → Odoo Development
> → Full-Stack Odoo → Production Engineering → Odoo Engineer

## UNIT I: UNDERSTAND THE BUSINESS BEFORE THE CODE

### CHAPTER 1: What Is ERP?
- 1.1 Business Processes
  - 1.1.1 What Is a Business Process?
  - 1.1.2 Process Inputs
  - 1.1.3 Process Activities
  - 1.1.4 Process Outputs
  - 1.1.5 Process Owners

- 1.2 Departments
  - 1.2.1 Sales
  - 1.2.2 Purchasing
  - 1.2.3 Warehouse
  - 1.2.4 Finance
  - 1.2.5 HR
  - 1.2.6 Operations

- 1.3 Cross-Department Workflows
- 1.4 Master Data
  - 1.4.1 Customers
  - 1.4.2 Vendors
  - 1.4.3 Products
  - 1.4.4 Employees
  - 1.4.5 Accounts

- 1.5 Transactions
- 1.6 Single Source of Truth
- 1.7 ERP vs CRM
- 1.8 ERP vs Standalone Business Software
- 1.9 Business Process Mapping

### CHAPTER 2: Understanding Odoo
- 2.1 What Odoo Is
- 2.2 Odoo Ecosystem
- 2.3 Community Edition
- 2.4 Enterprise Edition
- 2.5 Odoo Online
- 2.6 Odoo.sh
- 2.7 On-Premise Odoo
- 2.8 Odoo Apps
- 2.9 Modules / Addons
- 2.10 Users
- 2.11 Companies
- 2.12 Shared Business Records
- 2.13 Standard vs Custom Modules
- 2.14 Odoo Studio Concept

### CHAPTER 3: Core Business Applications
- 3.1 Contacts
- 3.2 CRM
- 3.3 Sales
- 3.4 Purchase
- 3.5 Inventory
- 3.6 Accounting / Invoicing
- 3.7 Employees / HR
- 3.8 Projects
- 3.9 Timesheets
- 3.10 Manufacturing
- 3.11 Maintenance
- 3.12 Website
- 3.13 eCommerce
- 3.14 Point of Sale
- 3.15 Helpdesk
- 3.16 End-to-End Document Flow

## UNIT II: HOW ODOO ACTUALLY WORKS

### CHAPTER 4: Odoo Architecture
- 4.1 Three-Tier Architecture
- 4.2 Browser
- 4.3 Odoo Web Client
- 4.4 HTTP Request
- 4.5 Odoo Application Server
- 4.6 Python Runtime
- 4.7 ORM
- 4.8 PostgreSQL
- 4.9 Filestore
- 4.10 Addons
- 4.11 Registry
- 4.12 HTTP Layer
- 4.13 Sessions
- 4.14 Workers
- 4.15 Cron Workers
- 4.16 Long-Polling / WebSocket Concepts

### CHAPTER 5: Development Environment
- 5.1 Python Environment
- 5.2 Python Virtual Environments
- 5.3 Python Dependencies
- 5.4 PostgreSQL Setup
- 5.5 PostgreSQL User
- 5.6 Odoo Source
- 5.7 Git Clone
- 5.8 Odoo Configuration File
- 5.9 addons_path
- 5.10 Custom Addons Directory
- 5.11 Database Creation
- 5.12 Developer Mode
- 5.13 Developer Mode with Assets
- 5.14 Logging
- 5.15 IDE Setup
- 5.16 Debugger Setup

### CHAPTER 6: Odoo Source Code Structure
- 6.1 odoo/
- 6.2 addons/
- 6.3 Core Framework
- 6.4 api.py Concepts
- 6.5 fields.py Concepts
- 6.6 models.py Concepts
- 6.7 HTTP
- 6.8 Services
- 6.9 Tools
- 6.10 Registry
- 6.11 Modules Loader
- 6.12 Reading Official Addons
- 6.13 Tracing Model Definitions
- 6.14 Tracing XML IDs
- 6.15 Tracing Methods

## UNIT III: YOUR FIRST ODOO MODULE

### CHAPTER 7: Module Anatomy
- 7.1 Addon Directory
- 7.2 __manifest__.py
- 7.3 __init__.py
- 7.4 models/
- 7.5 views/
- 7.6 security/
- 7.7 data/
- 7.8 demo/
- 7.9 static/
- 7.10 controllers/
- 7.11 wizard/
- 7.12 report/
- 7.13 i18n/
- 7.14 tests/
- 7.15 README
- 7.16 Coding Conventions

### CHAPTER 8: Module Lifecycle
- 8.1 Module Discovery
- 8.2 Manifest Metadata
- 8.3 Dependencies
- 8.4 Installation
- 8.5 Initialization
- 8.6 Registry Loading
- 8.7 Upgrade
- 8.8 Uninstall
- 8.9 Data Load Order
- 8.10 application Flag
- 8.11 installable Flag
- 8.12 auto_install
- 8.13 External Dependencies
- 8.14 Module Version

## UNIT IV: MODELING BUSINESS DATA

### CHAPTER 9: Models
- 9.1 models.Model
- 9.2 models.AbstractModel
- 9.3 models.TransientModel
- 9.4 _name
- 9.5 _description
- 9.6 _rec_name
- 9.7 _order
- 9.8 _inherit
- 9.9 _inherits Introduction
- 9.10 Automatic Fields
- 9.11 id
- 9.12 create_date
- 9.13 create_uid
- 9.14 write_date
- 9.15 write_uid
- 9.16 Reserved Field Names

### CHAPTER 10: Fields
- 10.1 Char
- 10.2 Text
- 10.3 Html
- 10.4 Integer
- 10.5 Float
- 10.6 Boolean
- 10.7 Date
- 10.8 Datetime
- 10.9 Selection
- 10.10 Monetary
- 10.11 Binary
- 10.12 Image
- 10.13 Many2one Introduction
- 10.14 Field string
- 10.15 required
- 10.16 readonly
- 10.17 default
- 10.18 help
- 10.19 index
- 10.20 copy
- 10.21 groups
- 10.22 tracking
- 10.23 translate
- 10.24 company_dependent

### CHAPTER 11: Relationships
- 11.1 Many2one
- 11.2 One2many
- 11.3 Many2many
- 11.4 Inverse Fields
- 11.5 Related Fields
- 11.6 Relational Commands
- 11.7 Command.create()
- 11.8 Command.update()
- 11.9 Command.delete()
- 11.10 Command.unlink()
- 11.11 Command.link()
- 11.12 Command.clear()
- 11.13 Command.set()
- 11.14 Relationship Ownership
- 11.15 Cascading Behavior
- 11.16 ondelete
- 11.17 Referential Integrity

### CHAPTER 12: Computed & Dynamic Fields
- 12.1 compute
- 12.2 @api.depends
- 12.3 @api.depends_context
- 12.4 Stored Computed Fields
- 12.5 Non-Stored Computed Fields
- 12.6 inverse
- 12.7 Custom Search Methods
- 12.8 Related Fields
- 12.9 Default Values
- 12.10 default_get()
- 12.11 copy()
- 12.12 Compute Dependencies
- 12.13 Recompute Behavior
- 12.14 Performance of Stored vs Non-Stored Fields

## UNIT V: MASTERING THE ODOO ORM

### CHAPTER 13: Environment & Recordsets
- 13.1 env
- 13.2 self
- 13.3 Recordsets
- 13.4 Empty Recordsets
- 13.5 Singleton Records
- 13.6 Multiple Records
- 13.7 env.user
- 13.8 env.company
- 13.9 env.companies
- 13.10 env.context
- 13.11 Context
- 13.12 with_context()
- 13.13 with_user()
- 13.14 with_company()
- 13.15 sudo()
- 13.16 with_env()
- 13.17 Recordset Immutability

### CHAPTER 14: CRUD
- 14.1 create()
  - 14.1.1 Single Record Creation
  - 14.1.2 Multiple Record Creation
  - 14.1.3 @api.model_create_multi
- 14.2 browse()
- 14.3 search()
- 14.4 search_fetch()
- 14.5 fetch()
- 14.6 read()
- 14.7 write()
- 14.8 unlink()
- 14.9 copy()
- 14.10 exists()
- 14.11 Display Name Concepts
- 14.12 CRUD Return Values
- 14.13 CRUD Side Effects
- 14.14 Bulk CRUD

### CHAPTER 15: Domains & Searching
- 15.1 Domain Syntax
- 15.2 Comparison Operators
- 15.3 = / !=
- 15.4 > / >= / < / <=
- 15.5 in / not in
- 15.6 like / not like
- 15.7 ilike / not ilike
- 15.8 =like / =ilike
- 15.9 child_of
- 15.10 parent_of
- 15.11 AND
- 15.12 OR
- 15.13 NOT
- 15.14 search_count()
- 15.15 search_read()
- 15.16 Ordering
- 15.17 Limit
- 15.18 Offset
- 15.19 Dynamic Domains

### CHAPTER 16: Recordset Operations
- 16.1 Iteration
- 16.2 filtered()
- 16.3 filtered_domain()
- 16.4 mapped()
- 16.5 sorted()
- 16.6 ensure_one()
- 16.7 Recordset Membership
- 16.8 Recordset Union
- 16.9 Recordset Intersection
- 16.10 Recordset Difference
- 16.11 Batch Operations
- 16.12 Avoiding Per-Record Queries

### CHAPTER 17: ORM Internals & Performance
- 17.1 Prefetching
- 17.2 Prefetch Sets
- 17.3 ORM Cache
- 17.4 Transactions
- 17.5 Flush
- 17.6 flush_model()
- 17.7 flush_recordset()
- 17.8 Cache Invalidation
- 17.9 invalidate_model()
- 17.10 invalidate_recordset()
- 17.11 modified()
- 17.12 N+1 Queries
- 17.13 Batch Creation
- 17.14 Batch Updates
- 17.15 Aggregation
- 17.16 read_group()
- 17.17 Raw SQL
- 17.18 SQL Wrapper Concepts
- 17.19 ORM vs SQL
- 17.20 Security Implications of SQL
- 17.21 Algorithmic Complexity

## UNIT VI: BUSINESS RULES & WORKFLOWS

### CHAPTER 18: Business Methods
- 18.1 Model Methods
- 18.2 Recordset Methods
- 18.3 @api.model
- 18.4 @api.model_create_multi
- 18.5 create() Override
- 18.6 write() Override
- 18.7 unlink() Override
- 18.8 copy() Override
- 18.9 super()
- 18.10 Return Values
- 18.11 Business Actions
- 18.12 Private Methods
- 18.13 Public Methods
- 18.14 Method Design

### CHAPTER 19: Constraints & Validation
- 19.1 Business Validation
- 19.2 Python Constraints
- 19.3 @api.constrains
- 19.4 SQL Constraints
- 19.5 ValidationError
- 19.6 UserError
- 19.7 AccessError
- 19.8 MissingError
- 19.9 Validation Timing
- 19.10 Constraint Performance
- 19.11 Database vs Application Constraints

### CHAPTER 20: Onchange & UI Logic
- 20.1 @api.onchange
- 20.2 Defaults
- 20.3 default_get()
- 20.4 Context Defaults
- 20.5 Dynamic Forms
- 20.6 Returning Warnings
- 20.7 Onchange Limitations
- 20.8 Onchange vs Compute
- 20.9 Onchange vs Constraint

### CHAPTER 21: States & Workflows
- 21.1 State Fields
- 21.2 Draft
- 21.3 Confirmed
- 21.4 Approved
- 21.5 Done
- 21.6 Cancelled
- 21.7 Legal State Transitions
- 21.8 Workflow Buttons
- 21.9 Workflow Validation
- 21.10 Immutable States
- 21.11 Reopening Records
- 21.12 Auditability

## UNIT VII: BUILDING THE USER INTERFACE

### CHAPTER 22: XML Foundations
- 22.1 XML Syntax
- 22.2 XML Declaration
- 22.3 <odoo>
- 22.4 <data>
- 22.5 <record>
- 22.6 External IDs
- 22.7 ref()
- 22.8 eval
- 22.9 Data Files
- 22.10 XML Loading
- 22.11 noupdate

### CHAPTER 23: Form & List Views
- 23.1 Form Views
- 23.2 List Views
- 23.3 Field Display
- 23.4 Buttons
- 23.5 Groups
- 23.6 Sheets
- 23.7 Notebook
- 23.8 Pages
- 23.9 Widgets
- 23.10 Decorations
- 23.11 Header
- 23.12 Statusbar
- 23.13 Smart Buttons
- 23.14 Invisible / Readonly Logic
- 23.15 Editable Lists

### CHAPTER 24: Search, Kanban & Analytical Views
- 24.1 Search Views
- 24.2 Filters
- 24.3 Group By
- 24.4 Search Panels
- 24.5 Kanban
- 24.6 Kanban Templates
- 24.7 Calendar
- 24.8 Pivot
- 24.9 Graph
- 24.10 Activity Views
- 24.11 Cohort Concepts
- 24.12 Dashboard Concepts

### CHAPTER 25: Actions & Menus
- 25.1 Actions
- 25.2 Action Bindings
- 25.3 Window Actions
- 25.4 ir.actions.act_window
- 25.5 URL Actions
- 25.6 Server Actions
- 25.7 Report Actions
- 25.8 Client Actions
- 25.9 Scheduled Actions
- 25.10 Menus
- 25.11 Parent Menus
- 25.12 Menu Sequence
- 25.13 Context
- 25.14 Domains
- 25.15 Navigation

### CHAPTER 26: View Inheritance
- 26.1 inherit_id
- 26.2 XPath
- 26.3 position
- 26.4 before
- 26.5 after
- 26.6 inside
- 26.7 replace
- 26.8 attributes
- 26.9 Adding Elements
- 26.10 Removing Elements Safely
- 26.11 Moving Elements
- 26.12 View Priority
- 26.13 View Resolution
- 26.14 Debugging Inherited Views
- 26.15 Avoiding Brittle XPath

## UNIT VIII: SECURITY & MULTI-COMPANY

### CHAPTER 27: Users & Groups
- 27.1 Users
- 27.2 Internal Users
- 27.3 Portal Users
- 27.4 Public User
- 27.5 Groups
- 27.6 Group Membership
- 27.7 Implied Groups
- 27.8 Application Categories
- 27.9 Permission Design
- 27.10 Role Design

### CHAPTER 28: Access Control Lists
- 28.1 ACL Concepts
- 28.2 ir.model.access
- 28.3 ir.model.access.csv
- 28.4 Read Permission
- 28.5 Write Permission
- 28.6 Create Permission
- 28.7 Unlink Permission
- 28.8 Group ACLs
- 28.9 Additive Permissions
- 28.10 Default-Deny Thinking

### CHAPTER 29: Record Rules
- 29.1 ir.rule
- 29.2 domain_force
- 29.3 Global Rules
- 29.4 Group Rules
- 29.5 Rule Composition
- 29.6 Row-Level Security
- 29.7 User-Based Rules
- 29.8 Company-Based Rules
- 29.9 Ownership Rules
- 29.10 Multi-Group Interactions

### CHAPTER 30: Security Context & Safe Privilege
- 30.1 sudo()
- 30.2 with_user()
- 30.3 Access Checks
- 30.4 check_access()
- 30.5 Field Security
- 30.6 View / Menu Groups
- 30.7 Public Method Security
- 30.8 Unsafe Raw SQL
- 30.9 Controller Security
- 30.10 Security Bypass Risks
- 30.11 Least Privilege
- 30.12 Avoiding Unnecessary sudo()
- 30.13 Input Validation

### CHAPTER 31: Multi-Company Development
- 31.1 res.company
- 31.2 company_id
- 31.3 company_ids
- 31.4 env.company
- 31.5 env.companies
- 31.6 with_company()
- 31.7 Company-Dependent Fields
- 31.8 _check_company
- 31.9 Multi-Company Domains
- 31.10 Cross-Company Security
- 31.11 Shared Records
- 31.12 Company-Specific Sequences
- 31.13 Multi-Company Defaults

## UNIT IX: EXTENDING EXISTING ODOO

### CHAPTER 32: Model Inheritance
- 32.1 Extension Inheritance
- 32.2 _inherit
- 32.3 Classical Inheritance
- 32.4 Method Overriding
- 32.5 Field Extension
- 32.6 super()
- 32.7 Multiple Inheritance
- 32.8 Method Resolution Order
- 32.9 Extension Conflicts

### CHAPTER 33: Delegation & Mixins
- 33.1 _inherits
- 33.2 Delegated Fields
- 33.3 Delegation vs Extension
- 33.4 AbstractModel
- 33.5 Mixins
- 33.6 Reusable Model Behavior
- 33.7 Composition
- 33.8 mail.thread
- 33.9 mail.activity.mixin
- 33.10 portal.mixin Concepts

### CHAPTER 34: View Inheritance in Real Modules
- 34.1 Finding Parent Views
- 34.2 External IDs
- 34.3 XPath Targeting
- 34.4 Adding Fields
- 34.5 Modifying Attributes
- 34.6 Replacing Elements
- 34.7 Moving Elements
- 34.8 View Priority
- 34.9 Conflicting Inheritances
- 34.10 Debugging Inheritance Conflicts

### CHAPTER 35: Extending Official Applications
- 35.1 res.partner
- 35.2 product.template
- 35.3 product.product
- 35.4 crm.lead
- 35.5 sale.order
- 35.6 sale.order.line
- 35.7 purchase.order
- 35.8 stock.picking
- 35.9 stock.move
- 35.10 account.move
- 35.11 hr.employee
- 35.12 project.project
- 35.13 Existing Workflows
- 35.14 Extension Points
- 35.15 Upgrade-Safe Customization

## UNIT X: ADVANCED BUSINESS FEATURES

### CHAPTER 36: Wizards & TransientModel
- 36.1 TransientModel
- 36.2 Wizard Fields
- 36.3 Wizard Views
- 36.4 target="new"
- 36.5 active_model
- 36.6 active_id
- 36.7 active_ids
- 36.8 Context
- 36.9 Defaults
- 36.10 Multi-Step Wizards
- 36.11 Wizard Security

### CHAPTER 37: Sequences
- 37.1 ir.sequence
- 37.2 next_by_code()
- 37.3 Prefix
- 37.4 Suffix
- 37.5 Padding
- 37.6 Date-Based Sequences
- 37.7 Company-Specific Sequences
- 37.8 Business References
- 37.9 Concurrency Considerations

### CHAPTER 38: Scheduled Actions / Cron
- 38.1 ir.cron
- 38.2 Scheduling
- 38.3 Intervals
- 38.4 Cron Methods
- 38.5 Batch Processing
- 38.6 Progress
- 38.7 Failure Handling
- 38.8 Idempotency
- 38.9 Cron Security
- 38.10 Long-Running Jobs
- 38.11 Transaction Boundaries

### CHAPTER 39: Automation & Server Actions
- 39.1 Automated Actions
- 39.2 Triggers
- 39.3 Conditions
- 39.4 Server Actions
- 39.5 Evaluation Context
- 39.6 Action Chaining
- 39.7 Webhook Automation Concepts
- 39.8 Maintainability
- 39.9 Security
- 39.10 When to Use Code Instead

### CHAPTER 40: Mail, Chatter & Activities
- 40.1 mail.thread
- 40.2 mail.activity.mixin
- 40.3 Messages
- 40.4 Followers
- 40.5 Tracking
- 40.6 Activities
- 40.7 Activity Types
- 40.8 Notifications
- 40.9 Email Templates
- 40.10 Sending Mail
- 40.11 Incoming Mail Concepts
- 40.12 Mail Aliases
- 40.13 Mail Queue
- 40.14 Subtypes

### CHAPTER 41: Reports & QWeb
- 41.1 QWeb
- 41.2 QWeb Templates
- 41.3 t-if
- 41.4 t-foreach
- 41.5 t-field
- 41.6 t-esc / t-out
- 41.7 Report Actions
- 41.8 Report Templates
- 41.9 PDF Reports
- 41.10 HTML Reports
- 41.11 Paper Formats
- 41.12 Custom Report Data
- 41.13 Translatable Reports
- 41.14 Barcodes
- 41.15 Report Attachments

### CHAPTER 42: Data Files, Import & Export
- 42.1 XML Data
- 42.2 CSV Data
- 42.3 External IDs
- 42.4 env.ref()
- 42.5 noupdate
- 42.6 Demo Data
- 42.7 Seed Data
- 42.8 Import
- 42.9 Export
- 42.10 Data Load Order
- 42.11 XML Data Operations
- 42.12 Updating Existing Records
- 42.13 Reference Integrity
- 42.14 Large Imports

## UNIT XI: INTERNATIONALIZATION & LOCALIZATION

### CHAPTER 43: Internationalization & Localization
- 43.1 Translatable Strings
- 43.2 _() Translation Function
- 43.3 Translatable Fields
- 43.4 i18n/
- 43.5 .po Files
- 43.6 .pot Templates
- 43.7 Exporting Translations
- 43.8 Importing Translations
- 43.9 Languages
- 43.10 Locale / Formatting
- 43.11 Dates & Times
- 43.12 Numbers
- 43.13 Currencies
- 43.14 Translatable QWeb
- 43.15 Localization Modules
- 43.16 Accounting Localization Concept
- 43.17 Country-Specific Behavior

## UNIT XII: WEB DEVELOPMENT WITH ODOO

### CHAPTER 44: HTTP Controllers
- 44.1 http.Controller
- 44.2 @http.route
- 44.3 request
- 44.4 Request Environment
- 44.5 route type="http"
- 44.6 route type="json"
- 44.7 HTTP Methods
- 44.8 Parameters
- 44.9 Responses
- 44.10 Authentication
- 44.11 auth="user"
- 44.12 auth="public"
- 44.13 auth="none"
- 44.14 CSRF
- 44.15 Sessions
- 44.16 Cookies Concepts
- 44.17 Error Handling
- 44.18 Controller Inheritance
- 44.19 Controller Security

### CHAPTER 45: Website Development
- 45.1 Website Architecture
- 45.2 Website Pages
- 45.3 QWeb Templates
- 45.4 Dynamic Content
- 45.5 Website Controllers
- 45.6 Frontend Assets
- 45.7 Website Forms
- 45.8 Form Validation
- 45.9 Snippets Concepts
- 45.10 SEO Basics
- 45.11 Routing
- 45.12 Multi-Website
- 45.13 Website-Specific Records

### CHAPTER 46: Portal Development
- 46.1 Portal Users
- 46.2 Portal Controllers
- 46.3 Customer Pages
- 46.4 Portal Layout
- 46.5 Portal Security
- 46.6 Customer-Owned Records
- 46.7 Pagination
- 46.8 Search
- 46.9 Filters
- 46.10 Sort
- 46.11 Access Tokens
- 46.12 Chatter in Portal
- 46.13 Downloads

## UNIT XIII: APIs & INTEGRATIONS

### CHAPTER 47: External API Concepts
- 47.1 Client / Server
- 47.2 Resources
- 47.3 Endpoints
- 47.4 HTTP Methods
- 47.5 JSON
- 47.6 Authentication
- 47.7 Authorization
- 47.8 Status Codes
- 47.9 Headers
- 47.10 Pagination
- 47.11 Rate Limits
- 47.12 API Contracts
- 47.13 Idempotency

### CHAPTER 48: External Odoo Access
- 48.1 External API Architecture
- 48.2 Integration Users
- 48.3 Authentication
- 48.4 Calling Models
- 48.5 CRUD Remotely
- 48.6 Calling Methods
- 48.7 Domains
- 48.8 Permissions
- 48.9 Context
- 48.10 Error Handling
- 48.11 Version Compatibility
- 48.12 API Keys

### CHAPTER 49: Building API Endpoints
- 49.1 API Routes
- 49.2 Request Parsing
- 49.3 Input Validation
- 49.4 Serialization
- 49.5 Response Design
- 49.6 Authentication
- 49.7 Authorization
- 49.8 Pagination
- 49.9 Filtering
- 49.10 Sorting
- 49.11 Error Responses
- 49.12 Consistent Error Schema
- 49.13 API Versioning Concepts
- 49.14 Logging

### CHAPTER 50: Webhooks
- 50.1 Incoming Webhooks
- 50.2 Outgoing Events
- 50.3 Payload Validation
- 50.4 Signatures
- 50.5 Secrets
- 50.6 Timestamp Validation
- 50.7 Replay Attacks
- 50.8 Idempotency
- 50.9 Retries
- 50.10 Duplicate Events
- 50.11 Audit Logging
- 50.12 Dead-Letter Concepts

### CHAPTER 51: Third-Party Integrations
- 51.1 REST APIs
- 51.2 API Authentication
- 51.3 OAuth Concepts
- 51.4 Mapping External Data
- 51.5 Data Ownership
- 51.6 Synchronization
- 51.7 One-Way Sync
- 51.8 Two-Way Sync
- 51.9 Incremental Sync
- 51.10 Scheduled Sync
- 51.11 Retries / Backoff
- 51.12 Rate Limiting
- 51.13 Conflict Resolution
- 51.14 Error Handling
- 51.15 Integration Logs

### CHAPTER 52: Payment Integrations
- 52.1 Payment Architecture
- 52.2 Payment Providers
- 52.3 Payment Transactions
- 52.4 Checkout Flow
- 52.5 Redirects
- 52.6 Tokens
- 52.7 Callbacks
- 52.8 Webhooks
- 52.9 Payment Status
- 52.10 Pending Payments
- 52.11 Failure Handling
- 52.12 Refund Concepts
- 52.13 Security
- 52.14 Idempotency

## UNIT XIV: MODERN ODOO FRONTEND

### CHAPTER 53: Odoo JavaScript Architecture
- 53.1 Web Client
- 53.2 JavaScript Modules
- 53.3 Native JS Modules
- 53.4 Frontend Environment
- 53.5 Components
- 53.6 Registries
- 53.7 Services
- 53.8 Hooks
- 53.9 Backend ↔ Frontend Communication
- 53.10 ORM Service
- 53.11 RPC
- 53.12 Actions
- 53.13 Frontend Debugging

### CHAPTER 54: OWL Fundamentals
- 54.1 Components
- 54.2 Templates
- 54.3 Props
- 54.4 State
- 54.5 Events
- 54.6 Lifecycle
- 54.7 Composition
- 54.8 Subcomponents
- 54.9 Reactive UI
- 54.10 Event Handlers
- 54.11 Conditional Rendering
- 54.12 Loops

### CHAPTER 55: Services, Registries & Hooks
- 55.1 Registries
- 55.2 Registry Categories
- 55.3 Services
- 55.4 Service Dependencies
- 55.5 useService()
- 55.6 ORM Service
- 55.7 RPC Service
- 55.8 Notification Service
- 55.9 Action Service
- 55.10 Router Concepts
- 55.11 Hooks
- 55.12 useBus
- 55.13 useAssets
- 55.14 Custom Hooks

### CHAPTER 56: Assets & Frontend Resources
- 56.1 Asset Bundles
- 56.2 JavaScript Assets
- 56.3 SCSS / CSS
- 56.4 XML Templates
- 56.5 Manifest Assets
- 56.6 Bundle Ordering
- 56.7 Lazy Loading
- 56.8 Asset Debugging
- 56.9 Cache Busting Concepts

### CHAPTER 57: Extending & Patching the Web Client
- 57.1 Patching Code
- 57.2 patch()
- 57.3 Patching Components
- 57.4 Extending Components
- 57.5 Extending Registries
- 57.6 Custom Field Widgets
- 57.7 View Extensions
- 57.8 Upgrade Safety
- 57.9 Conflict Risks
- 57.10 When Not to Patch

### CHAPTER 58: Client Actions & Advanced Frontend
- 58.1 Client Actions
- 58.2 Action Registry
- 58.3 OWL Client Components
- 58.4 Loading Server Data
- 58.5 Custom Dashboards
- 58.6 Generic Components
- 58.7 Dialogs
- 58.8 Notifications
- 58.9 Error Handling
- 58.10 Error Boundaries
- 58.11 Odoo Editor Concepts
- 58.12 Mobile Web APIs
- 58.13 Responsive Odoo UI
- 58.14 Accessibility

## UNIT XV: FILES, ATTACHMENTS & MEDIA

### CHAPTER 59: Attachments & Filestore
- 59.1 ir.attachment
- 59.2 Binary Fields
- 59.3 Image Fields
- 59.4 Database vs Filestore
- 59.5 Attachment Relationships
- 59.6 Uploads
- 59.7 Downloads
- 59.8 MIME Types
- 59.9 File Names
- 59.10 Attachment Access
- 59.11 Attachment Security
- 59.12 Public / Private Files
- 59.13 Access Tokens
- 59.14 Large File Considerations
- 59.15 Image Processing Concepts

## UNIT XVI: POSTGRESQL & PERFORMANCE

### CHAPTER 60: Odoo Database Structure
- 60.1 Models → Tables
- 60.2 Fields → Columns
- 60.3 Many2one Foreign Keys
- 60.4 Many2many Relation Tables
- 60.5 Foreign Keys
- 60.6 Metadata Tables
- 60.7 ir_model
- 60.8 ir_model_fields
- 60.9 ir_model_data
- 60.10 Inspecting the Schema

### CHAPTER 61: PostgreSQL for Odoo Developers
- 61.1 SELECT
- 61.2 WHERE
- 61.3 JOIN
- 61.4 GROUP BY
- 61.5 Aggregates
- 61.6 Subqueries
- 61.7 CTE Concepts
- 61.8 Constraints
- 61.9 psql
- 61.10 Database Inspection
- 61.11 Information Schema

### CHAPTER 62: Transactions & Concurrency
- 62.1 Transactions
- 62.2 Commit
- 62.3 Rollback
- 62.4 Isolation
- 62.5 Locks
- 62.6 Row Locks
- 62.7 Deadlocks
- 62.8 Concurrent Updates
- 62.9 Lost Update Concepts
- 62.10 Savepoints
- 62.11 Retry Patterns

### CHAPTER 63: Indexes & Query Plans
- 63.1 Indexes
- 63.2 B-Tree Intuition
- 63.3 Selectivity
- 63.4 Composite Indexes
- 63.5 EXPLAIN
- 63.6 EXPLAIN ANALYZE
- 63.7 Query Plans
- 63.8 Sequential Scan
- 63.9 Index Scan
- 63.10 When to Add an Index
- 63.11 Over-Indexing

### CHAPTER 64: ORM Performance
- 64.1 Query Counts
- 64.2 Batch Operations
- 64.3 Prefetch
- 64.4 Cache
- 64.5 N+1 Problems
- 64.6 Computed Field Costs
- 64.7 Stored Computations
- 64.8 Efficient Domains
- 64.9 Algorithms & Complexity
- 64.10 Database Indexes from Models
- 64.11 read_group()
- 64.12 Avoiding Loops over Queries

### CHAPTER 65: Profiling & Optimization
- 65.1 Odoo Profiler
- 65.2 SQL Profiling
- 65.3 Query Collector
- 65.4 Periodic Collector
- 65.5 Finding Bottlenecks
- 65.6 Measuring Before Optimizing
- 65.7 Benchmarking
- 65.8 Baselines
- 65.9 Performance Regression
- 65.10 Memory Considerations

## UNIT XVII: TESTING & DEBUGGING

### CHAPTER 66: Odoo Logging & Debugging
- 66.1 Log Levels
- 66.2 Server Logs
- 66.3 Stack Traces
- 66.4 Python Debugger
- 66.5 Breakpoints
- 66.6 Odoo Shell
- 66.7 Browser Developer Tools
- 66.8 Developer Mode
- 66.9 Reproducing Bugs
- 66.10 Root Cause Analysis
- 66.11 Minimal Reproduction

### CHAPTER 67: Python Tests
- 67.1 Test Module Structure
- 67.2 TransactionCase
- 67.3 Savepoint / Transaction Concepts
- 67.4 Test Data
- 67.5 setUp()
- 67.6 Assertions
- 67.7 Test Tags
- 67.8 Running Selected Tests
- 67.9 Form Helper Concepts
- 67.10 Deterministic Tests

### CHAPTER 68: Testing Business Logic
- 68.1 CRUD Tests
- 68.2 Computed Field Tests
- 68.3 Constraint Tests
- 68.4 Workflow Tests
- 68.5 Cron Tests
- 68.6 Wizard Tests
- 68.7 Edge Cases
- 68.8 Regression Tests
- 68.9 Error Tests

### CHAPTER 69: Testing Security
- 69.1 User Context
- 69.2 ACL Tests
- 69.3 Record Rule Tests
- 69.4 sudo() Tests
- 69.5 Field Security Tests
- 69.6 Multi-Company Tests
- 69.7 Portal Access Tests
- 69.8 Public Access Tests
- 69.9 Permission Regression

### CHAPTER 70: Web & Frontend Testing
- 70.1 HTTP Tests
- 70.2 Controller Tests
- 70.3 browser_js
- 70.4 Test Tours
- 70.5 Integration Tours
- 70.6 JavaScript Unit Tests
- 70.7 HOOT
- 70.8 @odoo/hoot-dom
- 70.9 Web Test Helpers
- 70.10 Mock Server
- 70.11 Mocking RPC
- 70.12 End-to-End Flows

### CHAPTER 71: Performance & Regression Testing
- 71.1 Query Count Tests
- 71.2 assertQueryCount()
- 71.3 --log-sql
- 71.4 Performance Budgets
- 71.5 Regression Detection
- 71.6 Repeatable Benchmarks
- 71.7 Large Dataset Tests

## UNIT XVIII: CLI & DEVELOPER TOOLING

### CHAPTER 72: Odoo CLI & Developer Commands
- 72.1 odoo-bin / odoo
- 72.2 Configuration File
- 72.3 Database Selection
- 72.4 -i Install
- 72.5 -u Upgrade
- 72.6 --addons-path
- 72.7 --dev
- 72.8 --log-level
- 72.9 --log-sql
- 72.10 --test-enable
- 72.11 --test-tags
- 72.12 --stop-after-init
- 72.13 shell
- 72.14 scaffold
- 72.15 Database Commands
- 72.16 Neutralize Concepts

## UNIT XIX: DEPLOYMENT & OPERATIONS

### CHAPTER 73: Odoo Configuration
- 73.1 odoo.conf
- 73.2 addons_path
- 73.3 db_host
- 73.4 db_port
- 73.5 db_user
- 73.6 db_password
- 73.7 dbfilter
- 73.8 Logging
- 73.9 Proxy Mode
- 73.10 Secrets
- 73.11 Environment-Specific Configuration
- 73.12 Resource Limits

### CHAPTER 74: Linux Deployment
- 74.1 Linux User
- 74.2 Filesystem Layout
- 74.3 Python Environment
- 74.4 Source Deployment
- 74.5 Addons
- 74.6 File Permissions
- 74.7 PostgreSQL
- 74.8 systemd
- 74.9 Service Management
- 74.10 Logs
- 74.11 Deployment User Security

### CHAPTER 75: Reverse Proxy & HTTPS
- 75.1 Reverse Proxy
- 75.2 Nginx
- 75.3 Domains
- 75.4 DNS
- 75.5 TLS / HTTPS
- 75.6 Certificates
- 75.7 Proxy Headers
- 75.8 WebSocket / Long-Lived Connections
- 75.9 Static Content
- 75.10 Secure Production Exposure

### CHAPTER 76: Workers & Production Configuration
- 76.1 Development Mode
- 76.2 Multi-Processing
- 76.3 Workers
- 76.4 Worker Sizing
- 76.5 CPU Considerations
- 76.6 Memory Limits
- 76.7 Request Time Limits
- 76.8 Cron Workers
- 76.9 Long-Polling / WebSocket Worker Concepts
- 76.10 Capacity Planning

### CHAPTER 77: PostgreSQL Operations
- 77.1 Database Users
- 77.2 Connections
- 77.3 Connection Limits
- 77.4 Maintenance
- 77.5 VACUUM Concepts
- 77.6 ANALYZE
- 77.7 Monitoring
- 77.8 Basic Tuning
- 77.9 Disk Usage
- 77.10 Slow Queries

### CHAPTER 78: Backups & Disaster Recovery
- 78.1 Database Backup
- 78.2 Filestore Backup
- 78.3 Configuration Backup
- 78.4 Restore
- 78.5 Backup Scheduling
- 78.6 Off-Site Backups
- 78.7 Encryption
- 78.8 Retention
- 78.9 Recovery Testing
- 78.10 Recovery Point Objective
- 78.11 Recovery Time Objective
- 78.12 Disaster Recovery Plan

### CHAPTER 79: Odoo.sh
- 79.1 Odoo.sh Architecture
- 79.2 Projects
- 79.3 Git Integration
- 79.4 Branches
- 79.5 Development
- 79.6 Staging
- 79.7 Production
- 79.8 Builds
- 79.9 Logs
- 79.10 Shell Access
- 79.11 Database Management
- 79.12 Backups

### CHAPTER 80: Docker for Odoo
- 80.1 Images
- 80.2 Containers
- 80.3 Volumes
- 80.4 Networking
- 80.5 Environment Variables
- 80.6 Odoo Container
- 80.7 PostgreSQL Container
- 80.8 Persistent Filestore
- 80.9 Docker Compose
- 80.10 Custom Addons Mounts
- 80.11 Configuration
- 80.12 Container Logs

### CHAPTER 81: Monitoring & Production Troubleshooting
- 81.1 Application Logs
- 81.2 PostgreSQL Logs
- 81.3 CPU
- 81.4 Memory
- 81.5 Disk
- 81.6 Database Connections
- 81.7 Slow Requests
- 81.8 Failed Jobs
- 81.9 Error Monitoring
- 81.10 Health Checks
- 81.11 Alerting Concepts
- 81.12 Incident Diagnosis
- 81.13 Incident Timeline
- 81.14 Root Cause Analysis

## UNIT XX: UPGRADES, MIGRATIONS & MAINTENANCE

### CHAPTER 82: Module Versioning
- 82.1 Manifest Version
- 82.2 Semantic Change Thinking
- 82.3 Release Changes
- 82.4 Compatibility
- 82.5 Dependencies
- 82.6 Version Control Strategy
- 82.7 Changelog
- 82.8 Release Notes

### CHAPTER 83: Schema Changes
- 83.1 Adding Fields
- 83.2 Renaming Fields
- 83.3 Changing Field Types
- 83.4 Changing Relationships
- 83.5 Removing Fields
- 83.6 Constraints
- 83.7 Defaults
- 83.8 Required Fields
- 83.9 Index Changes
- 83.10 Safe Schema Evolution

### CHAPTER 84: Data Migrations
- 84.1 Migration Scripts
- 84.2 Pre-Migration
- 84.3 Post-Migration
- 84.4 Transforming Records
- 84.5 Renaming Data
- 84.6 Preserving Relationships
- 84.7 Validation
- 84.8 Large Dataset Considerations
- 84.9 Batching
- 84.10 Idempotent Migrations
- 84.11 Rollback Planning

### CHAPTER 85: Odoo Version Upgrades
- 85.1 Version Differences
- 85.2 Deprecated APIs
- 85.3 Framework Changes
- 85.4 Module Compatibility
- 85.5 Database Upgrade
- 85.6 Upgrade Scripts
- 85.7 Upgrade Utilities
- 85.8 Frontend Migration
- 85.9 XML / View Migration
- 85.10 Asset Migration
- 85.11 Post-Upgrade Testing

### CHAPTER 86: Module Hooks
- 86.1 Hooks Concept
- 86.2 pre_init_hook
- 86.3 post_init_hook
- 86.4 uninstall_hook
- 86.5 Environment During Hooks
- 86.6 Data Initialization
- 86.7 Appropriate Uses
- 86.8 Avoiding Hook Abuse

### CHAPTER 87: Upgrade-Safe Customization
- 87.1 Never Modify Core Directly
- 87.2 Extension Points
- 87.3 Model Inheritance
- 87.4 View Inheritance
- 87.5 Stable Overrides
- 87.6 Dependency Management
- 87.7 Avoiding Hard-Coding
- 87.8 Configuration-Driven Design
- 87.9 Stable XML IDs
- 87.10 Future-Proof Design

### CHAPTER 88: Legacy Module Maintenance
- 88.1 Read Before Changing
- 88.2 Trace Dependencies
- 88.3 Trace Execution
- 88.4 Reproduce Existing Behavior
- 88.5 Characterization Tests
- 88.6 Backward Compatibility
- 88.7 Safe Refactoring
- 88.8 Deprecation
- 88.9 Technical Debt
- 88.10 Incremental Modernization

## UNIT XXI: FUNCTIONAL ODOO FOR DEVELOPERS

### CHAPTER 89: Core Functional Applications

- 89.1 Contacts
  - 89.1.1 res.partner
  - 89.1.2 Customers
  - 89.1.3 Vendors
  - 89.1.4 Addresses
  - 89.1.5 Commercial Entities

- 89.2 CRM
  - 89.2.1 Leads
  - 89.2.2 Opportunities
  - 89.2.3 Pipeline
  - 89.2.4 Stages
  - 89.2.5 CRM → Sales

- 89.3 Sales
  - 89.3.1 Quotations
  - 89.3.2 Sales Orders
  - 89.3.3 Sale Order Lines
  - 89.3.4 Pricelists
  - 89.3.5 Discounts
  - 89.3.6 Taxes
  - 89.3.7 Delivery
  - 89.3.8 Invoicing

- 89.4 Purchase
  - 89.4.1 RFQ
  - 89.4.2 Purchase Orders
  - 89.4.3 Vendor Pricelists
  - 89.4.4 Receipts
  - 89.4.5 Vendor Bills

- 89.5 Inventory
  - 89.5.1 Products
  - 89.5.2 Product Variants
  - 89.5.3 Warehouses
  - 89.5.4 Locations
  - 89.5.5 Stock Moves
  - 89.5.6 Pickings
  - 89.5.7 Routes
  - 89.5.8 Reordering Rules
  - 89.5.9 Lots
  - 89.5.10 Serial Numbers
  - 89.5.11 Packages
  - 89.5.12 Inventory Adjustments

- 89.6 Accounting Concepts
  - 89.6.1 Chart of Accounts
  - 89.6.2 Journals
  - 89.6.3 Journal Entries
  - 89.6.4 account.move
  - 89.6.5 account.move.line
  - 89.6.6 Receivable
  - 89.6.7 Payable
  - 89.6.8 Taxes
  - 89.6.9 Fiscal Positions
  - 89.6.10 Reconciliation

- 89.7 Invoicing
  - 89.7.1 Customer Invoices
  - 89.7.2 Vendor Bills
  - 89.7.3 Credit Notes
  - 89.7.4 Payments
  - 89.7.5 Payment State

- 89.8 Employees
- 89.9 Recruitment
- 89.10 Time Off
- 89.11 Attendances
- 89.12 Projects
- 89.13 Timesheets

- 89.14 Manufacturing
  - 89.14.1 Bills of Materials
  - 89.14.2 Manufacturing Orders
  - 89.14.3 Components
  - 89.14.4 Work Centers
  - 89.14.5 Work Orders
  - 89.14.6 Inventory Integration

- 89.15 Maintenance
- 89.16 Helpdesk Concept
- 89.17 Website

- 89.18 eCommerce
  - 89.18.1 Products
  - 89.18.2 Cart
  - 89.18.3 Checkout
  - 89.18.4 Delivery
  - 89.18.5 Payment

- 89.19 Point of Sale
  - 89.19.1 POS Session
  - 89.19.2 POS Orders
  - 89.19.3 Payments
  - 89.19.4 Inventory Integration

- 89.20 End-to-End Business Flow
  - 89.20.1 Lead → Opportunity
  - 89.20.2 Opportunity → Quotation
  - 89.20.3 Quotation → Sale
  - 89.20.4 Sale → Delivery
  - 89.20.5 Sale → Invoice
  - 89.20.6 Purchase → Receipt
  - 89.20.7 Purchase → Vendor Bill
  - 89.20.8 Manufacturing → Stock
  - 89.20.9 Payment → Reconciliation

## UNIT XXII: REAL ODOO ENGINEERING

### CHAPTER 90: Requirements → ERP Design
- 90.1 Stakeholder Interviews
- 90.2 Business Requirements
- 90.3 Functional Requirements
- 90.4 Non-Functional Requirements
- 90.5 Business Process Mapping
- 90.6 As-Is Process
- 90.7 Pain Points
- 90.8 To-Be Process
- 90.9 Data Requirements
- 90.10 Roles
- 90.11 Permissions
- 90.12 Integrations
- 90.13 Reporting Requirements
- 90.14 Acceptance Criteria
- 90.15 Edge Cases
- 90.16 Change Requests

### CHAPTER 91: Odoo Solution Architecture
- 91.1 Module Boundaries
- 91.2 Model Ownership
- 91.3 Dependencies
- 91.4 Shared Models
- 91.5 Integration Boundaries
- 91.6 Security Architecture
- 91.7 Multi-Company Architecture
- 91.8 Data Flow
- 91.9 Reusability
- 91.10 Configuration
- 91.11 Reporting
- 91.12 Performance
- 91.13 Deployment
- 91.14 Upgrade Strategy

### CHAPTER 92: Configuration vs Customization vs Integration
- 92.1 Standard Odoo
- 92.2 Configuration
- 92.3 Studio Concepts
- 92.4 Custom Module
- 92.5 Third-Party Module
- 92.6 External Integration
- 92.7 Data Ownership
- 92.8 Upgrade Costs
- 92.9 Maintenance Costs
- 92.10 User Training Costs
- 92.11 Technical Debt
- 92.12 Choosing the Simplest Correct Solution

### CHAPTER 93: Maintainable Odoo Code
- 93.1 Naming
- 93.2 Small Methods
- 93.3 Separation of Concerns
- 93.4 Cohesion
- 93.5 Low Coupling
- 93.6 Reusable Mixins
- 93.7 Configuration over Hard-Coding
- 93.8 Constants
- 93.9 Error Handling
- 93.10 Logging
- 93.11 Documentation
- 93.12 Upgrade Safety
- 93.13 Performance Awareness
- 93.14 Security Awareness
- 93.15 Testability
- 93.16 Avoiding Premature Abstraction

### CHAPTER 94: Git, Collaboration & Code Review
- 94.1 Repository
- 94.2 Branches
- 94.3 Commits
- 94.4 Commit Messages
- 94.5 Pull Requests
- 94.6 Merge
- 94.7 Rebase Concepts
- 94.8 Conflict Resolution
- 94.9 Release Branches
- 94.10 Tags
- 94.11 Code Review for Correctness
- 94.12 Security Review
- 94.13 ORM Performance Review
- 94.14 Upgrade-Safety Review
- 94.15 Test Review
- 94.16 Documentation Review
- 94.17 CI Concepts
- 94.18 Automated Tests in CI
- 94.19 Linting / Static Quality Checks
- 94.20 Staging Workflow
- 94.21 Production Release Workflow

## UNIT XXIII: GRAND ODOO ENGINEERING CAPSTONE

### CHAPTER 95: Production ERP Engineering
- 95.1 Problem Discovery
- 95.2 Business Requirements
- 95.3 Process Maps
- 95.4 Architecture
- 95.5 Module Boundaries
- 95.6 Data Models
- 95.7 Relational Design
- 95.8 ORM
- 95.9 Business Rules
- 95.10 Security
- 95.11 Multi-Company
- 95.12 Views
- 95.13 Workflows
- 95.14 Wizards
- 95.15 Chatter & Activities
- 95.16 Automation
- 95.17 Reports
- 95.18 Attachments
- 95.19 Translations
- 95.20 Website
- 95.21 Portal
- 95.22 API
- 95.23 Webhooks
- 95.24 External Integration
- 95.25 OWL Dashboard
- 95.26 PostgreSQL Optimization
- 95.27 Automated Tests
- 95.28 Security Tests
- 95.29 Performance Tests
- 95.30 Migration Strategy
- 95.31 Backup Strategy
- 95.32 Deployment
- 95.33 Monitoring
- 95.34 README
- 95.35 Architecture Diagram
- 95.36 Technical Documentation
- 95.37 Functional Documentation
- 95.38 User Roles Matrix
- 95.39 API Documentation
- 95.40 Deployment Documentation
- 95.41 Disaster Recovery Documentation
- 95.42 Test Evidence
- 95.43 Performance Baseline
- 95.44 Security Review
- 95.45 Upgrade Review
- 95.46 Final Production Readiness Review

## UNIT XXIV: INTERVIEW & ODOO ENGINEER READINESS

### CHAPTER 96: Odoo Engineer Job Readiness

#### KNOWLEDGE REVIEW

- 96.1 ERP Fundamentals
- 96.2 Odoo Functional Knowledge
- 96.3 Odoo Architecture
- 96.4 Module Anatomy
- 96.5 Python
- 96.6 Models
- 96.7 Fields
- 96.8 Relationships
- 96.9 ORM
- 96.10 Recordsets
- 96.11 Domains
- 96.12 Computed Fields
- 96.13 Constraints
- 96.14 Workflows
- 96.15 XML
- 96.16 Views
- 96.17 Actions
- 96.18 Security
- 96.19 Multi-Company
- 96.20 Inheritance
- 96.21 Mixins
- 96.22 Wizards
- 96.23 Cron / Automation
- 96.24 Chatter
- 96.25 QWeb / Reports
- 96.26 Internationalization
- 96.27 Controllers
- 96.28 APIs
- 96.29 Webhooks
- 96.30 Integrations
- 96.31 OWL
- 96.32 JavaScript Framework
- 96.33 PostgreSQL
- 96.34 Performance
- 96.35 Testing
- 96.36 Debugging
- 96.37 CLI
- 96.38 Deployment
- 96.39 Odoo.sh
- 96.40 Docker
- 96.41 Upgrades
- 96.42 Migrations
- 96.43 Requirements Analysis
- 96.44 Solution Architecture

#### LIVE ENGINEERING

- 96.45 Live Module Design
  - Requirements
  - Models
  - Relationships
  - Security
  - Workflow
  - UI
  - Tests

- 96.46 Live Debugging
  - Reproduce
  - Read Logs
  - Trace
  - Diagnose
  - Fix
  - Regression Test

- 96.47 Code Review
  - Correctness
  - Odoo Conventions
  - Security
  - ORM Performance
  - Maintainability
  - Tests
  - Upgrade Safety

- 96.48 Portfolio Walkthrough

#### FINAL ASSESSMENT

- 96.49 Python / OOP Interview
- 96.50 ORM Interview
- 96.51 Security Interview
- 96.52 Functional Odoo Interview
- 96.53 PostgreSQL Interview
- 96.54 OWL Interview
- 96.55 Integration Interview
- 96.56 Deployment Interview
- 96.57 Architecture Interview
- 96.58 Live Coding
- 96.59 Live Debugging
- 96.60 System Design
- 96.61 Portfolio Defense
- 96.62 Final Mock Odoo Engineer Interview

> ↓

## ODOO ENGINEER
