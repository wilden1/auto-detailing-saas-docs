---
title: Identifiers and Requirement Status
type: standard
status: CONFIRMED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Identifiers and Requirement Status

This convention is `CONFIRMED` for the documentation process itself. It may be refined; any
change is recorded in the change log at the bottom of this file.

## 1. Identifier conventions

| Prefix | Meaning | Lives in | Numbering |
| --- | --- | --- | --- |
| `PG-###` | Product Goal | `docs/product/vision.md` | Global, sequential |
| `EPIC-###` | Epic — a large body of work | `docs/epics/` | Global, sequential |
| `FEAT-###` | Feature — belongs to one epic | `docs/features/` | Global, sequential |
| `US-###` | User Story — belongs to one feature | `docs/user-stories/` | Global, sequential |
| `AC-##` | Acceptance Criterion | Inside its user story | **Scoped to the story** |
| `BR-###` | Business Rule | `docs/business-rules/` | Global, sequential |
| `NFR-###` | Non-Functional Requirement | `docs/product/non-functional-requirements.md` | Global, sequential |
| `WF-###` | Workflow | `docs/workflows/` | Global, sequential |
| `MOD-###` | Module / product area | `docs/modules/` | Global, sequential |
| `ADR-###` | Architecture Decision Record | `docs/architecture/decisions/` | Global, sequential |
| `OQ-###` | Open Question | `docs/product/open-questions.md` | Global, sequential |
| `RISK-###` | Risk | `docs/product/risks.md` (when needed) | Global, sequential |
| `SPIKE-###` | Research spike | `docs/agile/product-backlog.md` | Global, sequential |
| `TC-###` | Test Case | `docs/testing/` | Global, sequential |
| `BUG-###` | Defect | Created during development | Global, sequential |

### Rules

1. **IDs are permanent.** Once an ID is issued it is never reused, renumbered, or reassigned
   — even if the item is deleted or deprecated. Deleting is done by setting status
   `DEPRECATED`, not by removing the file.
2. **Numbers are zero-padded to three digits** (`EPIC-007`), except `AC-##` which uses two.
3. **Acceptance criteria are story-scoped.** Refer to one as `US-014/AC-03`.
4. **File naming:** `<ID>-<kebab-case-slug>.md`, e.g. `EPIC-005-vehicle-management.md`.
   The slug may be improved later; the ID may not change.
5. **Allocation:** take the next free number from the relevant index file, and add your row to
   that index in the same change. If two people collide, the later change renumbers.

## 2. Requirement status

Every requirement-bearing document carries exactly one `status` in its front matter.

| Status | Definition | May be built against | Who may set it |
| --- | --- | --- | --- |
| `CONFIRMED` | Explicitly agreed by the product owner. | Yes | Product owner only |
| `PROPOSED` | Written down as a candidate. Plausible, not agreed. | No | Anyone |
| `UNDER DISCUSSION` | Actively contested or being worked out. Expect change. | No | Anyone |
| `OPEN QUESTION` | Information is missing; tracked as an `OQ-###`. | No | Anyone |
| `DEFERRED` | Understood, deliberately postponed beyond the current horizon. | No | Product owner |
| `DEPRECATED` | Was agreed, now withdrawn. Retained for traceability only. | No | Product owner |

### Rules

1. **Default status for anything newly written is `PROPOSED`.** Never write `CONFIRMED`
   unless the product owner has actually confirmed it, and the confirmation is recorded.
2. **An assumption is never `CONFIRMED`.** If you need a fact and do not have it, the
   correct artifact is an `OQ-###`, not a `PROPOSED` requirement that quietly hardens.
3. **Status may be set at document level and overridden at section level.** A `PROPOSED`
   epic may contain one `CONFIRMED` statement; mark it inline as
   `**[CONFIRMED]**` and explain why in the document's change log.
4. **Promotion is a recorded event.** When status changes, add a change-log row with the date
   and who agreed. This is the traceability the project requires in place of a frozen spec.
5. **`DEPRECATED` items stay in the repository.** They explain why the current design is what
   it is.

## 3. Inline status markers

When citing a requirement inside prose, carry its status with it if it is not `CONFIRMED`:

> Quotations may convert directly into jobs *(EPIC-007, PROPOSED)*.

This is what stops a reader — human or agent — from absorbing a draft as a decision.

## 4. Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Initial convention established during Phase 0 repository initialization. | Product owner (requested), drafted by Claude Code |
