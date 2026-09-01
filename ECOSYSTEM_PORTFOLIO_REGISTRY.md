# Ecosystem & Project Portfolio Registry

> **Controlled registry of Madina Barakasi ecosystem portfolio items**

---

## Document Information

| Field | Value |
| --- | --- |
| Document ID | MB-PORT-REG-001 |
| Title | Ecosystem & Project Portfolio Registry |
| Version | 0.1.1 |
| Status | Draft |
| Owner | Governance |
| Classification | Registry |
| Language | English |
| Created | 2026-09-01 |
| Last Updated | 2026-09-01 |

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
| Technical Status | Repository HEAD verified; the repository contains `apps/crm`. |
| Current Canonical Checkpoint | `f02641c098a71e851779d2e59c96af8c0b27cf11` — `chore(server): harden internet-facing pilot security` |
| Accepted / Frozen Decisions | None verified. MB-ADR-002 and MB-ADR-003 are Draft, not accepted decisions. |
| Open Questions | Confirm the controlled platform stage. |
| Next Authorized Stage | Pending verification of governed project stage; this registry does not authorize implementation. |
| Documentation References | MB-100, MB-101, MB-102; MB-ADR-002; MB-ADR-003 |
| Evidence Basis | Verified repository commit/HEAD; Controlled Draft documentation |

## 3.2 Madina CRM

| Field | Record |
| --- | --- |
| Portfolio Item | Madina CRM |
| Classification | Business application |
| Parent | Madina Platform |
| Repository | `madina-platform/apps/crm` verified; `madina-crm` is retained as a historical repository reference. |
| Lifecycle | Implementation evidence exists; governed lifecycle status pending verification. |
| Business Status | Controlled Draft CRM specifications exist; no Approved CRM stage status verified. |
| Technical Status | `apps/crm` exists in the verified `madina-platform` repository. |
| Current Canonical Checkpoint | No CRM-specific canonical checkpoint verified. Container repository HEAD: `f02641c098a71e851779d2e59c96af8c0b27cf11`. |
| Accepted / Frozen Decisions | None verified. MB-ADR-002 and MB-ADR-003 are Draft. |
| Open Questions | Verify the controlled CRM stage and canonical checkpoint. |
| Next Authorized Stage | Verify the governed CRM checkpoint before recording a next implementation stage. |
| Documentation References | MB-CRM-001 through MB-CRM-008; MB-100; MB-101; MB-102; MB-ADR-002; MB-ADR-003 |
| Evidence Basis | Verified repository commit/HEAD; Controlled Draft documentation |

## 3.3 SABONO Retail

| Field | Record |
| --- | --- |
| Portfolio Item | SABONO Retail |
| Classification | Platform domain/module |
| Parent | Madina Platform |
| Repository | Pending Verification |
| Lifecycle | Pending Verification |
| Business Status | Pending Verification |
| Technical Status | Pending Verification |
| Current Canonical Checkpoint | Pending Verification |
| Accepted / Frozen Decisions | None verified |
| Open Questions | Verify business requirements, technical fit-gap evidence, ownership, and repository relationship. |
| Next Authorized Stage | Evidence discovery and controlled architecture review required before any pilot or implementation stage is recorded. |
| Documentation References | None verified in this Documentation Library |
| Evidence Basis | Pending Verification |

## 3.4 SADEED AUTO | سديد أوتو

| Field | Record |
| --- | --- |
| Portfolio Item | SADEED AUTO \| سديد أوتو |
| Former working / technical identifier | Korea Auto |
| Classification | Platform domain/module |
| Parent | Madina Platform |
| Repository | Pending Verification |
| Lifecycle | Pending Verification |
| Business Status | Pending Verification |
| Technical Status | Pending Verification |
| Current Canonical Checkpoint | Pending Verification |
| Accepted / Frozen Decisions | None verified |
| Open Questions | Verify product/domain ownership, reported stage evidence, and implementation status. Historical technical identifiers do not create a separate portfolio item. |
| Next Authorized Stage | Controlled architecture evidence is required before an implementation stage is recorded. |
| Documentation References | None verified in this Documentation Library |
| Evidence Basis | Pending Verification |

## 3.5 Madina Arabic

| Field | Record |
| --- | --- |
| Portfolio Item | Madina Arabic |
| Classification | Independent product |
| Parent | Madina Barakasi ecosystem |
| Repository | `madina-arabic` |
| Lifecycle | Repository checkpoint verified; formal lifecycle status pending verification. |
| Business Status | Pending Verification |
| Technical Status | Repository HEAD and pronunciation-assets commit verified. |
| Current Canonical Checkpoint | `9b7dc74a8ba8ff86e35c1257394279f59dcb7891` — `feat(audio): add verified pronunciation assets` |
| Accepted / Frozen Decisions | None verified by controlled documentation. |
| Open Questions | Verify the claimed learning-experience, audio, localization, and acceptance/freeze evidence in controlled documentation. |
| Next Authorized Stage | Controlled review of the repository checkpoint and governance evidence before a product-stage decision is recorded. |
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
| 0.1.1 | Draft | Synchronized CRM repository-boundary documentation and historical repository traceability. |
| 0.1.0 | Draft | Initial controlled portfolio registry foundation. |
