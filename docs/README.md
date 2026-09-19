---
title: Documentation Index
type: index
status: CONFIRMED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Documentation Index

The single source of truth for the Platform. **Phase 0 — Product Discovery & Documentation.**

Before writing anything here, read [documentation standards](meta/documentation-standards.md)
and [AGENTS.md](../AGENTS.md).

---

## Product

| Document | Status | What it answers |
| --- | --- | --- |
| [product/vision.md](product/vision.md) | `UNDER DISCUSSION` | Why this product exists; goals `PG-001`–`PG-006` |
| [product/scope.md](product/scope.md) | `PROPOSED` | What is in, what is out, what is undecided |
| [product/personas.md](product/personas.md) | `PROPOSED` | Who uses it — candidates only, no research yet |
| [product/glossary.md](product/glossary.md) | `PROPOSED` | What our words mean. **Read before writing.** |
| [product/non-functional-requirements.md](product/non-functional-requirements.md) | `PROPOSED` | Quality constraints, `NFR-###` |
| [product/open-questions.md](product/open-questions.md) | `CONFIRMED` (process) | **Everything not decided — 40 questions** |

## Agile process

| Document | Status | What it answers |
| --- | --- | --- |
| [agile/product-backlog.md](agile/product-backlog.md) | `PROPOSED` | What work exists — 15 epics, 8 spikes, 8 doc items |
| [agile/definition-of-ready.md](agile/definition-of-ready.md) | `PROPOSED` | When an item may enter a sprint |
| [agile/definition-of-done.md](agile/definition-of-done.md) | `PROPOSED` | When work is finished |
| [agile/sprint-process.md](agile/sprint-process.md) | `PROPOSED` | How we run Agile; how requirements change |
| [agile/releases.md](agile/releases.md) | `PROPOSED` | Release planning — none yet |
| [agile/sprints/](agile/sprints/README.md) | — | One record per sprint |

## Requirements

| Folder | Contents | State |
| --- | --- | --- |
| [epics/](epics/README.md) | `EPIC-001`–`EPIC-015` | 15 placeholders, all `PROPOSED`, none refined |
| [features/](features/README.md) | `FEAT-###` | Empty |
| [user-stories/](user-stories/README.md) | `US-###` + `AC-##` | Empty |
| [business-rules/](business-rules/README.md) | `BR-###` | Empty — rules exist as open questions |
| [workflows/](workflows/README.md) | `WF-###` | Core lifecycle stated; `WF-001`–`WF-011` reserved, none written |
| [modules/](modules/README.md) | `MOD-001`–`MOD-015` | Listed, none specified |

## Design

| Folder | State |
| --- | --- |
| [ui-ux/](ui-ux/README.md) | Nothing designed |
| [architecture/](architecture/README.md) | Constraints and pending decisions only — **no technology chosen** |
| [architecture/decisions/](architecture/decisions/README.md) | `ADR-001` accepted |
| [data/](data/README.md) | Candidate entities; ownership boundaries open — **no schema** |
| [api/](api/README.md) | `DEFERRED` to Phase 1 |
| [security/](security/README.md) | `NFR-001`/`NFR-002` binding; role model open |
| [testing/](testing/README.md) | Traceability model set; strategy deferred |

## Planning and meta

| Document | Purpose |
| --- | --- |
| [roadmap/](roadmap/README.md) | Phases and exit criteria — no dates |
| [meta/documentation-standards.md](meta/documentation-standards.md) | How to write documents here |
| [meta/identifiers-and-status.md](meta/identifiers-and-status.md) | ID conventions and status taxonomy |
| [meta/traceability.md](meta/traceability.md) | Product goal → epic → feature → story → AC → test |
| [/templates](../templates/README.md) | Copy-from templates for every document type |

---

## Where things stand today

- **`CONFIRMED`:** the documentation process itself, the product direction at the highest
  level, the phase we are in, and two binding security principles.
- **`PROPOSED`:** everything about the product — vision wording, goals, scope, epics,
  modules, personas, glossary definitions.
- **Open:** 40 questions, none answered. The eight that block the most are listed at the top
  of [open-questions.md](product/open-questions.md).

**Nothing here is ready to build against.**
