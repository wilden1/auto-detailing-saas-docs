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
| `NFR-001` | **Tenant isolation.** Tenant isolation must be enforced throughout the system. Users must not access or modify data outside their authorized organizational context except where an explicitly `CONFIRMED` requirement defines controlled cross-organization access. Tenant isolation must not be bypassed for convenience, testing, development, or demonstrations. | `CONFIRMED` | Product owner decision, 2026-09-19 — see change log |
| `NFR-002` | **Authorization is mandatory.** Authorization must be enforced for protected operations and must not be bypassed for convenience, testing, development, or demonstrations. Public or unauthenticated operations must only exist where explicitly defined by a `CONFIRMED` requirement. | `CONFIRMED` | Product owner decision, 2026-09-19 — see change log |

**These two are the canonical wording.** Other documents reference them by ID rather than
restating them, so the wording cannot drift.

Deliberately *not* stated here, because they are unresolved:

| Not specified | Why | Tracked as |
| --- | --- | --- |
| What defines an "authorized organizational context", and whether controlled cross-organization access should ever exist | Under research; no scenario has been approved | [OQ-014](open-questions.md) |
| The dimensions authorization is enforced against (roles, permissions) | Role model unresolved | [OQ-019](open-questions.md) |
| How branch-level access and scoping work | Branch access model unresolved | [OQ-015](open-questions.md) |
| Where authorization is enforced (e.g. server-side) and by what mechanism | Belongs to later technical/security design, not to a product requirement | — |
| Whether public warranty verification becomes a defined exception under `NFR-002` | Not decided | [OQ-027](open-questions.md) |

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
| 2026-09-19 | **`NFR-001` rewritten, status `CONFIRMED` retained.** The original asserted that no user may read or modify another Organization's data, full stop. That decided [OQ-014](open-questions.md) — which was, and remains, `OPEN` — by implication, and contradicted `docs/data/README.md`, which recorded the same proposition as a working assumption rather than a decision. The rewrite confirms tenant isolation as a security principle **without** prematurely ruling out controlled cross-organization functionality. | Product owner decision |
| 2026-09-19 | **`NFR-002` rewritten, status `CONFIRMED` retained.** The original required every operation to be authorized against "role and branch scope", but the role model ([OQ-019](open-questions.md)) and branch access model ([OQ-015](open-questions.md)) are both unresolved — so a `CONFIRMED` requirement was expressed in undefined terms and could not be verified. The rewrite states the principle only; the enforcement dimensions follow once those questions are answered. "Server-side", which had drifted into the restated copy in `docs/security/README.md`, is deliberately excluded as implementation detail belonging to later technical/security design. | Product owner decision |
