# Automotive Detailing SaaS — Product Documentation

> **Working repository name.** The product does not have a confirmed name yet — see
> [OQ-001](docs/product/open-questions.md). Throughout this repository the product is
> referred to as **"the Platform"**. Renaming the repository later is expected and cheap.

This repository is the **single source of truth** for the product. It contains the product
vision, scope, terminology, epics, features, user stories, business rules, workflows,
architecture decisions and test strategy for a multi-tenant SaaS platform serving
automotive detailing and related automotive appearance/service businesses.

## Current phase

**PHASE 0 — PRODUCT DISCOVERY & DOCUMENTATION** (see [roadmap](docs/roadmap/README.md))

We are documenting, analyzing, designing and planning. We are **not** building.

| We are doing | We are not doing (yet) |
| --- | --- |
| Product vision, scope, terminology | Frontend or backend code |
| Personas and actors | Database schemas or migrations |
| Workflows and epics | API contracts or endpoints |
| Product backlog and Agile process | Technology / library selection |
| Open questions and decisions | Infrastructure or deployment |

Application source code will live in a **separate implementation repository**, created only
once this documentation reaches sufficient maturity.

## Start here

| If you are a… | Read, in this order |
| --- | --- |
| Product owner | [Vision](docs/product/vision.md) → [Scope](docs/product/scope.md) → [Open questions](docs/product/open-questions.md) → [Backlog](docs/agile/product-backlog.md) |
| Developer | [AGENTS.md](AGENTS.md) → [Glossary](docs/product/glossary.md) → [Epics](docs/epics/README.md) → [Architecture](docs/architecture/README.md) |
| QA engineer | [Glossary](docs/product/glossary.md) → [Definition of Done](docs/agile/definition-of-done.md) → [Testing](docs/testing/README.md) |
| AI coding agent | [AGENTS.md](AGENTS.md) (binding) and, for Claude Code, [CLAUDE.md](CLAUDE.md) |
| Anyone | [Documentation index](docs/README.md) |

## Requirement status legend

Every requirement-bearing document carries a status. Nothing is assumed to be fixed.

| Status | Meaning |
| --- | --- |
| `CONFIRMED` | Agreed by the product owner. Safe to build against. |
| `PROPOSED` | Drafted, plausible, **not** agreed. Do not treat as a requirement. |
| `UNDER DISCUSSION` | Actively being debated. Expect change. |
| `OPEN QUESTION` | Information is missing. Tracked in the open questions register. |
| `DEFERRED` | Deliberately postponed. Not in the current horizon. |
| `DEPRECATED` | Was once agreed, now withdrawn. Kept for traceability. |

Documents that assert no requirements — indexes, standards, registers — use a separate,
smaller vocabulary instead: `ACTIVE`, `DRAFT`, `SUPERSEDED`. ADRs use their own
(`Proposed` / `Accepted` / `Superseded` / `Rejected`).

Full definitions: [docs/meta/identifiers-and-status.md](docs/meta/identifiers-and-status.md)

## Identifier conventions (quick reference)

`PG-001` Product Goal · `EPIC-001` Epic · `FEAT-001` Feature · `US-001` User Story ·
`AC-01` Acceptance Criterion (scoped to a story) · `BR-001` Business Rule ·
`NFR-001` Non-Functional Requirement · `WF-001` Workflow · `MOD-001` Module ·
`ADR-001` Architecture Decision Record · `OQ-001` Open Question · `TC-001` Test Case ·
`SPIKE-001` Research Spike · `RISK-001` Risk · `BUG-001` Defect (during development)

Full conventions: [docs/meta/identifiers-and-status.md](docs/meta/identifiers-and-status.md)

## Contributing

1. Read [docs/meta/documentation-standards.md](docs/meta/documentation-standards.md).
2. Start from a file in [`templates/`](templates/README.md) — do not invent new document shapes.
3. If you do not know something, **create an [open question](docs/product/open-questions.md)**.
   Never write an assumption as if it were a decision.
4. Significant architectural or cross-cutting decisions require an
   [ADR](docs/architecture/decisions/README.md).

## Repository layout

```
.
├── README.md                  This file
├── CLAUDE.md                  Operating rules for Claude Code
├── AGENTS.md                  Binding operating rules for all AI coding agents
├── docs/
│   ├── README.md              Documentation index / navigation
│   ├── product/               Vision, scope, personas, glossary, NFRs, open questions
│   ├── agile/                 Backlog, DoR, DoD, sprint process, releases
│   ├── epics/                 EPIC-### — large bodies of work
│   ├── features/              FEAT-### — features within an epic
│   ├── user-stories/          US-### — stories with acceptance criteria
│   ├── business-rules/        BR-### — rules that constrain behaviour
│   ├── workflows/             WF-### — end-to-end process flows
│   ├── modules/               MOD-### — product areas of the application
│   ├── ui-ux/                 Interface principles, flows, wireframe notes
│   ├── architecture/          System design + decisions/ (ADRs)
│   ├── data/                  Conceptual data model, ownership, tenancy boundaries
│   ├── api/                   API design (deferred until architecture exists)
│   ├── security/              Tenancy isolation, authorization, privacy, audit
│   ├── testing/               Test strategy, test cases, traceability to AC
│   ├── roadmap/               Phases and horizons
│   └── meta/                  Documentation standards, identifiers, traceability
└── templates/                 Copy-from templates for every document type
```
