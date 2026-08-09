# MB-CRM-003 — CRM Business Entities

> Business entity definitions and ownership boundaries for the CRM application within the Madina Barakasi Platform

---

## Document Information

| Field          | Value                 |
| -------------- | --------------------- |
| Document ID    | MB-CRM-003            |
| Volume         | V — Business Modules  |
| Title          | CRM Business Entities |
| Version        | 0.1.0                 |
| Status         | Draft                 |
| Classification | Specification         |
| Language       | English               |
| Owner          | Business Architecture |
| Created        | 2026-08-10            |
| Last Updated   | 2026-08-10            |

---

# 1. Purpose

MB-CRM-003 defines the principal business entities within the CRM business domains established by MB-CRM-002.

The purpose of this document is to establish entity ownership, responsibility, and high-level relationships before detailed business-process, business-rule, data-contract, and implementation specifications are created.

This document does not define database schemas, API endpoints, UI components, or implementation details.

---

# 2. Entity Architecture Principles

CRM business entities must:

- represent meaningful business concepts;
- have one authoritative business owner;
- have a clearly defined responsibility;
- maintain explicit boundaries;
- avoid unnecessary duplication;
- minimize inappropriate coupling;
- expose only required relationships;
- remain consistent with the domain boundaries defined by MB-CRM-002.

An entity must not be introduced solely because a technical implementation requires a separate data structure.

---

# 3. Entity Ownership

Each authoritative business entity must belong to one CRM business domain.

The owning domain is responsible for:

- the business meaning of the entity;
- its authoritative business data;
- its lifecycle;
- its business rules;
- changes to its business definition.

Other domains may reference an entity through approved relationships or contracts but must not silently assume ownership.

---

# 4. CRM Core Entities

CRM Core provides application-level coordination and common CRM concepts.

At this stage, no major operational business entity is assigned exclusively to CRM Core.

CRM Core may contain approved CRM-level concepts when their ownership does not naturally belong to another business domain.

Such concepts must be explicitly specified before implementation.

---

# 5. Customer Entities

The Customers domain owns customer-related business entities.

Initial entities include:

- Customer
- Customer Contact
- Customer Status
- Customer Relationship

### Customer

Represents a business customer managed by the CRM.

### Customer Contact

Represents contact information associated with a customer.

### Customer Status

Represents the operational state of a customer relationship.

### Customer Relationship

Represents relevant business relationships associated with a customer.

Detailed attributes and lifecycle rules require subsequent specifications.

---

# 6. Product Entities

The Products domain owns the business definition of products.

Initial entities include:

- Product
- Product Category
- Product Unit
- Product Price
- Product Status

### Product

Represents a product offered or managed by the business.

### Product Category

Represents the business classification of products.

### Product Unit

Represents the unit in which a product is measured or sold.

### Product Price

Represents an applicable business price for a product.

### Product Status

Represents the operational state of a product.

Product definitions must remain separate from physical or operational stock information owned by Inventory.

---

# 7. Sales Entities

The Sales domain owns completed and recognized sales transactions.

Initial entities include:

- Sale
- Sale Item
- Sale Status

### Sale

Represents a completed or recognized sales transaction.

### Sale Item

Represents a product and quantity included in a sale.

### Sale Status

Represents the business state of a sale.

Sales may reference customers and products but do not own their master definitions.

---

# 8. Order Entities

The Orders domain owns customer orders and their lifecycle.

Initial entities include:

- Order
- Order Item
- Order Status
- Order Fulfillment

### Order

Represents an operational customer order.

### Order Item

Represents a product and quantity requested within an order.

### Order Status

Represents the lifecycle state of an order.

### Order Fulfillment

Represents the operational fulfillment state associated with an order.

An Order is distinct from a completed Sale.

---

# 9. Purchase Entities

The Purchases domain owns procurement transactions.

Initial entities include:

- Purchase
- Purchase Item
- Supplier
- Purchase Status

### Purchase

Represents a procurement transaction.

### Purchase Item

Represents a product and quantity included in a purchase.

### Supplier

Represents a party from which products are acquired.

### Purchase Status

Represents the lifecycle state of a purchase.

Purchases may affect Inventory and Finance but do not own inventory or financial records.

---

# 10. Inventory Entities

The Inventory domain owns operational stock information.

Initial entities include:

- Warehouse
- Inventory Record
- Inventory Movement
- Stock Adjustment
- Inventory Status

### Warehouse

Represents a physical or operational location used to manage stock.

### Inventory Record

Represents the stock state of a product within an inventory location.

### Inventory Movement

Represents a movement of stock.

### Stock Adjustment

Represents an intentional correction to inventory quantities.

### Inventory Status

Represents the operational state of an inventory record or stock position.

Inventory owns stock state, while Products owns product definitions.

---

# 11. Finance Entities

The Finance domain owns financial records associated with CRM operations.

Initial entities include:

- Financial Transaction
- Income
- Expense
- Payment
- Financial Category
- Payment Status

### Financial Transaction

Represents a financial record generated or recorded within CRM operations.

### Income

Represents an inflow of funds recognized by the business.

### Expense

Represents an outflow of funds recognized by the business.

### Payment

Represents a payment associated with a business transaction.

### Financial Category

Represents the classification of a financial record.

### Payment Status

Represents the state of a payment.

Finance owns the financial meaning of these entities.

---

# 12. Reporting Entities

Reporting primarily provides derived analytical representations.

Reporting must not become the authoritative owner of operational business entities.

Possible reporting representations include:

- Sales Report
- Purchase Report
- Inventory Report
- Financial Report
- Customer Report
- Operational Summary

These representations are derived from approved domain data and contracts.

They must not replace authoritative entities owned by operational domains.

---

# 13. Tasks and Activities Entities

Tasks and Activities owns operational work management.

Initial entities include:

- Task
- Activity
- Reminder
- Assignment
- Activity Status

### Task

Represents a unit of operational work.

### Activity

Represents an operational action or recorded business activity.

### Reminder

Represents a scheduled follow-up or notification requirement.

### Assignment

Represents responsibility for an operational task or activity.

### Activity Status

Represents the state of a task or activity.

Tasks and Activities may reference entities from other CRM domains without assuming ownership of those entities.

---

# 14. Principal Entity Relationships

The initial relationships include:

- Customers are associated with Orders.
- Customers are associated with Sales.
- Products are included in Orders.
- Products are included in Sales.
- Products are included in Purchases.
- Products have Inventory Records.
- Warehouses contain Inventory Records.
- Purchases may create Inventory Movements.
- Sales may create Inventory Movements.
- Orders may lead to Sales.
- Sales may create Financial Transactions.
- Purchases may create Financial Transactions.
- Payments may be associated with Sales, Purchases, or other approved business transactions.
- Tasks and Activities may reference entities across CRM domains.
- Reporting representations may consume approved data from operational domains.

These relationships describe business relationships and do not prescribe implementation mechanisms.

---

# 15. Entity Lifecycle

Each operational entity must have a defined lifecycle where lifecycle state materially affects business behavior.

Lifecycle definitions must be specified in subsequent business-process and business-rule documentation.

Examples include:

- Customer lifecycle;
- Product lifecycle;
- Order lifecycle;
- Sale lifecycle;
- Purchase lifecycle;
- Inventory lifecycle;
- Payment lifecycle;
- Task lifecycle.

No lifecycle should be implemented solely from assumptions when the business meaning has not yet been specified.

---

# 16. Entity Ownership Rules

The following rules apply:

1. Each authoritative entity has one owning domain.
2. The owning domain controls the business meaning of the entity.
3. Other domains may reference entities through approved relationships.
4. Operational domains must not silently duplicate authoritative master data.
5. Reporting representations must remain derived unless explicitly approved otherwise.
6. Shared technical packages must not become owners of CRM business entities.
7. Changes to entity ownership require architectural review.

---

# 17. Entity Identification Strategy

An entity should be introduced when it represents a distinct and meaningful business concept.

An entity should not be introduced merely because:

- a UI component exists;
- a database table appears convenient;
- an API endpoint requires a separate payload;
- a technical module requires additional structure.

Business meaning takes precedence over implementation convenience.

---

# 18. Future Refinement

Each entity may receive dedicated specifications covering:

- attributes;
- identifiers;
- lifecycle;
- business rules;
- validation;
- relationships;
- permissions;
- data contracts;
- audit requirements.

Detailed entity definitions must be introduced incrementally according to business priority.

---

# 19. Definition of Done

This document may be considered ready for approval when:

1. Principal CRM business entities are identified.
2. Each entity has an authoritative owner.
3. Entity responsibilities are documented.
4. Principal relationships are understood.
5. Entity boundaries are consistent with MB-CRM-002.
6. Ownership rules are explicit.
7. Lifecycle areas requiring further specification are identified.
8. The structure is consistent with MB-CRM-001.
9. The structure is consistent with MB-100, MB-101, and MB-102.

---

# 20. Status

This document is currently Draft.

The entity structure defined here provides the foundation for subsequent CRM business-process and business-rule specifications.
