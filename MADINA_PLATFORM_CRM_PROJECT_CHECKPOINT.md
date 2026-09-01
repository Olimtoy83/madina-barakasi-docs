# Madina Platform / CRM Canonical Project Checkpoint

> **Controlled technical checkpoint for the Madina Platform and CRM application**

---

## Document Information

| Field | Value |
| --- | --- |
| Document ID | MB-PLATFORM-CRM-CHK-001 |
| Title | Madina Platform / CRM Canonical Project Checkpoint |
| Version | 0.1.0 |
| Status | Draft |
| Owner | Governance |
| Classification | Registry |
| Language | English |
| Created | 2026-09-01 |
| Last Updated | 2026-09-01 |

---

# 1. Purpose and Scope

This document records a concise, evidence-based technical checkpoint for Madina Platform and its CRM application. It preserves verified repository state without declaring governance acceptance, production readiness, deployment, or business completion.

It is a controlled navigation and checkpoint record. It does not replace architecture documents, CRM specifications, ADRs, repository history, validation logs, or operational acceptance evidence.

# 2. Authoritative Repository Boundary

| Subject | Verified boundary |
| --- | --- |
| Platform repository | `madina-platform` |
| CRM application | `madina-platform/apps/crm` |
| Server application | `madina-platform/apps/server` |
| Historical repository reference | `madina-crm` is historical only; its current operating status is not asserted here. |

# 3. Verified Repository Checkpoint

| Field | Evidence |
| --- | --- |
| Repository | `madina-platform` |
| Commit / HEAD | `f02641c098a71e851779d2e59c96af8c0b27cf11` |
| Subject | `chore(server): harden internet-facing pilot security` |
| Commit date | 2026-09-01 |
| Evidence meaning | A verified technical checkpoint; it is not automatic governance approval. |

# 4. Verified Technical Foundations

The verified repository is a pnpm/Turborepo workspace. Relevant applications include `apps/crm` and `apps/server`; relevant packages include `@madina/core`, `@madina/api`, `@madina/database`, `@madina/auth`, `@madina/shared`, and `@madina/ui`.

| Area | Verified foundation |
| --- | --- |
| CRM domains | Server-backed CRM domains include clients, tasks, products, purchases, sales, stock movements, transactions, and reporting. |
| API and service runtime | Versioned Fastify API foundation, health/readiness endpoints, and controlled server lifecycle are present. |
| Persistence | SQLite repositories, migrations, transactions, integrity/backup utilities, and atomic-operation coverage are present. |
| Access control | Authentication sessions, cookie handling, RBAC, user management, and route protection are present. |
| Audit | Persistent audit records, attribution, protected audit access, and atomic audit writes are present. |
| Reporting | Server-backed reporting/read models, business-timezone handling, keyset pagination, and CRM reporting views are present. |
| Workbook exchange | Product workbook template/export and atomic import foundations are present. |
| Operational reads | Bounded stock, sales, and purchase reads are present. |
| Pilot hardening | Production-pilot foundation and internet-facing security hardening are present in repository history. |

# 5. Validation Recorded for This Checkpoint

| Validation | Result |
| --- | --- |
| `pnpm build` | Passed. |
| `pnpm test` | Passed after a permitted rerun. The initial sandbox run was blocked by an `EPERM` process-spawn limitation; this was not recorded as a source-test failure. |
| `git diff --check` | Passed. |

# 6. Limitations and Pending Verification

The following were not verified by this checkpoint: deployment execution; formal acceptance; live reverse-proxy or TLS configuration; live backup/restore rehearsal; monitoring; external-pilot scope; tenant model; and operational ownership.

The following remain **Pending Verification**:

- Formal Functional v1 and Visual v1 acceptance;
- Frozen governance status;
- Production-ready status;
- Live deployment;
- Pilot backup/restore rehearsal; and
- External-pilot and SABONO-readiness status.

# 7. Next Authorized Stage

**Production Pilot Readiness Verification** is the next authorized documentation stage. This checkpoint does not authorize deployment, an external pilot, or new CRM feature development.

# 8. Evidence References

## Controlled Documentation

- MB-004 — Master Plan (Draft)
- MB-100 — System Architecture (Draft)
- MB-101 — Data Architecture (Draft)
- MB-102 — Engineering Standards (Draft)
- MB-CRM-001 through MB-CRM-008 — CRM specifications (Draft)
- MB-ADR-002 and MB-ADR-003 — Architecture Decision Records (Draft)
- MB-PORT-REG-001 — Ecosystem & Project Portfolio Registry (Draft)

## Repository Evidence

- `madina-platform` commit `f02641c098a71e851779d2e59c96af8c0b27cf11`
- Workspace structure, application/package manifests, implementation sources, migrations, tests, and validation commands inspected at that checkpoint

# Version History

| Version | Status | Description |
| --- | --- | --- |
| 0.1.0 | Draft | Initial evidence-based Madina Platform / CRM technical checkpoint. |
