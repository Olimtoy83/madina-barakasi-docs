# SABONO Retail Canonical Project Checkpoint

> **Controlled continuity checkpoint for SABONO Retail as the first Madina Retail pilot**

---

## Document Information

| Field | Value |
| --- | --- |
| Document ID | MB-SABONO-RETAIL-CHK-001 |
| Title | SABONO Retail Canonical Project Checkpoint |
| Version | 0.1.7 |
| Status | Draft |
| Owner | Governance |
| Classification | Registry |
| Language | English |
| Created | 2026-09-01 |
| Last Updated | 2026-09-02 |

---

# 1. Purpose and Continuity Rule

This document preserves the controlled project state for **SABONO Retail**. It enables a future ChatGPT or Work session to continue from verified evidence and recorded business input without restarting discovery, the Technical Fit-Gap Audit, or the Storefront Readiness Audit.

This checkpoint is a concise navigation and handoff record. It does not approve an architecture, define an implementation, replace business specifications, create an ADR, or replace current repository inspection.

Future sessions must:

1. read this checkpoint first;
2. treat controlled documentation and current repository evidence as authoritative over chat history;
3. update the relevant **Confirmed** and **Open** sections when material business evidence arrives;
4. inspect the current `madina-platform` HEAD and target files before technical work; and
5. update this checkpoint after a material SABONO stage or business decision.

Do not restart SABONO discovery from scratch. Do not repeat completed audits without material new evidence.

# 2. Project Identity and Boundary

| Subject | Controlled record |
| --- | --- |
| Project | SABONO Retail |
| Business | SABONO |
| Location | Tashkent, Shota Rustaveli 49 |
| Retail focus | Cookware, kitchen, and home goods |
| Known brands | BergHOFF; Wilmax |
| Architecture direction | Madina Platform → generic Madina Retail capabilities → SABONO as first real pilot/business implementation |
| Current technical repository | `madina-platform` → `apps/crm` |
| Historical boundary | `madina-crm` is historical only and is not the current development boundary. |

SABONO must not receive SABONO-hardcoded architecture. Marketplace is not Pilot 0. The accepted directional separation is:

`Retail Product != Storefront Publication != Marketplace Offer != Online Order != Sale`

The current `sabono.uz` storefront is outside this checkpoint's implementation scope.

# 3. Evidence Classification

The labels below are intentional and must not be conflated.

| Label | Meaning in this checkpoint |
| --- | --- |
| **CONFIRMED BUSINESS REQUIREMENT** | Business input recorded for SABONO. It is not automatic technical design. |
| **VERIFIED REPOSITORY FACT** | Evidence observed at the stated repository commit/HEAD only. Re-inspect before relying on it. |
| **COMPLETED ANALYSIS / AUDIT** | A completed read-only stage; it is not automatic approval. |
| **PROPOSED ARCHITECTURE** | Recommendation from the completed architecture report; not approved. |
| **OPEN DECISION** | A required business or architecture decision that remains unresolved. |
| **PILOT BLOCKER** | A decision or evidence gap that must be resolved before the affected Pilot 0 capability or live rollout. |
| **DEFERRED** | Explicitly outside the current approved work scope; it is not cancelled. |

# 4. Confirmed Pilot Principle

**CONFIRMED BUSINESS REQUIREMENT**

Pilot 0 is controlled and parallel. The existing SABONO operational system remains the source of truth initially. Madina Retail runs alongside it, and reconciliation must cover at least:

- stock;
- sales;
- payments/money; and
- operational correctness.

Pilot 0 does not automatically replace GBS, ARCA/fiscal operation, tax/accounting systems, or every external SABONO system.

# 5. Completed Work — Do Not Repeat

| Stage | Status | Continuity instruction |
| --- | --- | --- |
| SABONO business requirements/discovery foundation | **COMPLETED ANALYSIS / AUDIT** | Do not restart without material new evidence. |
| SABONO Technical Fit-Gap Audit | **COMPLETED ANALYSIS / AUDIT** | Concluded current Madina CRM v1 cannot support full SABONO Pilot 0 without code changes. |
| SABONO Storefront Readiness Audit | **COMPLETED ANALYSIS / AUDIT** | Do not repeat unless material new storefront evidence arrives. |
| MADINA RETAIL — PILOT 0 ARCHITECTURE & SCOPE | **COMPLETED ANALYSIS / AUDIT** | Completed as a read-only proposal. It is **not approved architecture**. |
| PILOT 0 ARCHITECTURE REVIEW / CUT-LINE DECISION | **COMPLETED** | User approved the final P0/P1/Deferred cut-line for Technical Design. |
| PILOT 0 TECHNICAL DESIGN SPECIFICATION | **COMPLETED** | Recorded approved future implementation direction and remaining Technical Design open items; implementation planning has not started. |
| PILOT 0 IMPLEMENTATION PLANNING | **COMPLETED** | Accepted canonical plan records separately authorized stages, Sale completion safety boundary, and the limited Offline blocker; it did not itself start implementation. |
| Stage 1 — Retail boundary foundation | **COMPLETED / STAGE 1 PASS** | Verified at `b62ad74503c4d3fa32509807db41d8223b6f6138`; established generic composition boundaries only. |
| Stage 2 — Location + early Retail RBAC foundation | **COMPLETED / STAGE 2 PASS** | Verified at `197173b6922a0242e15c0a211e965ac465c9b18b` (`feat(retail): add location access foundation`); established the generic Retail Location and early access foundation only. |

The Technical Fit-Gap identified these major gaps: multi-location stock; split payments; offline POS; product/import requirements; supplier invoice/payment lifecycle; discount/promotion/loyalty; and reliable COGS/profit semantics.

Existing Madina Platform foundations are to be reused and extended, not replaced.

## Stage 2 Verification Record

**VERIFIED REPOSITORY FACT**

Stage 2 introduced the generic Retail Location/access foundation: the `RetailLocation` model with `central_warehouse` and `store` types and `active` and `inactive` statuses; additive migration `031_retail_access_locations_v1`; persistent `retail_locations` and `retail_user_location_grants`; Location create/list/read; Location grant/revoke; and append-only audit evidence for relevant mutations. Existing Auth user identities are reused; no separate Retail user identity system was introduced.

Existing global Auth roles remain `admin`, `manager`, `operator`, and `viewer`. Stage 2 did not introduce SABONO- or Retail-specific global roles. Retail capability and Location access are a separate authorization layer. Server-side Location-scoped authorization requires an authenticated session, the required Retail capability, an active Location, and an active Location grant. CRM does not depend on Retail, and `@madina/retail` does not depend on `@madina/core`.

During Stage 2 validation, the new runtime `createAuditEvent` import from the root `@madina/shared` barrel activated an extensionless-barrel runtime failure under the current Node runtime. Stage 2 corrected that regression by removing the new root-barrel runtime import and constructing the required audit evidence locally in the repository implementation. The existing extensionless shared barrel predated Stage 2; Stage 2 newly activated it at runtime. Final validation passed after the correction.

Stage 2 did not introduce SABONO-specific data, Product, Barcode, Inventory, Stock Movement business domain, Goods Receipt, Transfer, Retail Sale, Payment Allocation, discount engine, Return, Offline POS, Retail reporting, or POS UI. Stage 3 and later functionality remains outside Stage 2.

# 6. Confirmed Retail Requirements

## 6.1 POS and Payments

**CONFIRMED BUSINESS REQUIREMENT**

Retail flow:

`find/scan product → quantity → discount → payment → receipt/completed sale`

Required payment methods are cash, card, transfer, and other. Split payment is required: one Sale may have multiple payment methods/allocations. Barcode scanning and a fast cashier workflow are important.

## 6.2 Locations, Stock, Transfers, and Partners

**CONFIRMED BUSINESS REQUIREMENT**

Goods flow from Supplier to one Central Warehouse, then Store/location, then Customer. SABONO has one active store plus partners; known location concepts also include store/display, store-related warehouse, another warehouse, partner stock/locations, and future multiple stores.

Stock must be location-specific. Transfers require confirmation from both sides. A cashier must see stock only for the cashier's store and related warehouse/location scope. Partner sales may be entered manually by a manager.

**OPEN DECISION:** partner reward/commission formula.

## 6.3 Inventory

**CONFIRMED BUSINESS REQUIREMENT**

Inventory occurs approximately quarterly and is location-specific. Required flow:

`scan barcode → enter actual quantity → compare expected vs actual → shortage/surplus`

It requires reconciliation and audit semantics; it must not be reduced to arbitrary global quantity editing. Inconvenient inventory is a confirmed business pain point.

## 6.4 Product, Barcode, and Packaging

**CONFIRMED BUSINESS REQUIREMENT**

The catalog is approximately 1,700 Products. SABONO accounts for the discussed goods in pieces. A Product may have multiple barcodes: a primary/factory barcode and one or more additional internal barcodes. Every barcode assigned to the Product must identify that same Product in POS.

An additional internal barcode does not by itself mean a multi-piece package and does not automatically change quantity. To sell six pieces, the cashier scans the Product six times or sets quantity to six.

A real source-data/accounting case exists for `WL-992025 / A` with barcode `5052609920253`. It must not be discarded as an Excel typo.

**OPEN DECISION / PILOT BLOCKER:** exact source-data barcode semantics. Do not adopt global `UNIQUE(barcode)` as an approved invariant. Affected records require investigation or quarantine before Pilot scanning.

**CORRECTED BUSINESS EVIDENCE:** the previously discussed `1 BOX = 6 PCS` model is not confirmed as a current Packaging/UOM conversion requirement. It must not be treated as a confirmed business rule.

**PROPOSED ARCHITECTURE / DEFERRED:** a generic Packaging/UOM conversion capability may still have future value if a confirmed business scenario requires it. It is not a current P0 requirement, does not follow from an additional internal barcode, and does not automatically require Product Variants.

## 6.5 Discounts, Promotions, Loyalty, and Customer

**CONFIRMED BUSINESS REQUIREMENT**

Needs include individual Product percentage discount, receipt-level discount, promotional fixed price, and loyalty-card discount. Individual Product discount is percentage-based. When a Product has a fixed promotional price, loyalty discount does not apply to that Product.

Loyalty levels are 5%, 10%, 15%, and 20%; card number is five digits. Eventual needs are customer registration, card binding, customer search, customer history, and loyalty application.

**OPEN DECISION:** loyalty tier transition rules.

**CONFIRMED PILOT 0 CUT-LINE:** basic authorized Product percentage discount is P0. It is limited to an auditable item-level percentage discount. Promotion engine, fixed promotional price, receipt-level discount, loyalty discount, and Loyalty remain P1.

## 6.6 Returns and Exchanges

**CONFIRMED BUSINESS REQUIREMENT**

Customer returns and exchanges occur. A refund returns money to the customer. Current GBS records the operation and ARCA issues a separate fiscal return receipt. Return/Exchange is therefore a real business operation, not a manual stock adjustment.

**CONFIRMED PILOT 0 CUT-LINE:** full completed Sale/full receipt return is sufficient for P0. Partial item return is P1.

Damaged/non-resellable scenarios, complex promotion/loyalty reversal, and other advanced Return/Exchange cases are P1. Payment reversal, stock restoration, idempotency, audit, and exchange implementation mechanics remain Technical Design decisions rather than confirmed business rules.

## 6.7 Suppliers, Imports, and Landed Cost

**CONFIRMED BUSINESS REQUIREMENT**

Imports may use USD or EUR. Customs, logistics, and other attributable costs may contribute to future landed cost. The semantic principle is:

`Purchase / Supplier Invoice != Payment`

Future Retail capability must conceptually support supplier invoice, prepayment, multiple payments, and outstanding payable.

**CONFIRMED BUSINESS RULES / P1:** actual Product cost includes purchase price, delivery, customs, certification, bank commissions, storage, internal delivery, and customs declarant services. Additional shipment/import costs are allocated across Products proportionally to Product purchase value. When the same SKU arrives in different shipments at different costs, SABONO uses weighted-average costing.

These rules do not block Pilot 0. Remaining P1 questions are Technical Design matters: weighted-average calculation boundary, precision/rounding, late attributable expenses, capitalization timing, and corrections/reversals/audit. Do not claim reliable gross profit/margin until that P1 technical design is complete.

## 6.8 Offline POS

**CONFIRMED BUSINESS REQUIREMENT**

Cashiers must continue operating for several minutes of weak/no internet and synchronize automatically after connectivity returns. The future architecture must address durable local operation, idempotency, duplicate prevention, synchronization, and reconciliation/conflicts. A simplistic localStorage-only workaround is not an acceptable final architecture.

**PROPOSED ARCHITECTURE, NOT APPROVED:** the architecture report suggested controlled offline P0 concepts such as durable queue, client command UUID, server idempotency, reconciliation queue, provisional local receipt, and an offline stock safety reserve/threshold. These are not confirmed SABONO rules.

## 6.9 Roles, Access, and Reporting

**CONFIRMED BUSINESS REQUIREMENT**

Known roles are cashier, warehouse, accountant, manager, and chief/owner. Chief/Owner needs full access and a mobile-friendly Dashboard. Manager may change retail prices, manage promotions, create users, and change user permissions. Accountant needs purchases, supplier payments, expenses, cash, and financial/profit reporting as semantics permit. Cashier needs location-scoped stock visibility.

**OPEN DECISION:** final Retail permission matrix.

Do not call balance “profit”. Do not claim reliable gross profit/margin until historical COGS and landed-cost semantics are sufficient.

# 7. Verified Repository Facts at a Time-Bounded Checkpoint

**VERIFIED REPOSITORY FACT — `madina-platform` HEAD `f02641c098a71e851779d2e59c96af8c0b27cf11`**

The following facts are evidence for that inspected HEAD only; they are not eternal facts and must be re-verified before implementation.

- Product had one global quantity, one unit, `costPrice`, and `salePrice`.
- Barcode, Location, and Packaging/UOM conversion were absent from the current Product model.
- StockMovement supported purchase, sale, and adjustment with no source/destination Location.
- Sale and Purchase each had one paymentMethod.
- Completed Sale/Purchase produced one Transaction.
- CommerceService had SQLite transactional completion boundaries.
- Auth/session foundation existed.
- RBAC roles were `admin`, `manager`, `operator`, and `viewer`; they did not express SABONO Retail roles or location scope.
- Append-only audit foundation existed.
- Reporting used `financialBalance`, not an unsupported claim of profit.
- No current Barcode, Location, Transfer, Return/Exchange, Loyalty, Promotion, Offline Sync, ARCA adapter, or Landed Cost domains were found in that inspection.

**VERIFIED REPOSITORY FACT — `madina-platform` commit `b62ad74503c4d3fa32509807db41d8223b6f6138` — `feat(retail): add generic retail module boundary`**

Stage 1 — Retail boundary foundation is completed with acceptance verdict **STAGE 1 PASS**. It established a new independent `@madina/retail` package, empty Retail namespaces in `@madina/api` and `@madina/database`, and an empty server composition boundary at `/api/v1/retail`. The route boundary returns `404` because no Retail endpoint exists. `@madina/retail` does not depend on `@madina/core`, and `apps/crm` does not depend on `@madina/retail`.

Stage 1 did not create Retail Product, Product Barcode, Location, Retail capability/location grants, Inventory Balance, Retail Stock Movement, Opening Count, Goods Receipt, Transfer, Sale, Sale Item, Payment Allocation, Return, Offline POS, Retail reporting, `apps/retail`, POS UI, Retail migrations, Retail database tables, Retail business mutations, or SABONO data/configuration. CRM behavior and schema remained unchanged.

Verified validation evidence: Retail build and typecheck passed; database build passed and tests passed **71/71**; server build passed and tests passed **112/112**; CRM tests passed **72/72** and production build passed; full repository tests and build passed; `git diff --check` passed.

# 8. Proposed Architecture — Not Approved

**PROPOSED ARCHITECTURE**

The completed read-only architecture report evaluated generic boundaries for Catalog/Product, Product Barcode, potential Packaging/UOM conversion, Location, Inventory Balance, immutable Stock Movement, Transfer, Inventory Count/Reconciliation, Sale/Sale Item, Payment Allocation/Split Payment, Customer, Loyalty, Promotion/Discount, Return/Exchange, Supplier, Supplier Invoice, Supplier Payment, Expense/Landed Cost, Partner stock/sales, Retail RBAC/location scope, offline synchronization, and fiscal adapter.

It proposed relationships such as:

- `Product 1—N Barcode`;
- Product to possible sellable Packaging/UOM conversions;
- Product + Location to inventory balance;
- `Sale 1—N SaleItem`;
- `Sale 1—N PaymentAllocation`;
- Return to original Sale; and
- Supplier Invoice distinct from Supplier Payment.

These are recommendations for review. They are not approved data-model decisions, migrations, API contracts, or implementation instructions.

The user-approved cut-line in the next section approves scope for Technical Design only. It does not approve unspecified technical mechanics or implementation.

# 9. Pilot 0 Cut-Line Status

**APPROVED BY USER FOR TECHNICAL DESIGN**

## P0 — mandatory for the controlled pilot

- Product catalog and stable source ID;
- Product Barcode: factory/internal barcodes resolve one Product, additional barcode does not change quantity, ambiguous source data is quarantined;
- piece-based sale;
- Central Warehouse plus one selected pilot Store;
- location-specific Inventory Balance and immutable attributable Stock Movements;
- two-sided Transfer: `draft → dispatched → received`;
- opening stock validation and daily reconciliation;
- POS Sale / Sale Item;
- split payments: `Sale 1—N Payment Allocations` using cash/card/transfer/other;
- basic authorized item percentage discount;
- full completed Sale/full receipt return;
- Supplier goods receipt into Central Warehouse;
- controlled offline POS functional capability;
- minimum Retail RBAC and Location scope; and
- reconciliation dashboard without profit/margin claim.

## P1 — after validation of the basic Pilot 0

- full quarterly Inventory workflow;
- promotion engine, fixed promotional price, receipt-level discount, loyalty discount, and Loyalty;
- partial item returns and advanced Return/Exchange cases;
- Supplier Invoice, prepayment, Supplier Payment, and payable lifecycle;
- Landed Cost / weighted-average COGS; and
- partner stock/sales/commission.

## Deferred

- Packaging/UOM conversion;
- ARCA/fiscal adapter; and
- Storefront/Marketplace.

# 9.1 Approved Technical Design — Future Implementation Direction

**APPROVED TECHNICAL DESIGN / FUTURE IMPLEMENTATION DIRECTION**

This section records the completed Pilot 0 Technical Design. It is not evidence that any described package, app, table, migration, API, or workflow already exists in `madina-platform`.

## Physical and Product Boundaries

The approved direction is:

```text
Madina Platform
├── Madina CRM
├── Madina Retail
└── SABONO configuration / controlled pilot
```

- Madina CRM remains independently usable.
- Generic Retail capability must not become SABONO-specific.
- Implemented Stage 1 composition boundary: `packages/retail`, Retail namespace in `@madina/api`, Retail namespace in `@madina/database`, and Retail server composition under `/api/v1/retail`. These boundaries are not evidence that a Retail business capability exists.
- Future physical Retail direction may add `apps/retail`, Retail API contracts, and Retail database repositories/migrations only through separately authorized stages.
- SABONO is a configuration/business implementation over generic Madina Retail; no SABONO-specific P0 domain package is required.
- Retail does not depend on the current CRM `@madina/core` aggregate, and CRM does not depend on Retail or SABONO.
- `@madina/ui` remains reusable visual primitives.

`RetailProduct` is an independent Retail catalog identity. CRM Product is not authoritative Retail Product, and CRM `Product.quantity` is not Retail stock. P0 has no implicit CRM ↔ RetailProduct two-way synchronization; SABONO catalog import targets RetailProduct. Any future CRM/Retail master-data mapping or synchronization requires separate design.

## Stock, Sale, Payment, and Return Direction

- Retail StockMovement is immutable operational evidence.
- InventoryBalance is a transactionally maintained current-stock projection. Authoritative operational stock is per `Product + Location`.
- CRM global `Product.quantity` remains legacy CRM behavior. Retail opening balances come from controlled Opening Count evidence; no automatic Retail stock backfill from CRM Product.quantity is approved.
- Sale is location-bound and uses `Sale 1 → N Payment Allocations` with `cash`, `card`, `transfer`, and `other`. The invariant is `sum allocations == Sale payable total`.
- Retail money direction is integer minor units, explicit currency, and a deterministic Retail rounding utility. Exact pilot currency/exponent remains pilot configuration.
- P0 Return is full completed Sale/full receipt only. The original Sale remains immutable; a separate Return aggregate restores stock to the original Sale Location; one completed full Return is permitted per Sale.
- Return Payment Allocations mirror original Sale allocations as **internal Retail refund representation only**. They do not prove card refund execution, bank-transfer refund execution, physical cash refund, ARCA fiscal return, or external payment/fiscal success. ARCA/payment integration remains Deferred; partial Return remains P1.

## Offline Design Status

The confirmed P0 functional direction is durable local operation using IndexedDB, stable client operation ID, server idempotency, automatic retry/sync, exactly-once business effect after server acceptance, and visible reconciliation exceptions.

**OPEN BUSINESS DECISION — BLOCKS OFFLINE POS IMPLEMENTATION ONLY:** if an offline Sale has physically delivered goods and accepted money but later server synchronization rejects it because current server stock is insufficient, SABONO must define the authorized operating policy. Do not infer automatic negative stock, safety reserve, hidden adjustment, silent acceptance, or automatic refund/recovery behavior.

This blocks Offline POS implementation and Offline live-pilot readiness only. It does not block non-offline P0 implementation planning or foundation work.

## Approved Future Implementation Sequence

1. Retail boundary foundation;
2. Location + early Retail RBAC foundation;
3. Retail Product / Barcode / import;
4. Inventory ledger foundation;
5. Opening counts / reconciliation evidence;
6. Goods Receipt;
7. Transfer;
8. POS Sale / Payment Allocation;
9. Authorized item discount;
10. Full completed-Sale Return;
11. Offline POS sync;
12. Retail reporting / reconciliation dashboard;
13. Complete P0 permission hardening;
14. Pilot import / bootstrap; and
15. Pilot readiness verification.

Stage 2 is required before protected Retail mutations. Stage 13 is hardening/verification and does not replace the early authorization foundation. Stage 11 is blocked by the Offline operating-policy decision above.

# 9.2 Canonical Implementation Plan — Future Work Only

**ACCEPTED IMPLEMENTATION PLAN / STAGES 1–2 SUBSEQUENTLY COMPLETED**

The canonical future sequence is:

1. Retail boundary foundation;
2. Location + early Retail RBAC foundation;
3. Retail Product / Barcode / import;
4. Inventory ledger foundation;
5. Opening counts / reconciliation evidence;
6. Goods Receipt;
7. Transfer;
8A. Sale domain / draft / idempotency foundation;
8B. Money / Payment Allocation / atomic Sale completion;
8C. Retail POS UI;
9. Authorized item discount;
10. Full completed-Sale Return;
11. Offline POS sync;
12. Retail reporting / reconciliation dashboard;
13. Complete P0 permission hardening;
14. Pilot import / bootstrap; and
15. Pilot readiness verification.

Each is a separately authorized implementation boundary. Recording this plan does not start, authorize, or complete any implementation stage.

## Stage 8 Sale Safety Boundary

Stage 8A is limited to Sale/SaleItem domain foundation, draft lifecycle, validation/contracts, and operation ID/payload-hash/idempotency primitives. It must not create a completed Sale, Sale stock decrement, completed-Sale business effect, completed-Sale audit event, or payment-pending completed Sale. At the end of 8A, there is no supported completed P0 Sale.

Stage 8B is the first stage permitted to create a completed Retail Sale. Its invariant is `SUM(PaymentAllocation.amount) == Sale.payableTotal`.

The completed-Sale transaction must atomically cover authorization/location validation; Sale/Product/item validation; deterministic money calculation; Payment Allocation and exact-total validation; guarded Store stock decrement; immutable Sale StockMovement; completed Sale/SaleItems/Payment Allocations; idempotency receipt; and audit evidence. Any failure rolls back the complete business effect.

Stage 8A does not require a persistent Retail Sale migration. Stage 8B provisionally introduces combined additive migration `037_retail_sales_payment_completion_v1` for `retail_sales`, `retail_sale_items`, `retail_payment_allocations`, and `retail_operation_receipts`. Subsequent provisional direction is `038_retail_sale_discounts_v1`, `039_retail_returns_v1`, and `040_retail_reporting_indexes_v1`. Migration numbering must be rechecked against the actual registry immediately before implementation.

## Access, Money, Offline, and Bootstrap Gates

Existing global Auth roles remain `admin`, `manager`, `operator`, and `viewer`. The approved access model is:

```text
Authenticated User
→ existing Auth/session/base role
→ Retail capabilities
→ Retail Location grants
→ server-side Retail command authorization
```

Cashier/Warehouse/Retail Manager/Owner behavior is expressed through Retail capability profiles/grants unless future implementation evidence requires a separately approved change. CRM retains current Auth behavior and does not depend on Retail grants.

Generic Stage 8B money support uses `currency_code`, configurable exponent, integer minor units, and deterministic rounding. The exact deterministic rounding rule must be selected and tested before 8B can complete a Sale. SABONO pilot currency/exponent is configuration required before actual SABONO bootstrap/payment configuration, financial acceptance, and live-pilot use; it does not block generic Retail foundation work.

Stage 11 remains blocked by the Offline physical-goods/accepted-money rejected-sync operating-policy decision. It blocks Stage 11 business-effect implementation and Offline live-pilot readiness only; it does not block Stages 1–10, Stage 12 without Offline metrics, Stage 13, or allowed Stage 14 tooling.

Stage 14 tooling may prepare import dry run, validation, quarantine, content hash, repeatability, bootstrap validation/reporting, and backup/restore tooling through separately authorized stages. Actual SABONO pilot bootstrap requires all required non-offline P0 operational/security stages completed and accepted, Stage 12 reporting/reconciliation, Stage 13 permission hardening, selected pilot Store/register/users, Location grants, SABONO currency/exponent, backup/restore rehearsal, catalog and opening-balance sign-off, and explicit authorization to load actual pilot data. Actual bootstrap does not mean Live Pilot ready. Because Offline is required P0 capability, final Live Pilot readiness also requires Stage 11 blocker resolution and Offline validation.

**Next planned implementation stage:** **Stage 3 — Retail Product / Barcode / import** — **NOT STARTED**. This is a planned next stage only and requires separate explicit implementation authorization.

# 10. Current Open Decisions and Pilot Blockers

| Item | Classification | Required by |
| --- | --- | --- |
| Offline physical-goods/accepted-money rejected-sync policy | **OPEN BUSINESS DECISION** | Before Offline POS implementation only |
| Exact Retail rounding implementation | **OPEN TECHNICAL DECISION** | Before POS implementation |
| Exact Retail capability naming and membership schema | **OPEN TECHNICAL DECISION** | Before early RBAC/location foundation |
| Offline command retention/pruning | **OPEN TECHNICAL DECISION** | Before Offline POS implementation |
| Exact pilot Store/register, users, and dates | **LIVE PILOT PARAMETER** | Before live pilot |
| Stock/money discrepancy tolerances and escalation rules | **LIVE PILOT PARAMETER** | Before live pilot acceptance |
| Offline outage-test duration and reconciliation procedure | **LIVE PILOT PARAMETER** | Before live pilot validation |
| Pilot currency/exponent | **LIVE PILOT PARAMETER** | Before POS pilot configuration |
| Catalog/opening-stock sign-off | **LIVE PILOT PARAMETER** | Before live pilot |
| Loyalty tier transitions and complete promotion/loyalty rules | **P1 BUSINESS/TECHNICAL** | Before P1 scope |
| Advanced Return/Exchange cases | **P1 BUSINESS/TECHNICAL** | Before P1 scope |
| Supplier Invoice/Payment/Payable details | **P1 BUSINESS/TECHNICAL** | Before P1 scope |
| Landed Cost technical semantics | **P1 TECHNICAL DESIGN** | Before P1 costing/profit reporting |
| Partner commission/rules | **P1 BUSINESS/TECHNICAL** | Before P1 partner scope |

**NO KNOWN BUSINESS DECISION BLOCKS PILOT 0 TECHNICAL DESIGN.**

# 11. Deferred Boundaries

**DEFERRED** from the approved Pilot 0 cut-line:

- Packaging/UOM conversion;
- ARCA/fiscal adapter; and
- Storefront/Marketplace.

# 12. Current Status and Next Authorized Stage

| Area | Status |
| --- | --- |
| Business Requirements / Fit-Gap foundation | Sufficient for architecture |
| Technical Fit-Gap | Completed |
| Storefront Readiness Audit | Completed |
| Pilot 0 Architecture & Scope report | **COMPLETED AS READ-ONLY PROPOSAL** |
| Pilot 0 Architecture Review / Cut-Line Decision | Completed |
| Cut-line | **APPROVED FOR TECHNICAL DESIGN** |
| Pilot 0 Technical Design | Completed |
| Technical Design verdict | **READY WITH TECHNICAL OPEN ITEMS** |
| Pilot 0 Implementation Planning | Completed |
| Implementation Plan verdict | **IMPLEMENTATION PLAN READY WITH BLOCKED OFFLINE STAGE** |
| Pilot 0 Implementation | **IN PROGRESS** |
| Stage 1 — Retail boundary foundation | **COMPLETED / STAGE 1 PASS** |
| Stage 2 — Location + early Retail RBAC foundation | **COMPLETED / STAGE 2 PASS** |
| Stage 11 — Offline POS sync | **BLOCKED** pending approved rejected-sync operating policy |
| Live Pilot | **NOT STARTED** |

The original architecture-report verdict was **BLOCKED — BUSINESS INPUT REQUIRED**. It remains historical evidence for the initial read-only report and has been superseded for cut-line purposes by the completed user-approved review.

**Next planned implementation stage:** **Stage 3 — Retail Product / Barcode / import** — **NOT STARTED**; it requires separate explicit implementation authorization.

Stage 2 established the mandatory authorization/location foundation before protected Retail mutations. Its completion does not authorize Stage 3, later migrations, implementation beyond Stage 2, or Live Pilot automatically.

# 13. SABONO Retail User & Operating Guide Requirement

**REQUIRED PILOT DELIVERABLE — FUTURE / NOT YET CREATED**

A future **SABONO Retail User & Operating Guide** is required for practical, role-oriented operating instructions for SABONO staff using Madina Retail. It must describe actual accepted system behavior, evolve with implementation, and never present planned functionality as implemented.

Expected operational audiences are Cashier, Warehouse staff, Retail Manager, Owner / Chief, and Administrator. These are guide audiences only; they do not create or reinterpret global `@madina/auth` roles.

After the corresponding functionality is implemented and accepted, the guide is expected to cover login and access; Retail capabilities and Location access; Product/barcode lookup; goods receipt; Location-specific stock visibility; opening stock and reconciliation; Transfers (create, dispatch, receive); POS Sale (scan/find Product, quantity, authorized item discount, Payment Allocations/split payment, completion); full completed-Sale Return; daily reconciliation; dashboard/report interpretation; common errors and safe recovery actions; actions users must not perform; and manager approval/escalation cases.

User instructions are evidence-based. A workflow becomes operational documentation only after the corresponding functionality is implemented and accepted. Planned, Deferred, and Blocked capabilities must be clearly distinguished from implemented functionality; screenshots, if used, must reflect the actual accepted UI; instructions must be updated when accepted behavior materially changes; and guide language must be practical for SABONO employees. Where role or Location permissions matter, the guide must clearly state what a user may see and do.

The future guide must include appropriate safety/control instructions: do not bypass Location access controls; do not correct stock through unsupported or manual database operations; do not treat CRM `Product.quantity` as authoritative Retail stock; do not invent unsupported financial adjustments; use supported workflows for completed Sale/Return operations; do not describe internal Return Payment Allocation representation as proof of external card, bank, or fiscal refund execution; and do not silently bypass blocked or rejected operations.

Offline POS instructions may be added only after the Stage 11 rejected-sync operating policy is approved, Offline behavior is implemented, and actual behavior is accepted and verified. Offline conflicts must then follow that approved SABONO operating policy. No Offline procedure is recorded now.

Stage 1 introduced only the generic Retail architectural boundary. It has no SABONO end-user Retail workflow requiring a user procedure, so no operational instruction is written for Stage 1. This requirement is recorded now so documentation evolves with later accepted implementation stages; it does not create a guide, cashier/warehouse/manager manual, screenshots, SOP, training material, or instructions for unimplemented functionality.

Before Stage 15 — Pilot readiness verification, the required SABONO Retail User & Operating Guide must be reviewed against the actual implemented Pilot system. Stage 15 must verify, where applicable, that required operational workflows are documented; instructions and any screenshots match accepted behavior and UI; roles/Location permissions are accurately represented; Blocked/P1/Deferred functionality is not presented as available; and known operational escalation paths are documented. Documentation readiness is one component of Pilot readiness and does not by itself establish Live Pilot readiness.

# 14. Evidence References

## Controlled Documentation

- MB-004 — Master Plan (Draft)
- MB-100 — System Architecture (Draft)
- MB-101 — Data Architecture (Draft)
- MB-102 — Engineering Standards (Draft)
- MB-ENG-001 — Evidence-Based Engineering Execution Protocol (Draft)
- MB-SOP-001 — Documentation Workflow (Draft)
- MB-CRM-001 through MB-CRM-008 — CRM specifications (Draft)
- MB-PLATFORM-CRM-CHK-001 — Madina Platform / CRM Canonical Project Checkpoint (Draft)
- MB-PORT-REG-001 — Ecosystem & Project Portfolio Registry (Draft)

## Repository Evidence

- `madina-platform` inspected at `f02641c098a71e851779d2e59c96af8c0b27cf11` during the completed read-only Pilot 0 Architecture & Scope stage.
- `madina-platform` verified at `b62ad74503c4d3fa32509807db41d8223b6f6138` for completed Stage 1 — Retail boundary foundation.
- `madina-platform` verified at `197173b6922a0242e15c0a211e965ac465c9b18b` for completed Stage 2 — Location + early Retail RBAC foundation. Accepted validation: Retail route tests 2/2 PASS; database tests 74/74 PASS; server tests 113/113 PASS; CRM tests 72/72 PASS; CRM production build PASS; full `pnpm build` PASS; full `pnpm test` PASS; and `git diff --check` PASS.

# Version History

| Version | Status | Description |
| --- | --- | --- |
| 0.1.7 | Draft | Recorded completed Stage 2 — Location + early Retail RBAC foundation with `STAGE 2 PASS` at `197173b6922a0242e15c0a211e965ac465c9b18b`, factual scope/security/runtime-regression evidence, and accepted validation. Stage 3 remains not started; Stage 11 Offline POS remains blocked; Live Pilot remains not started. |
| 0.1.6 | Draft | Recorded the future SABONO Retail User & Operating Guide as a required Pilot deliverable, its evidence-based lifecycle and safety expectations, and Stage 15 documentation-readiness verification. No guide, procedure, screenshot, training material, or unimplemented workflow documentation was created. |
| 0.1.5 | Draft | Recorded completed Stage 1 — Retail boundary foundation with `STAGE 1 PASS`, verified implementation and validation evidence at `b62ad74503c4d3fa32509807db41d8223b6f6138`, and the Stage 2 next-stage boundary. No Retail business capability, migration, POS UI, SABONO configuration, or later stage was started. |
| 0.1.4 | Draft | Recorded completed accepted Pilot 0 Implementation Planning, canonical stage sequence, safe Stage 8A/8B Sale boundary, access/money/bootstrap gates, and the Offline Stage 11-only blocker; no implementation stage started. |
| 0.1.3 | Draft | Recorded completed Pilot 0 Technical Design, its `READY WITH TECHNICAL OPEN ITEMS` verdict, independent Retail/CRM boundary, P0 stock/payment/return direction, corrected authorization-first implementation sequence, and the Offline operating-policy blocker limited to Offline POS. |
| 0.1.2 | Draft | Recorded completed Pilot 0 Architecture Review, user-approved P0/P1/Deferred cut-line, confirmed Landed Cost rules, and confirmed full receipt return P0 scope; Technical Design remains not started. |
| 0.1.1 | Draft | Corrected barcode and piece-sale business evidence; moved the unconfirmed `1 BOX = 6 PCS` model from Confirmed to proposed/deferred; retained Landed Cost/COGS as P1 open decisions with required business questions. |
| 0.1.0 | Draft | Initial controlled SABONO Retail continuity checkpoint; records evidence, completed audits, proposed architecture, open decisions, and next authorized review stage without approving implementation. |
