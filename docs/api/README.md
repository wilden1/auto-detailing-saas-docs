---
title: API Design
type: index
status: DEFERRED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# API

**Deliberately empty. `DEFERRED` until Phase 1.**

No endpoints, contracts, payloads, protocol choice or API style (REST, GraphQL, RPC) have
been decided, and none should be. Defining an API now would mean fixing the data model and
the technology stack by implication — both of which are explicitly undecided.

## Preconditions

API design may begin when:

1. The conceptual [data model](../data/README.md) exists
2. The [architecture](../architecture/README.md) exists, including an accepted ADR on the
   stack and on the authorization model
3. The v1 scope boundary is drawn

## What will live here

- API style and conventions (as an ADR)
- Authentication and authorization on the API surface
- Resource/operation catalogue, traced to `US-###`
- Tenancy scoping rules on every operation — [NFR-001](../product/non-functional-requirements.md)
- Error model, versioning policy, pagination, idempotency
- Any public surface, e.g. warranty verification — [OQ-027](../product/open-questions.md)

## Note for agents

If you are asked to design an API in this repository during Phase 0, decline and point here.
See [AGENTS.md rule 13](../../AGENTS.md).
