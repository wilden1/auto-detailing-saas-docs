---
id: US-###
title: <Short story title>
type: user-story
status: PROPOSED
owner: TBD
created: <YYYY-MM-DD>
updated: <YYYY-MM-DD>
related: [<FEAT-###>, <BR-###>, <NFR-###>]
---

# US-### — <Short story title>

| | |
| --- | --- |
| **Status** | `PROPOSED` |
| **Ready** | No — see [Definition of Ready](../agile/definition-of-ready.md) |
| **Feature** | [`FEAT-###`](../features/FEAT-###-slug.md) |
| **Epic** | [`EPIC-###`](../epics/EPIC-###-slug.md) |
| **Estimate** | TBD |

## Story

> **As a** <role — from [personas](../product/personas.md)>
> **I want** <capability>
> **So that** <value>

## Context

<Why now, what the user is doing when this matters, anything a developer would otherwise
have to guess.>

## Acceptance criteria

Each criterion must be judgeable true or false without argument. Cover error and edge paths,
not only the happy path.

| ID | Given | When | Then |
| --- | --- | --- | --- |
| `AC-01` | <context> | <action> | <observable outcome> |
| `AC-02` | | | |

## Authorization

| Role | May perform this? | Scope |
| --- | --- | --- |
| <role> | Yes / No | Own branch / All branches in organization / Organization-wide |

**Tenant isolation:** <what must not be reachable outside the acting user's authorized
organizational context here — see [NFR-001](../product/non-functional-requirements.md)>

## Business rules applied

| ID | Rule |
| --- | --- |
| `BR-###` | <summary> |

*If a rule this story needs does not exist as a `BR-###`, stop. Do not state it here as new.
Raise an [open question](../product/open-questions.md).*

## Non-functional requirements

| ID | Requirement |
| --- | --- |
| `NFR-###` | <summary> |

## Out of scope

- <…>

## Dependencies

| Depends on | Why |
| --- | --- |
| `US-###` | <…> |

## Open questions

| ID | Question | Blocks READY? |
| --- | --- | --- |
| `OQ-###` | <…> | Yes / No |

## Test cases

| ID | Covers | Status |
| --- | --- | --- |
| `TC-###` | `AC-01` | Not written |

## Change log

| Date | Change | By |
| --- | --- | --- |
| <YYYY-MM-DD> | Created. | <who> |
