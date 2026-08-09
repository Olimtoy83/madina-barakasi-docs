# MB-CRM-002 — CRM Business Domains

> Business domain boundaries for the CRM application within the Madina Barakasi Platform

---

## Document Information

| Field          | Value                 |
| -------------- | --------------------- |
| Document ID    | MB-CRM-002            |
| Volume         | V — Business Modules  |
| Title          | CRM Business Domains  |
| Version        | 0.1.0                 |
| Status         | Draft                 |
| Classification | Specification         |
| Language       | English               |
| Owner          | Business Architecture |
| Created        | 2026-08-10            |
| Last Updated   | 2026-08-10            |

---

# 1. Purpose

MB-CRM-002 defines the principal business domains of the CRM application.

The purpose of this document is to establish explicit business boundaries before detailed entity, process, data, and implementation specifications are created.

This document does not define database schemas, API endpoints, UI components, or implementation details.

---

# 2. Domain Architecture Principles

CRM business domains must:

- represent real business responsibilities;
- have explicit ownership;
- maintain clear boundaries;
- minimize unnecessary coupling;
- avoid circular dependencies;
- expose only required business contracts;
- keep business rules within the domain responsible for them.

A domain must not exist solely because a technical implementation requires a separate module.

---

# 3. CRM Business Domains

The initial CRM domain structure consists of:

1. CRM Core
2. Customers
3. Products
4. Sales
5. Orders
6. Purchases
7. Inventory
8. Finance
9. Reporting
10. Tasks and Activities

This structure may be refined through subsequent approved specifications.

---

# 4. CRM Core

## Responsibility

CRM Core provides application-level business coordination and common CRM concepts that do not belong exclusively to another business domain.

## Ownership

CRM Core owns CRM-level business context and coordination rules.

## Boundary

CRM Core must not become a general container for unrelated business entities.

---

# 5. Customers

## Responsibility

The Customers domain manages customer-related business information and customer relationships.

## Examples

- customer identity;
- contact information;
- customer status;
- customer history;
- customer-related business relationships.

## Boundary

Customer-specific business rules belong to the Customers domain.

Sales, orders, and other domains may reference customers but must not assume ownership of customer master data.

---

# 6. Products

## Responsibility

The Products domain manages the business definition of products offered by the business.

## Examples

- product identity;
- product name;
- category;
- unit;
- pricing information;
- product status.

## Boundary

Products defines what a product is.

Inventory defines the physical or operational stock of that product.

---

# 7. Sales

## Responsibility

The Sales domain manages completed and recognized sales transactions.

## Examples

- sale transaction;
- sold products;
- quantities;
- sale price;
- customer relationship;
- sales status;
- sales date.

## Boundary

Sales owns the business meaning of a completed sale.

Inventory may provide stock information, while Finance may use sales information for financial records.

---

# 8. Orders

## Responsibility

The Orders domain manages customer orders and their lifecycle.

## Examples

- order creation;
- order status;
- ordered items;
- quantities;
- customer association;
- order fulfillment state.

## Boundary

An order represents an operational commitment and is distinct from a completed sale.

---

# 9. Purchases

## Responsibility

The Purchases domain manages procurement and acquisition of products.

## Examples

- purchase transaction;
- supplier relationship;
- purchased products;
- quantities;
- purchase cost;
- purchase date;
- purchase status.

## Boundary

Purchases owns the business meaning of procurement transactions.

Inventory may be affected by completed purchases.

---

# 10. Inventory

## Responsibility

The Inventory domain manages stock and inventory movements.

## Examples

- stock quantity;
- warehouse location;
- inventory movement;
- stock adjustment;
- receiving;
- stock issue;
- inventory status.

## Boundary

Inventory owns the operational state of stock.

Product definitions remain owned by the Products domain.

---

# 11. Finance

## Responsibility

The Finance domain manages financial records associated with CRM business operations.

## Examples

- income;
- expenses;
- financial transactions;
- payment status;
- financial categorization;
- financial reporting inputs.

## Boundary

Finance owns the financial meaning of financial records.

Operational domains provide business events or transaction information when financial consequences exist.

---

# 12. Reporting

## Responsibility

The Reporting domain provides business reporting and analytical views across CRM domains.

## Boundary

Reporting should primarily consume approved domain data and contracts.

Reporting must not become the owner of operational business data.

---

# 13. Tasks and Activities

## Responsibility

Tasks and Activities manages operational work related to CRM processes.

## Examples

- tasks;
- follow-ups;
- reminders;
- operational activities;
- assigned work;
- activity status.

## Boundary

Tasks and Activities owns operational work management but does not own the underlying customer, sales, product, or financial entities.

---

# 14. Domain Relationships

The principal relationships are:

- Customers may be associated with Orders.
- Customers may be associated with Sales.
- Products may be included in Orders.
- Products may be included in Sales.
- Products may be included in Purchases.
- Products may have Inventory records.
- Purchases may create Inventory movements.
- Sales may create Inventory movements.
- Sales may create Finance records.
- Purchases may create Finance records.
- Orders may lead to Sales.
- Reporting may consume information from all approved business domains.
- Tasks and Activities may reference entities across CRM domains.

These relationships represent business dependencies and must not automatically be interpreted as implementation dependencies.

---

# 15. Domain Ownership Rules

Each business entity must have one authoritative owner.

Other domains may reference or consume the entity through approved contracts.

No domain may silently duplicate ownership of another domain's authoritative business data.

Derived or reporting-specific representations may exist when justified, but they must not replace authoritative ownership.

---

# 16. Cross-Domain Transactions

Some business processes may affect multiple domains.

Examples include:

- completing a sale;
- receiving a purchase;
- fulfilling an order;
- recording a payment;
- adjusting inventory.

Cross-domain operations must preserve clear ownership of each affected business responsibility.

The implementation mechanism for cross-domain coordination will be defined in subsequent specifications.

---

# 17. Future Refinement

Each domain may receive dedicated specifications covering:

- entities;
- business processes;
- business rules;
- lifecycle states;
- data contracts;
- permissions;
- validation requirements.

The domain structure must be refined only when business requirements justify the change.

---

# 18. Definition of Done

This document may be considered ready for approval when:

1. Principal CRM business domains are identified.
2. Each domain has an explicit responsibility.
3. Domain boundaries are documented.
4. Ownership rules are established.
5. Major relationships are understood.
6. Cross-domain responsibilities are identified.
7. The structure is consistent with MB-CRM-001.
8. The structure is consistent with MB-100, MB-101, and MB-102.

---

# 19. Status

This document is currently Draft.

The domains defined here provide the foundation for subsequent CRM entity and business-process specifications.
