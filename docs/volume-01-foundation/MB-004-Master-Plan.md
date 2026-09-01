\# MB-004 — Master Plan



> \*\*The strategic master plan of the Madina Barakasi Platform\*\*



\---



\## Document Information



| Field          | Value              |

| -------------- | ------------------ |

| Document ID    | MB-004             |

| Volume         | I — Foundation     |

| Title          | Master Plan        |

| Version        | 1.0.1              |

| Status         | Draft              |

| Classification | Canonical          |

| Language       | English            |

| Owner          | Governance         |

| Created        | 2026-08-08         |

| Last Updated   | 2026-09-01         |



\---



\# 1. Purpose



MB-004 defines the long-term strategic direction, structural organization, development phases, and architectural boundaries of the Madina Barakasi Platform ecosystem.



This document establishes the master direction from which architecture, engineering, business-module development, documentation, and future platform expansion are planned.



It does not replace the constitutional foundation, architecture documents, engineering standards, or business specifications.



\---



\# 2. Scope



This Master Plan covers the Madina Barakasi ecosystem and its principal repositories and application locations:



\- `madina-platform` — the active monorepo, including the CRM application at `apps/crm`

\- `madina-barakasi-docs`

\- `madina-arabic`



It defines their responsibilities and their intended relationship.

`madina-crm` is retained as a historical repository reference. Its current operating status is outside the scope of this documentation correction.



\---



\# 3. Repository Architecture



\## 3.1 madina-platform



The shared technical platform.

The active CRM business application is implemented at `apps/crm` within this monorepo.



Primary responsibilities:



\- Shared types

\- Core abstractions

\- Reusable UI infrastructure

\- Authentication infrastructure

\- API infrastructure

\- Database infrastructure

\- Notifications

\- Configuration

\- Other reusable technical capabilities



The platform must remain independent of ERP-specific business logic.



\---



\## 3.2 CRM application (`apps/crm`)



The ERP / CRM business application within the active `madina-platform` monorepo.



Primary responsibilities include:



\- Products

\- Categories

\- Brands

\- Units

\- Suppliers

\- Customers

\- Warehouses

\- Inventory

\- Purchases

\- Sales

\- Finance

\- Accounting

\- Reports

\- Analytics

\- Tasks

\- Users

\- Roles

\- Settings



Business-domain logic belongs to this application rather than to generic shared platform capabilities.



\---



\## 3.3 madina-barakasi-docs



The canonical documentation repository.



Primary responsibilities:



\- Foundation

\- Architecture

\- Design \& Experience

\- Engineering

\- Business Modules

\- Operations

\- Knowledge Base

\- ADRs

\- Standards

\- Registries

\- Engineering Reviews

\- Release documentation



This repository is the canonical source for approved project documentation.



\---



\## 3.4 madina-arabic



A separate application focused on Arabic language learning.



Its application-specific logic remains independent from the ERP domain.



\---



\# 4. Architectural Boundary



The principal dependency direction is:



&#x20;   Business Applications

&#x20;           ↓

&#x20;   madina-platform

&#x20;           ↓

&#x20;   Infrastructure



Business-domain concepts must not be introduced into the shared platform merely for the convenience of a single application.



Examples of ERP-specific concepts include:



\- Product

\- Warehouse

\- Sale

\- Purchase

\- Customer

\- Supplier



These belong to the CRM application at `apps/crm`.



Reusable technical abstractions may belong to `madina-platform`.



\---



\# 5. Development Strategy



Development proceeds in controlled phases.



\## Phase 1 — Platform Foundation



Establish the minimum stable technical foundation required by applications.



Initial areas:



1\. Shared

2\. Core

3\. UI

4\. Database

5\. Authentication

6\. API



Additional infrastructure is introduced only when justified by project requirements.



\---



\## Phase 2 — ERP Foundation



Establish the application and domain foundation of the CRM application at `apps/crm` within `madina-platform`.



This phase defines:



\- Domain boundaries

\- Core entities

\- Application services

\- Infrastructure boundaries

\- Validation

\- Error handling

\- Persistence contracts

\- UI application structure



\---



\## Phase 3 — Master Data



Establish the fundamental business data required by the ERP.



Initial domains:



\- Categories

\- Brands

\- Units

\- Suppliers

\- Customers

\- Products

\- Warehouses



\---



\## Phase 4 — Inventory



Establish inventory management and warehouse operations.



Primary areas:



\- Stock

\- Stock movements

\- Warehouse balances

\- Inventory operations

\- Inventory history



\---



\## Phase 5 — Purchasing



Establish the purchasing lifecycle:



\- Suppliers

\- Purchase orders

\- Purchase items

\- Receiving

\- Purchase costs

\- Purchase history



\---



\## Phase 6 — Sales



Establish the sales lifecycle:



\- Customers

\- Orders

\- Sales

\- Sale items

\- Payments

\- Invoices

\- Sales history



\---



\## Phase 7 — Finance \& Accounting



Establish financial operations:



\- Income

\- Expenses

\- Payments

\- Financial records

\- Accounting structures



\---



\## Phase 8 — Reports \& Analytics



Establish operational and management reporting.



Areas include:



\- Sales reports

\- Purchase reports

\- Inventory reports

\- Financial reports

\- Performance indicators

\- Analytics



\---



\## Phase 9 — CRM



Expand customer relationship capabilities beyond basic customer records.



\---



\## Phase 10 — AI



Introduce AI capabilities only after the core operational system provides stable and reliable data and interfaces.



AI is therefore a later capability rather than a foundation dependency.



\---



\# 6. Engineering Lifecycle



Each significant development unit follows:



&#x20;   Plan

&#x20;     ↓

&#x20;   Architecture

&#x20;     ↓

&#x20;   Implementation

&#x20;     ↓

&#x20;   Validation

&#x20;     ↓

&#x20;   Review

&#x20;     ↓

&#x20;   Commit

&#x20;     ↓

&#x20;   Push

&#x20;     ↓

&#x20;   Documentation

&#x20;     ↓

&#x20;   Next Unit



A feature is not considered complete merely because its interface works.



\---



\# 7. Definition of Done



A significant module or feature should have, as applicable:



\- Defined architectural responsibility

\- Appropriate types

\- Business rules

\- Validation

\- Error handling

\- Integration

\- Testing

\- Documentation

\- Git history

\- Engineering review



The applicable completion criteria must be determined according to the scope of the change.



\---



\# 8. Documentation Governance



`madina-barakasi-docs` is the canonical documentation repository.



The documentation system follows the principle:



> One topic → One canonical document.



Official documents must:



\- Have a unique Document ID

\- Belong to exactly one Volume

\- Have a version

\- Have a status

\- Have an owner

\- Be registered in `DOCUMENT\_REGISTRY.md`



Only approved documents are considered official according to the current documentation governance.



\---



\# 9. Change Management



Changes to this Master Plan must follow the documentation lifecycle defined by the Documentation Library.



The current lifecycle is:



&#x20;   Draft

&#x20;     ↓

&#x20;   Review

&#x20;     ↓

&#x20;   Approved

&#x20;     ↓

&#x20;   Released

&#x20;     ↓

&#x20;   Archived



Material architectural changes should be supported by an Architecture Decision Record where required.



\---



\# 10. Long-Term Direction



The platform is intended to evolve from a shared technical foundation into an ecosystem capable of supporting multiple Madina Barakasi applications.



The immediate priority is not maximum feature count.



The immediate priority is:



\- Stable foundations

\- Clear boundaries

\- Reusable technical capabilities

\- Reliable ERP architecture

\- Controlled documentation

\- Sustainable engineering practices



Future capabilities may include integrations, mobile applications, advanced analytics, and AI capabilities when justified by the maturity and requirements of the platform.



\---



\# 11. Current State



At the creation of this document:



\- `madina-platform` is the active monorepo and is in Platform Foundation development.

\- `madina-platform` contains the CRM application at `apps/crm` and the initial shared workspace package.

\- `madina-crm` is retained as a historical repository reference; its current operating status is outside the scope of this document update.

\- `madina-barakasi-docs` is the canonical documentation repository.

\- `madina-arabic` remains a separate application.



The current platform foundation priority is to establish the minimum reusable technical core before beginning large-scale ERP implementation.



\---



\# 12. Governance



This document is governed as a Canonical Foundation document.



Changes must remain consistent with:



\- Volume I — Foundation

\- Volume II — Architecture

\- Engineering Standards

\- Approved ADRs

\- The Documentation Registry



Where conflicts arise, the higher-level approved governance and architecture documents take precedence until the conflict is formally resolved.



\---



\# Version History



| Version | Status | Description |

| ------- | ------ | ----------- |

| 1.0.1   | Draft  | Corrected the CRM repository boundary to the active `madina-platform` monorepo and `apps/crm`. |

| 1.0.0   | Draft  | Initial Master Plan |
