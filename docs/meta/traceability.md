---
title: Traceability Model
type: standard
status: ACTIVE
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Traceability Model

Deliberately lightweight. Traceability here is **links in front matter plus a single index
table** — not a matrix that has to be maintained by hand.

## The chain

```
Product Goal (PG)
   └── Epic (EPIC)
          └── Feature (FEAT)
                 └── User Story (US)
                        ├── Acceptance Criteria (AC)
                        │        └── Test Case (TC)
                        ├── Business Rules (BR)
                        └── Non-Functional Requirements (NFR)

Architecture / Data / API design  ──references──▶  EPIC / FEAT / US / BR / NFR
Architecture Decision Record (ADR) ──constrains──▶ the design that follows it
Open Question (OQ)                 ──blocks──▶     any item that cannot proceed without it
```

## How the links are recorded

| From | To | How |
| --- | --- | --- |
| Feature → Epic | parent | `related:` front matter + a link in the body |
| Story → Feature | parent | `related:` front matter + a link in the body |
| Story → Business rules | dependency | "Business rules" section listing `BR-###` |
| Story → NFRs | dependency | "Non-functional requirements" section listing `NFR-###` |
| AC → Test case | verification | Test case front matter `related: [US-014/AC-03]` |
| Anything → Open question | blocker | "Open questions" section listing `OQ-###` |
| Epic → Module | product area | Mapping table in [docs/modules/README.md](../modules/README.md) |

Each index (`docs/epics/README.md`, `docs/features/README.md`, …) carries the parent column,
so the chain is readable in one place per level without a separate matrix.

## Rules

1. **Every child names its parent.** A feature with no epic, or a story with no feature, is
   incomplete and cannot be `READY`.
2. **Orphans are a defect.** If a requirement cannot be traced up to a product goal, either
   the goal is missing or the requirement is not wanted. Raise it.
3. **Coverage is asserted at the story level.** A story is not `DONE` until every acceptance
   criterion has at least one test case referencing it.
4. **Blocked-by is explicit.** If an open question blocks an item, the item lists the `OQ-###`
   and cannot be `READY` (see [Definition of Ready](../agile/definition-of-ready.md)).
5. **Do not build a traceability matrix document.** It becomes stale immediately. The indexes
   are the matrix.

## What is deliberately *not* traced

- Individual commits to acceptance criteria (the PR and its cited IDs are enough)
- Design mockups to stories at pixel level
- Every NFR to every story — NFRs that apply platform-wide are stated once and referenced by
  the Definition of Done instead

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Initial model established during Phase 0 repository initialization. | Product owner (requested), drafted by Claude Code |
