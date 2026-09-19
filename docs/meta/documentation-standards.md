---
title: Documentation Standards
type: standard
status: ACTIVE
owner: TBD
created: 2026-09-19
updated: 2026-09-19
---

# Documentation Standards

How documents in this repository are written, named, reviewed and changed. Deliberately
short — the aim is discipline, not bureaucracy.

## 1. Front matter

Every document under `docs/` begins with a YAML front matter block. This is what lets AI
agents and future tooling read the repository reliably.

```yaml
---
id: EPIC-005                  # omit for documents without an ID (e.g. glossary)
title: Vehicle Management / Vehicle Passport
type: epic                    # epic | feature | user-story | business-rule | workflow |
                              # module | adr | nfr | standard | product-doc | process | index
status: PROPOSED              # see identifiers-and-status.md
owner: TBD                    # accountable person, or TBD
created: 2026-09-19
updated: 2026-09-19
related: [PG-004, MOD-004]    # optional: IDs this document depends on or serves
---
```

Rules:

- `updated` changes whenever the content changes materially.
- `owner: TBD` is honest and acceptable. A wrong owner is not.
- `related` holds IDs only, never prose.

## 2. File naming

- Identified documents: `<ID>-<kebab-slug>.md` — `US-014-record-vehicle-inspection.md`
- Non-identified documents: `kebab-slug.md` — `definition-of-ready.md`
- Every folder under `docs/` has a `README.md` acting as that folder's index.

## 3. Writing rules

1. **Write only what is known.** If you do not know, write `TODO` or raise an `OQ-###`.
   A document with gaps is healthy; a document with invented filler is a liability.
2. **Mark the status of anything not confirmed**, inline, where it is stated.
3. **Use glossary terms exactly.** If you need a new term, add it to the
   [glossary](../product/glossary.md) in the same change.
4. **Prefer tables and lists** for structured content; prefer short paragraphs for rationale.
5. **Link, do not duplicate.** A fact lives in exactly one document; everything else links to
   it. Duplicated facts drift and then conflict.
6. **Write for decision-making.** Say what someone should do with the information.
7. **No implementation detail.** No code, schemas, endpoints, libraries or vendor choices
   unless an accepted ADR has established them.
8. **British or American spelling** — pick one per document and be consistent.
   *(Project-wide convention is an open question; not worth blocking on.)*

## 4. Document lifecycle

```
draft (PROPOSED) → reviewed → agreed (CONFIRMED) → superseded (DEPRECATED)
                 ↘ contested (UNDER DISCUSSION) ↗
                 ↘ postponed (DEFERRED)
```

- Anyone may draft.
- Only the product owner may move a document to `CONFIRMED`, `DEFERRED` or `DEPRECATED`.
- Every status change is recorded in the document's change log.

## 5. Change traceability

Requirements are expected to change. Changes must be traceable. Two mechanisms, both cheap:

1. **Git history** is the authoritative record of what changed and when.
2. **A change log table** at the bottom of every requirement-bearing document records *why*
   and *who agreed*, which git cannot tell you:

   ```markdown
   ## Change log

   | Date | Change | By |
   | --- | --- | --- |
   | 2026-09-19 | Created as PROPOSED. | — |
   ```

Commit messages reference the affected IDs: `docs(US-014): split inspection story after refinement`.

## 6. Review

- Documentation changes are reviewed by at least one other person before being treated as
  agreed. *(Reviewer roles are an open question — see [OQ-029](../product/open-questions.md).)*
- A document may be merged while still `PROPOSED`. Merging is not agreement; status is.

## 7. What does **not** belong in this repository

- Application source code, schemas, migrations, API contracts *(Phase 0)*
- Secrets, credentials, customer data, real personal data
- Meeting transcripts — extract decisions and open questions instead
- Screenshots of competitor products without a note on why they are retained

## Change log

| Date | Change | By |
| --- | --- | --- |
| 2026-09-19 | Initial standards established during Phase 0 repository initialization. | Product owner (requested), drafted by Claude Code |
