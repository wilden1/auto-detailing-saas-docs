---
id: EPIC-014
title: CRM & Customer Follow-up
type: epic
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-005, MOD-013]
---

# EPIC-014 — CRM & Customer Follow-up

| | |
| --- | --- |
| **Status** | `PROPOSED` — an initial backlog item, **not** a finalized requirement |
| **Refinement** | Not started |
| **Product goals** | `PG-005` |
| **Module** | `MOD-013` |
| **Backlog** | [product-backlog.md](../agile/product-backlog.md) |

## Intent

Identify customers who need contacting — maintenance due, maintenance overdue, inactive customers, unconverted quotations, outstanding payments, warranty follow-ups — and support staff in contacting them.

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
| [`OQ-033`](../product/open-questions.md) | How are WhatsApp messages actually delivered — Cloud API, a provider, or staff-initiated links? |
| [`OQ-011`](../product/open-questions.md) | Which languages must customer-facing messages support? |

## Authorization and tenancy — `TODO`

Which roles may act in this epic, and how branch scoping applies, cannot be stated until
[OQ-019](../product/open-questions.md) is answered. [NFR-001](../product/non-functional-requirements.md)
(tenant isolation) applies unconditionally.

## Notes

WhatsApp workflows are expected to matter for the Malaysian SME market (PROPOSED). The delivery mechanism has large cost, approval and compliance consequences and is worth a spike (SPIKE-003) before this epic is refined.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
