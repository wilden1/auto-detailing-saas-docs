---
id: EPIC-005
title: Vehicle Management / Vehicle Passport
type: epic
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-004, MOD-004]
---

# EPIC-005 — Vehicle Management / Vehicle Passport

| | |
| --- | --- |
| **Status** | `PROPOSED` — an initial backlog item, **not** a finalized requirement |
| **Refinement** | Not started |
| **Product goals** | `PG-004` |
| **Module** | `MOD-004` |
| **Backlog** | [product-backlog.md](../agile/product-backlog.md) |

## Intent

Maintain vehicles and their centralized digital profile — information, owner, service history, job history, inspection history, before/after photos, warranty history, maintenance history and recommended future maintenance.

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
| [`OQ-013`](../product/open-questions.md) | Is a Vehicle unique platform-wide or per organization? |
| [`OQ-017`](../product/open-questions.md) | What identifies a Vehicle — registration, VIN, or both? What happens when a plate changes? |
| [`OQ-025`](../product/open-questions.md) | When a vehicle changes owner, what happens to history and warranties? |

## Authorization and tenancy — `TODO`

Which roles may act in this epic, and how branch scoping applies, cannot be stated until
[OQ-019](../product/open-questions.md) is answered. [NFR-001](../product/non-functional-requirements.md)
(tenant isolation) applies to all work in this epic; any cross-organization access would need
a separate `CONFIRMED` requirement, which does not exist — see
[OQ-014](../product/open-questions.md).

## Notes

The Vehicle Passport is the concept most likely to differentiate the product and the one most exposed to identity and privacy problems. OQ-013 and OQ-017 should be answered before any other part of this epic is refined.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
