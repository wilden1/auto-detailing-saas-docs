---
id: ADR-002
title: V1 is a single-company multi-branch system for PRO-TECH, not a multi-tenant SaaS
type: adr
status: Accepted
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# ADR-002 — V1 is a single-company multi-branch system for PRO-TECH, not a multi-tenant SaaS

**Status:** Accepted · **Date:** 2026-09-19 · **Decided by:** Product owner

## Context

The project was initiated as a multi-tenant SaaS platform for automotive detailing and
related appearance businesses. [ADR-001](ADR-001-documentation-first-and-adr-process.md)
records that framing in its context section, and the documentation built on it: the vision,
the glossary, `EPIC-001`, the security and data documentation, and the binding agent rules
in `AGENTS.md` all assumed many isolated companies sharing one deployment.

After reviewing the project direction, the product owner determined that V1 should serve one
business — **PRO-TECH** — operating multiple branches. The longer-term intention to
productize the system for other detailing businesses remains, but building multi-tenancy now
would add cost and complexity to serve customers who do not exist yet, and would do so before
the domain itself is understood. Research into the actual detailing job lifecycle has not yet
been done; fundamental questions such as what constitutes a Job ([OQ-028](../../product/open-questions.md))
remain open.

## Decision

**V1 is a single-company, multi-branch Automotive Detailing Management System for PRO-TECH.**

```
PRO-TECH
  → HQ / Management
    → Multiple Branches
      → Staff → Customers → Vehicles → Quotations → Appointments / Walk-ins
        → Jobs → Inspections → QC → Payments → Warranties → Maintenance / Follow-up
```

1. **Multi-branch operation is in V1 scope** and is an important requirement. HQ visibility
   across branches, branch-specific staff access, customer and vehicle history across
   branches, cross-branch warranty servicing, branch reporting, job ownership by branch, and
   staff working across branches are all real V1 concerns — and all are **unresolved**,
   pending research.

2. **Multi-tenancy is not a V1 requirement.** Specifically out of V1 scope: tenant
   provisioning, tenant onboarding, cross-tenant data sharing, SaaS subscription and billing,
   and tenant-specific configuration or branding unless separately approved.

3. **Complexity is not added solely to support hypothetical future tenants.**

4. **Generic domain concepts are retained.** PRO-TECH-specific assumptions are not hardcoded
   where a clean generic concept — `Company`, `Branch`, `Customer`, `Vehicle`, `Job` — is
   sufficient. This is the cheapest available productization insurance and costs nothing in
   V1. It is a naming and modelling discipline, **not** a licence to build tenancy machinery.

5. **Deferred SaaS considerations are preserved, not deleted**, in
   [`docs/future-productization/`](../../future-productization/README.md), clearly marked as
   non-requirements.

The governing principle: **build for one company now, keep future productization possible,
but do not implement multi-tenancy prematurely.**

## Relationship to ADR-001

`ADR-001` remains **Accepted** and is **not superseded**. Its decision — documentation-first
Phase 0, documentation as source of truth, explicit requirement status, Agile over waterfall,
ADRs for significant decisions, binding agent rules — is unaffected by this change and applies
in full.

What is affected is `ADR-001`'s *context*, which describes a multi-tenant SaaS. Per the
immutability rule, that text is left exactly as written; this ADR supplies the current product
context. Read together, they show the direction changed and when.

## Options considered

| Option | Why not chosen |
| --- | --- |
| **Single-company V1, productize later** | *Chosen.* Matches the only customer that exists, defers cost until there is revenue to justify it, and keeps the domain model clean enough to extend. |
| Build multi-tenant from the start | Pays the full cost of tenancy — isolation, provisioning, billing, configuration — to serve hypothetical customers, before the domain is understood. The most expensive way to discover the domain is wrong. |
| Single-company with no regard for future productization | Cheapest now, but bakes PRO-TECH into the domain model. Productizing later would mean a rewrite rather than an extension. Rejected because the productization intent is real. |
| Defer the decision until after research | Rejected because the documentation currently instructs AI agents that the system *is* multi-tenant. Leaving that in place means work is done on a false premise in the meantime. |

## Consequences

**Positive**

- V1 scope shrinks materially: no tenant provisioning, isolation, billing or onboarding.
- Branch modelling — the part that genuinely matters to PRO-TECH — gets the attention that
  tenancy would otherwise have absorbed.
- Agents are no longer instructed to design for multi-tenancy.
- Research can focus on how PRO-TECH actually works rather than on a market abstraction.

**Negative**

- **Productization later will cost more than building it in now**, if it happens. That is an
  accepted, deliberate trade.
- Documentation carries two horizons — V1 and future productization — and the boundary must
  be actively maintained or the deferred material will leak back in as requirements.
- Several documents still reflect the old direction. They are corrected progressively, not all
  at once, so a transitional period of inconsistency is expected and must be visible.
- Point 4 (generic concepts) and point 3 (no complexity for hypothetical tenants) are in
  tension at the margin. Judgement is required, and disagreements should surface as open
  questions rather than be settled silently.

**Neutral**

- The repository name and several document titles still reference SaaS. Cosmetic; renaming is
  cheap and can follow.

## Unresolved by this decision

| Item | State |
| --- | --- |
| [`NFR-001`](../../product/non-functional-requirements.md) tenant isolation | `CONFIRMED`, and its subject is not a V1 concern. **The product owner has deferred this decision.** Until it is made, the conflict stands and must not be resolved by inference in either direction. |
| [OQ-042](../../product/open-questions.md) | Does an explicit `Company` entity exist in V1's domain model? |
| [OQ-043](../../product/open-questions.md) | How many branches does PRO-TECH operate today? |
| [OQ-044](../../product/open-questions.md) | Is HQ a Branch, a level above Branch, or a permission scope? |
| `EPIC-001` | Still titled and scoped as *Platform & Organization Management*. Needs splitting: company/HQ configuration is V1, tenant administration is not. |

## Compliance

- `AGENTS.md` rule 7 and `CLAUDE.md` state the V1 boundary and the known `NFR-001` conflict.
- The [glossary](../../product/glossary.md) marks `Platform`, `Tenant` and
  `Single-branch business` as non-V1 concepts.
- [`docs/future-productization/`](../../future-productization/README.md) holds deferred items
  and states plainly that nothing in it is a requirement.

## Revisit when

PRO-TECH's system is in production and a second business wants to use it — or when a concrete,
funded productization decision is taken. At that point this ADR is superseded, not amended.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Accepted. Records the V1 single-company direction and its boundaries. | Product owner |
