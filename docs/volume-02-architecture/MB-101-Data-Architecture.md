# MB-101 — Data Architecture

> **The data architecture of the Madina Barakasi Platform**

---

## Document Information

| Field          | Value               |
| -------------- | ------------------- |
| Document ID    | MB-101              |
| Volume         | II — Architecture   |
| Title          | Data Architecture   |
| Version        | 0.1.0               |
| Status         | Draft               |
| Classification | Canonical           |
| Language       | English             |
| Owner          | Architecture        |
| Created        | 2026-08-08          |
| Last Updated   | 2026-08-08          |

---

# 1. Purpose

MB-101 defines the high-level data architecture of the Madina Barakasi Platform ecosystem.

The document establishes principles for data ownership, data boundaries, shared data structures, application-specific data, and the relationship between platform infrastructure and business applications.

This document does not define a final database schema.

---

# 2. Scope

The data architecture covers the relationship between:

- `madina-platform`
- `madina-crm`
- `madina-arabic`

The documentation repository `madina-barakasi-docs` remains the canonical source for approved data architecture documentation.

---

# 3. Data Architecture Principles

The following principles govern the current data architecture:

1. Data ownership must remain explicit.
2. Application-specific business data belongs to the application that owns the corresponding business domain.
3. Shared technical data structures may be provided by the platform when they are genuinely reusable.
4. Generic platform packages must not become containers for application-specific business models.
5. Data contracts should be defined before large-scale integration.
6. Changes to important data contracts should be documented.
7. The architecture should evolve incrementally.
8. The final physical database schema must follow the approved domain and application architecture.

---

# 4. Data Ownership

Data ownership follows application responsibility.

The general model is:

```text
Business Application
        ↓
Owns Business Data
        ↓
Uses Platform Capabilities
        ↓
Uses Infrastructure
```

## 5. Package Data Boundary Clarification

Within the current `madina-platform` monorepo, business data and domain models for the active CRM / ERP application may be owned by the application-domain package `@madina/core`. This does not make those models generic shared platform data structures.

`@madina/shared` and other genuinely shared packages must contain only reusable technical abstractions. Data ownership, historical meaning, and business rules for Sales, Purchases, Inventory, Transactions, Customers or Clients, and Tasks remain application-domain responsibilities.
