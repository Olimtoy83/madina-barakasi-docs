# MB-ENG-001 — Evidence-Based Engineering Execution Protocol

## Document Information

| Field          | Value                                      |
| -------------- | ------------------------------------------ |
| Document ID    | MB-ENG-001                                 |
| Title          | Evidence-Based Engineering Execution Protocol |
| Volume         | Volume IV — Engineering                    |
| Version        | 0.1.0                                      |
| Status         | Draft                                      |
| Classification | Standard                                   |
| Language       | English                                    |
| Owner          | Engineering                                |
| Created        | 2026-09-01                                 |
| Last Updated   | 2026-09-01                                 |

---

# 1. Purpose

MB-ENG-001 defines the proposed evidence-based execution protocol for technical work across Madina Barakasi repositories.

Its purpose is to prevent unverified conclusions, speculative fixes, stale-file edits, false acceptance, uncontrolled scope expansion, and completion claims that are not supported by evidence.

This protocol governs how engineering work is inspected, changed, validated, accepted, and handed off.

It complements MB-102 Engineering Standards. It does not replace architecture standards, product specifications, repository-specific rules, or documentation governance.

# 2. Scope

This protocol is intended to apply to technical work across current and future Madina Barakasi repositories, including application code, frontend work, backend work, infrastructure, scripts, UI work, audits, debugging, repository maintenance, and technical implementation work that may affect documentation. Controlled-document lifecycle and governance remain governed by MB-SOP-001.

System and explicit user instructions take precedence over this protocol. Repository-specific rules remain applicable. While this document is Draft, it becomes mandatory for a repository only through explicit local adoption. After formal approval, it may serve as the canonical ecosystem execution protocol subject to higher-priority instructions.

Where an applicable repository-specific rule is stricter than this protocol, the stricter rule applies.

# 3. Evidence Categories

Engineering conclusions must distinguish between:

1. **Fact** — directly verified through current repository state, command output, runtime measurements, tests, or other reproducible evidence.
2. **Hypothesis** — a possible explanation that has not yet been verified.
3. **Visual observation** — an impression based on screenshots or visual inspection that may require measurement or comparison before being treated as fact.

A hypothesis or visual impression must not be presented as a verified fact.

# 4. Current-State Verification

Before modifying code, configuration, documentation, data, or repository structure:

1. inspect the current real target file or relevant block;
2. confirm that the expected code or content actually exists;
3. do not rely on stale chat context, memory, old diffs, or earlier file versions when the repository may have changed;
4. prefer current repository evidence over previous assumptions.

Do not request deletion, replacement, or modification of code that has not first been confirmed to exist in the current target.

# 5. Bounded Change Scope

Every implementation stage must have an explicit scope.

Engineering work must:

- change only what is necessary to satisfy the authorized stage;
- preserve unrelated working behavior;
- avoid opportunistic refactoring unless separately justified and authorized;
- avoid redesigning architecture when the task does not require it;
- stop before expanding into a new stage without explicit authorization.

# 6. Acceptance Criteria

Before implementing a change, define what successful completion means.

Acceptance criteria should be measurable or directly observable whenever possible.

Examples include:

- an element moves by an intended amount;
- a layout no longer overflows at specified viewport widths;
- a build completes successfully;
- a test reproducing a defect now passes;
- expected data remains compatible;
- a required file exists and maps correctly;
- a runtime value matches the expected result.

A vague impression such as "looks better" is not sufficient when a measurable criterion is available.

# 7. Validation Must Match the Claim

Validation must test the actual acceptance criterion.

Examples:

- a successful build does not prove that a visual UI defect is fixed;
- a clean Git diff does not prove that runtime behavior is correct;
- a screenshot without a valid comparison does not prove that an element moved by a requested number of pixels;
- a commit and push do not prove that the implementation achieved its intended result.

Validation evidence must support the specific claim being made.

# 8. Completion and Acceptance Language

Do not declare a stage:

- ACCEPTED;
- PASS;
- RESOLVED;
- DONE;
- COMPLETE;

unless the applicable acceptance criteria have actually been verified.

When evidence is incomplete or ambiguous, state that clearly.

Use statuses such as:

- pending verification;
- not yet accepted;
- partially verified;
- hypothesis;
- requires runtime confirmation;

when appropriate.

# 9. UI and Visual Verification

For UI changes:

1. define the intended visual or geometric result before changing code;
2. identify the relevant viewport, device, container, or runtime environment;
3. validate the exact target after implementation;
4. do not infer success solely from the absence of unrelated visual defects;
5. if a screenshot cannot establish the required difference, do not guess;
6. use before/after comparison or runtime measurements when needed.

Real-device acceptance must not be claimed unless a real-device check was actually performed when that check is part of the criterion.

# 10. Root Cause Before Additional Fixes

If a change does not achieve the expected result:

1. do not immediately stack another speculative CSS, JavaScript, configuration, or architectural fix;
2. inspect the actual result;
3. determine the likely cause from current evidence;
4. verify the hypothesis where practical;
5. apply the smallest justified correction.

Trial-and-error changes without evidence should be avoided.

# 11. Git Validation

Before committing:

1. inspect the actual diff;
2. confirm that only authorized files and changes are present;
3. run `git diff --check`;
4. run repository-specific validation required by the affected change;
5. inspect repository status.

A successful commit or push is evidence only that Git recorded and transferred the change. It is not evidence that the product requirement was satisfied.

# 12. Error Correction

If an earlier engineering conclusion is found to be wrong:

1. explicitly identify the previous conclusion as incorrect;
2. state what new evidence changed the conclusion;
3. do not invent a new explanation merely to preserve consistency with the previous answer;
4. update the current stage status accordingly;
5. preserve traceability of the correction.

# 13. Insufficient Evidence

When available evidence is insufficient:

- stop before making a definitive claim;
- request or perform only the smallest additional check required;
- do not fill gaps with assumptions;
- do not broaden the investigation unnecessarily.

# 14. Stage Control

Completion of one stage does not automatically authorize another stage.

After a stage is completed or rejected:

1. record the verified state;
2. identify unresolved issues if any;
3. wait for explicit authorization before beginning the next implementation stage.

# 15. Repository Checkpoints and Handoffs

Active repositories should maintain a concise project checkpoint when appropriate.

A new engineering session should:

1. read this protocol;
2. read repository-specific agent or development rules;
3. read the current project checkpoint when one exists and is applicable;
4. verify material checkpoint claims against the current repository before relying on them.

Repository evidence overrides stale checkpoint text or chat history.

# 16. Relationship to Other Standards

This protocol governs engineering execution and evidence discipline.

It does not replace:

- MB-102 Engineering Standards;
- architecture documents;
- ADRs;
- business-module specifications;
- design standards;
- repository-specific AGENTS.md rules;
- documentation workflow defined by MB-SOP-001.

Where another controlled standard defines a domain-specific rule, both documents apply unless they conflict.

# 17. Compliance Criteria

A technical stage complies with MB-ENG-001 when:

1. current state was verified before material change;
2. scope was explicit and bounded;
3. acceptance criteria were identified;
4. validation matched the claimed result;
5. facts, hypotheses, and visual impressions were not conflated;
6. Git changes were inspected before commit;
7. no completion claim exceeded the available evidence;
8. failed results were investigated before speculative additional fixes;
9. the next stage was not started without authorization;
10. handoff information reflects the verified current state.

# 18. Related Documents

- MB-102 — Engineering Standards
- MB-SOP-001 — Documentation Workflow
- MASTER_INDEX.md
- DOCUMENT_REGISTRY.md

---

**End of MB-ENG-001**
