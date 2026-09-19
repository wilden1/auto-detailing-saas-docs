# CLAUDE.md — Guidance for Claude Code

**Read [AGENTS.md](AGENTS.md) first. It is binding and applies to you in full.**
This file adds Claude Code specific operating guidance. Where the two ever disagree,
AGENTS.md wins and the conflict should be reported.

---

## Project in one paragraph

**V1 is a single-company, multi-branch Automotive Detailing Management System for
PRO-TECH** — one business operating multiple branches. It aims to manage the full customer
and vehicle lifecycle (detailing, ceramic coating, PPF, tinting, wrapping), not just
bookings.

**Multi-tenancy is not a V1 requirement.** There is a longer-term intention to productize
this into a multi-tenant SaaS for other detailing businesses, but nothing may be built for
that in V1 — see [ADR-002](docs/architecture/decisions/ADR-002-v1-single-company-scope.md)
and [docs/future-productization/](docs/future-productization/README.md).

**The project is in Phase 0 — documentation only. No application code.**

## The thirteen rules, compressed

1. Documentation is the source of truth — not conversation, not your priors.
2. Read the relevant docs before recommending anything; say which you read.
3. Never invent a business rule. Missing rule → write an `OQ-###`.
4. Flag ambiguity; never silently pick a reading.
5. Report conflicts between documents with `file:line`; do not resolve them yourself.
6. Respect requirement status. `PROPOSED` is not `CONFIRMED`.
7. Respect company and branch boundaries. V1 is single-company; branch scoping is the live concern, multi-tenancy is not.
8. Never bypass security or authorization for convenience.
9. Cite requirement IDs (`US-###`, `BR-###`) in recommendations, commits and PRs.
10. If implementation changes an approved design, update the documentation in the same change.
11. Never introduce a major architecture decision silently.
12. Record significant decisions as ADRs.
13. Do not begin application implementation during Phase 0 unless explicitly told to.

Full text and rationale: [AGENTS.md](AGENTS.md).

## Session start checklist

At the start of any substantive task in this repository:

1. Read [docs/README.md](docs/README.md) to orient.
2. Read [docs/product/open-questions.md](docs/product/open-questions.md) — it tells you what
   is *not* decided, which is usually the constraint on your answer.
3. Read the specific epic/feature/story you have been pointed at, plus its parents.
4. Skim [docs/product/glossary.md](docs/product/glossary.md) if the task touches domain terms.

## How to work here

**Prefer editing an existing document over creating a new one.** This repository should stay
navigable by a human. Do not create a new file when a section in an existing file will do.

**Use the templates.** `templates/` defines the shape of every document type. Copying a
template is not bureaucracy; inventing a new shape is.

**Write for three readers at once:** a product owner who needs to decide, a developer who
needs to build, and an agent who needs to parse. That means: front matter, stable IDs,
explicit status, short sentences, tables over prose where the content is structured.

**Keep the index current.** If you add a document, add it to the relevant index
(`docs/README.md`, and the folder's own `README.md`) in the same change.

**Length discipline.** A document that says less but says it truthfully is better than a long
one padded with plausible-sounding requirements. Empty sections marked `TODO` or
`OPEN QUESTION` are correct and expected at this stage.

## Things Claude Code specifically gets wrong here

| Temptation | What to do instead |
| --- | --- |
| Filling a template's empty sections with reasonable-sounding content | Leave `TODO` and raise an `OQ` |
| Writing a schema or ERD to "clarify" the data model | Describe entities and relationships in prose; no columns, no types, no DDL |
| Suggesting a stack because the domain "usually" uses one | Nothing is chosen. Raise it as an ADR candidate. |
| Answering a domain question from general knowledge of detailing businesses | Check the glossary and docs; if absent, it is an `OQ` |
| Turning an `OQ` into an answer because the answer seems obvious | Obvious to you is not agreed by the product owner |
| Expanding scope because an adjacent feature "would be needed anyway" | Deliver the asked scope; note the adjacency |
| Creating `docs/**/*.md` stubs in bulk to look complete | Create a document when there is something true to put in it |

## When asked to write code

The correct response during Phase 0 is to decline and offer the documentation equivalent —
for example a workflow (`WF-###`), a business rule (`BR-###`), or an ADR. If the product
owner explicitly overrides Phase 0 for a specific task, proceed with that task only, and say
that Phase 0 was explicitly overridden.

## Commits and pull requests

- Reference the document IDs affected: `docs(EPIC-005): add vehicle passport open questions`.
- One logical documentation change per commit.
- Do not commit or push unless asked.

## Useful entry points

| Need | File |
| --- | --- |
| What are we building and why | [docs/product/vision.md](docs/product/vision.md) |
| What is in and out of scope | [docs/product/scope.md](docs/product/scope.md) |
| What a term means here | [docs/product/glossary.md](docs/product/glossary.md) |
| What is not decided | [docs/product/open-questions.md](docs/product/open-questions.md) |
| What work exists | [docs/agile/product-backlog.md](docs/agile/product-backlog.md) |
| Epic list | [docs/epics/README.md](docs/epics/README.md) |
| When a story may enter a sprint | [docs/agile/definition-of-ready.md](docs/agile/definition-of-ready.md) |
| When work is finished | [docs/agile/definition-of-done.md](docs/agile/definition-of-done.md) |
| ID and status conventions | [docs/meta/identifiers-and-status.md](docs/meta/identifiers-and-status.md) |
| How to trace goal → test | [docs/meta/traceability.md](docs/meta/traceability.md) |
