---
title: Roadmap
type: index
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [OQ-005, OQ-037]
---

# Roadmap

> **No dates.** No delivery timeline has been set or agreed —
> [OQ-037](../product/open-questions.md). The phases below describe sequence and exit
> criteria, not a schedule.

## Phase 0 — Product Discovery & Documentation ← **current**

**Goal:** know what we are building, and know what we do not yet know.

| Objective | State |
| --- | --- |
| Establish product vision | Drafted — [vision.md](../product/vision.md), `UNDER DISCUSSION` |
| Establish terminology | Drafted — [glossary.md](../product/glossary.md), `PROPOSED` |
| Establish documentation standards | Done — [docs/meta](../meta/README.md), `CONFIRMED` |
| Identify actors / personas | Placeholder — needs `SPIKE-001` |
| Identify major workflows | Reserved, none written — [workflows](../workflows/README.md) |
| Identify epics | Done — 15 placeholders, all `PROPOSED` |
| Build initial product backlog | Done — [product-backlog.md](../agile/product-backlog.md), unprioritized |
| Identify open questions | Done — 41 recorded, all open |
| Refine features and user stories | Not started — blocked on the high-impact questions |
| Define architecture | Not started — deliberately |

**Exit criteria:** the eight highest-impact open questions answered; the core lifecycle
documented as `WF-001`; a conceptual data model; a v1 scope boundary; at least one epic
refined to `READY` stories; the first technology ADRs accepted.

## Phase 1 — Foundation

Begins only when Phase 0's exit criteria are met. Creates the implementation repository and
builds the tenancy, authentication and authorization foundation that every other epic
depends on. Scope not defined.

## Phase 2 — Core lifecycle

The operational spine — customer, vehicle, booking/walk-in, job, inspection, payment. Which
parts reach v1 is undecided ([scope §5](../product/scope.md)).

## Phase 3 — Differentiators

Vehicle Passport, Digital Warranty, Maintenance, CRM follow-up. Sequenced after the spine
because each depends on it.

## Phase 4 and beyond

Everything currently unscoped or deferred, including the boundaries in
[scope §4](../product/scope.md).

---

**Phases 1–4 are `PROPOSED` sequencing only.** They are not commitments, they carry no
dates, and their contents will change as open questions are answered.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created during Phase 0 initialization. Phase 0 objectives tracked against actual state; later phases sketched without dates. | Drafted by Claude Code |
