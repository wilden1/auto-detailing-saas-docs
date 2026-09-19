---
id: EPIC-003
title: Staff & Access Control
type: epic
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-002, MOD-015]
---

# EPIC-003 — Staff & Access Control

| | |
| --- | --- |
| **Status** | `PROPOSED` — an initial backlog item, **not** a finalized requirement |
| **Refinement** | Not started |
| **Product goals** | `PG-002` |
| **Module** | `MOD-015` |
| **Backlog** | [product-backlog.md](../agile/product-backlog.md) |

## Intent

Manage staff accounts, their roles, and what each role may see and do, within and across branches.

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
| [`OQ-016`](../product/open-questions.md) | Can one user belong to multiple branches? Multiple organizations? |
| [`OQ-019`](../product/open-questions.md) | What roles exist and what may each do? Can one person hold several? |

## Authorization and tenancy — `TODO`

Which roles may act in this epic, and how branch scoping applies, cannot be stated until
[OQ-019](../product/open-questions.md) is answered. [NFR-001](../product/non-functional-requirements.md)
(tenant isolation) applies unconditionally.

## Notes

Nothing in this epic can be refined until OQ-019 is answered; every other epic's authorization criteria depend on its outcome. See [NFR-002](../product/non-functional-requirements.md).

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
