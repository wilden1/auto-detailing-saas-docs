---
title: Product Vision
type: product-doc
status: UNDER DISCUSSION
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [OQ-001, OQ-002, OQ-005]
---

# Product Vision

> **Status note.** The *direction* below is `CONFIRMED` — it restates what the product owner
> has stated. The *framing, goals and hypotheses* are `PROPOSED` and need explicit
> confirmation before anything is built against them. Nothing here has been validated with
> real businesses yet.

## 1. What we are building — `CONFIRMED`

**V1 is a single-company, multi-branch Automotive Detailing Management System for
PRO-TECH.** PRO-TECH may operate multiple branches, so multi-branch operation is an
important V1 requirement.

```
PRO-TECH
  → HQ / Management
    → Multiple Branches
      → Staff → Customers → Vehicles → Quotations → Appointments / Walk-ins
        → Jobs → Inspections → QC → Payments → Warranties → Maintenance / Follow-up
```

**V1 is not a multi-tenant SaaS platform.** There is a longer-term intention to potentially
productize the system and offer it to other automotive detailing businesses, but
multi-tenancy, tenant provisioning, tenant onboarding, cross-tenant sharing, SaaS billing and
tenant-specific branding are **all out of V1 scope** —
[ADR-002](../architecture/decisions/ADR-002-v1-single-company-scope.md),
[future-productization](../future-productization/README.md).

The governing principle: **build for one company now, keep future productization possible,
but do not implement multi-tenancy prematurely.**

Service types PRO-TECH may offer — to be confirmed by research, not assumed:

- Car detailing
- Ceramic coating
- Paint Protection Film (PPF)
- Tinting
- Car wrapping
- Other closely related automotive appearance/service businesses

*Which of these are in the launch scope and which follow later is not decided —
see [OQ-003](open-questions.md).*

## 2. What makes it more than a booking system — `CONFIRMED`

The product manages the **customer and vehicle lifecycle end to end**:

```
Customer → Vehicle → Quotation → Booking / Walk-in → Check-in → Vehicle Inspection
  → Job → Job Progress → Quality Control → Payment → Digital Warranty
  → Maintenance → Follow-up → Repeat Business
```

This lifecycle is `CONFIRMED` as the product's intended spine. The **detail of each stage**
— what it records, who performs it, what it is called, whether it is mandatory — is
`PROPOSED` and lives in [workflows](../workflows/README.md).

## 3. Vision statement — `PROPOSED`

> ⚠️ **Written for the superseded multi-tenant SaaS direction.** The wording below pitches to
> a market of businesses rather than describing a system for PRO-TECH. It needs reworking and
> has deliberately **not** been rewritten here, because a replacement needs product owner
> input rather than a mechanical edit.

> For automotive detailing and appearance businesses that today run on notebooks, WhatsApp
> threads and spreadsheets, the Platform is an operating system for the workshop: one place
> where every vehicle carries its full history, every job carries its evidence, and every
> completed job creates the next one.

*This wording is a draft for the product owner to accept, amend or reject. It is not a
requirement.*

## 4. Product goals

Product goals are the root of the [traceability chain](../meta/traceability.md). Every epic
should serve at least one.

| ID | Goal | Status | Source |
| --- | --- | --- | --- |
| `PG-001` | Manage the complete customer and vehicle lifecycle in one system, rather than bookings alone. | `CONFIRMED` | Stated by product owner |
| `PG-002` | Support PRO-TECH's multi-branch operation — HQ and multiple branches working in one system. | `CONFIRMED` | Restated by product owner, 2026-09-19 (V1 direction change) |
| `PG-003` | Allow authorized branches within one organization to access relevant customer, vehicle, service and warranty history. | `CONFIRMED` (goal) / `OPEN QUESTION` (rules) | Stated by product owner; rules undefined — [OQ-015](open-questions.md) |
| `PG-004` | Give every vehicle a durable digital profile (Vehicle Passport) that outlives any single job or staff member. | `PROPOSED` | Derived from stated product concept |
| `PG-005` | Turn completed work into repeat business through maintenance reminders and structured follow-up. | `PROPOSED` | Derived from stated lifecycle and CRM direction |
| `PG-006` | Make work defensible — inspection evidence and digital warranties that reduce disputes over pre-existing damage and warranty claims. | `PROPOSED` (unvalidated hypothesis) | Inferred — needs validation, [OQ-005](open-questions.md) |

> `PG-006` is an **inference**, not something the product owner has stated. It is recorded so
> it can be confirmed or struck, not so it can be assumed.

## 5. Target market — `PROPOSED`

> ⚠️ **Affected by the V1 direction change.** If V1 serves one named company, "target market"
> applies to future productization rather than to V1. Whether PRO-TECH is the market or the
> first customer is an open product owner decision — see the impact analysis. Left unchanged
> pending that decision.

- **Geography:** Malaysian SME market is expected to matter, particularly for WhatsApp-based
  customer communication. Whether Malaysia is the only launch market is not decided —
  [OQ-002](open-questions.md).
- **Business size:** SME operators, single-branch through small multi-branch chains.
  Upper bound not defined.
- **Buyer vs user:** not yet distinguished — [OQ-004](open-questions.md).

## 6. Why now / why this wins — `TODO`

No competitive analysis, customer interviews or market sizing have been done. This section
must not be filled with plausible-sounding reasoning.

**Needed:** interviews with detailing operators; review of what they use today (paper,
WhatsApp, generic booking tools, workshop management systems); what they would pay for.

Tracked as a research spike in the [product backlog](../agile/product-backlog.md).

## 7. Success measures — `OPEN QUESTION`

No success metrics have been defined. Without them, scope decisions have no tiebreaker.

**Needed:** what a successful v1 looks like in numbers — see [OQ-005](open-questions.md).

## 8. What this product is explicitly *not* — `TODO`

Non-goals are as valuable as goals and none have been agreed yet. Candidates are listed as
open questions rather than asserted as exclusions in [scope.md](scope.md#4-scope-boundaries-not-yet-decided).

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created during Phase 0 initialization. Direction restated from product owner; goals `PG-001`–`PG-006` drafted. | Drafted by Claude Code |
| 2026-09-19 | **V1 direction change.** §1 rewritten: V1 is a single-company multi-branch system for PRO-TECH, not a multi-tenant SaaS. `PG-002` restated accordingly. §3 and §5 flagged as written for the superseded direction — not rewritten, because replacements need product owner input. | Product owner decision |
