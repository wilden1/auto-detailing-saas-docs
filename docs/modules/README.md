---
title: Module Index
type: index
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Modules

A **module** is a product area as users perceive it — what they would call a section of the
application. Modules map to epics but are not the same thing: an epic is work, a module is a
place in the product.

> All modules are `PROPOSED` current product direction. None has been specified.

| ID | Module | Epic | Specified |
| --- | --- | --- | --- |
| `MOD-001` | Platform & Organization Administration | `EPIC-001` | No |
| `MOD-002` | Branch Management | `EPIC-002` | No |
| `MOD-003` | Customer CRM | `EPIC-004` | No |
| `MOD-004` | Vehicle Management / Vehicle Passport | `EPIC-005` | No |
| `MOD-005` | Services & Packages | `EPIC-006` | No |
| `MOD-006` | Quotations | `EPIC-007` | No |
| `MOD-007` | Booking & Walk-ins | `EPIC-008` | No |
| `MOD-008` | Job Management | `EPIC-009` | No |
| `MOD-009` | Vehicle Inspection | `EPIC-010` | No |
| `MOD-010` | Payments | `EPIC-011` | No |
| `MOD-011` | Digital Warranty | `EPIC-012` | No |
| `MOD-012` | Maintenance | `EPIC-013` | No |
| `MOD-013` | CRM / Customer Follow-up | `EPIC-014` | No |
| `MOD-014` | Dashboard | `EPIC-015` | No |
| `MOD-015` | Staff, Roles & Reporting | `EPIC-003` | No |

## Known overlaps to resolve

| Overlap | Question |
| --- | --- |
| `MOD-003` Customer CRM vs `MOD-013` CRM / Customer Follow-up | The product direction lists both. Is CRM one module (records + outreach) or two (records vs campaigns)? |
| `MOD-014` Dashboard vs `MOD-015` …& Reporting | Reporting appears in both. Where does a report live? |
| `MOD-001` vs `MOD-002` | For a single-branch business, is branch management a separate place at all, or part of company settings? |

These overlaps come from the current product direction itself and should be settled during
refinement rather than left for implementation to guess at.

## Cross-cutting concerns — not modules

Authentication, multi-tenancy, RBAC, audit logging, file/image management, search, PDF
generation, responsive web and company configuration are platform concerns, not modules.
They are listed in [scope.md §3](../product/scope.md) and specified in
[architecture](../architecture/README.md) and [security](../security/README.md).

## Adding a module document

Use [`templates/module-template.md`](../../templates/module-template.md), file as
`MOD-###-slug.md`, and add a row above. Write one **only** when there is something specified
to write — not to fill the table.
