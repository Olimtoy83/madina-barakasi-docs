# MB-DEC-Index — Design Decisions Index

> **Index of design decisions for the Madina Barakasi Platform**

---

## Document Information

| Field          | Value                     |
| -------------- | ------------------------- |
| Document ID    | MB-DEC-INDEX              |
| Volume         | III — Design & Experience |
| Title          | Design Decisions Index    |
| Version        | 0.1.3                     |
| Status         | Draft                     |
| Classification | Registry                  |
| Language       | English                   |
| Owner          | Design & Experience       |
| Created        | 2026-08-08                |
| Last Updated   | 2026-08-21                |

---

# 1. Purpose

This document provides an index of documented design decisions within the Madina Barakasi Platform.

The index provides a navigational reference to Architecture Decision Records and other formally documented design decisions.

It does not replace the individual decision documents.

---

# 2. Design Decision Registry

| ID | Decision | Status | Related Standard |
| --- | --- | --- | --- |
| MB-ADR-001 | Symbol Independent From Name | Draft | MB-STD-007 |
| MB-DEC-001 | Brandmark Architecture | Approved | MB-STD-007 |
| MB-DEC-002 | Arabic Typography Architecture | Approved | MB-201 / MB-200 |

| MB-DEC-003 | Latin Wordmark and Horizontal Lockup Architecture | Approved | MB-201 / MB-200 |

---

# 3. Decision Records

## MB-ADR-001 — Symbol Independent From Name

**Status:** Draft

The symbol is treated as an element that remains independent from the textual name.

The symbol and textual name may be combined through an approved lockup, but they remain independently maintainable elements.

**Related documents:**

- MB-ADR-001 — Symbol Independent From Name
- MB-STD-007 — Symbol Design Principles
- MB-200 — Design System

---

## MB-DEC-001 — Brandmark Architecture

**Status:** Approved

B2.1-S1 Canonical Pass 5 is the primary Madina Barakasi brandmark.

B2.1-S1-MICRO Pass 2 is the approved optical companion for the 16–23 px size range.

The Canonical and Micro geometries form one controlled brandmark architecture and must not be modified without a new reviewed design decision.

**Related documents:**

- MB-DEC-001 — Brandmark Architecture
- MB-STD-007 — Symbol Design Principles
- MB-ADR-001 — Symbol Independent From Name
- MB-200 — Design System

---

## MB-DEC-002 — Arabic Typography Architecture

**Status:** Approved

IBM Plex Sans Arabic is the canonical Arabic typography foundation. Noto Sans Arabic is the controlled primary Arabic fallback.

The controlled fallback architecture is: IBM Plex Sans Arabic → Noto Sans Arabic → sans-serif.

The approved static weights are 400, 500, and 600. Source Sans 3 + IBM Plex Sans Arabic is the institutional pairing architecture. Inter + IBM Plex Sans Arabic is the operational pairing architecture.

Arabic brand spelling and bilingual lockup geometry remain outside this decision.

**Related documents:**

- MB-DEC-002 — Arabic Typography Architecture
- MB-201 — Visual Identity Foundation
- MB-200 — Design System
- MB-DEC-001 — Brandmark Architecture
- MB-ADR-001 — Symbol Independent From Name

---

## MB-DEC-003 — Latin Wordmark and Horizontal Lockup Architecture

**Status:** Approved

Source Sans 3 static 500 is the canonical Madina Barakasi Latin wordmark typeface and weight.

The canonical wordmark uses `0 em` tracking with native OpenType spacing and kerning.

L2 / Balanced Optical is the approved horizontal lockup architecture.

With `S` defined as symbol height, the approved normalized relationships are:

- Wordmark size: `0.2556 S`
- Symbol-to-wordmark gap: `0.2667 S`
- Optical raise: `0.0111 S`
- Practical minimum complete horizontal lockup: `S = 48 px`

Vertical and Arabic / bilingual lockup architectures remain outside this decision.

**Related documents:**

- MB-DEC-003 — Latin Wordmark and Horizontal Lockup Architecture
- MB-201 — Visual Identity Foundation
- MB-200 — Design System
- MB-DEC-001 — Brandmark Architecture
- MB-DEC-002 — Arabic Typography Architecture
- MB-ADR-001 — Symbol Independent From Name

---
# 4. Governance

New design decisions should be documented before or alongside implementation when the decision has a material and reusable impact on the platform's design system.

Each decision should:

- have a unique identifier;
- state the context;
- record the decision;
- describe the consequences;
- identify relevant alternatives where appropriate;
- reference related standards and documents.

---

# 5. Status

This index is a Draft registry.

Additional decisions will be added as they are formally documented.

---

**Madina Barakasi Design & Experience Library**
