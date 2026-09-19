---
id: EPIC-010
title: Vehicle Inspection
type: epic
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-006, MOD-009]
---

# EPIC-010 — Vehicle Inspection

| | |
| --- | --- |
| **Status** | `PROPOSED` — an initial backlog item, **not** a finalized requirement |
| **Refinement** | Not started |
| **Product goals** | `PG-006` |
| **Module** | `MOD-009` |
| **Backlog** | [product-backlog.md](../agile/product-backlog.md) |

## Intent

Document vehicle condition with structured observations and photographs — front, rear, left, right, interior, windscreen, wheels, existing scratches, dents, stone chips, paint damage and other observations — before and after service.

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
| [`OQ-036`](../product/open-questions.md) | Is an inspection mandatory before every job, or only for certain services? |
| [`OQ-038`](../product/open-questions.md) | Must inspection work with poor or no connectivity on the workshop floor? |
| [`OQ-039`](../product/open-questions.md) | How many photos per inspection, at what quality, kept for how long? |

## Authorization and tenancy — `TODO`

Which roles may act in this epic, and how branch scoping applies, cannot be stated until
[OQ-019](../product/open-questions.md) is answered. [NFR-001](../product/non-functional-requirements.md)
(tenant isolation) applies unconditionally.

## Notes

This is the most demanding epic technically: many photographs, captured on mobile devices, in the place with the worst signal. OQ-038 is an architectural decision made at the start or never.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
