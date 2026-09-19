---
id: BR-###
title: <Rule name>
type: business-rule
status: PROPOSED
owner: TBD
created: <YYYY-MM-DD>
updated: <YYYY-MM-DD>
related: [<EPIC-###>, <US-###>]
---

# BR-### — <Rule name>

| | |
| --- | --- |
| **Status** | `PROPOSED` |
| **Applies to** | `EPIC-###`, `MOD-###` |
| **Source** | **<Who stated this rule, and when. Required.>** |

> **A business rule with no source is an assumption wearing an ID.** If you cannot name the
> person who told us this is the rule, it is not a rule — it is an
> [open question](../product/open-questions.md).

## Rule

<State it in one sentence, unambiguously, in domain language.>

## Rationale

<Why the business works this way. Often commercial, legal or historical. This is what stops
the rule being "simplified" later by someone who does not know why it exists.>

## Conditions

| When | Then |
| --- | --- |
| <condition> | <consequence> |

## Exceptions

<Who may override it, under what circumstances, and whether the override is recorded.
"None" is a valid and useful answer.>

## Examples

| Scenario | Outcome |
| --- | --- |
| <concrete case> | <result> |
| <edge case> | <result> |

## Consequences of getting it wrong

<What breaks — commercially, legally, or for the customer — if this rule is implemented
incorrectly. Drives how hard it is tested.>

## Related

| ID | Relationship |
| --- | --- |
| `US-###` | Constrained by this rule |
| `BR-###` | Interacts with |
| `OQ-###` | Unresolved aspect |

## Change log

| Date | Change | By |
| --- | --- | --- |
| <YYYY-MM-DD> | Created. | <who> |
