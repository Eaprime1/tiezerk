# old_tiezerk — File Rename Guide
🪶 Claude — Reference for Copilot or manual rename

Repo: `eaprime1/old_tiezerk`  
Purpose: Fix all filenames before merging content into tiezerk.  
Convention source: `frameworks/file-naming-conventions.md`

---

## Rename Mappings

Each row is one `git mv` operation. Run these in order inside the `old_tiezerk` repo.

### Issues present in this repo
- Spaces in names (breaks shell and some git clients)
- Emoji in names (encoding failures on some filesystems and CI)
- Em-dash `—` in name (non-ASCII, breaks paths)
- Double extension `.md.pdf` (tool confusion)
- Mixed/uppercase names (convention violation)
- Underscores in content files (convention: use hyphens)

---

### Rename Commands

```bash
# Run from inside the old_tiezerk repo root

git mv "Dialogue tiezerk and ashkharh.pdf" \
       "dialogue-tiezerk-and-ashkharh.pdf"

git mv "PINNACLE_REFINEMENT_WORKFLOW.md.pdf" \
       "pinnacle-refinement-workflow.pdf"

git mv "Pinnacle Refinement Template- Elevate Document Entity.pdf" \
       "pinnacle-refinement-template-elevate-document-entity.pdf"

git mv "Pinnacle Refinement Workflow Development.pdf" \
       "pinnacle-refinement-workflow-development.pdf"

git mv "tiezerk_Repository_Development_Plan.pdf" \
       "tiezerk-repository-development-plan.pdf"

git mv "♓∰🌳The irreducible thing.pdf" \
       "the-irreducible-thing.pdf"

git mv "🔐 Primoris_Observation_Workflow_v2 — BM-20260419113547.pdf" \
       "primoris-observation-workflow-v2-bm-20260419113547.pdf"
```

> ⚠️ The file `Operational Architecture for the Marrowing of Prim....pdf` has a
> truncated name in the GitHub UI. **Verify the full filename** before renaming.
> Pattern will be: `operational-architecture-marrowing-of-[full-word].pdf`

---

## Issue-by-Issue Breakdown

| Old Filename | Problems | New Filename |
|---|---|---|
| `Dialogue tiezerk and ashkharh.pdf` | spaces, uppercase | `dialogue-tiezerk-and-ashkharh.pdf` |
| `Operational Architecture for the Marrowing of Prim....pdf` | spaces, uppercase, name truncated | `operational-architecture-marrowing-of-[verify].pdf` |
| `PINNACLE_REFINEMENT_WORKFLOW.md.pdf` | all-caps, underscores, double extension | `pinnacle-refinement-workflow.pdf` |
| `Pinnacle Refinement Template- Elevate Document Entity.pdf` | spaces, uppercase, hyphen spacing | `pinnacle-refinement-template-elevate-document-entity.pdf` |
| `Pinnacle Refinement Workflow Development.pdf` | spaces, uppercase | `pinnacle-refinement-workflow-development.pdf` |
| `tiezerk_Repository_Development_Plan.pdf` | underscores, mixed case | `tiezerk-repository-development-plan.pdf` |
| `♓∰🌳The irreducible thing.pdf` | emoji, spaces, uppercase | `the-irreducible-thing.pdf` |
| `🔐 Primoris_Observation_Workflow_v2 — BM-20260419113547.pdf` | emoji, space, underscores, em-dash, mixed case | `primoris-observation-workflow-v2-bm-20260419113547.pdf` |

---

## After Renaming

Once all renames are done:

```bash
git commit -m "fix: filenames — apply kebab-case convention to all PDFs"
git push origin main
```

Then the files can be moved into tiezerk under `documents/` or the appropriate
environment folder, depending on their content.

---

## Copilot Instructions (paste into Copilot session)

> I need to rename files in the `eaprime1/old_tiezerk` repository to follow
> kebab-case naming conventions. Please run the following `git mv` commands and
> commit the result with message `fix: filenames — apply kebab-case convention to all PDFs`.
>
> [paste the rename commands block above]
>
> Do not change file contents — only rename. Verify the full name of the truncated
> `Operational Architecture for the Marrowing of Prim....pdf` file before renaming it.

---

*🪶 20260505*
