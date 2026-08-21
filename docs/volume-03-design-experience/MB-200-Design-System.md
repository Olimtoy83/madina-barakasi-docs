# MB-200 — Design System

> **The design system of the Madina Barakasi Platform**

---

## Document Information

| Field          | Value                     |
| -------------- | ------------------------- |
| Document ID    | MB-200                    |
| Volume         | III — Design & Experience |
| Title          | Design System             |
| Version        | 0.1.2                     |
| Status         | Draft                     |
| Classification | Specification             |
| Language       | English                   |
| Owner          | Design & Experience       |
| Created        | 2026-08-08                |
| Last Updated   | 2026-08-21                |

---

# 1. Purpose

MB-200 defines the structure, scope, and governing principles of the Madina Barakasi Platform Design System.

The Design System provides a common foundation for creating consistent, reusable, accessible, and maintainable user interfaces across the platform.

This document establishes the Design System framework.

It does not define application-specific business workflows or business-domain rules.

---

# 2. Scope

The Design System applies to user interface infrastructure and experience patterns used across the Madina Barakasi Platform.

It covers:

- Design foundations
- Design tokens
- Typography
- Spacing
- Layout
- Color
- Iconography
- Components
- Interaction patterns
- Accessibility
- Responsive behavior
- UI documentation

Application-specific interfaces may extend the Design System where required by their domain.

Such extensions must remain consistent with the established Design System principles.

---

# 3. Design System Principles

The Design System should follow these principles:

1. Prefer clarity over visual complexity.
2. Prefer consistency over unnecessary variation.
3. Prefer reusable interface patterns.
4. Keep components focused on clear responsibilities.
5. Separate reusable UI infrastructure from business-domain logic.
6. Avoid introducing visual patterns without a justified use case.
7. Prefer accessible interaction patterns.
8. Keep design decisions explicit and documented.
9. Allow controlled evolution of the Design System.
10. Keep the Design System aligned with the platform architecture.

---

# 4. Design Foundations

The Design System will establish a common foundation for interface construction.

The foundation includes:

- Color
- Typography
- Spacing
- Sizing
- Borders
- Radius
- Elevation
- Motion
- Iconography
- Layout rules

Specific values may be introduced and approved as the Design System evolves.

Until such values are formally established, applications must avoid treating undocumented values as canonical Design System tokens.

---

# 5. Design Tokens

Design tokens provide reusable named values for interface construction.

Token categories may include:

- Color tokens
- Typography tokens
- Spacing tokens
- Size tokens
- Border tokens
- Radius tokens
- Elevation tokens
- Motion tokens

Tokens should be:

- Explicitly named
- Reusable
- Consistent
- Documented
- Independent from application-specific business logic

Applications should prefer established tokens instead of introducing equivalent local values.

---

# 6. Typography

Typography defines the rules used to present interface content.

The Design System may define:

- Font families
- Font sizes
- Font weights
- Line heights
- Letter spacing
- Heading hierarchy
- Body text hierarchy
- Supporting text
- Labels

Typography decisions must remain consistent across platform interfaces.

Specific font selections and token values require explicit Design System decisions.

MB-DEC-002 governs the canonical Arabic typography family architecture: IBM Plex Sans Arabic is the canonical Arabic typography foundation, and Noto Sans Arabic is its controlled fallback. The controlled fallback architecture is IBM Plex Sans Arabic → Noto Sans Arabic → sans-serif.

MB-DEC-003 governs the canonical Latin wordmark and horizontal Latin lockup architecture. Source Sans 3 static 500 is canonical specifically for the Madina Barakasi Latin wordmark role, using `0 em` tracking with native OpenType spacing and kerning.

MB-DEC-003 does not establish Source Sans 3 as the universal platform or operational interface typeface, and it does not canonicalize Inter operational metrics.

Exact reusable typography tokens and application implementation values remain subject to further Design System specification work.

---

# 7. Color

The Design System provides a common color framework for platform interfaces.

Color definitions may include:

- Brand colors
- Background colors
- Surface colors
- Text colors
- Border colors
- Interactive colors
- Status colors
- Feedback colors

Color usage must communicate hierarchy and state clearly.

Application-specific colors should not replace established Design System tokens without a documented reason.

---

# 8. Layout and Spacing

The Design System defines reusable layout and spacing principles.

These include:

- Containers
- Grid systems
- Flex layouts
- Spacing scales
- Alignment
- Responsive breakpoints
- Content density

Layout rules should support consistent behavior across desktop, tablet, and mobile interfaces where applicable.

---

# 9. Components

Components are reusable interface building blocks.

The Design System may include:

- Buttons
- Inputs
- Forms
- Cards
- Tables
- Navigation
- Dialogs
- Notifications
- Tabs
- Menus
- Select controls
- Loading states
- Empty states
- Error states

Components should have:

- A clear responsibility
- Predictable behavior
- Consistent visual treatment
- Defined states
- Reusable interfaces
- Accessibility considerations

Business-specific components may exist at the application level and should not automatically become shared Design System components.

---

# 10. Interaction Patterns

The Design System defines reusable interaction patterns for common interface behavior.

Patterns may include:

- Navigation
- Form submission
- Confirmation
- Validation
- Loading
- Error handling
- Success feedback
- Empty states
- Modal interaction
- Search and filtering
- Pagination

Interaction patterns should remain predictable and consistent.

---

# 11. Responsive Design

Platform interfaces should support appropriate behavior across supported screen sizes.

Responsive design should consider:

- Layout adaptation
- Navigation behavior
- Component resizing
- Content priority
- Touch interaction
- Readability
- Usability

Responsive behavior should be defined at the Design System level where the behavior is shared across applications.

---

# 12. Accessibility

Accessibility is part of the Design System baseline.

Components and interaction patterns should consider:

- Keyboard interaction
- Focus states
- Readable contrast
- Semantic structure
- Form labels
- Error communication
- Screen-reader compatibility
- Appropriate touch targets

Accessibility requirements should be incorporated into reusable components rather than repeatedly implemented at the application level.

---

# 13. UI Infrastructure

The platform may provide reusable UI infrastructure through the shared UI package.

The UI infrastructure should contain reusable technical interface capabilities.

It should not contain ERP-specific business-domain concepts.

Application-specific business logic remains within the relevant application or domain layer.

---

# 14. Design Decisions

Material Design System decisions should be documented separately when they establish a significant or reusable rule.

Relevant decisions may be recorded through:

- Architecture Decision Records
- Design Decisions
- Design Standards

The Design System should reference those decisions where appropriate.

MB-DEC-002 is the governing Design Decision for the canonical Arabic typography family architecture.

---

# 15. Relationship to Other Documentation

MB-200 operates within the broader Madina Barakasi documentation architecture.

Related documentation includes:

- MB-100 — System Architecture
- MB-101 — Data Architecture
- MB-102 — Engineering Standards
- MB-004 — Master Plan
- Design Decision Records
- Design Standards
- MB-201 — Visual Identity Foundation
- MB-DEC-002 — Arabic Typography Architecture

MB-200 defines the Design System framework.

It does not replace system architecture, engineering standards, business-module specifications, or governance documentation.

---

# 16. Governance

Changes to the Design System should be made through controlled and reviewable changes.

Material changes should:

1. Identify the affected Design System area.
2. Explain the reason for the change.
3. Consider affected applications and shared components.
4. Update relevant documentation.
5. Be validated before approval.

Canonical Design System rules should not be changed implicitly through application implementation.

---

# 17. Current Status

MB-200 is currently a structural Design System specification.

The canonical Arabic typography family architecture is established by MB-DEC-002. Exact reusable typography tokens remain pending Design System specification.

The following areas require future explicit decisions before becoming canonical:

- Exact color tokens
- Exact typography tokens
- Exact spacing scale
- Exact responsive breakpoints
- Component API conventions
- Accessibility target level
- Motion guidelines
- Icon system
- Component maturity levels

Until these decisions are approved, this document defines the framework rather than final visual values.

---

# 18. Definition of Done

MB-200 may progress beyond Draft when:

- The Design System structure is reviewed.
- Required design decisions are identified.
- Canonical tokens are defined where necessary.
- Core component conventions are established.
- Accessibility requirements are confirmed.
- Related Design Decisions and Standards are aligned.
- The document is reviewed and approved.

---

**Madina Barakasi Design & Experience Library**
