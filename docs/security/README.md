---
title: Security, Privacy and Access Control
type: index
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [NFR-001, NFR-002, OQ-014, OQ-015, OQ-018, OQ-019, OQ-027, OQ-040]
---

# Security, Privacy and Access Control

Two things here are `CONFIRMED` and binding. Everything else is open.

## Binding principles — `CONFIRMED`

| ID | Principle |
| --- | --- |
| [`NFR-001`](../product/non-functional-requirements.md) | **Tenant isolation.** No user may read or modify another organization's data. Isolation holds at every layer and is never bypassed — not for tests, not for local development, not for a demo. |
| [`NFR-002`](../product/non-functional-requirements.md) | **Authorization is mandatory.** Every operation is authorized server-side against the acting user's role and branch scope. Exceptions exist only where a `CONFIRMED` requirement defines one. |

These are not negotiable and not deferrable to "after the feature works".
[AGENTS.md rules 7–8](../../AGENTS.md).

## Tenancy model — `PROPOSED`

```
Platform
  └── Organization        ← working tenant boundary
        └── Branch
              └── User / Staff
```

Unresolved, and each answer changes the security model materially:

| Question | |
| --- | --- |
| Is cross-organization access ever permitted? | [OQ-014](../product/open-questions.md) |
| Open-by-default or explicitly granted cross-branch access? | [OQ-015](../product/open-questions.md) |
| Can a user span branches or organizations? | [OQ-016](../product/open-questions.md) |
| Is a platform-wide vehicle identity compatible with tenant isolation? | [OQ-013](../product/open-questions.md) |

## Access control — `OPEN QUESTION`

Role-based access control is named as a platform concern, but **no roles are defined**
([OQ-019](../product/open-questions.md)) and no permission matrix exists. Two constraints
are already visible from the domain:

1. A single-person business holds every role at once — the model must not assume separation
   of duties.
2. Branch scope and role are **independent** dimensions. "Manager" says what you may do;
   branch scope says where. Conflating them will not survive multi-branch customers.

## Privacy — `OPEN QUESTION`

The product handles personal data (customers), asset data (vehicles, plates) and
photographic evidence. Obligations are undetermined —
[OQ-018](../product/open-questions.md), and depend on market
([OQ-002](../product/open-questions.md)).

Highest-risk open item: **public QR warranty verification**
([OQ-027](../product/open-questions.md)). An endpoint that turns a scanned code into
customer and vehicle details is a data-exposure decision, not a feature detail.

## Audit logging — `OPEN QUESTION`

Listed as a platform concern with no definition: what is audited, who may read it, how long
it is kept — [OQ-040](../product/open-questions.md).

## To be documented here

- Threat model
- Authentication mechanism (as an ADR)
- Permission matrix: role × operation × scope
- Data classification and handling rules
- Photo/file access control — an inspection photo is customer data
- Secret management, dependency policy, incident response

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created during Phase 0 initialization. `NFR-001`/`NFR-002` recorded as binding; role model and privacy obligations left open. | Drafted by Claude Code |
