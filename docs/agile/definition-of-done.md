---
title: Definition of Done
type: process
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [NFR-001, NFR-002]
---

# Definition of Done (DoD)

What "finished" means. One shared bar, applied to every item, every time. "Done except for
tests" is not done.

> `PROPOSED` — drafted for the team to ratify. Section A is usable **today**; section B
> takes effect when implementation begins and will need revising once the technology stack
> and CI approach exist.

---

## A. Definition of Done — documentation work (applies now, Phase 0)

A documentation item is `DONE` when:

- [ ] It uses the correct template and carries complete front matter
- [ ] It has an ID where the [conventions](../meta/identifiers-and-status.md) require one
- [ ] Its `status` is set honestly — `PROPOSED` unless the product owner actually confirmed it
- [ ] **No assumption is stated as fact.** Anything unknown is a `TODO` or an `OQ-###`
- [ ] New open questions uncovered while writing it were added to the register
- [ ] It links to its parent, and the parent/index links back to it
- [ ] Terms match the [glossary](../product/glossary.md); new terms were added there
- [ ] It does not contradict another document — or the contradiction is reported, not absorbed
- [ ] Its change log has a row for this change
- [ ] It has been reviewed by at least one other person *([OQ-029](../product/open-questions.md))*

## B. Definition of Done — implementation work (applies from Phase 1)

> This section is a **starting draft**. It must be revisited once the stack, CI and review
> process exist. Do not treat unresolved items as optional; treat them as unfinished.

**Function**

- [ ] Every acceptance criterion of the story is satisfied and demonstrated
- [ ] Business rules (`BR-###`) referenced by the story are implemented as written
- [ ] Error and edge paths behave as the criteria specify

**Security and tenancy** *(non-negotiable — [NFR-001](../product/non-functional-requirements.md), [NFR-002](../product/non-functional-requirements.md))*

- [ ] Authorization is enforced for every new operation, server-side
- [ ] Tenant isolation is verified: it is proven that a user of one organization cannot reach
      another organization's data through this change
- [ ] Branch scoping behaves as the story specifies
- [ ] No authorization was loosened, stubbed or bypassed anywhere, including in tests and
      local development configuration
- [ ] Nothing new is logged or exposed that should not be — customer data, vehicle data, images

**Quality**

- [ ] Automated tests cover each acceptance criterion, referencing it (`US-###/AC-##`)
- [ ] Tests pass in CI
- [ ] Code reviewed and approved by someone other than the author
- [ ] No known defect introduced by this work is left unrecorded

**Documentation**

- [ ] If implementation changed an approved design, the documentation was updated in the
      **same** change *([AGENTS.md rule 10](../../AGENTS.md))*
- [ ] Significant decisions taken during implementation are recorded as ADRs
- [ ] The story is linked to what was built (PR references the ID)

**Acceptance**

- [ ] The product owner has accepted it
- [ ] It is deployable — not necessarily deployed

## What "Done" never means

- Done on the developer's machine
- Done pending a follow-up ticket for authorization
- Done with tenant isolation "to be checked later"
- Done with the documentation "to be updated in a batch"

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Drafted during Phase 0 initialization; split into documentation (active) and implementation (future) definitions. | Drafted by Claude Code |
