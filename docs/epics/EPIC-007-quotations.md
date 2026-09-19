---
id: EPIC-007
title: Quotations
type: epic
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-001, MOD-006]
---

# EPIC-007 — Quotations

| | |
| --- | --- |
| **Status** | `PROPOSED` — an initial backlog item, **not** a finalized requirement |
| **Refinement** | Not started |
| **Product goals** | `PG-001` |
| **Module** | `MOD-006` |
| **Backlog** | [product-backlog.md](../agile/product-backlog.md) |

## Intent

Produce priced offers for a customer and vehicle, share them, track their outcome, and convert accepted quotations into scheduled or executed work.

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
| [`OQ-021`](../product/open-questions.md) | What does an accepted quotation become — a booking, a job, both, or nothing automatic? |

## Authorization and tenancy — `TODO`

Which roles may act in this epic, and how branch scoping applies, cannot be stated until
[OQ-019](../product/open-questions.md) is answered. [NFR-001](../product/non-functional-requirements.md)
(tenant isolation) applies to all work in this epic; any cross-organization access would need
a separate `CONFIRMED` requirement, which does not exist — see
[OQ-014](../product/open-questions.md).

## Notes

Unconverted quotations are named as a CRM follow-up trigger (EPIC-014), so quotation state must be tracked well enough to support that.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
