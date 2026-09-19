---
id: EPIC-011
title: Payments
type: epic
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-001, MOD-010]
---

# EPIC-011 — Payments

| | |
| --- | --- |
| **Status** | `PROPOSED` — an initial backlog item, **not** a finalized requirement |
| **Refinement** | Not started |
| **Product goals** | `PG-001` |
| **Module** | `MOD-010` |
| **Backlog** | [product-backlog.md](../agile/product-backlog.md) |

## Intent

Record money received against work, and whatever documentation of it the business and its customers require.

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
| [`OQ-007`](../product/open-questions.md) | Is invoicing and tax compliance (e.g. Malaysian e-Invoice) in scope? |
| [`OQ-024`](../product/open-questions.md) | Are deposits and partial payments supported? Must a job be paid before handover? |
| [`OQ-034`](../product/open-questions.md) | Which payment methods must be supported? |

## Authorization and tenancy — `TODO`

Which roles may act in this epic, and how branch scoping applies, cannot be stated until
[OQ-019](../product/open-questions.md) is answered. [NFR-001](../product/non-functional-requirements.md)
(tenant isolation) applies to all work in this epic; any cross-organization access would need
a separate `CONFIRMED` requirement, which does not exist — see
[OQ-014](../product/open-questions.md).

## Notes

OQ-007 determines whether this epic is record-keeping or a statutory integration workstream. The answer changes its size by an order of magnitude.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
