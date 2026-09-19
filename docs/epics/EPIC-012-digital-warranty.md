---
id: EPIC-012
title: Digital Warranty
type: epic
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-006, MOD-011]
---

# EPIC-012 — Digital Warranty

| | |
| --- | --- |
| **Status** | `PROPOSED` — an initial backlog item, **not** a finalized requirement |
| **Refinement** | Not started |
| **Product goals** | `PG-006` |
| **Module** | `MOD-011` |
| **Backlog** | [product-backlog.md](../agile/product-backlog.md) |

## Intent

Generate and maintain digital warranties for eligible services — covering customer, vehicle, service/package, installation date, period, expiry, originating branch, terms, maintenance requirements and status — and allow them to be verified.

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
| [`OQ-025`](../product/open-questions.md) | Does warranty transfer when the vehicle changes owner? |
| [`OQ-026`](../product/open-questions.md) | What warranty statuses exist, who may void one, and does missed maintenance void it automatically? |
| [`OQ-027`](../product/open-questions.md) | Is QR verification public? What data may a scanner see? |

## Authorization and tenancy — `TODO`

Which roles may act in this epic, and how branch scoping applies, cannot be stated until
[OQ-019](../product/open-questions.md) is answered. [NFR-001](../product/non-functional-requirements.md)
(tenant isolation) applies to all work in this epic; any cross-organization access would need
a separate `CONFIRMED` requirement, which does not exist — see
[OQ-014](../product/open-questions.md).

## Notes

Warranty terms are commercial and legal promises. None of them may be inferred. OQ-027 in particular is a privacy decision: a public endpoint that resolves a QR code to customer and vehicle data is a different thing from one that returns only 'valid until <date>'.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
