---
title: Definition of Ready
type: process
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [OQ-029, OQ-030, OQ-032]
---

# Definition of Ready (DoR)

The bar a backlog item must clear **before** it may be pulled into a sprint. Its purpose is
to stop work starting on something that will stall halfway through because a decision was
never made.

> `PROPOSED` — drafted for the team to ratify. Ratification is blocked by
> [OQ-029](../product/open-questions.md) (who the team is).

## A user story is READY when

**Substance**

- [ ] It states a user, an action and a value: *As a … I want … so that …*
- [ ] It is understood the same way by the product owner, a developer and QA
- [ ] It is small enough to be completed inside one sprint *(sprint length is [OQ-030](../product/open-questions.md))*
- [ ] It delivers value on its own, or its dependency is explicitly named

**Acceptance**

- [ ] It has acceptance criteria (`AC-##`) that are specific and testable
- [ ] Each criterion can be judged true or false without argument
- [ ] Negative and error paths are covered, not just the happy path
- [ ] QA has read them and believes they can be tested

**Traceability**

- [ ] It names its parent feature, and through it an epic and a product goal
- [ ] Business rules it depends on exist as `BR-###` — **not** described inline as new rules
- [ ] Non-functional requirements that apply are referenced (`NFR-###`)

**Decisions**

- [ ] **No open question blocks it.** If an `OQ-###` must be answered for the story to be
      built correctly, the story is `BLOCKED`, not `READY`
- [ ] Every rule it relies on is `CONFIRMED` — a story built on a `PROPOSED` requirement is
      not ready, it is a gamble
- [ ] Authorization is specified: which roles may perform this, and within which branch scope
- [ ] Tenant scoping is explicit where the story touches shared or cross-branch data

**Practicalities**

- [ ] UI work has whatever design input the team agreed it needs
- [ ] External dependencies (integrations, third parties) are identified and available
- [ ] It is estimated, if the team estimates *([OQ-032](../product/open-questions.md))*

## A spike is READY when

- [ ] The question it answers is written down, and is an `OQ-###` where one exists
- [ ] It is time-boxed
- [ ] The output is defined — a decision, an ADR, a recommendation, a document
- [ ] It is clear who receives the output and decides on it

## Not-ready is a normal state

Most of the backlog is not ready most of the time. That is the point. Forcing an item
through the DoR by answering its open questions inside the sprint is how invented
requirements enter a product.

**Today: no item in this backlog is `READY`.**

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Drafted during Phase 0 initialization. Awaiting team ratification. | Drafted by Claude Code |
