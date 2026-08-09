# MB-ADR-001 — Symbol Independent From Name

> **Architecture Decision Record concerning symbolic identity independence**

---

## Document Information

| Field          | Value                     |
| -------------- | ------------------------- |
| Document ID    | MB-ADR-001                |
| Volume         | III — Design & Experience |
| Title          | Symbol Independent From Name |
| Version        | 0.1.0                     |
| Status         | Draft                     |
| Classification | ADR                       |
| Language       | English                   |
| Owner          | Design & Experience       |
| Created        | 2026-08-08                |
| Last Updated   | 2026-08-08                |

---

# 1. Context

The Madina Barakasi Platform requires a consistent approach to symbolic identity.

A design question exists concerning whether a symbol should remain structurally dependent on the textual name of the entity it represents.

The existing design standard, MB-STD-007, establishes the principle that a symbol and its associated name should be treated as related but independently maintainable elements.

This ADR records the corresponding design decision.

---

# 2. Decision

The symbol is treated as an element that should remain independent from the textual name.

The symbol should not require the full entity, product, or application name to be embedded within its visual structure.

The symbol and the textual name may be combined in an approved lockup where required, but they remain independently maintainable elements.

Text may accompany the symbol when required for:

- Clarity
- Identification
- Accessibility
- Communication
- Context

This decision does not prohibit text from appearing alongside a symbol.

It establishes that the textual name is not an inseparable structural dependency of the symbol.

---

# 3. Consequences

This decision establishes several consequences for design work.

### Positive consequences

- Symbols can be reused in compact interface contexts.
- Symbols can be maintained independently from textual names.
- The same symbolic element can support different presentation contexts.
- Symbol and typography changes can be managed independently.
- Small interface surfaces can use the symbol without requiring the complete name.

### Constraints

- Symbol design must remain recognizable without depending exclusively on the textual name.
- Symbol variants must remain consistent with the approved visual identity.
- Text-symbol lockups require controlled spacing and hierarchy.
- New symbolic elements should follow MB-STD-007.

---

# 4. Alternatives Considered

The following alternatives are identified for this decision:

### Alternative A — Embed the name into the symbol

The symbol would contain the textual name as an inseparable part of its structure.

**Rejected** because this would reduce independent reuse of the symbol and create unnecessary dependency between symbolic and textual identity.

### Alternative B — Keep symbol and name independent

The symbol and textual name remain separate elements and may be combined through controlled lockups.

**Selected** because it provides greater reuse and supports different interface and communication contexts.

---

# 5. Scope

This decision applies to symbolic identity within the Madina Barakasi Platform.

It primarily concerns:

- Brand symbols
- Application symbols
- Product symbols
- Interface symbols
- Reusable symbolic elements

It does not define the complete Design System.

The broader Design System is defined by MB-200.

---

# 6. Relationship to Standards

MB-STD-007 defines the general principles that govern symbolic design.

This ADR records the specific decision that symbolic identity should remain independent from the textual name.

MB-STD-007 therefore provides the governing standard, while this ADR records the design decision.

---

# 7. Related Documents

- MB-200 — Design System
- MB-STD-007 — Symbol Design Principles
- MB-DEC-INDEX — Design Decisions Index

---

# 8. Status

The original repository artifact contained an `Approved` status marker but did not contain the substantive decision text or a valid decision date.

The present document is therefore recorded as a **Draft reconstruction** rather than as a claim of the original approved decision.

Formal approval should occur after review of the reconstructed decision.

---

**Madina Barakasi Design & Experience Library**
