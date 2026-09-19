---
title: Data Model
type: index
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [OQ-012, OQ-013, OQ-014, OQ-015, OQ-016, OQ-017, OQ-028]
---

# Data

> **No schema. No tables. No columns. No ERD.** Phase 0 produces a *conceptual* model — what
> exists and how it relates — not a physical one. Producing a schema now would freeze the
> answers to questions nobody has asked yet.

## Conceptual entities — `PROPOSED`

Entities implied by the current product direction. Each is a candidate, not a table.

**Tenancy**

- Organization *(working tenant boundary)*
- Branch
- User / Staff
- Role

**Parties and assets**

- Customer
- Vehicle
- Vehicle Passport *(may be a view over other entities rather than an entity — undecided)*

**Commercial**

- Service
- Package
- Quotation
- Payment

**Operations**

- Booking / Walk-in
- Job
- Job Progress
- Vehicle Inspection *(with photographic evidence)*

**After-service**

- Digital Warranty
- Maintenance
- Follow-up / CRM activity

## Ownership boundaries — `OPEN QUESTION`

The product owner has stated that entity ownership and data boundaries are **not finalized**.
They are the most consequential unresolved part of the product.

| Question | |
| --- | --- |
| Is a Customer owned by the Organization or by a Branch? | [OQ-012](../product/open-questions.md) |
| Is a Vehicle unique platform-wide or per organization? | [OQ-013](../product/open-questions.md) |
| Is cross-**organization** sharing ever permitted? | [OQ-014](../product/open-questions.md) |
| What makes a branch authorized to see another branch's records? | [OQ-015](../product/open-questions.md) |
| Can a user belong to multiple branches or organizations? | [OQ-016](../product/open-questions.md) |
| What identifies a Vehicle, and what happens when a plate changes? | [OQ-017](../product/open-questions.md) |
| Is a Job one visit or one service within a visit? | [OQ-028](../product/open-questions.md) |

**The working assumption — not a decision — is that the Organization is the tenant boundary
and that no data crosses between organizations.** It is recorded here so it can be confirmed
or contradicted, and it must not be built on until it is
[confirmed](../product/open-questions.md) ([OQ-014](../product/open-questions.md)).

Note the tension: [OQ-013](../product/open-questions.md) (a platform-wide vehicle identity)
would make the Vehicle Passport far more valuable and would also breach that working
assumption. This is a product decision with privacy and competitive consequences, not a
modelling detail.

## What this folder will contain

| Document | When |
| --- | --- |
| Conceptual entity–relationship description (prose + diagram, no columns) | After `OQ-012`, `OQ-013`, `OQ-015`, `OQ-028` are answered — `DOC-005` |
| Tenancy and ownership rules, per entity | Same |
| Entity lifecycle and state descriptions | With the workflows |
| Data retention and deletion rules | With [OQ-018](../product/open-questions.md) |
| Physical schema | **Phase 1, in the implementation repository — never here** |

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created during Phase 0 initialization. Candidate entities listed; ownership boundaries left explicitly open. | Drafted by Claude Code |
