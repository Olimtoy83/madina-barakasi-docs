# SABONO Retail Canonical Project Checkpoint

> **Controlled continuity checkpoint for SABONO Retail as the first Madina Retail pilot**

---

## Document Information

| Field | Value |
| --- | --- |
| Document ID | MB-SABONO-RETAIL-CHK-001 |
| Title | SABONO Retail Canonical Project Checkpoint |
| Version | 0.1.2 |
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

The Technical Fit-Gap identified these major gaps: multi-location stock; split payments; offline POS; product/import requirements; supplier invoice/payment lifecycle; discount/promotion/loyalty; and reliable COGS/profit semantics.

Existing Madina Platform foundations are to be reused and extended, not replaced.

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

# 10. Current Open Decisions and Pilot Blockers

| Item | Classification | Required by |
| --- | --- | --- |
| Atomic Sale/Payment/stock/return/transfer semantics | **TECHNICAL DESIGN** | Before P0 implementation |
| Offline durable operation/idempotency/sync/conflict design | **TECHNICAL DESIGN** | Before P0 implementation |
| P0 RBAC permission details and Location enforcement | **TECHNICAL DESIGN** | Before P0 implementation |
| Barcode import validation/quarantine mechanics | **TECHNICAL DESIGN** | Before P0 catalog import |
| Exact pilot Store/register, users, and dates | **LIVE PILOT PARAMETER** | Before live pilot |
| Stock/money discrepancy tolerances and escalation rules | **LIVE PILOT PARAMETER** | Before live pilot acceptance |
| Offline outage-test duration and reconciliation procedure | **LIVE PILOT PARAMETER** | Before live pilot validation |
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
| Pilot 0 Architecture & Scope report | Completed as read-only proposal; not yet approved |
| Pilot 0 Architecture Review / Cut-Line Decision | Completed |
| Cut-line | Approved by user for Technical Design |
| Pilot 0 Technical Design | Not started |
| Pilot 0 implementation | Not started |
| Live Pilot | Not started |

The original architecture-report verdict was **BLOCKED — BUSINESS INPUT REQUIRED**. It remains historical evidence for the initial read-only report and has been superseded for cut-line purposes by the completed user-approved review.

**Next authorized activity:** **PILOT 0 TECHNICAL DESIGN SPECIFICATION** — read-only / no implementation.

It must specify the user-approved P0 scope without creating migrations, code, commits, or implementation. It does not authorize implementation automatically.

# 13. Evidence References

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

# Version History

| Version | Status | Description |
| --- | --- | --- |
| 0.1.2 | Draft | Recorded completed Pilot 0 Architecture Review, user-approved P0/P1/Deferred cut-line, confirmed Landed Cost rules, and confirmed full receipt return P0 scope; Technical Design remains not started. |
| 0.1.1 | Draft | Corrected barcode and piece-sale business evidence; moved the unconfirmed `1 BOX = 6 PCS` model from Confirmed to proposed/deferred; retained Landed Cost/COGS as P1 open decisions with required business questions. |
| 0.1.0 | Draft | Initial controlled SABONO Retail continuity checkpoint; records evidence, completed audits, proposed architecture, open decisions, and next authorized review stage without approving implementation. |
