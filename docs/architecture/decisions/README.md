---
title: Architecture Decision Records
type: index
status: CONFIRMED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Architecture Decision Records (ADRs)

An ADR records a decision that is expensive to reverse: the context it was taken in, the
options considered, what was decided, and what it costs us. It answers "why is it like
this?" long after everyone involved has forgotten.

## Log

| ID | Decision | Status | Date |
| --- | --- | --- | --- |
| [ADR-001](ADR-001-documentation-first-and-adr-process.md) | Documentation-first Phase 0, with ADRs for significant decisions | Accepted | 2026-09-19 |

## When to write one

Write an ADR when a choice:

- is expensive or disruptive to reverse, **or**
- constrains other decisions, **or**
- would surprise a competent engineer joining later, **or**
- selects a technology, vendor, protocol or external dependency, **or**
- changes the tenancy, security or data model

If in doubt, write it. An unnecessary ADR costs twenty minutes; a silent decision costs
months. [AGENTS.md rules 11–12](../../../AGENTS.md).

## Statuses

| Status | Meaning |
| --- | --- |
| `Proposed` | Written, not yet agreed |
| `Accepted` | Agreed and in force |
| `Superseded by ADR-###` | Replaced by a later decision |
| `Rejected` | Considered and declined — kept, because the reasoning is valuable |

## Rules

1. **ADRs are immutable once accepted.** To change a decision, write a new ADR and mark the
   old one `Superseded by ADR-###`. Never rewrite history.
2. One decision per ADR.
3. Record the options **not** chosen and why. That is most of the value.
4. Record the consequences honestly, including the bad ones.
5. Number sequentially; never reuse a number.

Template: [`templates/adr-template.md`](../../../templates/adr-template.md).
File as `ADR-###-kebab-slug.md` and add a row to the log above in the same change.
