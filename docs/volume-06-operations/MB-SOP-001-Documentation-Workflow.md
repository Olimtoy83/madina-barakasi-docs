# MB-SOP-001 — Documentation Workflow

## Document Information

| Field | Value |
|---|---|
| Document ID | MB-SOP-001 |
| Title | Documentation Workflow |
| Volume | Volume VI — Operations |
| Version | 0.1.0 |
| Status | Draft |
| Classification | SOP |

---

# 1. Purpose

MB-SOP-001 defines the standard workflow for creating, reviewing, approving, registering, maintaining, versioning, superseding, and archiving documentation within the Madina Barakasi Documentation Library.

The purpose of this document is to ensure that documentation remains structured, traceable, consistent, reviewable, and aligned with the established Documentation Architecture.

# 2. Scope

This SOP applies to documentation maintained within the Madina Barakasi Documentation Library.

It covers:

- document creation;
- document identification;
- document classification;
- document review;
- document approval;
- document registration;
- document versioning;
- document modification;
- document supersession;
- document archival;
- documentation validation;
- repository-based documentation workflow.

This SOP does not define application business logic, technical implementation logic, or operational procedures belonging to other documents.

# 3. Documentation Lifecycle

Documentation follows the following lifecycle:

1. Planned
2. Draft
3. Review
4. Approved
5. Active
6. Superseded
7. Archived

A document must not be treated as an approved source of truth before it reaches the Approved status.

# 4. Document Identification

Each controlled document must have a unique Document ID.

The Document ID must remain stable throughout the document lifecycle.

A document ID must not be silently reused for another document.

# 5. Document Classification

Documents must belong to an established documentation classification.

Examples include:

- Foundation;
- Architecture;
- Design;
- Engineering;
- Business Module;
- Standard Operating Procedure;
- Knowledge Base;
- Architecture Decision Record;
- Registry.

Classification must reflect the primary responsibility of the document.

# 6. Document Status

The following statuses are recognized:

| Status | Meaning |
|---|---|
| Planned | Document is identified but not yet created |
| Draft | Document is being developed |
| Review | Document is undergoing formal review |
| Approved | Document has been approved as a controlled reference |
| Active | Document is currently applicable |
| Superseded | Document has been replaced by another approved document |
| Archived | Document is retained for historical reference and is no longer active |

Status changes must be intentional and traceable.

# 7. Creation Workflow

A new controlled document should follow this sequence:

1. Identify the documentation need.
2. Assign or confirm the Document ID.
3. Determine the responsible Volume.
4. Determine the document classification.
5. Create the document structure.
6. Draft the content.
7. Perform internal consistency checks.
8. Perform cross-reference checks.
9. Submit the document for review.
10. Apply required corrections.
11. Approve the document when criteria are satisfied.
12. Register the document in the Document Registry.

# 8. Review Workflow

Review must verify that:

- the document has a valid Document ID;
- the document belongs to the correct Volume;
- the classification is appropriate;
- terminology is consistent;
- referenced documents exist or are explicitly identified as planned;
- requirements do not contradict higher-level documentation;
- duplicated responsibilities are avoided;
- the document has a defined scope;
- the document is internally coherent.

# 9. Approval Workflow

Approval establishes the document as a controlled reference.

Approval must occur only after required review activities have been completed.

An approved document must have:

- a valid Document ID;
- a defined version;
- a defined classification;
- a recorded status;
- an entry in the Document Registry.

# 10. Registry Requirements

Every controlled document must be represented in the Document Registry.

The registry entry must contain, at minimum:

- Document ID;
- title;
- version;
- status;
- classification.

The registry must reflect documents that actually exist within the Documentation Library.

# 11. Versioning

Document versions must be explicit.

A version change must reflect a meaningful modification to the document.

Version changes must remain traceable through repository history and documentation records.

# 12. Change Management

Changes to controlled documentation must preserve:

- document identity;
- architectural consistency;
- terminology consistency;
- cross-reference integrity;
- registry consistency.

Changes that materially alter architectural or system decisions should be evaluated against the applicable Architecture Decision Record process.

# 13. Supersession

When a document is replaced by another approved document:

1. the replacement document must be identified;
2. the previous document must not be silently deleted;
3. the previous document must be marked as Superseded or Archived as appropriate;
4. references must be updated where required;
5. the relationship between the documents must remain traceable.

# 14. Archiving

Archived documents must remain available when historical traceability is required.

Archiving must not remove the historical identity of the document.

Archived documentation must not be treated as the current source of truth.

# 15. Cross-Reference Rules

Cross-references between controlled documents must use stable Document IDs whenever possible.

References must not silently point to obsolete or superseded documents when an active replacement exists.

Cross-reference integrity should be validated before approval.

# 16. Validation Requirements

Before approval, a controlled document should be checked for:

- file existence;
- correct filename;
- correct Document ID;
- correct title;
- version consistency;
- classification consistency;
- registry presence;
- cross-reference integrity;
- formatting consistency;
- repository cleanliness where applicable.

# 17. Repository Workflow

Controlled documentation is maintained through the project repository.

Documentation changes should follow the repository workflow:

1. modify or create the document;
2. inspect the working tree;
3. validate the document;
4. review the staged changes;
5. commit the approved change;
6. preserve repository history.

Commit messages should clearly describe the documentation change.

# 18. Responsibilities

Documentation authors are responsible for the accuracy and completeness of proposed content.

Reviewers are responsible for checking consistency, scope, terminology, references, and compliance with documentation standards.

Maintainers are responsible for preserving registry integrity and documentation structure.

# 19. Exceptions

Exceptions to this workflow must be explicit.

An exception must not silently invalidate the Document Registry, document identity, version history, or architectural traceability.

# 20. Compliance Criteria

A controlled document is considered compliant when:

1. it has a valid Document ID;
2. it belongs to an appropriate Volume;
3. its classification is defined;
4. its status is defined;
5. its version is defined;
6. it is registered;
7. required references are valid;
8. required validation has been completed;
9. its repository history is traceable.

# 21. Related Documents

- DOCUMENT_REGISTRY.md
- MASTER_INDEX.md
- MB-ADR-001-Symbol-Independent-From-Name.md
- MB-004-Master-Plan.md

---

**End of MB-SOP-001**
