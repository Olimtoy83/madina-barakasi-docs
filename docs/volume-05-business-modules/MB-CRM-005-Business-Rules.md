# MB-CRM-005 — CRM Business Rules

> Business rule specification for the Madina Barakasi CRM application

---

## Document Information

| Field          | Value                 |
| -------------- | --------------------- |
| Document ID    | MB-CRM-005            |
| Volume         | V — Business Modules  |
| Title          | CRM Business Rules    |
| Version        | 0.1.0                 |
| Status         | Draft                 |
| Classification | Specification         |
| Language       | English               |
| Owner          | Business Architecture |
| Created        | 2026-08-10            |
| Last Updated   | 2026-08-10            |

---

# 1. Purpose

MB-CRM-005 defines the principal business rules governing the CRM application.

Business rules establish constraints, conditions, responsibilities, and expected business behavior for CRM entities and processes.

This document does not define implementation details, database schemas, API implementations, or UI designs.

---

# 2. Business Rule Principles

CRM business rules must:

- represent an actual business requirement;
- be explicit and understandable;
- apply to clearly identified business entities or processes;
- preserve business ownership boundaries;
- be consistent with approved CRM architecture;
- avoid unnecessary technical assumptions;
- remain independent from a particular implementation technology.

A technical validation rule must not automatically be treated as a business rule.

---

# 3. Rule Categories

CRM business rules may be classified into the following categories:

- Entity Rules
- Customer Rules
- Product Rules
- Sales Rules
- Order Rules
- Purchase Rules
- Inventory Rules
- Finance Rules
- Task and Activity Rules
- Cross-Domain Rules
- Reporting Rules

The classification exists to make business constraints easier to identify and maintain.

---

# 4. Entity Rules

## 4.1 Entity Identity

Each principal CRM entity must have a stable identity.

An update to an entity must not unintentionally create a new entity.

## 4.2 Entity Ownership

Each entity must have an explicitly defined owning business domain.

Participation in a business process does not transfer entity ownership.

## 4.3 Entity Status

Where an entity has a defined status, status changes must follow approved business rules.

An entity must not enter an undefined business state.

## 4.4 Entity Lifecycle

Entity creation, modification, completion, cancellation, or archival must follow the lifecycle defined for that entity.

---

# 5. Customer Rules

## 5.1 Customer Identity

A customer must be represented by a distinct customer record.

The CRM should avoid creating duplicate customer records when an existing customer can be identified.

## 5.2 Customer Information

Customer information must remain associated with the correct customer identity.

Updates must not overwrite unrelated customer records.

## 5.3 Customer Status

Customer status must represent a recognized business state.

Status transitions must follow applicable business rules.

## 5.4 Customer Relationship

Customer relationships with sales, orders, activities, and other CRM processes must reference the appropriate customer entity.

---

# 6. Product Rules

## 6.1 Product Identity

Each product must have a stable product identity.

## 6.2 Product Category

A product may be associated with a product category where categorization is required by the business.

## 6.3 Product Unit

Product quantities must use an explicitly defined unit where the business process requires quantity measurement.

## 6.4 Product Price

A product price must be associated with the applicable product and pricing context.

Changes to pricing must not silently rewrite historical transaction values.

## 6.5 Product Status

Products that are no longer available for normal business activity must be represented by an appropriate status rather than being silently removed from historical transactions.

---

# 7. Sales Rules

## 7.1 Sale Identity

Each sale must have a unique business identity.

## 7.2 Sale Items

A sale must contain one or more sale items when the business transaction represents product or service quantities.

## 7.3 Historical Price

The price recorded on a completed sale must represent the price applicable to that transaction.

Later product price changes must not alter historical sale values.

## 7.4 Sale Completion

A sale must not be considered completed until the required business conditions have been satisfied.

## 7.5 Sale Cancellation

A cancelled sale must remain distinguishable from a completed sale.

Any inventory or financial consequences of cancellation must follow the applicable business process.

---

# 8. Order Rules

## 8.1 Order Identity

Each order must have a unique business identity.

## 8.2 Order Ownership

An order belongs to the Orders domain.

Other domains may participate in order processing without owning the order entity.

## 8.3 Order Items

An order must contain the products or services requested by the customer.

## 8.4 Order Status

Order status must represent the actual operational state of the order.

## 8.5 Order Fulfillment

An order must not be considered fulfilled unless the required fulfillment conditions have been satisfied.

## 8.6 Order Cancellation

Cancelled orders must remain distinguishable from active or completed orders.

---

# 9. Purchase Rules

## 9.1 Purchase Identity

Each purchase must have a unique business identity.

## 9.2 Supplier Association

A purchase must identify the relevant supplier where supplier information is required by the business process.

## 9.3 Purchase Items

A purchase must identify the products, quantities, and applicable purchase values.

A Purchase must contain at most one Purchase Item for each Product.

When the same Product is added again to a Purchase, the quantity of the existing Purchase Item must be increased rather than creating another Purchase Item for that Product.

This normalization rule is a Purchase business rule and must not be enforced only by the user interface.

## 9.4 Purchase Receipt

Inventory must only be increased as a result of an approved receiving process.

## 9.5 Purchase Cancellation

A cancelled purchase must not be treated as an active completed purchase.

---

# 10. Inventory Rules

## 10.1 Inventory Ownership

Inventory records belong to the Inventory domain.

## 10.2 Inventory Movement

Changes to inventory quantities must be represented by valid inventory movements or approved adjustment processes.

For a completed, normalized Purchase, each Product must have one Purchase Item and one corresponding Stock Movement.

The Stock Movement must remain traceable to the source Purchase or business event. Movement history must not be lost or silently overwritten.

This rule does not introduce line references, an aggregation engine, or a separate movement entity.

## 10.3 Stock Receipt

Stock received through an approved purchase process must produce the appropriate inventory effect.

## 10.4 Stock Issue

Stock issued through an approved business process must produce the appropriate inventory effect.

## 10.5 Stock Transfer

Inventory transfers must preserve the relationship between the source and destination inventory locations.

## 10.6 Stock Adjustment

Manual inventory adjustments must have an identifiable business reason.

## 10.7 Historical Inventory Records

Historical inventory movements must not be silently rewritten when later inventory changes occur.

---

# 11. Finance Rules

## 11.1 Financial Transaction Identity

Each financial transaction must have a stable business identity.

## 11.2 Income

Income must be associated with the business activity that generated it where such association is required.

## 11.3 Expense

Expenses must be recorded with the applicable business category where categorization is required.

## 11.4 Payment

Payments must be associated with the relevant financial or business obligation where applicable.

## 11.5 Financial Categories

Financial transactions must use recognized financial categories where categorization is required.

## 11.6 Historical Financial Values

Historical financial transaction values must not be changed merely because related master data has subsequently changed.

---

# 12. Task and Activity Rules

## 12.1 Task Ownership

Each task must have an identifiable responsible party where assignment is required.

## 12.2 Task Status

Task status must represent the actual operational state of the task.

## 12.3 Task Completion

A task must only be marked completed when the required work has been completed according to its business purpose.

## 12.4 Activity Recording

Activities must be associated with the relevant CRM context where such association is required.

---

# 13. Cross-Domain Rules

## 13.1 Domain Ownership

A business process involving multiple domains must preserve the ownership of each participating entity.

## 13.2 Cross-Domain Consistency

Cross-domain processes must maintain a consistent business state across the affected domains.

## 13.3 Explicit Dependencies

Dependencies between domains must be explicit.

A domain must not silently modify another domain's business entities without an approved business contract.

## 13.4 Historical Integrity

Completed business transactions must preserve the historical values required to represent what actually occurred.

---

# 14. Reporting Rules

## 14.1 Source Data

Reports must use authoritative CRM business data.

## 14.2 Historical Reporting

Historical reports must preserve the values applicable to the original business transactions.

## 14.3 Reporting Independence

Reporting operations must not modify source business transactions unless explicitly authorized by an approved business rule.

---

# 15. Validation Rules

Business processes must validate required business conditions before performing consequential state changes.

Validation must occur before the business operation is considered complete.

Failed validation must not silently produce a completed business transaction.

The exact technical validation mechanism is outside the scope of this document.

---

# 16. Exception Rules

Business exceptions must be explicitly recognized where they materially affect business outcomes.

An exception must not silently produce an invalid business state.

Where an operation cannot be completed, the resulting business state must remain understandable and consistent.

Detailed exception handling must be defined by the relevant process specification.

---

# 17. Audit and Traceability Rules

Important business transactions should remain traceable.

Where audit information is required, the system must preserve sufficient information to understand the relevant business event.

The exact technical audit mechanism is outside the scope of this document.

---

# 18. Rule Priority

Where multiple business rules apply, the more specific approved rule takes precedence over a general rule unless higher-level architecture explicitly defines otherwise.

Conflicting rules must be resolved through the documentation governance process before implementation.

---

# 19. Future Refinement

The following areas require further specification:

- detailed customer validation rules;
- detailed product and pricing rules;
- sale and order state transitions;
- purchase receiving rules;
- inventory availability rules;
- financial settlement rules;
- permissions affecting business operations;
- detailed exception conditions;
- audit requirements;
- cross-domain business contracts.

These refinements must be introduced through subsequent approved specifications.

---

# 20. Definition of Done

The CRM business rules may be considered ready for detailed implementation when:

1. The rule categories are defined.
2. Important entity constraints are documented.
3. Principal process constraints are documented.
4. Domain ownership rules are explicit.
5. Historical integrity requirements are defined.
6. Cross-domain rules are understood.
7. Important validation conditions are documented.
8. Relevant exception behavior is specified.
9. Required audit considerations are identified.
10. The rules are consistent with CRM architecture and business processes.

---

# 21. Status

This document is currently Draft.

The principal CRM business rules are defined at a high level and require further refinement before being considered implementation-complete.
