# MB-DEC-001 — Brandmark Architecture

> **Design decision for the canonical Madina Barakasi brandmark architecture**

---

## Document Information

| Field          | Value                     |
| -------------- | ------------------------- |
| Document ID    | MB-DEC-001                |
| Volume         | III — Design & Experience |
| Title          | Brandmark Architecture    |
| Version        | 1.0.0                     |
| Status         | Approved                  |
| Classification | Design Decision           |
| Language       | English                   |
| Owner          | Design & Experience       |
| Created        | 2026-08-20                |
| Last Updated   | 2026-08-20                |

---

# 1. Context

The Madina Barakasi visual identity requires a canonical symbolic mark that can operate independently from the textual name while remaining usable across brand, product, interface, documentation, and physical presentation contexts.

A controlled brandmark development and validation process produced a primary canonical geometry and a separate micro-size companion.

This decision records the resulting brandmark architecture.

It does not redefine the broader Design System and does not replace MB-STD-007.

---

# 2. Decision

The Madina Barakasi brandmark architecture consists of two approved geometric roles:

## 2.1 Primary Canonical

The primary canonical brandmark is:

**B2.1-S1 Canonical Pass 5**

This geometry is the authoritative master symbol for standard and large-size use.

It must not be modified, reinterpreted, redrawn, simplified, or proportionally altered without a new reviewed design decision.

## 2.2 Micro Companion

The approved small-size companion is:

**B2.1-S1-MICRO Pass 2**

The Micro geometry is a controlled optical derivative of the Canonical geometry.

It exists only to improve small-size raster stability.

It does not constitute a separate logo or independent visual identity.

---

# 3. Size Architecture

The approved size-selection rule is:

- **24 px and above:** use B2.1-S1 Canonical Pass 5.
- **23–16 px:** use B2.1-S1-MICRO Pass 2.
- **Below 16 px:** no approved brandmark geometry is currently defined.

The 12 px rendering remains a stress-test condition and is not an approved production size.

The Canonical geometry must not be altered merely to improve performance below its approved minimum size.

---

# 4. Canonical Geometry Identity

The Canonical and Micro variants belong to one visual system.

Their shared identity includes:

- Four cardinal tips
- Four-way rotational symmetry
- Two-level flow topology
- Outer flow
- Inner flow
- Controlled white inter-flow channel
- Central concave-diamond aperture
- Shared overall silhouette
- Shared curvature language

The Micro variant may contain controlled optical corrections to the inner geometry while preserving the Canonical silhouette and topology.

---

# 5. Canonical Master Measurements

The validated Canonical master uses:

- Master bounding box: `900 × 900`
- Master unit: `U = 900`
- Central aperture construction envelope: `360 × 360` = `0.400 U`
- Maximum outer-flow width: approximately `53.3` = `0.059 U`
- Maximum inner-flow width: approximately `50.7` = `0.056 U`
- White inter-flow channel: approximately `23.5–75.0` = `0.026–0.083 U`

These measurements are derived from the approved Canonical SVG and supersede earlier exploratory or generative numerical annotations.

---

# 6. Micro Companion Measurements

The approved Micro companion preserves:

- Outer silhouette deviation from Canonical: `0`
- Outer flow unchanged
- Four-way symmetry
- Cardinal tips
- Two-level flow topology
- White channel
- Central aperture

Validated Micro measurements include:

- Maximum inner-flow width: `58.0`
- Weakest white-channel bottleneck: `32.7`
- Central aperture envelope: `276`

The Micro geometry is approved only as a controlled small-size derivative.

---

# 7. File Integrity

The approved master SVG files are identified by the following SHA-256 hashes:

## Canonical Pass 5

`30DAFE49CF80F9CDBD15493EBE807F180359DE0409CFF6C9D2FF485264F095DA`

## B2.1-S1-MICRO Pass 2

`AEF1884E31E0C5DA9BE17005B74C92158D5374F9B0192EFD67B8D47F1F5191E4`

A file claiming to be one of these approved masters must match the corresponding hash unless a later approved decision explicitly replaces it.

---

# 8. Polarity

The brandmark may be used in:

- Black on white
- White on black

The underlying geometry must remain unchanged between polarity variants.

Color-system decisions beyond monochrome polarity are outside the scope of this decision.

---

# 9. Relationship to the Name

The brandmark remains structurally independent from the textual name **Madina Barakasi**.

The symbol may be used:

- Independently
- In an approved symbol + name lockup

The textual name is not part of the Canonical symbol geometry.

Lockup proportions, typography, spacing, and alignment will be governed by separate Visual Identity decisions.

This decision is consistent with MB-ADR-001.

---

# 10. Clear Space

A provisional clear-space value of:

**C = 0.15 U**

is retained as the current proposed brandmark clearance value.

This value must not be treated as a final canonical Visual Identity token until validated together with the complete symbol + wordmark system.

The exact clear-space rule will be confirmed during the Visual Identity Foundation stage.

---

# 11. Alternative Family Exploration

An independent family-monogram exploration based on the conceptual structure:

**M / A / A / A**

was evaluated as an alternative direction.

The strongest retained representative was:

**MAAA R3-P2-B**

The family branch was stopped after head-to-head brand-context review.

Its status is:

**STOPPED / ARCHIVED FOR REFERENCE**

It is not part of the active brandmark architecture and has no canonical or candidate status.

The retained exploration must not be used as an alternative production logo without a new reviewed decision.

---

# 12. Validation Summary

The Canonical architecture was evaluated through:

- Visual reconstruction review
- Geometric validation
- Mathematical symmetry validation
- Bézier continuity review
- Raster testing
- Small-size testing
- Canonical / Micro comparison
- Black / white polarity review
- Brand-context testing
- Preliminary visual trademark-similarity review

The brandmark architecture passed the human Brandmark Architecture Closure Review.

The preliminary trademark-similarity review did not identify an obvious blocking duplicate within the reviewed search set.

This review does not constitute legal trademark clearance.

---

# 13. Consequences

This decision establishes that:

- B2.1-S1 Canonical Pass 5 is the primary Madina Barakasi brandmark.
- B2.1-S1-MICRO Pass 2 is the approved small-size companion.
- The Canonical and Micro files are controlled assets.
- The Canonical geometry must not be silently changed.
- Small-size use follows the approved size-selection rule.
- Future Visual Identity work must build around this architecture.
- Alternative exploratory symbols remain non-production assets unless separately approved.
- Further brandmark changes require a new reviewed design decision.

---

# 14. Relationship to Existing Documentation

This decision operates under:

- MB-200 — Design System
- MB-STD-007 — Symbol Design Principles
- MB-ADR-001 — Symbol Independent From Name
- MB-DEC-INDEX — Design Decisions Index

MB-STD-007 defines the governing symbolic principles.

MB-ADR-001 establishes symbol independence from the textual name.

This decision defines the specific approved Madina Barakasi brandmark architecture.

---

# 15. Next Stage

After approval of this decision, the next design stage is:

**Visual Identity Foundation**

That stage may define:

- Symbol + wordmark lockups
- Typography
- Brand color system
- Clear-space confirmation
- Alignment rules
- Background rules
- Contrast rules
- Application guidance

The Visual Identity Foundation must not redefine the approved Canonical geometry without a new design decision.

---

# 16. Status

This document records the human-reviewed Brandmark Architecture Closure decision.

This decision is **Approved** and defines the active Madina Barakasi brandmark architecture.

---

**Madina Barakasi Design & Experience Library**
