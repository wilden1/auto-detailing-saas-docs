---
title: Sprint Process
type: process
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [OQ-029, OQ-030, OQ-031, OQ-032]
---

# Sprint Process

How Agile works on this project.

> **Sprint length is deliberately undecided** — [OQ-030](../product/open-questions.md).
> Nothing here assumes one. Team roles are also undecided —
> [OQ-029](../product/open-questions.md).

## The cycle

```
Product Vision
  → Epics → Features → User Stories → Acceptance Criteria
      → Product Backlog
          → Sprint Planning
              → Implementation
                  → Testing
                      → Sprint Review
                          → Retrospective
                              → Backlog Refinement ──┐
                                   ▲                 │
                                   └─────────────────┘
```

Requirements evolve. Changes are traceable through document status, change logs and git
history — not through a frozen specification.

## Roles — `OPEN QUESTION`

| Role | Responsibility | Who |
| --- | --- | --- |
| Product Owner | Owns the backlog and its order; the only person who may set `CONFIRMED` | TBD |
| Delivery team | Developers and QA who build and verify | TBD |
| Facilitator / Scrum Master | Runs the cadence, removes blockers | TBD — may not be a separate person |

## Events

| Event | Purpose | Output | Notes |
| --- | --- | --- | --- |
| **Sprint Planning** | Choose what to build from `READY` items | Sprint goal + sprint backlog | Only `READY` items ([DoR](definition-of-ready.md)) may be selected |
| **Daily sync** | Surface blockers early | Adjusted plan | Format and necessity TBD by the team |
| **Implementation** | Build it | Working, reviewed software | Governed by [DoD](definition-of-done.md) section B |
| **Testing** | Verify against acceptance criteria | Test results linked to `AC` | Testing is inside the sprint, not after it |
| **Sprint Review** | Show what was built to the product owner | Accepted / not accepted; backlog feedback | Demonstrate, don't describe |
| **Retrospective** | Improve how we work | Concrete actions with owners | At most 2–3 actions; they go into the next sprint |
| **Backlog Refinement** | Prepare future items | Items moved toward `READY`; new `OQ`s raised | Standing activity, not a single meeting |

## Sprint records

Each sprint gets a file: `docs/agile/sprints/SPRINT-##.md`, from
[`templates/sprint-template.md`](../../templates/sprint-template.md). It records the goal,
the committed items, what actually happened, and the retrospective actions — so that
"why did we change direction in sprint 4?" is answerable a year later.

## How Phase 0 differs

Phase 0 is not run as sprints. It is run as a sequence of documentation activities from
[`product-backlog.md` §7](product-backlog.md#7-phase-0-documentation-backlog), each reviewed
and approved by the product owner before the next begins. Sprints start when:

1. The documentation framework is approved *(in progress)*
2. The highest-impact open questions are answered
3. At least one epic is refined into `READY` stories
4. A technology stack exists, recorded as ADRs
5. The implementation repository exists

## Estimation — `OPEN QUESTION`

No estimation approach has been chosen ([OQ-032](../product/open-questions.md)). Decide at
the first sprint planning; do not retro-fit estimates to the backlog now.

## Changing a requirement mid-flight

1. Do not edit the story quietly. Comment on the change and its cause.
2. If it invalidates work already accepted, mark the affected requirement `DEPRECATED` and
   write the replacement with a new ID.
3. Record the reason in the document's change log — the reason is the part git cannot store.
4. If it was an architectural assumption, write or supersede an ADR.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Drafted during Phase 0 initialization. Cadence and roles left open. | Drafted by Claude Code |
