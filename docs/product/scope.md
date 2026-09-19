---
title: Initial Scope
type: product-doc
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-001, PG-002]
---

# Initial Scope

> **Read this first.** Everything in section 2 is **current product direction**, not agreed
> requirements. No release scope (v1 / MVP) has been defined. Section 4 lists the scope
> boundaries that are genuinely undecided — those are the questions that most need answers.

## 1. Scope of the *current phase* — `CONFIRMED`

**Phase 0 — Product Discovery & Documentation.**

In scope now:

- Product vision, terminology, documentation standards
- Actors and personas
- Major workflows
- Epics and an initial product backlog
- Open questions register
- Progressive refinement of features and user stories
- Architecture work **only once sufficient product requirements exist**

Explicitly out of scope now:

- Frontend code, backend code, database migrations, API definitions
- Technology, framework, library or vendor selection
- Infrastructure and deployment
- Any production feature

## 2. Product areas under consideration — `PROPOSED`

These are the fourteen areas currently envisaged. They are **not** a committed feature list,
and each maps to an epic in the [backlog](../agile/product-backlog.md).

| # | Product area | Epic | Module |
| --- | --- | --- | --- |
| 1 | Dashboard | `EPIC-015` | `MOD-014` |
| 2 | Branch Management | `EPIC-002` | `MOD-002` |
| 3 | Customer CRM | `EPIC-004` | `MOD-003` |
| 4 | Vehicle Management / Vehicle Passport | `EPIC-005` | `MOD-004` |
| 5 | Booking & Walk-ins | `EPIC-008` | `MOD-007` |
| 6 | Job Management | `EPIC-009` | `MOD-008` |
| 7 | Vehicle Inspection | `EPIC-010` | `MOD-009` |
| 8 | Services & Packages | `EPIC-006` | `MOD-005` |
| 9 | Quotations | `EPIC-007` | `MOD-006` |
| 10 | Payments | `EPIC-011` | `MOD-010` |
| 11 | Digital Warranty | `EPIC-012` | `MOD-011` |
| 12 | Maintenance | `EPIC-013` | `MOD-012` |
| 13 | CRM / Customer Follow-up | `EPIC-014` | `MOD-013` |
| 14 | Staff, Roles & Reporting | `EPIC-003` | `MOD-015` |

## 3. Platform-level concerns under consideration — `PROPOSED`

Cross-cutting capabilities that are not features in themselves but constrain every feature:

| Concern | Notes | Where it will be specified |
| --- | --- | --- |
| Authentication | Mechanism undecided | [security](../security/README.md) |
| Multi-tenancy | Platform → Organization → Branch → Users, `PROPOSED` | [data](../data/README.md), [security](../security/README.md) |
| Role-based access control | Roles not defined — [OQ-019](open-questions.md) | [security](../security/README.md) |
| Audit logging | What is audited, retention: undefined | [security](../security/README.md) |
| File/image management | Inspection photos are expected to be volume-heavy | [architecture](../architecture/README.md) |
| Search and filtering | Cross-branch search depends on [OQ-015](open-questions.md) | [architecture](../architecture/README.md) |
| PDF / document generation | Quotations, invoices, warranty certificates | [architecture](../architecture/README.md) |
| Responsive web interface | Workshop-floor usage implies mobile/tablet — [OQ-011](open-questions.md) | [ui-ux](../ui-ux/README.md) |
| Company configuration | Per-organization settings, branding | [modules](../modules/README.md) |

## 4. Scope boundaries not yet decided — `OPEN QUESTION`

These are the questions that determine how large this product actually is. **No exclusion
below has been agreed** — they are listed as questions precisely so they are not silently
assumed either way.

| Question | Open question |
| --- | --- |
| Is consumable/inventory stock tracking in scope? | [OQ-006](open-questions.md) |
| Is invoicing/tax compliance (e.g. Malaysian e-Invoice) in scope? | [OQ-007](open-questions.md) |
| Is staff commission or payroll in scope? | [OQ-008](open-questions.md) |
| Is there a customer-facing portal or app, or is this staff-only? | [OQ-009](open-questions.md) |
| Can customers self-book online? | [OQ-010](open-questions.md) |
| Which languages must the interface support? | [OQ-011](open-questions.md) |
| Is appointment/bay/technician scheduling capacity-aware? | [OQ-020](open-questions.md) |
| Do staff need a native mobile app, or is responsive web enough? | [OQ-041](open-questions.md) |
| Does the Platform own customer messaging, or integrate with WhatsApp? | [OQ-033](open-questions.md) |
| Is there a free tier / trial / subscription billing for the SaaS itself? | [OQ-035](open-questions.md) |

## 5. Release scope — `TODO`

No v1 / MVP boundary has been drawn. Drawing it requires, at minimum:
success measures ([OQ-005](open-questions.md)), the launch business types
([OQ-003](open-questions.md)), and a decision on the boundaries in section 4.

This is the recommended next major product activity after the framework is approved.

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created during Phase 0 initialization. Product areas restated as `PROPOSED`; scope boundaries raised as open questions rather than asserted. | Drafted by Claude Code |
