# MB-201 — Visual Identity Foundation

> **Foundation specification for the Madina Barakasi visual identity**

---

## Document Information

| Field          | Value                     |
| -------------- | ------------------------- |
| Document ID    | MB-201                    |
| Volume         | III — Design & Experience |
| Title          | Visual Identity Foundation |
| Version        | 0.1.2                     |
| Status         | Draft                     |
| Classification | Specification             |
| Language       | English                   |
| Owner          | Design & Experience       |
| Created        | 2026-08-20                |
| Last Updated   | 2026-08-21                |

---

# 1. Purpose

MB-201 defines the visual identity foundation of Madina Barakasi.

It establishes the framework that connects the approved brandmark architecture with typography, color, lockups, spacing, contrast, multilingual presentation, and future Design System tokens.

This document builds on the approved brandmark decision recorded in MB-DEC-001 and the approved Arabic typography decision recorded in MB-DEC-002.

It does not redefine the approved Canonical or Micro brandmark geometry.

---

# 2. Scope

MB-201 governs the foundational visual identity used across Madina Barakasi brand and product contexts.

It covers:

- Brand visual principles
- Brandmark usage hierarchy
- Symbol and wordmark relationship
- Lockup architecture
- Typography foundation
- Brand color foundation
- Clear-space framework
- Background and contrast behavior
- Size hierarchy
- Monochrome and reversed presentation
- Multilingual visual considerations
- Relationship to Design System tokens
- Visual identity governance

It does not define:

- Application-specific business workflows
- Component APIs
- Complete UI component specifications
- Marketing campaign artwork
- Packaging production specifications
- Final legal trademark clearance

---

# 3. Governing Documents

MB-201 operates under the following documents:

- MB-200 — Design System
- MB-STD-007 — Symbol Design Principles
- MB-ADR-001 — Symbol Independent From Name
- MB-DEC-001 — Brandmark Architecture
- MB-DEC-002 — Arabic Typography Architecture

MB-DEC-001 is the authoritative decision for the active Madina Barakasi brandmark architecture.

MB-DEC-002 governs the canonical Arabic typography family architecture.

Where this document conflicts with MB-DEC-001 regarding brandmark geometry, MB-DEC-001 governs.

---

# 4. Approved Brandmark Architecture

The active brandmark architecture is:

## 4.1 Primary Canonical

**B2.1-S1 Canonical Pass 5**

Approved use:

- 24 px and above
- Standard brand presentation
- Documentation
- Product presentation
- Physical applications
- Medium and large digital contexts

## 4.2 Micro Companion

**B2.1-S1-MICRO Pass 2**

Approved use:

- 16–23 px
- Small digital presentation
- Compact interface contexts where the Canonical geometry loses sufficient internal separation

Below 16 px, no production brandmark geometry is currently approved.

The Micro companion is not a second logo.

It is a controlled optical derivative belonging to the same brandmark system.

---

# 5. Brand Visual Principles

The Madina Barakasi visual identity should express:

- Clarity
- Trust
- Stability
- Restraint
- Distinctiveness
- Continuity
- Precision
- Long-term usability

The visual identity should avoid unnecessary decoration, trend dependence, visual noise, and arbitrary stylistic variation.

The system should remain appropriate for both institutional and commercial contexts.

---

# 6. Symbol Independence

The brandmark must remain independently usable from the textual name.

The textual name **Madina Barakasi** may accompany the symbol through approved lockups.

The wordmark must not become a structural dependency of the approved Canonical symbol.

This follows MB-ADR-001.

---

# 7. Wordmark Foundation

The Madina Barakasi wordmark is a separate typographic identity element.

MB-DEC-003 establishes the canonical Latin wordmark architecture.

The canonical Madina Barakasi Latin wordmark uses:

- **Source Sans 3 static 500**
- **0 em tracking**
- Native OpenType spacing and kerning

The verified reviewed static asset is `SourceSans3-500.ttf`.

Source Sans 3 is canonical specifically for the Latin wordmark role. This approval does not establish Source Sans 3 as the universal typeface for all Madina Barakasi platform or operational interface roles.

The wordmark remains a separate typographic identity element and must not alter or become a structural dependency of the approved brandmark.

Broader brand/institutional typography, CRM / ERP operational typography, production asset distribution, and application implementation remain separate work.

---

# 8. Lockup Architecture

The visual identity may support controlled lockups including:

- Symbol only
- Symbol + Madina Barakasi horizontal lockup
- Symbol + Madina Barakasi vertical lockup
- Context-specific compact lockup where formally approved

Lockups must preserve:

- Brandmark integrity
- Clear hierarchy
- Consistent alignment
- Sufficient spacing
- Wordmark readability
- Optical balance

MB-DEC-003 establishes **L2 / Balanced Optical** as the canonical horizontal Latin lockup architecture.

Let:

**S = symbol height**

The approved normalized horizontal relationships are:

- Wordmark size = **0.2556 S**
- Symbol-to-wordmark gap = **0.2667 S**
- Wordmark optical raise = **0.0111 S**

The optical raise is specific to the horizontal lockup and is not a general Design System token.

The practical minimum for the complete horizontal Latin lockup is:

**S = 48 px**

At `S = 40 px`, the complete horizontal lockup remains diagnostic only.

Below the practical horizontal-lockup minimum, symbol-only presentation should be preferred according to MB-DEC-001.

The symbol-only size architecture defined by MB-DEC-001 remains unchanged.

Vertical and Arabic / bilingual lockup geometry remain unresolved.

---

# 9. Typography Foundation

Typography must support both brand communication and platform interfaces without unnecessary fragmentation.

MB-DEC-002 establishes IBM Plex Sans Arabic as the canonical primary Arabic typography foundation. Noto Sans Arabic is the controlled primary Arabic fallback.

The canonical controlled fallback architecture is:

```text
IBM Plex Sans Arabic
→ Noto Sans Arabic
→ sans-serif
```

The approved static Arabic weight set is 400, 500, and 600.

The following Latin directions have passed human review for further specification, but are not yet final canonical typography approvals:

- **Source Sans 3 static 400–600** is the approved direction for brand/institutional typography.
- **Inter static 400–600** is the approved direction for CRM / ERP operational typography.
- Source Sans 3 + IBM Plex Sans Arabic is the institutional pairing architecture.
- Inter + IBM Plex Sans Arabic is the operational pairing architecture.

The typography foundation must still define:

- Final canonical primary brand typeface specification
- Final canonical interface typeface specification
- Heading hierarchy
- Body text hierarchy
- Supporting text
- Labels
- Numerals
- Cyrillic compatibility where required
- Latin-script compatibility
- Exact production typography tokens and implementation specification

Arabic brand spelling, bilingual lockup geometry, final typography metrics, and all exact production sizes, line heights, and tracking values beyond the approved Arabic family architecture remain separate work.

---

# 10. Color Foundation

The visual identity must remain recognizable independently from color.

The approved brandmark architecture currently supports:

- Black on white
- White on black

A future brand color system may define:

- Primary brand color
- Secondary brand colors
- Neutral palette
- Surface colors
- Text colors
- Border colors
- Interactive colors
- Status and feedback colors

No new brand color should be treated as canonical until explicitly reviewed and documented.

---

# 11. Clear Space

MB-DEC-001 retains the following provisional clear-space value:

**C = 0.15 U**

where the Canonical master unit is:

**U = 900**

This value remains provisional within the Visual Identity Foundation.

It must be tested together with:

- Symbol-only applications
- Horizontal lockups
- Vertical lockups
- Small and large presentation contexts
- Physical applications

Final clear-space approval requires visual validation of the complete identity system.

---

# 12. Size Hierarchy

The approved symbol-size architecture is:

- **24 px and above:** Canonical Pass 5
- **16–23 px:** MICRO Pass 2
- **Below 16 px:** not approved

Future lockup minimum sizes may be greater than the symbol-only minimum sizes.

Wordmark legibility must be evaluated separately.

---

# 13. Background and Contrast

The identity must remain clear against its background.

Approved baseline polarity is:

- Dark mark on light background
- Light mark on dark background

Future color applications must maintain sufficient visual separation and accessibility.

The brandmark geometry must not be modified to compensate for an unsuitable background.

---

# 14. Monochrome and Reversed Use

Monochrome use is a foundational capability of the Madina Barakasi identity.

The symbol must remain structurally unchanged between:

- Positive presentation
- Reversed presentation
- Single-color reproduction

Effects such as shadows, gradients, outlines, bevels, or decorative overlays must not be applied to the canonical geometry unless explicitly approved in a later specification.

---

# 15. Multilingual Foundation

Madina Barakasi may operate across multiple language environments.

The visual identity should support at minimum:

- English / Latin script
- Russian / Cyrillic script
- Uzbek / Latin or approved project script usage

Arabic-script presentation may be introduced where required by product or communication context. MB-DEC-002 governs the canonical Arabic typography family architecture in those contexts.

Multilingual wordmarks must preserve:

- Identity hierarchy
- Visual balance
- Readability
- Clear relationship with the symbol

A translated or localized name must not silently replace the canonical brand name without a documented decision.

---

# 16. Relationship to Design Tokens

Approved visual identity values may become Design System tokens when they are reusable across platform interfaces.

Potential token groups include:

- Brand colors
- Typography
- Spacing
- Symbol sizing
- Clear space
- Contrast
- Background usage

A value must not become canonical merely because it has been implemented in application code.

Canonical tokens require explicit documentation and review.

---

# 17. Prohibited Practices

The following practices are not permitted without explicit approval:

- Redrawing the Canonical brandmark
- Changing brandmark proportions
- Changing cardinal tips
- Removing the two-level flow topology
- Closing the central aperture
- Creating unofficial Micro variants
- Stretching or skewing the symbol
- Adding decorative effects to the symbol
- Using arbitrary wordmark typography as canonical
- Introducing undocumented brand colors
- Creating unofficial lockup proportions
- Treating exploratory marks as production identity

The archived MAAA exploration is not part of the active visual identity.

---

# 18. Validation Requirements

Before visual identity elements become canonical, they should be evaluated in relevant contexts including:

- Symbol-only use
- Symbol + wordmark
- Desktop interface
- Mobile interface
- CRM / ERP navigation
- Documentation
- Presentation materials
- Digital application icons
- Web contexts
- Physical and print contexts
- Light and dark backgrounds
- Small-size presentation

Validation should distinguish visual preference from production reliability.

---

# 19. Governance

Material Visual Identity decisions must be explicit and reviewable.

Changes that affect:

- Approved brandmark geometry
- Canonical typography
- Canonical color
- Lockup architecture
- Minimum sizes
- Clear-space rules
- Multilingual brand presentation

must be documented through an appropriate Design Decision, Standard, or Specification update.

Implementation must not silently redefine the canonical Visual Identity.

---

# 20. Pending Foundation Decisions

The following areas remain intentionally unresolved before final canonical approval:

- Final brand and institutional typography specification
- Final CRM / ERP interface typography specification
- Production Arabic font asset manifest and distribution specification
- Final organizational legal release review
- Arabic typography implementation specification
- Canonical brand color palette
- Final clear-space rule
- Vertical lockup specification
- Multilingual lockup specification
- Background color rules beyond monochrome polarity
- Final visual identity tokens

These items will be resolved through controlled visual exploration and explicit approval.

---

# 21. Definition of Done

MB-201 may progress beyond Draft when:

- Canonical wordmark typography is approved.
- Brand color foundations are approved.
- Clear-space rules are validated.
- Primary lockup architecture is approved.
- Minimum lockup sizes are validated.
- Background and contrast rules are confirmed.
- Multilingual presentation rules are reviewed.
- Required Design System tokens are identified.
- Related Design Decisions and Standards are synchronized.
- Repository review is complete.

---

# 22. Status

MB-201 is currently a Draft Visual Identity Foundation specification.

The approved B2.1-S1 brandmark architecture is inherited from MB-DEC-001 and is not reopened by this Draft. The approved Arabic typography family architecture is inherited from MB-DEC-002; its downstream tokens and implementation remain separate work.

---

**Madina Barakasi Design & Experience Library**
