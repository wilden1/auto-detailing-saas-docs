---
title: Identifiers and Requirement Status
type: standard
status: ACTIVE
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Identifiers and Requirement Status

This convention is `ACTIVE` — in force for the documentation process itself. It may be
refined; any change is recorded in the change log at the bottom of this file.

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
| `OQ-###` | Open Question | `docs/product/open-questions.md` — one row per question. Long form, where a question needs more than a row: `docs/product/open-questions/OQ-###-slug.md` | Global, sequential |
| `RISK-###` | Risk | `docs/product/risks.md` — **not yet created. Create it with the first risk; do not create it empty.** | Global, sequential |
| `SPIKE-###` | Research spike | `docs/agile/product-backlog.md` | Global, sequential |
| `TC-###` | Test Case | `docs/testing/` | Global, sequential |
| `BUG-###` | Defect | Raised during development; where they live depends on [OQ-031](../product/open-questions.md) | Global, sequential |

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

Every **requirement-bearing** document carries exactly one `status` in its front matter.
Documents that carry no requirements use the separate vocabulary in section 3.

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
   epic may contain one `CONFIRMED` statement. Mark it using the section-heading form in
   section 4 and explain why in the document's change log.
4. **Promotion is a recorded event.** When status changes, add a change-log row with the date
   and who agreed. This is the traceability the project requires in place of a frozen spec.
5. **`DEPRECATED` items stay in the repository.** They explain why the current design is what
   it is.

## 3. Status for non-requirement documents

Indexes, standards and registers assert no requirements, so the taxonomy above does not
apply to them — calling a navigation page `CONFIRMED` says nothing useful. They use:

| Status | Meaning | Applies to |
| --- | --- | --- |
| `ACTIVE` | In force and current | Indexes, standards, registers (`type: index`, `standard`) |
| `DRAFT` | Being written; do not rely on it yet | Any non-requirement document |
| `SUPERSEDED` | Replaced by another document, kept for traceability | Any non-requirement document |

Two clarifications:

- **Process documents keep the requirement vocabulary.** The Definition of Ready, Definition
  of Done and sprint process are `PROPOSED` because they genuinely await team ratification.
  That is a meaningful claim, not a category error.
- **A document that carries content as well as navigation uses the requirement vocabulary.**
  `docs/workflows/README.md` is `PROPOSED` because it states the lifecycle, not merely links
  to it. Status describes the *content*, not the file's role.

### ADR status is its own vocabulary

Architecture Decision Records use `Proposed` / `Accepted` / `Superseded by ADR-###` /
`Rejected`, defined in
[docs/architecture/decisions/README.md](../architecture/decisions/README.md). Do not mix the
two vocabularies.

## 4. Inline and section status markers

**Citing a requirement in prose** — carry its status with it if it is not `CONFIRMED`:

> Quotations may convert directly into jobs *(EPIC-007, PROPOSED)*.

**Marking a section** whose status differs from the document's — append the backticked status
to the heading:

```markdown
## 2. What makes it more than a booking system — `CONFIRMED`
```

This is what stops a reader — human or agent — from absorbing a draft as a decision.

## 5. Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Initial convention established during Phase 0 repository initialization. | Product owner (requested), drafted by Claude Code |
| 2026-09-19 | Review cleanup: added the non-requirement status vocabulary (`ACTIVE`/`DRAFT`/`SUPERSEDED`) and documented ADR's separate vocabulary (finding 8); replaced the unused `**[CONFIRMED]**` inline marker with the section-heading form already in use (finding 7); removed the dangling `risks.md` path and gave long-form open questions a home (findings 5, 6). | Drafted by Claude Code |
