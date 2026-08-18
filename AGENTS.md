# AI Agent Rules for Madina Barakasi Documentation

These rules are mandatory for AI agents working in this repository.

## Source of Truth and Required Reading

1. Before making any change, read the current content of the real target file and the related governance documents. Do not rely on previous versions, assumptions, or memory.
2. Do not create a duplicate document when the topic already has a canonical or registered document. Follow this principle at all times: **One topic -> One canonical document.**
3. Before creating or changing a document, check:
   - `MASTER_INDEX.md`;
   - `DOCUMENT_REGISTRY.md`;
   - `ADR_REGISTRY.md`;
   - applicable Foundation, Architecture, SOP, and CRM documents.
4. `Approved` has priority over `Draft`. Draft documents may guide work, but must not be presented as approved policy or an approved architectural decision.
5. `MB-004` — Master Plan is currently `Draft`. Do not treat it as a formally approved source of truth until its status is changed through the required governance process.
6. English is the canonical language of official documentation. Do not change the language of a canonical document without an explicit decision.
7. Do not use the word “Bible” in project document titles or content. Use a neutral and appropriate term such as Guide, Standards, Foundation, or Reference.

## Required Reading Order for Architecture or Planning Changes

Read the following in order before proposing or making architecture or project-plan changes:

1. `MASTER_INDEX.md`
2. `DOCUMENT_REGISTRY.md`
3. `docs/volume-01-foundation/readme.md`
4. `docs/volume-01-foundation/MB-004-Master-Plan.md`
5. Applicable `MB-100`, `MB-101`, and `MB-102` documents
6. `ADR_REGISTRY.md` and applicable ADRs
7. `docs/volume-06-operations/MB-SOP-001-Documentation-Workflow.md`
8. For CRM work, `MB-CRM-001` through `MB-CRM-008`

## Governance and Change Control

1. Do not change a document status from `Draft` to `Approved` without explicit user authorization.
2. Do not change document versions automatically. A version change requires a documented need and explicit basis.
3. Do not change the Document ID of an existing document.
4. Do not move a document between Volumes without an architecture or governance decision.
5. Maintain registry discipline:
   - every controlled document must be represented in `DOCUMENT_REGISTRY.md`;
   - every ADR must be represented in `ADR_REGISTRY.md`.
6. When changing a document, determine whether the change also requires updates to its registry entry, version history, `CHANGELOG.md`, a related ADR, or related documents.
7. Do not automatically correct registry inconsistencies or other governance discrepancies.
8. If a conflict is found between `MASTER_INDEX.md`, `DOCUMENT_REGISTRY.md`, the document itself, or architecture documents, stop and report the conflict to the user before making the change.
9. Do not independently create new architecture when the requirements are ambiguous. For an architecture change, first determine whether an ADR is required.
10. For CRM changes, consider the full `MB-CRM-001` through `MB-CRM-008` specification chain. For documentation-process changes, consider `MB-SOP-001`.
11. Do not rewrite approved documents merely for stylistic consistency unless that is the explicit task.
12. Do not perform repository-wide formatting without an explicit need.

## Git Safety and Completion Checks

1. After making changes, show `git diff`, run `git diff --check`, and inspect `git status`.
2. Never run `git commit`, `git push`, `git merge`, `git rebase`, or `git reset` without explicit user authorization.
3. Do not perform destructive Git operations.
4. At the end of every task, provide a concise report stating:
   - what changed;
   - which documents changed;
   - which registry or changelog updates were made, or why they were not required;
   - which checks were performed;
   - any governance conflicts or unresolved questions.
