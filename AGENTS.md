# AGENTS.md — Operating rules for AI coding agents

**Audience:** OpenAI Codex, Claude Code, Cursor, Copilot agents, and any other automated
coding or authoring agent working in this repository or in the future implementation
repository.

**Status of this file:** BINDING. These rules override convenience, speed and inference.
Claude Code users: read this file, then [CLAUDE.md](CLAUDE.md) for tool-specific guidance.

---

## 0. What this repository is

A **documentation repository**. It holds the product's vision, requirements, rules,
decisions and plans. It contains **no application source code**, and must not.

The project is currently in **PHASE 0 — PRODUCT DISCOVERY & DOCUMENTATION**.

---

## 1. Documentation is the source of truth

If a statement is not in this repository, it is not a requirement. Conversation history,
your own reasoning, and industry convention are **not** sources of truth.

When documentation and any other input disagree, the documentation wins — or the conflict
is raised (rule 5). It is never silently resolved.

## 2. Read before you recommend

Before answering a question, proposing a design, or (later) writing code:

1. Read the relevant document(s) under `docs/`.
2. Check the [glossary](docs/product/glossary.md) so you use terms the way this project uses them.
3. Check the [open questions register](docs/product/open-questions.md) — the thing you are
   about to assume may already be a known unknown.
4. Check the [status](docs/meta/identifiers-and-status.md) of every requirement you rely on.

State which documents you read. Do not answer from memory of an earlier session.

## 3. Never invent business rules

You must not create, infer, or extrapolate:

- business rules, pricing logic, warranty terms, tax treatment, validation rules
- state machines, status transitions, role permissions
- data ownership or visibility rules
- SLAs, retention periods, limits or thresholds

If a rule is needed and absent, **write an open question** (`OQ-###`) and stop. A plausible
invented rule is more damaging than a visible gap, because it looks like a decision.

## 4. Flag ambiguity instead of guessing

When a document is unclear or two readings are possible:

- say so explicitly, naming the document and the ambiguous passage
- present the candidate readings and their consequences
- propose an open question
- do **not** pick one and proceed quietly

## 5. Identify conflicts between documents

If two documents disagree, report it with both `file:line` references, and do not act on
either until it is resolved. Record the resolution in the affected documents.

## 6. Respect requirement status

| Status | What you may do with it |
| --- | --- |
| `CONFIRMED` | Build on it, cite it, design against it. |
| `PROPOSED` | Discuss it. Never treat it as agreed. Label it when you cite it. |
| `UNDER DISCUSSION` | Discuss it. Expect it to change. Do not design around it. |
| `OPEN QUESTION` | Do not resolve it yourself. Surface it. |
| `DEFERRED` | Out of the current horizon. Do not pull it back in unasked. |
| `DEPRECATED` | Do not build on it. It exists only for traceability. |

Never promote a status. Only the product owner does that, and the change is recorded in
the document.

## 7. Respect organization and tenant boundaries

The Platform is multi-tenant. The intended hierarchy is
**Platform → Organization → Branch → Users/Staff**
(status: PROPOSED — see [docs/data/README.md](docs/data/README.md)).

Every design and, later, every query, endpoint and UI must be scoped to the acting user's
organization. Cross-organization data access is not permitted unless a `CONFIRMED`
requirement explicitly allows it. Cross-**branch** access within one organization is a
stated product goal but its rules are **not yet defined** — see
[OQ-015](docs/product/open-questions.md).

When tenancy scoping is unclear for something you are asked to design, that is a blocker,
not a detail to fill in later.

## 8. Security and authorization are never bypassed for convenience

No "temporary" unauthenticated endpoints, no "just for local dev" tenant-scope bypasses,
no disabling authorization to make a test pass, no broad role grants to avoid modelling a
narrow one. If a task appears to require bypassing authorization, stop and raise it.

## 9. Reference requirement IDs

Recommendations, designs, commits, pull requests and (later) code comments should cite the
requirement they serve — `US-014`, `BR-007`, `NFR-002` — wherever it is practical. Work
that cannot cite anything is a signal that the documentation is missing, not that the
citation is optional.

## 10. Keep documentation true after implementation

If implementation later proves an approved design wrong or unworkable, the documentation is
updated in the same change that proves it. Documentation that lags implementation has
failed at its only job.

## 11. Do not introduce major architecture decisions silently

Choosing a framework, datastore, tenancy strategy, auth model, background-job approach,
file-storage approach, or integration provider is a **decision**, not an implementation
detail. Surface it, get agreement, record it.

## 12. Record significant decisions as ADRs

Use [`templates/adr-template.md`](templates/adr-template.md) and file it under
[`docs/architecture/decisions/`](docs/architecture/decisions/README.md). An ADR states the
context, the options considered, the decision, and the consequences. ADRs are immutable
once accepted — supersede, never rewrite.

## 13. Do not start implementation during Phase 0

While the project is in Phase 0 you must not, unless the product owner explicitly instructs
otherwise in the current task:

- write application source code of any kind
- create database schemas, migrations, or ORM models
- define API endpoints, routes or contracts
- select frameworks, languages, libraries or vendors
- write configuration for infrastructure, CI/CD or deployment
- scaffold a project with any generator or CLI

Sample snippets purely to illustrate a *documentation* point are acceptable when clearly
marked as illustrative and non-binding.

---

## Working rules for this repository

### Where things go

| Producing | Put it in | From template |
| --- | --- | --- |
| Epic | `docs/epics/EPIC-###-slug.md` | `epic-template.md` |
| Feature | `docs/features/FEAT-###-slug.md` | `feature-template.md` |
| User story | `docs/user-stories/US-###-slug.md` | `user-story-template.md` |
| Business rule | `docs/business-rules/BR-###-slug.md` | `business-rule-template.md` |
| Workflow | `docs/workflows/WF-###-slug.md` | `workflow-template.md` |
| Module overview | `docs/modules/MOD-###-slug.md` | `module-template.md` |
| Architecture decision | `docs/architecture/decisions/ADR-###-slug.md` | `adr-template.md` |
| Open question | a row in `docs/product/open-questions.md`; long form in `docs/product/open-questions/` | `open-question-template.md` |
| NFR | `docs/product/non-functional-requirements.md` | `nfr-template.md` |
| Sprint record | `docs/agile/sprints/SPRINT-##.md` | `sprint-template.md` |

### Every document must

- begin with the YAML front matter block defined in
  [docs/meta/documentation-standards.md](docs/meta/documentation-standards.md)
- carry a `status` from the table in rule 6
- link to its parent (a feature links its epic; a story links its feature)
- use glossary terms exactly as the glossary defines them

### Before you finish a task

- [ ] Did I cite the documents I read?
- [ ] Did I write any statement that no document supports? (If yes: remove it or make it an `OQ`.)
- [ ] Did I label the status of every requirement I cited?
- [ ] Did I add new open questions I uncovered to the register?
- [ ] Did I update the index / parent documents so the new file is reachable?
- [ ] Did I avoid producing application code?

### When you disagree with these rules

Say so, explain why, and proceed under the rules until the product owner changes them.
