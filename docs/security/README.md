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

| ID | Principle | Canonical wording |
| --- | --- | --- |
| `NFR-001` | Tenant isolation | [non-functional-requirements.md](../product/non-functional-requirements.md) |
| `NFR-002` | Authorization is mandatory | [non-functional-requirements.md](../product/non-functional-requirements.md) |

**The wording of both lives in exactly one place** — the file linked above. It is not
restated here. An earlier version of this page carried its own paraphrase, which had already
drifted from the canonical text (it added "server-side", which the requirement does not say).

These are not negotiable and not deferrable to "after the feature works".
[AGENTS.md rules 7–8](../../AGENTS.md).

Note what `NFR-001` does **not** say: it does not rule out controlled cross-organization
access. Whether any such access should exist, and under what circumstances, is
[OQ-014](../product/open-questions.md) — `OPEN`. Nothing may be designed on the assumption of
either answer.

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
| Under what circumstances, if any, is controlled cross-organization access permitted? | [OQ-014](../product/open-questions.md) |
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
| 2026-09-19 | Removed the locally-worded copies of `NFR-001`/`NFR-002` in favour of references to the canonical definitions, after the paraphrase here was found to have drifted (it added "server-side"). Aligned the `OQ-014` wording. | Product owner decision |
