# Templates

Copy-from templates for every document type. **Use them.** Consistent shape is what lets a
reader — or an agent — find the same information in the same place every time.

| Template | Produces | Files to |
| --- | --- | --- |
| [epic-template.md](epic-template.md) | `EPIC-###` | `docs/epics/` |
| [feature-template.md](feature-template.md) | `FEAT-###` | `docs/features/` |
| [user-story-template.md](user-story-template.md) | `US-###` + `AC-##` | `docs/user-stories/` |
| [business-rule-template.md](business-rule-template.md) | `BR-###` | `docs/business-rules/` |
| [nfr-template.md](nfr-template.md) | `NFR-###` | `docs/product/non-functional-requirements.md` |
| [workflow-template.md](workflow-template.md) | `WF-###` | `docs/workflows/` |
| [module-template.md](module-template.md) | `MOD-###` | `docs/modules/` |
| [adr-template.md](adr-template.md) | `ADR-###` | `docs/architecture/decisions/` |
| [open-question-template.md](open-question-template.md) | `OQ-###` | `docs/product/open-questions.md` |
| [sprint-template.md](sprint-template.md) | `SPRINT-##` | `docs/agile/sprints/` |

## Rules for using a template

1. **Delete nothing.** If a section does not apply, write `N/A` and why. If it applies but
   is unknown, write `TODO` or raise an `OQ-###`. A missing section is indistinguishable
   from an overlooked one.
2. **Never fill a section with plausible content to make it look complete.** An honest gap
   is a finding; invented filler is a defect that reads like a requirement.
3. Set `status` honestly — `PROPOSED` unless the product owner has actually confirmed it.
4. Take the next free ID from the relevant index and add your row there in the same change.
5. Start the change log with the row for the document's creation.

Angle-bracket placeholders `<like this>` are prompts. Remove the brackets when you fill them.

## A note on links inside templates

Relative links in these templates are written **for the destination folder**, not for
`templates/`. For example `../agile/definition-of-ready.md` in the user story template is
correct once the file sits in `docs/user-stories/`. They will appear broken while you are
reading the template itself — check them after you copy the file, not before.
