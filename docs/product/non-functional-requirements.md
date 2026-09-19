---
title: Non-Functional Requirements
type: nfr
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [OQ-018, OQ-038, OQ-039, OQ-040]
---

# Non-Functional Requirements

Quality constraints that apply across the product. **Almost nothing here is decided yet** —
this file exists so that NFRs have a home and an ID space, and so that the categories that
must be filled are visible.

> Numbers are the substance of an NFR. An NFR without a number ("must be fast") is not a
> requirement. Where no number has been agreed, this file says so rather than inventing one.

## Defined

| ID | Requirement | Status | Source |
| --- | --- | --- | --- |
| `NFR-001` | **Tenant isolation.** No user may read or modify data belonging to another Organization. Isolation must hold at every layer and must never be bypassed for convenience, testing or local development. | `CONFIRMED` | Stated by the product owner as a binding rule ([AGENTS.md](../../AGENTS.md) rules 7–8) |
| `NFR-002` | **Authorization is mandatory.** Every operation is authorized against the acting user's role and branch scope. There are no unauthenticated or unauthorized operations except where a `CONFIRMED` requirement explicitly defines one (e.g. possible public warranty verification, [OQ-027](open-questions.md)). | `CONFIRMED` | Stated by the product owner |

## Categories still to be defined

Each of these needs a measurable target from the product owner. Listed so the gaps are
visible; **do not fill them in with industry defaults.**

| Category | What must be decided | Related |
| --- | --- | --- |
| Performance | Page/interaction response targets, under what load, on what devices | — |
| Photo handling | Upload size, count per inspection, compression, time to upload on mobile data | [OQ-039](open-questions.md) |
| Availability | Uptime expectation, acceptable maintenance windows, what happens during an outage mid-job | — |
| Connectivity | Whether the workshop floor requires offline or degraded-network operation | [OQ-038](open-questions.md) |
| Scale | Organizations, branches, users, vehicles, jobs/day, photos/month at year 1 and year 3 | — |
| Data retention | How long jobs, photos, inspections and audit logs are kept | [OQ-018](open-questions.md), [OQ-040](open-questions.md) |
| Privacy / PDPA | Consent, access, correction, deletion obligations | [OQ-018](open-questions.md) |
| Auditability | What is logged, who may read it, retention | [OQ-040](open-questions.md) |
| Backup & recovery | RPO and RTO | — |
| Usability | Target device and context (tablet in a workshop, gloved hands, glare), accessibility level | — |
| Localization | Languages, date/number/currency formats | [OQ-011](open-questions.md) |
| Security | Authentication strength, session handling, secret handling, dependency policy | — |
| Observability | What must be measurable in production | — |

## Rules for adding an NFR

1. State a number and the conditions under which it must hold.
2. Say how it will be verified — an unverifiable NFR is a wish.
3. Set status honestly: `PROPOSED` until the product owner agrees.
4. Reference it from the [Definition of Done](../agile/definition-of-done.md) if it applies
   to all work, rather than copying it into every story.

Use [`templates/nfr-template.md`](../../templates/nfr-template.md).

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created during Phase 0 initialization. `NFR-001`/`NFR-002` recorded as `CONFIRMED` from stated agent rules; all other categories left open. | Drafted by Claude Code |
