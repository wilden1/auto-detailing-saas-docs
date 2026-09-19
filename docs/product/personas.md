---
title: Personas and Actors
type: product-doc
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [OQ-004, OQ-019]
---

# Personas and Actors

> **Placeholder.** No user research has been done. The actors below are **candidates derived
> from the stated product direction**, not validated personas. Each needs confirming, merging
> or striking by the product owner. Goals, frustrations and day-in-the-life narratives are
> deliberately left `TODO` rather than invented — a fabricated persona quietly becomes a
> fabricated requirement.

## 1. Candidate actors — `PROPOSED`

| Actor | Works at level | Why we think they exist | Confirmed? |
| --- | --- | --- | --- |
| Platform Operator | Platform | Someone must administer the SaaS itself, onboard organizations, and support tenants | No |
| Organization Owner | Organization | Stated hierarchy includes Organization; the business owner buys the product | No |
| Branch Manager | Branch | Stated hierarchy includes Branch; someone runs day-to-day operations per branch | No |
| Service Advisor / Front Desk | Branch | Lifecycle includes quotation, booking, check-in and payment — customer-facing steps | No |
| Technician / Detailer | Branch | Lifecycle includes job execution and job progress | No |
| Quality Control Inspector | Branch | Lifecycle names Quality Control as a distinct stage — may be a separate person or the same one — [OQ-023](open-questions.md) | No |
| Cashier / Finance | Branch | Lifecycle includes payment | No |
| End Customer (vehicle owner) | External | Owns the vehicle, receives warranty and follow-up; whether they log in is [OQ-009](open-questions.md) | No |

**These are roles, not necessarily people.** In a small single-branch shop one person may be
owner, advisor, technician and cashier. The role model must support that —
see [OQ-019](open-questions.md).

## 2. Non-product stakeholders

Consumers of *this repository*, confirmed by the product owner:

- Product owner
- Developers
- QA engineers
- Claude Code, OpenAI Codex and other AI coding agents

## 3. What each persona needs — `TODO`

For each confirmed actor, the following must be filled in from research, not assumption:

- Primary goal when using the Platform
- Context of use (desk, workshop floor, phone in hand, oily gloves, poor signal)
- Frequency and session length
- What they currently use instead
- What would make them abandon the Platform
- Permissions they must and must not have

## 4. Research needed

| # | Activity | Blocks |
| --- | --- | --- |
| 1 | Interview 3–5 detailing operators (single-branch and multi-branch) | Persona validation, `PG-006`, [OQ-005](open-questions.md) |
| 2 | Observe one full job from check-in to handover | [Workflows](../workflows/README.md), inspection scope |
| 3 | Confirm the role list and what each role may see and do | [OQ-019](open-questions.md), `EPIC-003` |

Tracked as spikes in the [product backlog](../agile/product-backlog.md).

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as placeholder during Phase 0 initialization. Candidate actors derived from stated hierarchy and lifecycle; no personas fabricated. | Drafted by Claude Code |
