---
title: Releases
type: process
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [OQ-005, OQ-037]
---

# Releases

> **No release has been planned.** A release boundary needs success measures
> ([OQ-005](../product/open-questions.md)) and the scope decisions in
> [scope.md §4](../product/scope.md#4-scope-boundaries-not-yet-decided). This file exists to
> hold that plan when it is made, and to record how documentation versions relate to
> product versions.

## Product releases

| Release | Goal | Scope | Target | Status |
| --- | --- | --- | --- | --- |
| v1 / MVP | TBD | TBD | TBD — [OQ-037](../product/open-questions.md) | Not planned |

Drawing the v1 boundary is tracked as `DOC-007` in the
[backlog](product-backlog.md#7-phase-0-documentation-backlog).

## Documentation versions

The documentation repository is versioned by **git history plus per-document status**, not
by release tags. Two conventions:

1. **A documentation baseline is tagged when a phase is approved** — e.g. `phase-0-approved`
   — so it is always possible to see what was agreed at the point a decision was taken.
2. **When implementation begins, the implementation repository references a documentation
   commit** in its own README, so a build can be traced to the specification it was built
   against.

## Relationship to the implementation repository

| Repository | Contains | Created |
| --- | --- | --- |
| This one | Vision, requirements, rules, decisions, plans | Now |
| Implementation | Application source code | When Phase 0 reaches sufficient maturity — not yet |

The implementation repository will carry its own `CLAUDE.md` / `AGENTS.md` pointing back
here, so that the source-of-truth rule survives the split.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created as a placeholder during Phase 0 initialization. | Drafted by Claude Code |
