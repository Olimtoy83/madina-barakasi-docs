# MB-ADR-002 — Application-Domain Core Package Boundary

> **Architecture Decision Record for the `@madina/core` package boundary**

---

## Document Information

| Field | Value |
| --- | --- |
| Document ID | MB-ADR-002 |
| Volume | II — Architecture |
| Title | Application-Domain Core Package Boundary |
| Version | 0.1.0 |
| Status | Draft |
| Classification | ADR |
| Language | English |
| Owner | Architecture |
| Created | 2026-08-18 |
| Last Updated | 2026-08-18 |

---

# 1. Context

The current `madina-platform` monorepo contains `@madina/core`, `@madina/shared`, and `@madina/ui`. Existing architecture documents require generic reusable shared packages to remain independent from ERP-specific business logic, but did not explicitly map those package names to their responsibilities.

The active CRM / ERP application requires an application-domain package for Sales, Purchases, Inventory, Transactions, Customers or Clients, Tasks, and related domain services. This decision clarifies the package boundary without changing the principle that genuinely shared platform capabilities remain independent from ERP-specific business logic.

# 2. Decision

`@madina/core` is the application-domain/core package of the active CRM / ERP application within the current monorepo.

It may contain CRM / ERP business and domain logic, including Sales, Purchases, Inventory, Transactions, Customers or Clients, Tasks, and related domain services.

`@madina/core` is not a generic reusable shared technical package.

`@madina/shared` and other genuinely shared packages contain generic reusable technical abstractions. `@madina/ui` remains a reusable UI package.

CRM-specific application or UI composition must not be placed in `@madina/core`.

# 3. Scope

This decision applies to package ownership and responsibility within the current `madina-platform` monorepo. It does not define CRM business rules, data contracts, user-interface composition, or a physical code-migration plan.

# 4. Consequences

- CRM / ERP domain logic may remain in `@madina/core` without treating that package as a reusable shared platform capability.
- Generic reusable abstractions must remain in `@madina/shared` or another genuinely shared package.
- `@madina/ui` remains reusable UI infrastructure and must not become the owner of CRM business rules.
- Application composition remains outside `@madina/core`.
- Future package changes must preserve the distinction between application-domain ownership and genuinely shared technical capabilities.

# 5. Alternatives Considered

## Alternative A — Treat `@madina/core` as a generic reusable shared package

Rejected because the active CRM / ERP domain logic would then conflict with the documented boundary for generic shared packages.

## Alternative B — Treat `@madina/core` as the application-domain/core package

Selected because it makes the current application-domain ownership explicit while preserving the separation of genuinely shared abstractions.

## Alternative C — Leave the package mapping unspecified

Rejected because it leaves the architecture documents open to conflicting interpretations and blocks controlled implementation decisions.

# 6. Relationship to Existing Documentation

- MB-004 establishes that generic shared platform capabilities must remain independent from ERP-specific business logic.
- MB-100 defines the system boundary between reusable platform capabilities and application-specific business logic.
- MB-101 defines explicit data ownership and prevents generic platform packages from becoming containers for application-specific business models.
- MB-102 defines package-boundary standards for reusable technical capabilities.
- MB-CRM-001 and MB-CRM-007 define the CRM application's ownership of CRM-specific business functionality and business rules.
- MB-CRM-004, MB-CRM-005, and MB-CRM-006 define CRM processes, business rules, and data contracts that remain application-domain responsibilities.

# 7. Status

This ADR is Draft and requires review before becoming Approved.

---

**Madina Barakasi Architecture Library**
