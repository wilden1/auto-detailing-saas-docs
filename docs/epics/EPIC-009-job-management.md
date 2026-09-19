---
id: EPIC-009
title: Job Management
type: epic
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-001, MOD-008]
---

# EPIC-009 — Job Management

| | |
| --- | --- |
| **Status** | `PROPOSED` — an initial backlog item, **not** a finalized requirement |
| **Refinement** | Not started |
| **Product goals** | `PG-001` |
| **Module** | `MOD-008` |
| **Backlog** | [product-backlog.md](../agile/product-backlog.md) |

## Intent

Track the work performed on a vehicle from check-in through execution and progress to quality control and handover.

*This is a restatement of the current product direction. It has not been validated with
users and it is not a commitment to build.*

## Scope — `TODO`

Not defined. Scope will be drawn when this epic is refined, and refinement should not begin
until the blocking open questions below are answered. Filling this section in now would mean
inventing the rules the features would assert.

## Features

| ID | Feature | Status |
| --- | --- | --- |
| — | None yet | — |

Features are created in [docs/features/](../features/README.md) using
[`templates/feature-template.md`](../../templates/feature-template.md).

## Business rules

None recorded. Rules discovered during refinement are written to
[docs/business-rules/](../business-rules/README.md) as `BR-###` and referenced from here.

## Blocking open questions

| ID | Question |
| --- | --- |
| [`OQ-028`](../product/open-questions.md) | Is a Job one visit, or one service within a visit? Can one booking produce multiple jobs? |
| [`OQ-023`](../product/open-questions.md) | Is Quality Control a job status, or a separate record with its own outcome and rework loop? |

## Authorization and tenancy — `TODO`

Which roles may act in this epic, and how branch scoping applies, cannot be stated until
[OQ-019](../product/open-questions.md) is answered. [NFR-001](../product/non-functional-requirements.md)
(tenant isolation) applies unconditionally.

## Notes

OQ-028 is the highest-leverage unanswered modelling question in the product. Inspections, payments, warranties and reporting all attach to whatever a Job turns out to be.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
