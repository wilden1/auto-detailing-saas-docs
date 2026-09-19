---
id: ADR-001
title: Documentation-first Phase 0, with ADRs for significant decisions
type: adr
status: Accepted
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# ADR-001 — Documentation-first Phase 0, with ADRs for significant decisions

**Status:** Accepted · **Date:** 2026-09-19 · **Decided by:** Product owner

## Context

A multi-tenant SaaS platform for automotive detailing and related businesses is being
started. The product spans the full customer and vehicle lifecycle across roughly fifteen
areas, is multi-tenant and multi-branch, and carries commercial promises (warranties) whose
rules are not yet known.

The work will be delivered by a mix of people and AI coding agents — Claude Code, OpenAI
Codex and others. Agents produce plausible output cheaply. Without a written source of
truth, an agent's invented business rule is indistinguishable from an agreed one, and the
invention becomes a requirement by the time anyone notices.

Several parts of the domain are genuinely undecided (what a Job is, who owns a Customer,
what voids a warranty). Deciding them implicitly, in code, would be the most expensive
possible way to decide them.

## Decision

1. The project runs a **Phase 0 — Product Discovery & Documentation** before any application
   code is written. Application code lives in a **separate repository**, created only when
   the documentation is sufficiently mature.
2. **This documentation repository is the single source of truth.** Anything not written
   here is not a requirement.
3. **Requirements carry an explicit status** (`CONFIRMED` / `PROPOSED` / `UNDER DISCUSSION` /
   `OPEN QUESTION` / `DEFERRED` / `DEPRECATED`). Assumptions are never recorded as
   confirmed requirements; missing information becomes an `OQ-###`.
4. **Agile, not waterfall.** Requirements may evolve. Changes are traceable through document
   status, per-document change logs and git history — not through a frozen specification.
5. **Significant decisions are recorded as ADRs** in this folder, and may not be taken
   silently.
6. **Operating rules for AI agents are binding** and live in `AGENTS.md`, with Claude
   Code-specific guidance in `CLAUDE.md`.

## Options considered

| Option | Why not |
| --- | --- |
| Start coding immediately, document later | The undecided domain rules would be decided by whoever wrote the first implementation, invisibly. Multi-tenancy and warranty logic are the two worst candidates for that. |
| Full waterfall specification signed off before any build | Explicitly rejected by the product owner. The requirements are not knowable in advance; a frozen spec would be wrong and would pretend otherwise. |
| Lightweight notes in a wiki, no status discipline | Does not survive AI agents. Without status, a draft and a decision look identical, and both get built. |
| Documentation inside the implementation repository | Chosen against for Phase 0 because it invites code before requirements. The two repositories will cross-reference each other. |

## Consequences

**Positive**

- A decision, an assumption and a question are visibly different things.
- AI agents have a citable contract; their output can be checked against it.
- Open questions accumulate visibly instead of being answered by whoever codes first.
- The reasoning behind each decision survives staff and tooling changes.

**Negative**

- Phase 0 produces no working software. Progress is harder to feel.
- Discipline is required: the status field is worthless the first time someone writes
  `CONFIRMED` for something that was merely plausible.
- Two repositories must be kept in step once implementation begins.
- Documentation that lags implementation is worse than no documentation, so rule 10
  (update docs in the same change) must be enforced in review, not merely stated.

**Neutral**

- Templates and ID conventions add a small fixed cost per document.

## Compliance

- `AGENTS.md`, `CLAUDE.md` — the binding agent rules
- [docs/meta/identifiers-and-status.md](../../meta/identifiers-and-status.md) — status taxonomy
- [docs/meta/documentation-standards.md](../../meta/documentation-standards.md) — how documents are written
- [docs/agile/definition-of-done.md](../../agile/definition-of-done.md) — enforces rule 10

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Accepted at Phase 0 initialization. | Product owner |
