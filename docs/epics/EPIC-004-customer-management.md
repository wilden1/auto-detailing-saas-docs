---
id: EPIC-004
title: Customer Management
type: epic
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-001, MOD-003]
---

# EPIC-004 — Customer Management

| | |
| --- | --- |
| **Status** | `PROPOSED` — an initial backlog item, **not** a finalized requirement |
| **Refinement** | Not started |
| **Product goals** | `PG-001` |
| **Module** | `MOD-003` |
| **Backlog** | [product-backlog.md](../agile/product-backlog.md) |

## Intent

Record and maintain customers — the people and companies who own the vehicles the business serves — and their relationship to vehicles, quotations, jobs, payments and warranties.

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
| [`OQ-012`](../product/open-questions.md) | Is a Customer owned by the Organization or by a Branch? |
| [`OQ-018`](../product/open-questions.md) | What PDPA / data-protection obligations apply to customer records? |

## Authorization and tenancy — `TODO`

Which roles may act in this epic, and how branch scoping applies, cannot be stated until
[OQ-019](../product/open-questions.md) is answered. [NFR-001](../product/non-functional-requirements.md)
(tenant isolation) applies unconditionally.

## Notes

Duplicate customers are a predictable operational problem (same person, two phone numbers, two branches). How duplicates are prevented or merged is not yet specified.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
