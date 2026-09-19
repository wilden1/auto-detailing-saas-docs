---
id: WF-###
title: <Workflow name>
type: workflow
status: PROPOSED
owner: TBD
created: <YYYY-MM-DD>
updated: <YYYY-MM-DD>
related: [<EPIC-###>, <MOD-###>]
---

# WF-### — <Workflow name>

| | |
| --- | --- |
| **Status** | `PROPOSED` |
| **Trigger** | <what starts it> |
| **Outcome** | <what state the world is in when it ends> |
| **Actors** | <roles involved> |
| **Modules** | `MOD-###` |

## Overview

<One paragraph: what this process achieves end to end.>

## Flow

```
<Step 1: actor — action>
   → <Step 2: actor — action>
      → <Step 3: actor — action>
```

## Steps

| # | Actor | Action | What is recorded | What can go wrong |
| --- | --- | --- | --- | --- |
| 1 | <role> | <action> | <data created or changed> | <failure and its handling> |
| 2 | | | | |

## Exception paths

**The exceptions are the point** — the happy path is usually already understood.

| Exception | When it happens | What the system does |
| --- | --- | --- |
| <…> | <…> | <…> |

## Variations

<How this differs for a single-branch vs multi-branch business, a walk-in vs a booking, or
between service types.>

## Business rules

| ID | Rule |
| --- | --- |
| `BR-###` | <summary> |

## Authorization and tenancy

<Who may perform each step. Anything that crosses a branch boundary, and by what rule.>

## Open questions

| ID | Question |
| --- | --- |
| `OQ-###` | <…> |

## Source

<Observed / described by whom, on what date. A workflow written from imagination is fiction.>

## Change log

| Date | Change | By |
| --- | --- | --- |
| <YYYY-MM-DD> | Created. | <who> |
