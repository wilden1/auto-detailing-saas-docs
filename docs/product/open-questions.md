---
title: Open Questions Register
type: product-doc
status: ACTIVE
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Open Questions Register

The single place where **known unknowns** live. The register itself is `CONFIRMED` as a
process artifact; every question in it is by definition unanswered.

**Rule:** when information is missing, a question is added here. It is never replaced by a
plausible assumption. See [AGENTS.md rule 3](../../AGENTS.md).

**Impact scale:** `HIGH` = blocks data model, security model or release scope ·
`MEDIUM` = blocks an epic or feature · `LOW` = can be answered during refinement.

---

## The eight that block the most

If only a handful get answered, these are the ones.

**Each question is worded once, in its section below.** This table is ordering and urgency
only — deliberately not a second copy of the question text, which would drift.

| # | ID | Area | Why this one first |
| --- | --- | --- | --- |
| 1 | `OQ-028` | Domain semantics | Everything downstream — inspection, QC, payment, warranty, reporting, pricing — attaches to whatever a Job turns out to be |
| 2 | `OQ-012` | Tenancy | Determines duplicate handling, cross-branch visibility, and every authorization check |
| 3 | `OQ-015` | Tenancy | `PG-003` is a stated goal with no rules; both readings are defensible and produce different systems |
| 4 | `OQ-019` | Domain semantics | `EPIC-003` cannot start, and every other epic's authorization criteria depend on it |
| 5 | `OQ-017` | Tenancy | Malaysian plates are transferable; getting this wrong corrupts vehicle history permanently |
| 6 | `OQ-026` | Domain semantics | Core commercial logic of `EPIC-012`, with legal weight. Read alongside `OQ-027` |
| 7 | `OQ-033` | Integration | Cost, approval and compliance differ enormously; shapes `EPIC-014` and the architecture |
| 8 | `OQ-009` | Scope | Roughly doubles or halves the product |

`OQ-005` (success measures) sits outside this ranking because it is not a domain question —
but without it, no scope decision has a tiebreaker.

---

## 1. Product identity and market

| ID | Question | Impact | Why it matters | Status |
| --- | --- | --- | --- | --- |
| `OQ-001` | What is the product's name? | LOW | Repository, documents and UI all carry a placeholder ("the Platform") until decided. Cheap to change now, expensive later. | OPEN |
| `OQ-002` | Which markets are we launching in — Malaysia only, or wider? | HIGH | Drives language, tax/e-Invoice obligations, payment methods, data residency, messaging channels. | OPEN |
| `OQ-003` | Which business types are in the launch scope (detailing, coating, PPF, tint, wrap) and which come later? | HIGH | Each type has different job durations, warranty behaviour and inspection needs. Building for all five at once is a different product. | OPEN |
| `OQ-004` | Who buys, and who uses it daily? Are they the same person? | MEDIUM | Determines what the product must prove (owner: money and control; staff: speed). | OPEN |
| `OQ-005` | What measurable outcomes define a successful v1? | HIGH | Without this there is no basis for cutting scope. | OPEN |

## 2. Scope boundaries

| ID | Question | Impact | Why it matters | Status |
| --- | --- | --- | --- | --- |
| `OQ-006` | Is consumable/inventory stock tracking in scope? | MEDIUM | Coating and film are expensive consumables; operators may expect usage tracking. Large addition if yes. | OPEN |
| `OQ-007` | Is invoicing and tax compliance in scope — specifically Malaysian e-Invoice obligations? | HIGH | A statutory integration is a major workstream, not a feature. Answer depends on `OQ-002`. | OPEN |
| `OQ-008` | Is staff commission or payroll calculation in scope? | MEDIUM | Commission is common in this trade and affects job/staff data modelling if included. | OPEN |
| `OQ-009` | Is there a customer-facing portal or app, or is the Platform staff-only? | HIGH | Affects authentication, warranty verification, job-progress visibility, follow-up design. | OPEN |
| `OQ-010` | Can customers self-book online without staff involvement? | MEDIUM | Adds availability/capacity modelling and public-facing surfaces. | OPEN |
| `OQ-011` | Which languages must the interface support (English, Bahasa Malaysia, Chinese)? | MEDIUM | Retrofitting localization is costly; deciding now is nearly free. | OPEN |
| `OQ-035` | How is the SaaS itself sold — subscription tiers, per-branch, per-user, free trial? | MEDIUM | Affects tenant provisioning, limits, and whether billing is an epic. | OPEN |

## 3. Tenancy, ownership and data boundaries

| ID | Question | Impact | Why it matters | Status |
| --- | --- | --- | --- | --- |
| `OQ-012` | Is a Customer owned by the Organization or by a Branch? | HIGH | The single most consequential modelling decision. Determines duplicate handling, cross-branch visibility, and every authorization check. | OPEN |
| `OQ-013` | Is a Vehicle unique platform-wide, or per Organization? | HIGH | A platform-wide vehicle identity enables a true "Vehicle Passport" across businesses but raises serious privacy and competitive questions. | OPEN |
| `OQ-014` | Is cross-**organization** data sharing ever permitted, under any circumstance? | HIGH | Current working assumption is **no**. That must be confirmed, because `OQ-013` pulls in the opposite direction. | OPEN |
| `OQ-015` | What makes a branch "authorized" to access another branch's customer, vehicle, service and warranty history — open by default within the organization, or explicitly granted? | HIGH | `PG-003` is stated as a goal but has no rules. Both readings are defensible and they produce different systems. | OPEN |
| `OQ-016` | Can one user belong to multiple branches? To multiple organizations? | HIGH | Affects session model, branch switching, and every scoped query. | OPEN |
| `OQ-017` | What identifies a Vehicle — registration number, VIN, or both? What happens when a plate changes or is transferred? | HIGH | Malaysian plates are transferable between vehicles. Getting this wrong corrupts vehicle history permanently. | OPEN |
| `OQ-018` | What data residency, retention and PDPA obligations apply? | HIGH | Affects hosting, backups, photo retention, deletion rights. Depends on `OQ-002`. | OPEN |
| `OQ-040` | What must be audit-logged, who can read the log, and for how long is it kept? | MEDIUM | Audit logging is listed as a platform concern with no definition. | OPEN |

## 4. Domain semantics

| ID | Question | Impact | Why it matters | Status |
| --- | --- | --- | --- | --- |
| `OQ-019` | What roles exist and what may each see and do? Can one person hold several roles? | HIGH | `EPIC-003` cannot start. In a one-person shop the same user is owner, advisor and technician. | OPEN |
| `OQ-020` | Is scheduling capacity-aware — bays, lifts, technician availability, job duration? | MEDIUM | A calendar of appointments and a capacity-planning system are different products. | OPEN |
| `OQ-021` | What does an accepted Quotation become — a Booking, a Job, both, or nothing automatic? | MEDIUM | Determines conversion tracking, which `EPIC-014` depends on. | OPEN |
| `OQ-022` | Is a Walk-in a Booking created on arrival, or a separate concept? | MEDIUM | Affects reporting ("how many walk-ins?") and the check-in flow. | OPEN |
| `OQ-023` | Is Quality Control a Job status, or a separate record with its own outcome, approver and possible failure/rework loop? | MEDIUM | A QC failure that sends a job backwards is materially more complex than a checkbox. | OPEN |
| `OQ-024` | Are deposits and partial payments supported? Must a Job be fully paid before handover? | MEDIUM | Deposits are common for coating and PPF bookings. | OPEN |
| `OQ-025` | When a Vehicle changes owner, what happens to its history and its warranties? Does warranty transfer? | HIGH | Warranty transferability is a commercial promise with legal weight, not a technical detail. | OPEN |
| `OQ-026` | What warranty statuses exist, who may void a warranty, and does missed maintenance void it automatically? | HIGH | This is the core commercial logic of `EPIC-012`. Must not be invented. | OPEN |
| `OQ-027` | Is QR warranty/vehicle verification public (no login)? What data may a scanner see? | HIGH | A public endpoint exposing customer and vehicle data is a privacy decision, not a convenience feature. | OPEN |
| `OQ-028` | Is a Job one visit to the branch, or one service within a visit? Can one Booking produce multiple Jobs? | HIGH | Cascades into inspection, QC, payment, warranty, reporting and pricing. Nothing downstream can be modelled until this is settled. | OPEN |
| `OQ-036` | Is a Vehicle Inspection mandatory before every Job, or only for certain services? | MEDIUM | Mandatory inspection changes the check-in flow for every job. | OPEN |
| `OQ-034` | Which payment methods must be supported — cash, card terminal, bank transfer, FPX, e-wallet, online gateway? | MEDIUM | Determines whether payment is a record-keeping feature or an integration. | OPEN |

## 5. Experience and environment

| ID | Question | Impact | Why it matters | Status |
| --- | --- | --- | --- | --- |
| `OQ-038` | Must the Platform work with poor or no connectivity on the workshop floor? | HIGH | Offline capability is an architectural decision made at the start or never. Inspections with photos are captured exactly where signal is worst. | OPEN |
| `OQ-041` | Do **staff** need a native mobile app, or is responsive web enough on a phone or tablet? | MEDIUM | Independent of whether *customers* log in (`OQ-009`). Camera access, offline capture and app-store distribution are the deciding factors, and they land on `EPIC-010`. | OPEN |
| `OQ-039` | How many photos per inspection, at what quality, kept for how long? | HIGH | Drives storage cost, upload UX and the whole file-handling design. | OPEN |
| `OQ-033` | How are WhatsApp messages delivered — WhatsApp Cloud API, a third-party provider, or staff-initiated `wa.me` links? | HIGH | Cost, approval process, template rules and compliance differ enormously. The cheapest option may also be the only viable one for SMEs. | OPEN |

## 6. Delivery process

| ID | Question | Impact | Why it matters | Status |
| --- | --- | --- | --- | --- |
| `OQ-029` | Who is the Product Owner, who reviews documentation, and who is on the delivery team? | MEDIUM | The Definition of Ready and the review rule both depend on named roles. | OPEN |
| `OQ-030` | How long is a sprint? | MEDIUM | Deliberately not assumed. Affects story sizing and the Definition of Ready. | OPEN |
| `OQ-031` | Does the backlog live in this repository, or in Jira / GitHub Issues with this repository as the specification? | MEDIUM | Determines whether `product-backlog.md` is the backlog or a mirror of it. | OPEN |
| `OQ-032` | How is work estimated — story points, t-shirt sizes, or not at all? | LOW | Can be decided at the first sprint planning. | OPEN |
| `OQ-037` | Is there a target launch date or external deadline? | MEDIUM | A hard date changes scope strategy fundamentally. | OPEN |

---

## How to use this register

- **Adding:** take the next free `OQ` number, add a row to the right section, and link it
  from every document the question affects. Use
  [`templates/open-question-template.md`](../../templates/open-question-template.md) if the
  question needs more than a row's worth of context.
- **Answering:** replace `OPEN` with `ANSWERED — <date>`, record the answer and who gave it,
  and update the documents that referenced it in the same change. Answered questions stay in
  the register; they are the record of why the product is shaped the way it is.
- **Never** silently delete a question, and never close one with a guess.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Register created during Phase 0 initialization with `OQ-001`–`OQ-040`. | Drafted by Claude Code |
| 2026-09-19 | Review cleanup. Added `OQ-041` — `OQ-009` was being cited for two different questions, customer login and staff device (finding 3). Rewrote the "eight that block the most" table so it no longer restates question text; the two wordings of `OQ-009` had already diverged (finding 4). | Drafted by Claude Code |
