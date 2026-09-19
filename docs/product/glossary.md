---
title: Glossary
type: product-doc
status: PROPOSED
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Glossary

The project's shared vocabulary. **Every document and every agent must use these terms with
these meanings.** If you need a word that is not here, add it here first.

> **Status: `PROPOSED`.** These are *working definitions* drafted to make discussion
> possible. Several carry a ⚠️ marker where the definition materially affects the data model
> or behaviour and is genuinely undecided — those must be resolved, not assumed.

## Tenancy and structure

| Term | Working definition | Notes |
| --- | --- | --- |
| **PRO-TECH** | The automotive detailing business this system is built for. **In V1 there is exactly one company, and it is PRO-TECH.** | ⚠️ Branch count today unknown — [OQ-043](open-questions.md) |
| **Company** (Organization) | A business that owns branches, staff, customers, vehicles and jobs. Retained as a **generic** concept — not replaced by "PRO-TECH" — so future productization stays possible without redesign. See [ADR-002](../architecture/decisions/ADR-002-v1-single-company-scope.md). | ⚠️ Whether an explicit Company entity exists in V1, or PRO-TECH is implicit — [OQ-042](open-questions.md) |
| **HQ / Management** | PRO-TECH's central function, as distinct from an individual branch. | ⚠️ Whether HQ is a Branch, a level above Branch, or a permission scope — [OQ-044](open-questions.md) |
| **Branch** | A physical location or operating unit belonging to one Company. A Company has at least one. | |
| **Staff / User** | A person with a login, belonging to the Company and working at one or more Branches. | ⚠️ Multi-branch membership undecided — [OQ-016](open-questions.md) |
| **Role** | A named set of permissions assigned to a user. | ⚠️ Role list undefined — [OQ-019](open-questions.md) |

### Not V1 concepts

Deferred to future productization. **Do not use these terms when describing V1** — using
them is how multi-tenancy creeps into a single-company system.

| Term | Working definition | Status |
| --- | --- | --- |
| **Platform** | A SaaS product operated by us and shared by many customer businesses. | `DEFERRED` — see [future-productization](../future-productization/README.md) |
| **Tenant** | One isolated customer business within a multi-tenant platform. | `DEFERRED` — not a V1 concept |
| **Single-branch business** | A company with exactly one branch, which must not feel burdened by multi-branch concepts. | `DEFERRED` — a productization concern. PRO-TECH's branch count is a fact to research ([OQ-043](open-questions.md)), not a variable to design for |

## Customer and vehicle

| Term | Working definition | Notes |
| --- | --- | --- |
| **Customer** | A person or company that owns or brings in a vehicle, and to whom quotations, jobs and payments relate. | ⚠️ Owned by Organization or by Branch? — [OQ-012](open-questions.md) |
| **Vehicle** | A specific motor vehicle serviced by the Organization, identified by its registration and/or VIN. | ⚠️ Identity key undecided — [OQ-017](open-questions.md) |
| **Vehicle Passport** | The centralized, durable digital profile of a Vehicle: its information, owner, service, job, inspection, warranty and maintenance history, and recommended future maintenance. | `PROPOSED` product concept — `EPIC-005` |
| **Ownership change** | A Vehicle changing hands from one Customer to another. | ⚠️ Effect on history and warranty undefined — [OQ-025](open-questions.md) |

## Commercial

| Term | Working definition | Notes |
| --- | --- | --- |
| **Service** | A single sellable unit of work (e.g. a full interior detail, a windscreen tint). | |
| **Package** | A named bundle of Services sold together, usually at a set price. | ⚠️ Whether packages are priced independently of their services is undecided |
| **Quotation** | A priced offer of Services/Packages for a Customer and Vehicle, valid for a period, which may be accepted or lapse. | ⚠️ What it converts into — Booking, Job, or both — [OQ-021](open-questions.md) |
| **Payment** | Money received against a Job or Quotation. | ⚠️ Deposits and partial payments undecided — [OQ-024](open-questions.md) |

## Operations

| Term | Working definition | Notes |
| --- | --- | --- |
| **Booking** | A scheduled future appointment for a Customer and Vehicle at a Branch. | |
| **Walk-in** | A Customer arriving without a prior Booking. | ⚠️ A Booking created on arrival, or a separate concept? — [OQ-022](open-questions.md) |
| **Check-in** | The act of receiving the Vehicle at the Branch and starting its visit. | |
| **Visit** | One occasion on which a Vehicle is at a Branch, from check-in to handover. | ⚠️ Working term introduced here to expose the Job ambiguity — [OQ-028](open-questions.md) |
| **Job** | The work performed on a Vehicle. | ⚠️ **Materially undecided:** one Job per visit, or one Job per service within a visit? — [OQ-028](open-questions.md) |
| **Job Progress** | The recorded advancement of a Job through its stages, visible to staff and possibly to the Customer. | ⚠️ Stage list undefined |
| **Vehicle Inspection** | Documentation of the Vehicle's condition, recorded as structured observations and photographs, typically before and after work. | `EPIC-010` |
| **Before / After record** | Inspection evidence captured at the start and at the end of a Job. | |
| **Quality Control (QC)** | The check that completed work meets standard before handover. | ⚠️ A Job status, or a separate record with its own outcome and approver? — [OQ-023](open-questions.md) |
| **Handover** | Returning the Vehicle to the Customer. | Working term; not yet a confirmed lifecycle stage |

## After-service

| Term | Working definition | Notes |
| --- | --- | --- |
| **Digital Warranty** | A record generated for eligible Services, covering a Customer, Vehicle, Service/Package, installation date, period, expiry, originating Branch, terms, maintenance requirements and status. | `EPIC-012` |
| **Warranty status** | Where a warranty stands: active, expired, voided, transferred, claimed. | ⚠️ Status list and who may change it are undefined — [OQ-026](open-questions.md) |
| **Warranty verification** | Confirming a warranty is genuine and current, possibly by scanning a QR code. | ⚠️ Whether verification is public (no login) and what it exposes — [OQ-027](open-questions.md) |
| **Maintenance** | Servicing required to keep a warranty valid or a treatment performing (e.g. a coating maintenance wash). | `EPIC-013` |
| **Maintenance due / overdue** | A maintenance item approaching, or past, its required date. | ⚠️ Thresholds undefined |
| **Follow-up** | A deliberate contact with a Customer after service — reminder, check-in, or re-sell. | `EPIC-014` |
| **Inactive customer** | A Customer with no activity for some period. | ⚠️ Period undefined; must not be invented |
| **Repeat business** | A Customer returning for further paid work. | The lifecycle's intended end state |

## Process and documentation

| Term | Working definition |
| --- | --- |
| **Product Goal (`PG`)** | A top-level outcome the product exists to achieve. |
| **Epic (`EPIC`)** | A large body of work, too big for one sprint, delivering part of a product goal. |
| **Feature (`FEAT`)** | A coherent capability within an epic. |
| **User Story (`US`)** | A small, valuable change described from a user's point of view. |
| **Acceptance Criterion (`AC`)** | A testable condition that must hold for a story to be accepted. |
| **Business Rule (`BR`)** | A constraint on behaviour that holds independently of any one story. |
| **Non-Functional Requirement (`NFR`)** | A quality constraint — performance, security, availability, usability. |
| **Workflow (`WF`)** | An end-to-end process crossing several actors or modules. |
| **Module (`MOD`)** | A product area of the application, as users perceive it. |
| **ADR** | Architecture Decision Record — context, options, decision, consequences. |
| **Open Question (`OQ`)** | A known unknown, recorded rather than guessed at. |
| **Spike (`SPIKE`)** | Time-boxed research to answer a question or reduce risk. |
| **Definition of Ready (DoR)** | The bar a story must clear to enter a sprint. |
| **Definition of Done (DoD)** | The bar work must clear to be called finished. |

## Deliberately undefined

The following terms are used in the industry but have **no agreed meaning in this project
yet**. Do not use them in documentation until they are defined here: *work order, job card,
service ticket, estimate, invoice, appointment slot, bay, technician assignment, SLA,
loyalty, membership.*

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Created during Phase 0 initialization. Working definitions drafted from the product owner's own vocabulary; material ambiguities marked ⚠️ and raised as open questions rather than resolved. | Drafted by Claude Code |
| 2026-09-19 | **V1 direction change.** Added `PRO-TECH` and `HQ / Management`. `Organization` renamed to `Company` (kept generic per [ADR-002](../architecture/decisions/ADR-002-v1-single-company-scope.md)). `Platform`, `Tenant` and `Single-branch business` moved to a "Not V1 concepts" section rather than deleted — they remain meaningful for future productization. | Product owner decision |
