# MB-CRM-006 — CRM Data Contracts

> Data contract specification for the Madina Barakasi CRM application

---

## Document Information

| Field          | Value                 |
| -------------- | --------------------- |
| Document ID    | MB-CRM-006            |
| Volume         | V — Business Modules  |
| Title          | CRM Data Contracts    |
| Version        | 0.1.0                 |
| Status         | Draft                 |
| Classification | Specification         |
| Language       | English               |
| Owner          | Business Architecture |
| Created        | 2026-08-10            |
| Last Updated   | 2026-08-10            |

---

# 1. Purpose

MB-CRM-006 defines the principal data contracts required for communication between CRM business domains and processes.

A data contract establishes the expected meaning, ownership, required information, and business constraints of data exchanged between domains.

This document does not define database schemas, API endpoints, transport protocols, or implementation-specific serialization formats.

---

# 2. Data Contract Principles

CRM data contracts must:

- have a clearly defined business meaning;
- identify the owning domain;
- define the principal data being exchanged;
- preserve entity identity;
- preserve historical business meaning;
- avoid unnecessary duplication of ownership;
- make cross-domain dependencies explicit;
- remain independent from a specific technical implementation.

A data contract describes an agreed business data boundary, not merely a software object.

---

# 3. Contract Ownership

Each principal data contract must identify an owning business domain.

The owning domain is responsible for the meaning and integrity of the data represented by the contract.

A consuming domain may use contract data without becoming the owner of the underlying business entity.

Ownership must not be transferred implicitly through data exchange.

---

# 4. Customer Data Contract

## 4.1 Purpose

The Customer Data Contract provides customer information required by other CRM domains.

## 4.2 Owner

Customers.

## 4.3 Principal Data

The contract may provide:

- customer identity;
- customer name or business name;
- contact information;
- customer status;
- relevant relationship information.

## 4.4 Consumers

Potential consumers include:

- Sales;
- Orders;
- Tasks and Activities;
- Reporting;
- Finance where customer association is required.

## 4.5 Contract Rules

Consumers must reference the customer identity rather than creating competing customer ownership structures.

Changes to customer information must not invalidate historical transactions that reference the customer.

---

# 5. Product Data Contract

## 5.1 Purpose

The Product Data Contract provides product information required by operational CRM domains.

## 5.2 Owner

Products.

## 5.3 Principal Data

The contract may provide:

- product identity;
- product name;
- product category;
- product unit;
- product status;
- applicable current pricing information where appropriate.

## 5.4 Consumers

Potential consumers include:

- Sales;
- Orders;
- Purchases;
- Inventory;
- Reporting.

## 5.5 Contract Rules

Consumers must reference the product identity.

Historical transactions must retain the product information required to represent the original transaction independently from later master-data changes.

---

# 6. Sales Data Contract

## 6.1 Purpose

The Sales Data Contract defines the principal information exchanged when a sale is created, processed, completed, or cancelled.

## 6.2 Owner

Sales.

## 6.3 Principal Data

The contract may provide:

- sale identity;
- customer identity;
- sale status;
- sale date;
- sale items;
- quantities;
- transaction prices;
- applicable totals;
- relevant payment information.

## 6.4 Consumers

Potential consumers include:

- Inventory;
- Finance;
- Customers;
- Reporting;
- Tasks and Activities.

## 6.5 Contract Rules

The sale contract must preserve the historical values required to represent the transaction.

Consumers must not directly modify sales-owned business data outside an approved sales process.

---

# 7. Order Data Contract

## 7.1 Purpose

The Order Data Contract defines the information exchanged during order processing and fulfillment.

## 7.2 Owner

Orders.

## 7.3 Principal Data

The contract may provide:

- order identity;
- customer identity;
- order status;
- order items;
- quantities;
- requested fulfillment information;
- relevant dates.

## 7.4 Consumers

Potential consumers include:

- Customers;
- Products;
- Inventory;
- Sales;
- Reporting;
- Tasks and Activities.

## 7.5 Contract Rules

Order status must represent the business state defined by the Orders domain.

Consumers must not independently redefine the meaning of an order status.

---

# 8. Purchase Data Contract

## 8.1 Purpose

The Purchase Data Contract defines information exchanged during supplier purchasing and receiving.

## 8.2 Owner

Purchases.

## 8.3 Principal Data

The contract may provide:

- purchase identity;
- supplier identity;
- purchase status;
- purchase items;
- quantities;
- purchase prices;
- relevant dates;
- receiving information where applicable.

## 8.4 Consumers

Potential consumers include:

- Products;
- Inventory;
- Finance;
- Reporting.

## 8.5 Contract Rules

Purchase information must preserve the historical values required to represent the original transaction.

Receiving information must not be interpreted as a completed purchase unless the applicable purchase process has satisfied its business conditions.

---

# 9. Inventory Data Contract

## 9.1 Purpose

The Inventory Data Contract defines information exchanged when business processes affect stock.

## 9.2 Owner

Inventory.

## 9.3 Principal Data

The contract may provide:

- product identity;
- warehouse or inventory location;
- quantity;
- inventory status;
- movement type;
- source business transaction;
- movement date.

## 9.4 Consumers

Potential consumers include:

- Sales;
- Orders;
- Purchases;
- Products;
- Reporting.

## 9.5 Contract Rules

Consumers must not directly change inventory-owned quantities without using an approved inventory process.

Inventory changes must remain traceable to the applicable business event where traceability is required.

---

# 10. Finance Data Contract

## 10.1 Purpose

The Finance Data Contract defines information exchanged when CRM business activities produce financial effects.

## 10.2 Owner

Finance.

## 10.3 Principal Data

The contract may provide:

- financial transaction identity;
- transaction type;
- amount;
- currency where applicable;
- financial category;
- related business transaction;
- payment status;
- transaction date.

## 10.4 Consumers

Potential consumers include:

- Sales;
- Purchases;
- Reporting;
- Customers where financial association is required.

## 10.5 Contract Rules

Financial consumers must not directly modify Finance-owned transaction data outside approved financial processes.

Historical financial values must remain stable after the underlying business transaction has been recorded.

---

# 11. Task and Activity Data Contract

## 11.1 Purpose

The Task and Activity Data Contract provides operational follow-up information.

## 11.2 Owner

Tasks and Activities.

## 11.3 Principal Data

The contract may provide:

- task identity;
- activity identity;
- related CRM entity;
- assigned responsibility;
- task status;
- due date where applicable;
- activity information.

## 11.4 Consumers

Potential consumers include:

- Customers;
- Sales;
- Orders;
- Purchases;
- Reporting.

## 11.5 Contract Rules

Consumers must not redefine task or activity status outside the owning domain.

---

# 12. Reporting Data Contract

## 12.1 Purpose

The Reporting Data Contract defines the business information made available for reporting and analytical purposes.

## 12.2 Owner

Reporting.

## 12.3 Principal Data

Reporting may consume authoritative information from:

- Customers;
- Products;
- Sales;
- Orders;
- Purchases;
- Inventory;
- Finance;
- Tasks and Activities.

## 12.4 Contract Rules

Reporting must not become the owner of source business entities merely because it consumes their data.

Reporting outputs must preserve the meaning of the source business data.

---

# 13. Cross-Domain Contract Rules

## 13.1 Stable Identity

Contracts must use stable business identities for referenced entities.

## 13.2 Ownership Preservation

Data consumption must not transfer ownership.

## 13.3 Historical Integrity

Contracts representing completed transactions must preserve the historical information required to describe what occurred.

## 13.4 Explicit Dependencies

Cross-domain data dependencies must be documented where they materially affect business behavior.

## 13.5 Contract Stability

Changes to an established contract must be evaluated for their effect on consuming domains.

Material contract changes require appropriate documentation and validation before implementation.

---

# 14. Contract Validation

Data exchanged through a CRM contract must satisfy the business conditions defined by the owning domain.

Validation should establish that:

- required business identity is present;
- required business state is valid;
- referenced entities are valid where required;
- required quantities or values are present;
- historical transaction information is preserved where applicable.

The exact technical validation mechanism is outside the scope of this document.

---

# 15. Contract Versioning

Data contracts may require versioning when a change materially affects consumers.

A contract change should be evaluated for:

- added data;
- removed data;
- changed meaning;
- changed business rules;
- changed ownership;
- changed required fields;
- changed lifecycle behavior.

The exact technical versioning mechanism belongs to the appropriate engineering documentation.

---

# 16. Contract Change Management

Changes to a business data contract must be reviewed against:

- MB-CRM-002 — Business Domains;
- MB-CRM-003 — Business Entities;
- MB-CRM-004 — Business Processes;
- MB-CRM-005 — Business Rules.

A contract must not silently contradict an approved business rule or entity ownership definition.

Material changes must be documented through the established documentation governance process.

---

# 17. Implementation Boundary

This document does not prescribe:

- REST or GraphQL endpoints;
- request or response JSON schemas;
- database tables;
- ORM models;
- TypeScript interfaces;
- serialization formats;
- message brokers;
- event transport mechanisms.

Those concerns belong to the appropriate architecture and engineering specifications.

---

# 18. Future Refinement

The following areas require subsequent specification:

- detailed field definitions;
- required versus optional data;
- validation constraints;
- contract state transitions;
- event contracts;
- API contracts;
- integration contracts;
- contract versioning policy;
- error and rejection contracts.

These refinements must be introduced through subsequent approved specifications.

---

# 19. Definition of Done

A CRM data contract may be considered ready for detailed implementation when:

1. Its business purpose is defined.
2. Its owning domain is identified.
3. Principal data elements are identified.
4. Consumer domains are understood.
5. Ownership boundaries are explicit.
6. Historical integrity requirements are documented.
7. Validation requirements are identified.
8. Material dependencies are documented.
9. Contract change considerations are understood.
10. The contract is consistent with CRM domains, entities, processes, and business rules.

---

# 20. Status

This document is currently Draft.

The principal CRM data contracts are defined at a high level and require further refinement before being considered implementation-complete.