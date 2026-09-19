---
title: Epic Index
type: index
status: CONFIRMED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Epics

> **All fifteen epics are `PROPOSED` initial backlog items, not finalized requirements.**
> None has been refined. The order below is ID order, **not** priority — no prioritization
> exists yet.

| ID | Epic | Goals | Module | Refined | Key blockers |
| --- | --- | --- | --- | --- | --- |
| [EPIC-001](EPIC-001-platform-and-organization-management.md) | Platform & Organization Management | `PG-002` | `MOD-001` | No | `OQ-035` |
| [EPIC-002](EPIC-002-branch-management.md) | Branch Management | `PG-002`, `PG-003` | `MOD-002` | No | `OQ-012`, `OQ-015` |
| [EPIC-003](EPIC-003-staff-and-access-control.md) | Staff & Access Control | `PG-002` | `MOD-015` | No | `OQ-016`, `OQ-019` |
| [EPIC-004](EPIC-004-customer-management.md) | Customer Management | `PG-001` | `MOD-003` | No | `OQ-012`, `OQ-018` |
| [EPIC-005](EPIC-005-vehicle-management-and-passport.md) | Vehicle Management / Vehicle Passport | `PG-004` | `MOD-004` | No | `OQ-013`, `OQ-017`, `OQ-025` |
| [EPIC-006](EPIC-006-services-and-packages.md) | Services & Packages | `PG-001` | `MOD-005` | No | `OQ-003` |
| [EPIC-007](EPIC-007-quotations.md) | Quotations | `PG-001` | `MOD-006` | No | `OQ-021` |
| [EPIC-008](EPIC-008-booking-and-walk-ins.md) | Booking & Walk-ins | `PG-001` | `MOD-007` | No | `OQ-010`, `OQ-020`, `OQ-022` |
| [EPIC-009](EPIC-009-job-management.md) | Job Management | `PG-001` | `MOD-008` | No | `OQ-023`, `OQ-028` |
| [EPIC-010](EPIC-010-vehicle-inspection.md) | Vehicle Inspection | `PG-006` | `MOD-009` | No | `OQ-036`, `OQ-038`, `OQ-039` |
| [EPIC-011](EPIC-011-payments.md) | Payments | `PG-001` | `MOD-010` | No | `OQ-007`, `OQ-024`, `OQ-034` |
| [EPIC-012](EPIC-012-digital-warranty.md) | Digital Warranty | `PG-006` | `MOD-011` | No | `OQ-025`, `OQ-026`, `OQ-027` |
| [EPIC-013](EPIC-013-maintenance.md) | Maintenance | `PG-005` | `MOD-012` | No | `OQ-026` |
| [EPIC-014](EPIC-014-crm-and-follow-up.md) | CRM & Customer Follow-up | `PG-005` | `MOD-013` | No | `OQ-033`, `OQ-011` |
| [EPIC-015](EPIC-015-dashboard-and-reporting.md) | Dashboard & Reporting | `PG-001` | `MOD-014` | No | `OQ-005`, `OQ-015` |

## Not yet epics

The cross-cutting platform concerns — authentication, multi-tenancy enforcement, audit
logging, file/image management, search, PDF generation, company configuration — are listed
in [scope.md §3](../product/scope.md) and have no epic. Whether each becomes an epic or is
absorbed is an open decision.

## Adding an epic

1. Take the next free `EPIC-###` from this table.
2. Copy [`templates/epic-template.md`](../../templates/epic-template.md).
3. Name it `EPIC-###-kebab-slug.md`.
4. Add a row here and to [product-backlog.md](../agile/product-backlog.md) in the same change.
