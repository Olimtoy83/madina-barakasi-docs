# Ecosystem & Project Portfolio Registry

> **Controlled registry of Madina Barakasi ecosystem portfolio items**

---

## Document Information

| Field | Value |
| --- | --- |
| Document ID | MB-PORT-REG-001 |
| Title | Ecosystem & Project Portfolio Registry |
| Version | 0.1.12 |
| Status | Draft |
| Owner | Governance |
| Classification | Registry |
| Language | English |
| Created | 2026-09-01 |
| Last Updated | 2026-09-02 |

---

# 1. Purpose

MB-PORT-REG-001 is the cross-ecosystem registry of Madina Barakasi portfolio items. It provides a controlled answer to what exists, its architectural classification and parent, its repository or location, its verified current checkpoint, its recorded accepted or frozen decisions, its open questions, its next authorized stage, and where authoritative detail is held.

This registry is a navigation and checkpoint record. It does not replace project specifications, Architecture Decision Records (ADRs), design decisions, repository history, validation evidence, or the Document Registry.

# 2. Scope and Evidence Rules

The registry covers projects, products, platform domains or modules, commercial or public brands, integrations, research, future concepts, and governance or knowledge layers that are part of the Madina Barakasi ecosystem.

The controlled classifications are:

- Shared platform;
- Business application;
- Platform domain/module;
- Independent product;
- Commercial/public brand;
- Integration;
- Experiment/research;
- Future concept;
- Governance/knowledge layer.

Each material status or checkpoint statement must identify its evidence basis. The evidence labels are:

| Evidence basis | Meaning |
| --- | --- |
| Approved documentation | An Approved controlled document supports the statement. |
| Controlled Draft documentation | A current controlled Draft document supports the statement, but does not establish approved policy. |
| Verified repository commit/HEAD | The stated repository reference was independently verified. It is a technical checkpoint, not automatic governance approval. |
| Pending Verification | No sufficient controlled-document or repository evidence has yet been verified. |

Statements derived only from planning context are marked Pending Verification. A repository must not be created or inferred merely because an item appears in this registry.

# 3. Portfolio Entries

## 3.1 Madina Platform

| Field | Record |
| --- | --- |
| Portfolio Item | Madina Platform |
| Classification | Shared platform |
| Parent | Madina Barakasi ecosystem |
| Repository | `madina-platform` |
| Lifecycle | Implementation; governed lifecycle status pending verification |
| Business Status | Pending Verification |
| Technical Status | Verified technical foundations include server-backed CRM, Fastify API, SQLite persistence, authentication/RBAC, audit, reporting, workbook exchange, bounded reads, and pilot/security hardening. |
| Current Canonical Checkpoint | MB-PLATFORM-CRM-CHK-001 (Draft): `f02641c098a71e851779d2e59c96af8c0b27cf11` — `chore(server): harden internet-facing pilot security` |
| Accepted / Frozen Decisions | None verified. MB-ADR-002 and MB-ADR-003 are Draft, not accepted decisions. |
| Open Questions | Verify formal acceptance, production deployment/rehearsal evidence, and operational ownership. |
| Next Authorized Stage | Production Pilot Readiness Verification; this registry does not authorize deployment, an external pilot, or new CRM feature development. |
| Documentation References | MB-PLATFORM-CRM-CHK-001; MB-100, MB-101, MB-102; MB-ADR-002; MB-ADR-003 |
| Evidence Basis | Verified repository commit/HEAD; Controlled Draft documentation |

## 3.2 Madina CRM

| Field | Record |
| --- | --- |
| Portfolio Item | Madina CRM |
| Classification | Business application |
| Parent | Madina Platform |
| Repository | `madina-platform/apps/crm` verified; `madina-crm` is retained as a historical repository reference. |
| Lifecycle | Implementation evidence exists; the controlled technical checkpoint is Draft and governed lifecycle status remains pending verification. |
| Business Status | Controlled Draft CRM specifications exist; no Approved CRM stage status verified. |
| Technical Status | Verified server-backed CRM foundations include domain workflows, persistence, authentication/RBAC, audit, reporting, workbook exchange, and bounded operational reads. |
| Current Canonical Checkpoint | MB-PLATFORM-CRM-CHK-001 (Draft): repository checkpoint `f02641c098a71e851779d2e59c96af8c0b27cf11`. |
| Accepted / Frozen Decisions | None verified. MB-ADR-002 and MB-ADR-003 are Draft. |
| Open Questions | Verify formal Functional v1 and Visual v1 acceptance, production/deployment evidence, and operational ownership. |
| Next Authorized Stage | Production Pilot Readiness Verification; this registry does not authorize deployment, an external pilot, or new CRM feature development. |
| Documentation References | MB-PLATFORM-CRM-CHK-001; MB-CRM-001 through MB-CRM-008; MB-100; MB-101; MB-102; MB-ADR-002; MB-ADR-003 |
| Evidence Basis | Verified repository commit/HEAD; Controlled Draft documentation |

## 3.3 SABONO Retail

| Field | Record |
| --- | --- |
| Portfolio Item | SABONO Retail |
| Classification | Platform domain/module |
| Parent | Madina Platform |
| Repository | `madina-platform` → `apps/crm` is the current technical boundary; `madina-crm` is historical only. |
| Lifecycle | Business discovery, Technical Fit-Gap, Storefront Readiness, read-only Pilot 0 Architecture & Scope, Architecture Review / Cut-Line Decision, Technical Design, Implementation Planning, and Stages 1–3 are completed. Pilot 0 Implementation is in progress; Live Pilot has not started. |
| Business Status | Confirmed Retail requirements and the approved P0/P1/Deferred cut-line are recorded in MB-SABONO-RETAIL-CHK-001 (Draft). |
| Technical Status | Stage 1 passed at `b62ad74503c4d3fa32509807db41d8223b6f6138` (`feat(retail): add generic retail module boundary`). Stage 2 passed at `197173b6922a0242e15c0a211e965ac465c9b18b` (`feat(retail): add location access foundation`). Stage 3 passed at `0311c87cf48bdf2413da0068cc89b99928c13c8e` (`feat(retail): add product barcode import foundation`): generic Product, Barcode, controlled import, catalog authorization, and audit foundation. No blind `UNIQUE(barcode)`, Product stock, CRM dependency, SABONO-specific data, Inventory, Stock Movement, POS UI, or later-stage capability is asserted. Stage 11 Offline POS remains blocked. |
| Current Canonical Checkpoint | MB-SABONO-RETAIL-CHK-001 (Draft) |
| Accepted / Frozen Decisions | None verified |
| Open Questions | Offline physical-goods/accepted-money rejected-sync policy blocks Stage 11 Offline POS only; exact rounding, capability/membership, offline retention, and pilot configuration parameters remain open. P1 loyalty, advanced returns, supplier/payable, Landed Cost technical design, and partner rules remain outside P0. A future SABONO Retail User & Operating Guide is a required Pilot deliverable and must be reviewed against actual accepted implementation before Stage 15; it is not yet created. |
| Next Authorized Stage | Stage 4 — Inventory ledger foundation; planned next stage only, not started, and requires separate explicit implementation authorization. |
| Documentation References | MB-SABONO-RETAIL-CHK-001; MB-PLATFORM-CRM-CHK-001; MB-CRM-001 through MB-CRM-008; MB-100; MB-101; MB-102; MB-ENG-001; MB-SOP-001 |
| Evidence Basis | Confirmed business requirements recorded in controlled Draft documentation; Verified repository commit/HEAD; Controlled Draft documentation |

## 3.4 SADEED AUTO | سديد أوتو

| Field | Record |
| --- | --- |
| Portfolio Item | SADEED AUTO \| سديد أوتو |
| Former working / technical identifier | Korea Auto |
| Classification | Platform domain/module |
| Parent | Madina Platform |
| Repository | `madina-platform` → bounded `korea-auto` vehicle domain. |
| Lifecycle | Verified implementation foundation; governed business lifecycle status remains pending verification. |
| Business Status | Pending Verification |
| Technical Status | Verified `@madina/core` vehicle domain; SQLite `korea_auto_vehicles` migration/repository; transactional audit events; Fastify v1 vehicle read/list/create/update routes; API contracts; RBAC; trusted-origin protection; validation; and bounded keyset listing. Implemented scope is limited to vehicle records with make, model, year, `available`/`inactive` status, and read/list/create/update operations. |
| Current Canonical Checkpoint | `1b22c1579f44f9296b284f0247f8374269cdece6` — `feat(korea-auto): add vehicle domain foundation` |
| Accepted / Frozen Decisions | None verified |
| Open Questions | Verify business lifecycle/status, KSA operational scope, sourcing/import, sales channels, complete inventory/vehicle lifecycle, pricing/costs, customers/leads/sales, partner/investor terms, capital/profit allocation, accounting/reporting, Sharia constraints/approval, Telegram integration, SADEED-specific CRM UI, deployment/production operation, monitoring, operational ownership, roadmap, and formal acceptance/freeze. Korea Auto / `korea-auto` remain historical/technical identifiers and do not create a separate portfolio item. |
| Next Authorized Stage | Controlled business and governance evidence review is required before a business, product, deployment, or acceptance stage is recorded. |
| Documentation References | External repository `madina-platform` — `korea-auto` technical domain. The Auto Korea KSA partner presentation is retained only as historical/supporting, non-canonical evidence. |
| Evidence Basis | Verified repository commit/HEAD; Pending Verification for business and governance status |

## 3.5 Madina Arabic

| Field | Record |
| --- | --- |
| Portfolio Item | Madina Arabic |
| Classification | Independent product |
| Parent | Madina Barakasi ecosystem |
| Repository | `madina-arabic` |
| Lifecycle | Repository checkpoint verified; formal lifecycle status pending verification. |
| Business Status | Pending Verification |
| Technical Status | Verified static HTML/CSS/plain JavaScript Telegram WebApp-aware frontend with three vocabulary lessons / 12 words, Russian and Uzbek translations, a word-builder exercise, XP/streak/attempt/correct-answer tracking, browser-local `localStorage` progress, and 12 local MP3 pronunciation assets. |
| Current Canonical Checkpoint | `9b7dc74a8ba8ff86e35c1257394279f59dcb7891` — `feat(audio): add verified pronunciation assets` |
| Accepted / Frozen Decisions | None verified by controlled documentation. |
| Open Questions | Verify business status, formal acceptance/freeze, production readiness/deployment, bot configuration, secure Telegram `initData` validation, backend/API, remote persistence/synchronization, monitoring, operational ownership, and roadmap. |
| Next Authorized Stage | Repository evidence verification and controlled product-state review; this registry does not authorize deployment or feature implementation. |
| Documentation References | External repository `madina-arabic`; no controlled project document verified in this Documentation Library. |
| Evidence Basis | Verified repository commit/HEAD; Pending Verification for governance status |

## 3.6 Madina Umrah

| Field | Record |
| --- | --- |
| Portfolio Item | Madina Umrah |
| Classification | Future concept |
| Parent | Madina Barakasi ecosystem |
| Repository | Pending Verification |
| Lifecycle | Pending Verification |
| Business Status | Pending Verification |
| Technical Status | Pending Verification |
| Current Canonical Checkpoint | Pending Verification |
| Accepted / Frozen Decisions | None verified |
| Open Questions | Verify product-definition scope, ownership, repository need, and the required religious-source verification boundary. |
| Next Authorized Stage | Controlled product-definition and source-verification decision work is required before implementation is recorded. |
| Documentation References | None verified in this Documentation Library |
| Evidence Basis | Pending Verification |

## 3.7 Madina Barakasi Documentation Library / Knowledge Base

| Field | Record |
| --- | --- |
| Portfolio Item | Madina Barakasi Documentation Library / Knowledge Base |
| Classification | Governance/knowledge layer |
| Parent | Madina Barakasi ecosystem |
| Repository | `madina-barakasi-docs` |
| Lifecycle | Active documentation governance; Knowledge Base volume remains Planned. |
| Business Status | Canonical documentation library maintained; project-specific business status is out of scope. |
| Technical Status | Repository HEAD verified. |
| Current Canonical Checkpoint | `3c2c0d743f1fdd8877164db759be680116943ad9` — `docs(design): approve Latin wordmark and horizontal lockup architecture` |
| Accepted / Frozen Decisions | MB-DEC-001; MB-DEC-002; MB-DEC-003 |
| Open Questions | Establish controlled portfolio coverage for unverified items; Knowledge Base implementation remains Planned. |
| Next Authorized Stage | Review this registry and maintain it after meaningful project stages. |
| Documentation References | MASTER_INDEX.md; DOCUMENT_REGISTRY.md; ADR_REGISTRY.md; MB-004; MB-SOP-001; MB-DEC-001 through MB-DEC-003 |
| Evidence Basis | Approved documentation; Controlled Draft documentation; Verified repository commit/HEAD |

# 4. Historical Repository Traceability

The active CRM application is implemented at `apps/crm` within the `madina-platform` monorepo.

`madina-crm` is retained as a historical repository reference. Its current operating status is outside the scope of this registry update.

# 5. Maintenance / Update Policy

After a meaningful project stage:

1. verify the evidence;
2. update authoritative project documentation where applicable;
3. record an ADR or design decision separately when required;
4. update the portfolio checkpoint, accepted/frozen references, open questions, and next authorized stage;
5. update the Document Registry and Change Log only where governance requires.

This registry must remain concise. It must not store full requirements, API or schema details, implementation instructions, audit reports, test logs, daily history, chat transcripts, religious source content, duplicated ADR prose, or speculative roadmaps.

# 6. Related Documents

- MASTER_INDEX.md
- DOCUMENT_REGISTRY.md
- ADR_REGISTRY.md
- MB-004 — Master Plan
- MB-100 — System Architecture
- MB-SOP-001 — Documentation Workflow

# Version History

| Version | Status | Description |
| --- | --- | --- |
| 0.1.12 | Draft | Recorded verified Stage 3 completion at `0311c87cf48bdf2413da0068cc89b99928c13c8e`, bounded generic Product/Barcode/import and validation evidence; Stage 4 remains not started, Stage 11 remains blocked, and Live Pilot remains not started. |
| 0.1.11 | Draft | Recorded verified Stage 2 completion at `197173b6922a0242e15c0a211e965ac465c9b18b`, the bounded generic Location/access foundation and validation evidence; Stage 3 remains not started, Stage 11 remains blocked, and Live Pilot remains not started. |
| 0.1.10 | Draft | Recorded the future SABONO Retail User & Operating Guide requirement and its Stage 15 documentation-readiness gate without creating a guide or asserting any unimplemented workflow as available. |
| 0.1.9 | Draft | Recorded verified Stage 1 Retail boundary completion at `b62ad74503c4d3fa32509807db41d8223b6f6138`, Pilot 0 Implementation in progress, Stage 2 not started, and the unchanged Stage 11-only Offline blocker without asserting Retail business capability or Live Pilot readiness. |
| 0.1.4 | Draft | Updated SADEED AUTO with verified bounded vehicle-domain evidence and retained pending-verification boundaries. |
| 0.1.5 | Draft | Added the controlled SABONO Retail checkpoint, completed-stage record, evidence classifications, and architecture-review boundary without approving Pilot 0 architecture or implementation. |
| 0.1.6 | Draft | Recorded the completed user-approved SABONO Pilot 0 cut-line and Technical Design boundary without recording implementation, live-pilot, or production approval. |
| 0.1.7 | Draft | Recorded completed SABONO Pilot 0 Technical Design, the limited Offline POS blocker, and the next implementation-planning boundary without recording implementation or live-pilot approval. |
| 0.1.8 | Draft | Recorded completed SABONO Pilot 0 Implementation Planning, the first separately authorized Retail boundary stage, and the Stage 11-only Offline blocker without recording implementation or live-pilot approval. |
| 0.1.3 | Draft | Updated Madina Arabic with verified static frontend capabilities and retained pending-verification boundaries. |
| 0.1.2 | Draft | Recorded the Madina Platform / CRM evidence-based technical checkpoint and pending-verification boundary. |
| 0.1.1 | Draft | Synchronized CRM repository-boundary documentation and historical repository traceability. |
| 0.1.0 | Draft | Initial controlled portfolio registry foundation. |
