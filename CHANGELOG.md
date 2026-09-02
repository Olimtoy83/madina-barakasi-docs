## 2026-09-02

### Changed

- Updated MB-SABONO-RETAIL-CHK-001 to v0.1.9: recorded completed Stage 4 — Inventory ledger foundation at `d9b3dae2c055209d1f7402e87c22bb057d717817`, its bounded location-scoped ledger/balance, integer quantity, guarded negative-stock, source/reference idempotency, immutable-history, authorization, audit, and validation evidence. Stage 5 remains not started; Stage 11 Offline POS remains blocked; Live Pilot remains not started.
- Updated MB-PORT-REG-001 to v0.1.13 and MB-REG-001 to v1.1.15 for Stage 4 checkpoint traceability. The SABONO Retail User & Operating Guide requirement and Stage 15 documentation-readiness gate remain unchanged; no guide or Stage 5+ workflow documentation was created.
- Updated MB-SABONO-RETAIL-CHK-001 to v0.1.8: recorded completed Stage 3 — Retail Product / Barcode / import at `0311c87cf48bdf2413da0068cc89b99928c13c8e`, its bounded Product/Barcode/import, conflict/quarantine, authorization, audit, and validation evidence. Stage 4 remains not started; Stage 11 Offline POS remains blocked; Live Pilot remains not started.
- Updated MB-PORT-REG-001 to v0.1.12 and MB-REG-001 to v1.1.14 for Stage 3 checkpoint traceability. The SABONO Retail User & Operating Guide requirement and Stage 15 documentation-readiness gate remain unchanged; no guide or Stage 4+ workflow documentation was created.
- Updated MB-SABONO-RETAIL-CHK-001 to v0.1.7: recorded completed Stage 2 — Location + early Retail RBAC foundation at `197173b6922a0242e15c0a211e965ac465c9b18b`, its bounded generic implementation/security/runtime-regression evidence, and accepted validation. Stage 3 remains not started; Stage 11 Offline POS remains blocked; Live Pilot remains not started.
- Updated MB-PORT-REG-001 to v0.1.11 and MB-REG-001 to v1.1.13 for Stage 2 checkpoint traceability. The SABONO Retail User & Operating Guide requirement and Stage 15 documentation-readiness gate remain unchanged; no guide or Stage 3+ workflow documentation was created.
- Updated MB-SABONO-RETAIL-CHK-001 to v0.1.6: recorded the future SABONO Retail User & Operating Guide as a required Pilot deliverable, its evidence-based lifecycle/safety expectations, and the Stage 15 documentation-readiness gate. No guide, procedure, screenshot, training material, or unimplemented workflow documentation was created.
- Updated MB-PORT-REG-001 to v0.1.10 and MB-REG-001 to v1.1.12 for User & Operating Guide requirement traceability; implementation status and the Stage 2 / Stage 11 / Live Pilot boundaries remain unchanged.
- Updated MB-SABONO-RETAIL-CHK-001 to v0.1.5: recorded completed Stage 1 — Retail boundary foundation with `STAGE 1 PASS` at `b62ad74503c4d3fa32509807db41d8223b6f6138`, its validated generic Retail composition boundaries, and the Stage 2 next-stage boundary. No Retail business capability, migration, POS UI, SABONO configuration, or later stage was started.
- Updated MB-PORT-REG-001 to v0.1.9 and MB-REG-001 to v1.1.11 for Stage 1 checkpoint traceability; Pilot 0 Implementation is in progress, Stage 2 is not started, Stage 11 Offline POS remains blocked, and Live Pilot remains not started.
- Updated MB-SABONO-RETAIL-CHK-001 to v0.1.4: recorded completed accepted Pilot 0 Implementation Planning, the canonical stage sequence, safe Stage 8A/8B Sale completion boundary, access/money/bootstrap gates, and the limited Stage 11 Offline blocker. No implementation stage started.
- Updated MB-PORT-REG-001 to v0.1.8 and MB-REG-001 to v1.1.10 for implementation-plan checkpoint traceability; code, migrations, implementation, and live pilot remain not started.
- Updated MB-SABONO-RETAIL-CHK-001 to v0.1.3: recorded completed Pilot 0 Technical Design, `READY WITH TECHNICAL OPEN ITEMS`, the independent Retail/CRM boundary, P0 stock/payment/return design direction, authorization-first sequencing, and the Offline POS-only operating-policy blocker.
- Updated MB-PORT-REG-001 to v0.1.7 and MB-REG-001 to v1.1.9 for controlled Technical Design checkpoint traceability; implementation planning, code, migrations, implementation, and live pilot remain not started.
- Updated MB-SABONO-RETAIL-CHK-001 to v0.1.2: recorded the completed user-approved Pilot 0 Architecture Review / Cut-Line Decision, P0/P1/Deferred scope, confirmed Landed Cost rules, and full receipt return P0 scope. Technical Design, implementation, and live pilot remain not started.
- Updated MB-PORT-REG-001 to v0.1.6 and MB-REG-001 to v1.1.8 to preserve the approved cut-line and next-stage traceability.
- Updated MB-SABONO-RETAIL-CHK-001 to v0.1.1 with confirmed piece-sale and multiple-barcode evidence; the unconfirmed `1 BOX = 6 PCS` model is now proposed/deferred rather than a confirmed requirement.
- Recorded Landed Cost and COGS as P1 open decisions, with required business questions before allocation, cost, gross-profit, or margin semantics are chosen.
- Updated MB-REG-001 to v1.1.7 to retain the controlled checkpoint version in the Document Registry.

## 2026-09-01

### Added

- Added MB-SABONO-RETAIL-CHK-001 — SABONO Retail Canonical Project Checkpoint v0.1.0 (Draft).
- Recorded confirmed business requirements, time-bounded repository facts, completed audits, proposed-but-unapproved architecture, open Pilot decisions, blockers, deferred boundaries, and the next no-code architecture review stage.

### Changed

- Updated MB-PORT-REG-001 with the controlled SABONO Retail checkpoint and the evidence-based architecture-review boundary; no Pilot 0 approval or implementation authorization was recorded.
- Updated MB-REG-001 to v1.1.6 to register the new checkpoint and the current MB-PORT-REG-001 version.

### Engineering Governance

- Added MB-ENG-001 — Evidence-Based Engineering Execution Protocol v0.1.0 (Draft).
- Established a proposed evidence discipline for engineering execution, validation, acceptance, correction, and repository handoff.
- Registered MB-ENG-001 under Volume IV — Engineering.
- Reconciled the Document Registry self-version and registry statistics.
- Aligned the Master Index Volume IV status with the existing in-progress Engineering state.

### Changed

- Updated the SADEED AUTO portfolio entry with verified bounded vehicle-domain evidence and retained pending-verification boundaries.
- Updated the Madina Arabic portfolio entry with verified static frontend capabilities and retained pending-verification boundaries.
- Corrected the CRM repository boundary: `madina-platform` is the active monorepo and the CRM application is implemented at `apps/crm`.
- Retained `madina-crm` as a historical repository reference without asserting its current operating status.
- Updated MB-PORT-REG-001 with the verified Madina Platform / CRM technical checkpoint and pending-verification boundary.

### Added

- Added MB-PORT-REG-001 — Ecosystem & Project Portfolio Registry v0.1.0 (Draft).
- Registered the controlled cross-ecosystem portfolio registry in the Master Index and Document Registry.
- Recorded initial verified repository checkpoints and Pending Verification boundaries without promoting supplied project context to approved facts.
- Added MB-PLATFORM-CRM-CHK-001 — Madina Platform / CRM Canonical Project Checkpoint v0.1.0 (Draft).

## 2026-08-21

### Added

- Added and approved MB-DEC-003 — Latin Wordmark and Horizontal Lockup Architecture v1.0.0.
- Established Source Sans 3 static 500 with `0 em` tracking and native OpenType spacing and kerning as the canonical Latin wordmark.
- Established L2 / Balanced Optical as the canonical horizontal Latin lockup architecture with normalized relationships and a practical minimum of `S = 48 px`.
- Synchronized Latin wordmark and horizontal lockup governance across MB-201, MB-200, the Design Decisions Index, and the Documentation Registry.
## 2026-08-20

### Added

- MB-DEC-001 — Brandmark Architecture v1.0.0 (Approved)
- Approved B2.1-S1 Canonical Pass 5 as the primary Madina Barakasi brandmark.
- Approved B2.1-S1-MICRO Pass 2 as the controlled companion for 16–23 px use.
- Registered the brandmark architecture in the Design Decisions Index and Documentation Registry.
- Added MB-201 — Visual Identity Foundation v0.1.0 (Draft).
- Added and approved MB-DEC-002 — Arabic Typography Architecture v1.0.0.
- Established IBM Plex Sans Arabic as the canonical Arabic typography foundation and Noto Sans Arabic as the controlled fallback.
- Synchronized Arabic typography governance across MB-201, MB-200, the Design Decisions Index, and the Documentation Registry.

\## 2026-08-08



\### Added



\- MB-004 — Master Plan v1.0.0 (Draft)

\- Added the strategic master plan for the Madina Barakasi Platform ecosystem.

\- Defined repository responsibilities, architectural boundaries, development phases, engineering lifecycle, and governance.
