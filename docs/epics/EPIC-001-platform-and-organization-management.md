---
id: EPIC-001
title: Platform & Organization Management
type: epic
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-002, MOD-001]
---

# EPIC-001 — Platform & Organization Management

| | |
| --- | --- |
| **Status** | `PROPOSED` — an initial backlog item, **not** a finalized requirement |
| **Refinement** | Not started |
| **Product goals** | `PG-002` |
| **Module** | `MOD-001` |
| **Backlog** | [product-backlog.md](../agile/product-backlog.md) |

## Intent

Create and administer the tenants of the Platform: organizations (customer businesses), their top-level settings, and the platform-operator functions needed to onboard and support them.

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
| [`OQ-035`](../product/open-questions.md) | How is the SaaS itself sold — subscription tiers, per-branch, per-user, trial? |
| [`OQ-014`](../product/open-questions.md) | Is cross-organization data sharing ever permitted? |

## Authorization and tenancy — `TODO`

Which roles may act in this epic, and how branch scoping applies, cannot be stated until
[OQ-019](../product/open-questions.md) is answered. [NFR-001](../product/non-functional-requirements.md)
(tenant isolation) applies unconditionally.

## Notes

The Organization is the working tenant boundary (see [glossary](../product/glossary.md)). Whether this epic also covers subscription billing for the Platform depends on OQ-035.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
