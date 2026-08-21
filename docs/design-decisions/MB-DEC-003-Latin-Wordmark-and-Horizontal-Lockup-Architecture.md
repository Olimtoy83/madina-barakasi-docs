# MB-DEC-003 — Latin Wordmark and Horizontal Lockup Architecture

> **Design decision for the canonical Madina Barakasi Latin wordmark and horizontal lockup architecture**

---

## Document Information

| Field          | Value                                         |
| -------------- | --------------------------------------------- |
| Document ID    | MB-DEC-003                                    |
| Volume         | III — Design & Experience                     |
| Title          | Latin Wordmark and Horizontal Lockup Architecture |
| Version        | 1.0.0                                         |
| Status         | Approved                                      |
| Classification | Design Decision                               |
| Language       | English                                       |
| Owner          | Design & Experience                           |
| Created        | 2026-08-21                                    |
| Last Updated   | 2026-08-21                                    |

---

# 1. Context

The Madina Barakasi visual identity requires a controlled Latin wordmark and a reproducible horizontal relationship between the approved brandmark and textual name.

Prior typography and lockup review selected Source Sans 3 static 500 with neutral tracking and the L2 / Balanced Optical horizontal direction. A subsequent canonicalization pass normalized the reviewed relationship against symbol height and established a practical minimum for the complete horizontal lockup.

This decision records the approved Latin wordmark role and horizontal lockup architecture.

It does not redefine the approved brandmark geometry, Arabic typography architecture, broader institutional typography system, operational interface typography, vertical lockup, or bilingual lockup.

---

# 2. Decision

The canonical Madina Barakasi Latin wordmark uses:

**Source Sans 3 static 500**

with:

**0 em tracking and native OpenType spacing and kerning**

The approved horizontal symbol + Latin wordmark architecture is:

**L2 / Balanced Optical**

The horizontal relationship is normalized against symbol height and must preserve the independence and integrity of the approved brandmark.

---

# 3. Canonical Latin Wordmark

Source Sans 3 static 500 is approved specifically for the **Madina Barakasi Latin wordmark role**.

The wordmark remains a separate typographic identity element from the brandmark.

This decision does not establish Source Sans 3 as the universal typeface for all Madina Barakasi platform interfaces, operational applications, or documentation roles.

Broader institutional typography and CRM / ERP operational typography remain governed separately.

The wordmark must not alter, replace, or become a structural dependency of the approved brandmark.

---

# 4. Tracking and Kerning

The canonical Latin wordmark tracking value is:

**0 em**

The wordmark uses the font's native OpenType spacing and kerning behavior.

Artificial positive or negative tracking must not be introduced as though it were part of the canonical wordmark architecture.

Any future change to canonical wordmark tracking requires explicit reviewed approval.

---

# 5. Horizontal Lockup Architecture

The approved horizontal lockup architecture is:

**L2 / Balanced Optical**

The architecture combines:

- the approved Madina Barakasi brandmark;
- the canonical Latin wordmark;
- a normalized symbol-to-wordmark gap;
- a controlled optical vertical adjustment.

The lockup must preserve:

- brandmark integrity;
- wordmark readability;
- clear hierarchy;
- optical balance;
- reproducible spacing;
- symbol independence.

The horizontal lockup is a controlled composition of two independently governed identity elements. It does not merge the textual name into the Canonical symbol geometry.

---

# 6. Normalized Geometry

Let:

**S = symbol height**

The approved normalized horizontal relationships are:

- Wordmark size = **0.2556 S**
- Symbol-to-wordmark gap = **0.2667 S**
- Wordmark optical raise = **0.0111 S**

These ratios normalize the reviewed L2 / Balanced Optical relationship and replace reliance on a single fixed-size specimen.

For the original reviewed reference condition:

- Symbol height: `180 px`
- Wordmark size: approximately `46 px`
- Symbol-to-wordmark gap: approximately `48 px`
- Optical raise: approximately `2 px`

The normalized ratios govern the relationship rather than those individual reference pixel values.

---

# 7. Optical Alignment

The wordmark optical raise is:

**0.0111 S**

This value is a controlled optical correction within the approved horizontal lockup architecture.

It exists to preserve the reviewed visual relationship between the symbol and Latin wordmark.

It must not be interpreted as:

- a general spacing token;
- a general typography token;
- a universal vertical-alignment rule;
- a component positioning token.

Its scope is limited to the canonical horizontal Latin lockup defined by this decision.

---

# 8. Minimum Horizontal Lockup Size

The practical approved minimum for the complete horizontal Latin lockup is:

**S = 48 px**

At this symbol height, the normalized wordmark size is approximately:

**12.3 px**

A complete horizontal lockup using:

**S = 40 px**

remains diagnostic only and is not approved as the normal production minimum.

Below the practical horizontal-lockup minimum, symbol-only presentation should be preferred according to the approved brandmark size architecture in MB-DEC-001.

This horizontal-lockup minimum does not redefine the minimum sizes for symbol-only use.

---

# 9. Relationship to Brandmark Architecture

MB-DEC-001 remains authoritative for the Madina Barakasi brandmark architecture.

Its approved symbol-size rules remain unchanged:

- **24 px and above:** B2.1-S1 Canonical Pass 5
- **16–23 px:** B2.1-S1-MICRO Pass 2
- **Below 16 px:** no approved brandmark geometry

The horizontal lockup architecture defined here does not modify those rules.

The symbol remains independently usable from the textual name in accordance with MB-ADR-001.

The Canonical and Micro brandmark geometries must not be modified to accommodate the wordmark or horizontal lockup.

---

# 10. Technical Asset Integrity

The reviewed Latin wordmark asset is:

`SourceSans3-500.ttf`

The verified SHA-256 value for the reviewed static asset is:

`3772689BDEF0CD284428994189D89D1FD412591E8906FB5BD0C4692A3314CBE7`

This decision applies to the reviewed static 500 asset and does not define a variable-font configuration.

A production asset manifest must preserve the verified identity of the font asset before production integration.

Unverified asset substitutions must not be treated as equivalent canonical wordmark assets.

---

# 11. Licensing and Distribution Boundary

Source Sans 3 licensing and source evidence were reviewed during typography evaluation.

The exact production source and distribution record must be captured as part of production-readiness documentation before font integration and distribution.

Final organizational legal release remains a separate gate.

This decision does not invent or approve unverified distribution metadata and does not replace organizational legal review.

---

# 12. Excluded Decisions

This decision does not approve:

- vertical lockup geometry;
- Arabic or bilingual lockup geometry;
- Arabic brand spelling;
- a complete institutional typography system beyond the canonical Latin wordmark role;
- CRM / ERP Latin typography canonicalization;
- production typography tokens;
- application-level typography implementation;
- final organizational legal release;
- unverified font source or distribution metadata.

MB-DEC-002 remains authoritative for the approved Arabic typography family architecture.

This decision does not redefine IBM Plex Sans Arabic, Noto Sans Arabic fallback governance, Arabic weight architecture, RTL / Bidi principles, Arabic brand spelling, or bilingual lockup geometry.

---

# 13. Relationship to Existing Documentation

This decision operates with:

- MB-200 — Design System
- MB-201 — Visual Identity Foundation
- MB-DEC-001 — Brandmark Architecture
- MB-DEC-002 — Arabic Typography Architecture
- MB-ADR-001 — Symbol Independent From Name
- MB-DEC-INDEX — Design Decisions Index

MB-200 defines the broader Design System framework.

MB-201 defines the Visual Identity Foundation.

MB-DEC-001 defines the approved brandmark architecture and symbol-size governance.

MB-DEC-002 defines the approved Arabic typography family architecture.

MB-ADR-001 establishes symbol independence from the textual name.

This decision defines the canonical Latin wordmark role and horizontal symbol + Latin wordmark relationship within those boundaries.

---

# 14. Consequences

This decision establishes that:

- Source Sans 3 static 500 is the canonical Madina Barakasi Latin wordmark typeface and weight.
- The canonical Latin wordmark uses `0 em` tracking with native OpenType spacing and kerning.
- L2 / Balanced Optical is the approved horizontal lockup architecture.
- Horizontal lockup geometry is normalized against symbol height.
- Wordmark size is `0.2556 S`.
- Symbol-to-wordmark gap is `0.2667 S`.
- Optical raise is `0.0111 S`.
- The practical minimum complete horizontal lockup uses `S = 48 px`.
- The `S = 40 px` complete lockup remains diagnostic only.
- Symbol-only size governance remains unchanged.
- The symbol remains independently usable from the wordmark.
- Vertical and bilingual lockup architectures remain unresolved.
- Future changes to this canonical Latin wordmark or horizontal lockup architecture require a new reviewed Design Decision.

This decision does not authorize production implementation by itself.

---

# 15. Status

This document records the human-approved Latin Wordmark and Horizontal Lockup Architecture decision.

This decision is **Approved** and defines the canonical Madina Barakasi Latin wordmark role and horizontal lockup architecture.

---

**Madina Barakasi Design & Experience Library**