---
title: Architecture
type: index
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Architecture

> **No architecture exists, and none should yet.** No technology, framework, language,
> datastore, hosting model or vendor has been chosen. Per
> [AGENTS.md rule 13](../../AGENTS.md), selecting any of them during Phase 0 is out of bounds.

## When architecture work starts

Architecture is defined **only when sufficient product requirements exist**. Concretely,
when:

1. The highest-impact open questions are answered — especially
   [OQ-012](../product/open-questions.md), [OQ-013](../product/open-questions.md),
   [OQ-015](../product/open-questions.md), [OQ-028](../product/open-questions.md)
2. A conceptual data model exists ([docs/data](../data/README.md))
3. The core workflows are documented ([docs/workflows](../workflows/README.md))
4. Non-functional requirements have numbers
   ([docs/product/non-functional-requirements.md](../product/non-functional-requirements.md))
5. A v1 scope boundary is drawn

Tracked as `DOC-008` in the [backlog](../agile/product-backlog.md).

## Constraints already known

These are architectural facts, not choices, and they hold whatever stack is selected:

| # | Constraint | Source |
| --- | --- | --- |
| 1 | Multi-tenant: one deployment serves many organizations, isolated from each other | Product direction |
| 2 | Tenant isolation may never be bypassed, including in tests and local development | [NFR-001](../product/non-functional-requirements.md) |
| 3 | Hierarchy Platform → Organization → Branch → Users must be representable | Product direction (`PROPOSED`) |
| 4 | Image-heavy: inspections generate many photographs per job | `EPIC-010` |
| 5 | Document generation is required (quotations, warranties, receipts) | Product direction |
| 6 | Cross-branch read access within an organization must be expressible — the rules are not yet known | `PG-003`, [OQ-015](../product/open-questions.md) |

## Decisions that will need an ADR

Named here so none of them is taken silently
([AGENTS.md rule 11](../../AGENTS.md)). This list is not a plan and implies no ordering.

- Multi-tenancy strategy (shared schema, schema-per-tenant, database-per-tenant)
- Authentication and session model
- Authorization model (how roles and branch scope are expressed and enforced)
- Language, framework and datastore
- File and image storage, and image processing
- Background/scheduled work (reminders, maintenance due detection)
- Document/PDF generation approach
- Messaging integration, especially WhatsApp — [OQ-033](../product/open-questions.md)
- Offline or degraded-connectivity capability — [OQ-038](../product/open-questions.md)
- Hosting, environments, deployment
- Audit logging approach — [OQ-040](../product/open-questions.md)
- Search approach, including cross-branch search

## Contents

| Document | Status |
| --- | --- |
| [decisions/](decisions/README.md) | ADR log — `ADR-001` recorded |
| System overview | Not written |
| Component model | Not written |
| Integration landscape | Not written |
| Environments | Not written |

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created during Phase 0 initialization. Known constraints recorded; pending decisions named; no technology selected. | Drafted by Claude Code |
