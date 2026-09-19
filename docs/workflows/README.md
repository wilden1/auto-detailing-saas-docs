---
title: Workflow Index
type: index
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-001]
---

# Workflows

End-to-end processes crossing several actors or modules. These are where the product is
actually understood — more than any module list.

## The core lifecycle — `CONFIRMED` as direction, `PROPOSED` in detail

```
Customer
  → Vehicle
    → Quotation
      → Booking / Walk-in
        → Check-in
          → Vehicle Inspection
            → Job
              → Job Progress
                → Quality Control
                  → Payment
                    → Digital Warranty
                      → Maintenance
                        → Follow-up
                          → Repeat Business
```

The product owner has confirmed this chain as the product's spine. **What happens at each
step — who does it, what it records, whether it is mandatory, what may be skipped — is not
documented.** That is the gap this folder exists to close.

## Workflows to be documented

| ID | Workflow | Covers | Status |
| --- | --- | --- | --- |
| `WF-001` | Core service lifecycle, end to end | The whole chain above | Not written |
| `WF-002` | Quotation to accepted work | Quote → follow-up → acceptance → booking or job | Not written |
| `WF-003` | Walk-in arrival | Unscheduled arrival → check-in | Not written |
| `WF-004` | Check-in and pre-service inspection | Receiving the vehicle, recording condition | Not written |
| `WF-005` | Job execution and progress | Assignment, stages, progress visibility | Not written |
| `WF-006` | Quality control and handover | QC outcome, rework, returning the vehicle | Not written |
| `WF-007` | Payment and documentation | Deposits, settlement, what the customer receives | Not written |
| `WF-008` | Warranty issue and verification | Generation, delivery, QR verification | Not written |
| `WF-009` | Maintenance due and reminder | Detecting due/overdue, contacting the customer | Not written |
| `WF-010` | Customer follow-up and reactivation | Inactive customers, unconverted quotations | Not written |
| `WF-011` | Cross-branch history access | What one branch sees of another's records | Not written — blocked by [OQ-015](../product/open-questions.md) |

*IDs are reserved; the list may change. `WF-001` and `WF-004` are the highest value, because
they expose the ambiguities in [OQ-028](../product/open-questions.md) (what a Job is) and
[OQ-036](../product/open-questions.md) (whether inspection is mandatory).*

## How to document one

Use [`templates/workflow-template.md`](../../templates/workflow-template.md). A workflow
document must state, for every step: the actor, the trigger, what is recorded, what may go
wrong, and what happens when it does. **Exception paths are the point** — the happy path is
usually already understood.

The best source is observation, not discussion: `SPIKE-002` in the
[backlog](../agile/product-backlog.md).

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created during Phase 0 initialization. Core lifecycle restated; `WF-001`–`WF-011` reserved, none written. | Drafted by Claude Code |
