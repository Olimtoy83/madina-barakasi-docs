# MB-DEC-002 — Arabic Typography Architecture

> **Design decision for the canonical Madina Barakasi Arabic typography architecture**

---

## Document Information

| Field          | Value                     |
| -------------- | ------------------------- |
| Document ID    | MB-DEC-002                |
| Volume         | III — Design & Experience |
| Title          | Arabic Typography Architecture |
| Version        | 1.0.0                     |
| Status         | Approved                  |
| Classification | Design Decision           |
| Language       | English                   |
| Owner          | Design & Experience       |
| Created        | 2026-08-20                |
| Last Updated   | 2026-08-20                |

---

# 1. Context

Madina Barakasi operates across institutional, product, CRM / ERP, documentation, multilingual, and Saudi / Arabic environments. These contexts require an Arabic typography architecture that is legible, technically controlled, and compatible with the established Latin typography roles without creating competing primary Arabic typefaces.

The Arabic typography exploration, micro validation, specification, and canonical-readiness review established a preferred direction suitable for human approval.

This decision records the approved family architecture. It does not approve Arabic brand spelling, bilingual lockup geometry, final production typography tokens, application-level RTL / Bidi component behavior, or production implementation.

---

# 2. Decision

The canonical Arabic typography foundation for Madina Barakasi is:

**IBM Plex Sans Arabic**

The primary controlled Arabic fallback is:

**Noto Sans Arabic**

The canonical controlled fallback architecture is:

```text
IBM Plex Sans Arabic
→ Noto Sans Arabic
→ sans-serif
```

Noto Sans Arabic is a controlled fallback. It is not a parallel primary Arabic identity typeface.

---

# 3. Weight Architecture

The approved static weight set is:

- **400** — regular reading and body content
- **500** — labels, navigation, and emphasized operational UI
- **600** — headings and controlled emphasis

Synthetic bold, synthetic italic, and unnecessary additional weights must not be introduced silently.

Any future implementation must use explicit available font files and must not request unavailable weight or style combinations as though they were approved assets.

---

# 4. Role Architecture

The Arabic typography foundation operates within the approved dual-family architecture.

## 4.1 Brand / Institutional

**Source Sans 3 + IBM Plex Sans Arabic**

Source Sans 3 provides the Latin institutional role. IBM Plex Sans Arabic provides the corresponding Arabic role.

## 4.2 CRM / ERP / Operational

**Inter + IBM Plex Sans Arabic**

Inter provides the Latin operational role, including operational numerical and code-oriented presentation where appropriate. IBM Plex Sans Arabic provides Arabic interface prose and Arabic UI content.

Arabic typography must not be mechanically forced to match Latin font metrics. Pairing decisions must preserve optical hierarchy, reading rhythm, and role clarity across scripts.

---

# 5. RTL / Bidi Principle

The canonical Arabic typography architecture relies on native browser RTL and Bidi behavior.

Architectural principles are:

- Arabic document or content roots use RTL direction where the content is Arabic.
- Logical layout properties are preferred over physical left / right layout rules.
- Arabic prose follows the native direction and reading order of the browser.
- Isolated LTR operational values may require explicit isolation where they occur inside RTL content.

Detailed application-level behavior for tables, forms, navigation, phone numbers, currencies, dates, identifiers, codes, and other component cases remains implementation engineering guidance. It is not defined here as canonical typography tokens.

---

# 6. Size and Line-Height Boundary

Reviewed Arabic size and line-height scales exist and may inform downstream typography specification, semantic token work, and implementation guidance.

Passing a specimen does not make every tested numeric value canonical. Exact final production tokens require their own controlled specification and implementation review.

The 12 px Arabic condition remains diagnostic only. It is not an approved general production size or a canonical typography token.

---

# 7. Fallback Governance

The controlled fallback chain is limited to:

```text
IBM Plex Sans Arabic
→ Noto Sans Arabic
→ sans-serif
```

Tahoma and Arial are not canonical controlled Arabic fallbacks. A generic `sans-serif` entry permits the platform to select an appropriate system fallback only after the two controlled Arabic families are unavailable.

---

# 8. Technical Asset Integrity

The canonical family architecture depends on exact static font assets for the approved 400, 500, and 600 weights of IBM Plex Sans Arabic and Noto Sans Arabic.

Before production implementation, the exact asset names, source or release reference, SHA-256 values, applicable license text, and copyright notices must be captured in a production asset manifest.

This decision does not reproduce hashes that are not stored here as verified production-manifest evidence.

---

# 9. Licensing

Technical licensing evidence for IBM Plex Sans Arabic and Noto Sans Arabic identifies the SIL Open Font License, Version 1.1.

Production distribution of the font software must preserve applicable license and copyright notices. Final organizational legal release review remains a separate gate and is not replaced by this technical licensing evidence.

---

# 10. Arabic Brand Spelling

No Arabic spelling of **Madina Barakasi** is approved by this decision.

Any Arabic spelling used in prior typography specimens was diagnostic only. Typography testing must not be treated as a decision on official localized brand naming.

---

# 11. Lockups

This decision does not approve bilingual lockup geometry.

The Arabic typography foundation may inform a later bilingual lockup decision, but it does not establish symbol-to-name proportions, alignment, spacing, or any Arabic wordmark treatment.

---

# 12. Relationship to Existing Documentation

This decision operates with:

- MB-200 — Design System
- MB-201 — Visual Identity Foundation
- MB-DEC-001 — Brandmark Architecture
- MB-ADR-001 — Symbol Independent From Name
- MB-DEC-INDEX — Design Decisions Index

MB-200 defines the Design System framework. MB-201 defines the Visual Identity Foundation. MB-DEC-001 defines the approved brandmark architecture. MB-ADR-001 establishes symbol independence from the textual name.

This decision defines the approved Arabic typography family architecture within those boundaries.

---

# 13. Consequences

This decision establishes that:

- Arabic typography now has a canonical family architecture.
- IBM Plex Sans Arabic is the canonical primary Arabic typography foundation.
- Noto Sans Arabic remains the controlled Arabic fallback and is not a parallel primary identity typeface.
- Future Arabic typography tokens and implementation work must inherit this architecture.
- Implementation must not silently substitute another primary Arabic family.
- Arabic brand spelling and bilingual lockup geometry remain separate decisions.
- Future changes to the canonical Arabic typography architecture require a reviewed Design Decision.

This decision does not authorize production font integration or application changes.

---

# 14. Status

This document records the human-approved Arabic Typography Architecture decision.

This decision is **Approved** and defines the canonical Arabic typography family architecture for Madina Barakasi.

---

**Madina Barakasi Design & Experience Library**
