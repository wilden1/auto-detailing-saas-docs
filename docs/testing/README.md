---
title: Testing
type: index
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Testing

No test strategy yet — a strategy depends on the stack, which is undecided. What *can* be
established now is how tests relate to requirements, and that does not depend on technology.

## Principles — `PROPOSED`

1. **Acceptance criteria are the specification for tests.** Every `AC-##` has at least one
   test case referencing it. An untested criterion is an unmet one.
2. **QA is involved before the sprint, not after.** The
   [Definition of Ready](../agile/definition-of-ready.md) requires QA to believe the criteria
   are testable.
3. **Tenant isolation is tested explicitly**, not assumed. For every feature touching tenant
   data there is a test proving a user of one organization cannot reach another's —
   [NFR-001](../product/non-functional-requirements.md).
4. **Authorization is tested negatively.** Proving the permitted role can act is half a test;
   the other half proves the forbidden role cannot.
5. **Testing happens inside the sprint.** Work is not `DONE` until it is verified —
   [Definition of Done](../agile/definition-of-done.md).

## Traceability

```
US-### ── AC-## ──▶ TC-### ──▶ result
```

Test cases live here as `TC-###`, with front matter `related: [US-###/AC-##]`. See
[traceability](../meta/traceability.md).

| ID | Test case | Covers | Status |
| --- | --- | --- | --- |
| — | None yet | — | — |

No test cases exist, because no user stories exist.

## To be decided

| Decision | Depends on |
| --- | --- |
| Test levels and the balance between them | Architecture |
| Tooling and frameworks | Stack ADR |
| Environments and test data — **no real customer data** | Architecture, [OQ-018](../product/open-questions.md) |
| Automation in CI, and what gates a merge | Stack ADR |
| Non-functional testing (load, photo upload on mobile data, offline) | [NFRs](../product/non-functional-requirements.md), [OQ-038](../product/open-questions.md), [OQ-039](../product/open-questions.md) |
| Manual/exploratory testing and UAT with a real workshop | `SPIKE-001` |

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created during Phase 0 initialization. Requirement-to-test traceability established; strategy deferred to Phase 1. | Drafted by Claude Code |
