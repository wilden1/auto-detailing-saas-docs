---
title: Future Productization
type: index
status: ACTIVE
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [ADR-002]
---

# Future Productization

> # ⚠️ NOTHING IN THIS FOLDER IS A V1 REQUIREMENT
>
> Everything here is **deferred**. It must not be built, designed for, estimated, or cited as
> justification for any V1 decision. It exists so that considerations already identified are
> **preserved rather than lost**, and so that a future productization effort does not start
> from scratch.
>
> Moving an item **out** of this folder requires an explicit product owner decision, recorded
> as an ADR.

## Why this folder exists

V1 is a single-company, multi-branch system for PRO-TECH —
[ADR-002](../architecture/decisions/ADR-002-v1-single-company-scope.md). There is a
longer-term intention to potentially productize it into a multi-tenant SaaS for other
automotive detailing businesses.

The documentation was originally written on the multi-tenant assumption. Rather than delete
that thinking, it is parked here.

## Deferred items

Recorded **by reference**. The source documents are not edited, so nothing is duplicated and
nothing can drift.

### Tenancy and platform operation

| Item | Where it currently lives | Note |
| --- | --- | --- |
| Multi-tenancy strategy (shared schema, schema-per-tenant, database-per-tenant) | [architecture/README.md](../architecture/README.md) ADR candidates | Deferred as a *decision*. It remains the single largest technical consequence of productizing later rather than now — see `ADR-002` consequences |
| Tenant provisioning and onboarding | `EPIC-001` intent | Not V1 |
| Tenant-specific configuration and branding | [scope.md §3](../product/scope.md) | Not V1 unless separately approved |
| Platform Operator persona | [personas.md](../product/personas.md) | A pure SaaS role with no V1 equivalent |
| "Single-branch business must not feel burdened by multi-branch concepts" | [glossary.md](../product/glossary.md) | A productization concern. PRO-TECH's branch count is a fact to research ([OQ-043](../product/open-questions.md)), not a variable to design around |
| `EPIC-001`'s tenant-administration half | [EPIC-001](../epics/EPIC-001-platform-and-organization-management.md) | The company/HQ configuration half stays in V1. The epic still needs splitting |

### Commercial

| Item | Where | Note |
| --- | --- | --- |
| SaaS subscription and billing — [OQ-035](../product/open-questions.md) | Open questions register | Question stays `OPEN` in the register; it is simply not a V1 question |

### Cross-organization data sharing

[OQ-014](../product/open-questions.md) — *"Under what circumstances, if any, should
controlled cross-organization data sharing be permitted?"* — stays `OPEN` in the register and
is **not** a V1 question.

Its four candidate scenarios remain **research topics only**, explicitly not requirements:

| Scenario | Why it is worth preserving |
| --- | --- |
| Vehicle Passport portability | The most valuable version of `PG-004` may require a vehicle's history to cross company boundaries |
| Warranty verification | A warranty issued by one company may need verifying by another |
| Franchise / network access | Related but separate businesses sharing a customer or vehicle view |
| Customer-authorized history sharing | The vehicle owner, rather than either business, authorizing a transfer of their own history |

These carry privacy, consent, competitive and possibly legal consequences that are not
understood. Do not design for any of them.

### Pending product owner decision — not yet deferred

| Item | State |
| --- | --- |
| [`NFR-001`](../product/non-functional-requirements.md) tenant isolation | **Still `CONFIRMED` and still in the main documentation.** Its subject — isolation between companies — is not a V1 concern, but the product owner has **deferred the decision** on what to do with it. It has deliberately **not** been moved here. Do not treat it as deferred, and do not build multi-tenancy on the strength of it. |

## What is *not* deferred

To prevent over-correction. These are **V1 concerns** and belong in the main documentation:

- Everything multi-**branch**: HQ visibility across branches, branch-specific staff access,
  customer and vehicle history across PRO-TECH branches, cross-branch warranty servicing,
  branch reporting, jobs belonging to branches, staff working across branches
- `Company`, `Branch`, `Customer`, `Vehicle`, `Job` as generic domain concepts
- Authorization ([`NFR-002`](../product/non-functional-requirements.md)), roles
  ([OQ-019](../product/open-questions.md)), branch scoping
  ([OQ-015](../product/open-questions.md), [OQ-016](../product/open-questions.md))
- Privacy, PDPA and audit obligations — they apply to one company too

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created following the V1 single-company direction change. Deferred items recorded by reference; `NFR-001` deliberately excluded pending a product owner decision. | Product owner decision |
