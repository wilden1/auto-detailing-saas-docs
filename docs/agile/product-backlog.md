---
title: Product Backlog
type: process
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [OQ-031, OQ-032]
---

# Product Backlog

> **Nothing in this backlog is ordered yet.** Priority requires success measures
> ([OQ-005](../product/open-questions.md)) and a release boundary, neither of which exists.
> The sequence below is the epic ID order, **not** a priority order. Do not read it as one.
>
> **Where the backlog lives** is undecided — this file, or Jira/GitHub Issues with this
> repository as the specification. See [OQ-031](../product/open-questions.md).

## 1. What the backlog contains

| Item type | ID | Description |
| --- | --- | --- |
| Epic | `EPIC-###` | A large body of work spanning multiple sprints |
| Feature | `FEAT-###` | A coherent capability inside an epic |
| User story | `US-###` | A small, valuable, independently deliverable change |
| Technical work | `US-###` (tagged `tech`) | Enabling work with no direct user-visible change |
| Spike | `SPIKE-###` | Time-boxed research to answer a question or reduce risk |
| Defect | `BUG-###` | Raised once development begins |
| Documentation | `DOC-###` | Phase 0 work items (this phase's output) |

Only **user stories, spikes, technical items and defects** are ever pulled into a sprint.
Epics and features are containers.

## 2. Backlog states

```
IDEA → REFINING → READY → IN SPRINT → DONE
             ↘ BLOCKED (by an OQ or dependency)
             ↘ DEFERRED / DEPRECATED
```

`READY` means it satisfies the [Definition of Ready](definition-of-ready.md). Today, **no
item is `READY`**, because no epic has been refined into stories.

## 3. Epic backlog

All epics are `PROPOSED`. Priority is deliberately blank.

| ID | Epic | Serves | Module | Refined? | Priority | Blocked by |
| --- | --- | --- | --- | --- | --- | --- |
| [`EPIC-001`](../epics/EPIC-001-platform-and-organization-management.md) | Platform & Organization Management | `PG-002` | `MOD-001` | No | TBD | `OQ-035` |
| [`EPIC-002`](../epics/EPIC-002-branch-management.md) | Branch Management | `PG-002`, `PG-003` | `MOD-002` | No | TBD | `OQ-012`, `OQ-015` |
| [`EPIC-003`](../epics/EPIC-003-staff-and-access-control.md) | Staff & Access Control | `PG-002` | `MOD-015` | No | TBD | `OQ-016`, `OQ-019` |
| [`EPIC-004`](../epics/EPIC-004-customer-management.md) | Customer Management | `PG-001` | `MOD-003` | No | TBD | `OQ-012` |
| [`EPIC-005`](../epics/EPIC-005-vehicle-management-and-passport.md) | Vehicle Management / Vehicle Passport | `PG-004` | `MOD-004` | No | TBD | `OQ-013`, `OQ-017`, `OQ-025` |
| [`EPIC-006`](../epics/EPIC-006-services-and-packages.md) | Services & Packages | `PG-001` | `MOD-005` | No | TBD | — |
| [`EPIC-007`](../epics/EPIC-007-quotations.md) | Quotations | `PG-001` | `MOD-006` | No | TBD | `OQ-021` |
| [`EPIC-008`](../epics/EPIC-008-booking-and-walk-ins.md) | Booking & Walk-ins | `PG-001` | `MOD-007` | No | TBD | `OQ-010`, `OQ-020`, `OQ-022` |
| [`EPIC-009`](../epics/EPIC-009-job-management.md) | Job Management | `PG-001` | `MOD-008` | No | TBD | `OQ-023`, `OQ-028` |
| [`EPIC-010`](../epics/EPIC-010-vehicle-inspection.md) | Vehicle Inspection | `PG-006` | `MOD-009` | No | TBD | `OQ-036`, `OQ-038`, `OQ-039` |
| [`EPIC-011`](../epics/EPIC-011-payments.md) | Payments | `PG-001` | `MOD-010` | No | TBD | `OQ-007`, `OQ-024`, `OQ-034` |
| [`EPIC-012`](../epics/EPIC-012-digital-warranty.md) | Digital Warranty | `PG-006` | `MOD-011` | No | TBD | `OQ-025`, `OQ-026`, `OQ-027` |
| [`EPIC-013`](../epics/EPIC-013-maintenance.md) | Maintenance | `PG-005` | `MOD-012` | No | TBD | `OQ-026` |
| [`EPIC-014`](../epics/EPIC-014-crm-and-follow-up.md) | CRM & Customer Follow-up | `PG-005` | `MOD-013` | No | TBD | `OQ-033` |
| [`EPIC-015`](../epics/EPIC-015-dashboard-and-reporting.md) | Dashboard & Reporting | `PG-001` | `MOD-014` | No | TBD | `OQ-005` |

**Cross-cutting, not yet an epic:** authentication, multi-tenancy enforcement, audit
logging, file/image management, search, PDF generation, company configuration. These are
listed in [scope.md §3](../product/scope.md). Whether each becomes its own epic or is
absorbed into the epics above is an open decision — raise an ADR when it is made.

## 4. Feature backlog

Empty. Features are created when an epic is refined.
Index: [docs/features/README.md](../features/README.md)

## 5. Story backlog

Empty. **No user story exists yet, and none should be written until its epic has been
refined and its blocking open questions answered.** Writing stories now would mean inventing
the rules they assert.
Index: [docs/user-stories/README.md](../user-stories/README.md)

## 6. Research spikes

These are the items that can genuinely be worked on **now**, because they produce answers
rather than assume them.

| ID | Spike | Answers | Priority |
| --- | --- | --- | --- |
| `SPIKE-001` | Interview 3–5 detailing/coating/PPF operators: how they work today, what they'd pay for, what they'd never adopt | `OQ-003`, `OQ-004`, `OQ-005`, personas, `PG-006` | High |
| `SPIKE-002` | Observe one complete job end to end, check-in to handover, recording every artifact produced | [Workflows](../workflows/README.md), `OQ-028`, `OQ-036` | High |
| `SPIKE-003` | WhatsApp delivery options: Cloud API vs provider vs `wa.me` links — cost, approval, template rules, compliance | `OQ-033` | High |
| `SPIKE-004` | Malaysian e-Invoice / LHDN obligations for SME service businesses — do we inherit any? | `OQ-007`, `OQ-002` | High |
| `SPIKE-005` | Vehicle identity in Malaysia: plate transferability, VIN availability in practice, duplicate risk | `OQ-017` | High |
| `SPIKE-006` | Warranty practice in the trade: typical terms, transferability, voiding, how disputes actually occur | `OQ-025`, `OQ-026` | Medium |
| `SPIKE-007` | Workshop-floor connectivity and device reality — what staff actually hold while inspecting | `OQ-038`, `OQ-039` | Medium |
| `SPIKE-008` | Competitor / adjacent-tool review (workshop management, booking tools, generic CRM) | [vision.md §6](../product/vision.md) | Medium |

*Spikes are `PROPOSED`. Time-boxing and assignment await [OQ-029](../product/open-questions.md).*

## 7. Phase 0 documentation backlog

Work items for the current phase.

| ID | Item | Status |
| --- | --- | --- |
| `DOC-001` | Initialize documentation repository, standards, templates, epic index | **Done — 2026-09-19** |
| `DOC-002` | Answer the eight highest-impact open questions with the product owner | Not started |
| `DOC-003` | Document the core lifecycle as `WF-001` end to end | Not started |
| `DOC-004` | Confirm or strike the candidate actor list; write real personas from `SPIKE-001` | Not started |
| `DOC-005` | Define the conceptual data model and entity ownership boundaries | Blocked by `OQ-012`, `OQ-013`, `OQ-015`, `OQ-028` |
| `DOC-006` | Refine the first epic into features and stories | Blocked by `DOC-002` |
| `DOC-007` | Draw the v1 / MVP release boundary | Blocked by `OQ-005`, `DOC-002` |
| `DOC-008` | Begin architecture documentation and first technology ADRs | Blocked by `DOC-005`, `DOC-007` |

## 8. Refinement

Backlog refinement is a standing activity, not a one-off. See
[sprint-process.md](sprint-process.md). Its purpose here is to move items
`IDEA → REFINING → READY`, and — just as importantly — to keep converting assumptions back
into open questions when they are spotted.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Backlog created during Phase 0 initialization with 15 epics, 8 spikes, 8 documentation items. No prioritization applied. | Drafted by Claude Code |
