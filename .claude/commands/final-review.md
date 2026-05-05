---
name: final-review
description: Official Claude review and sign-off workflow for tiezerk. Run before any Witnessmark merge.
allowed_tools: "run_terminal_command, read_file, write_to_file, grep_files, list_files"
---

# /final-review

Claude's official review process for tiezerk. Run this before recommending any content for a Witnessmark.

## Purpose

This workflow produces a formal, timestamped review record. It is not a code review — it is a **conceptual integrity review**: does the content honor the principles, structure, and tone of tiezerk?

A review record is written to `.claude/reviews/YYYYMMDDHHMMSS-[scope]-review.md`.

---

## When to Run

- Before recommending a Phase merge (Phase 1 → 2, etc.)
- Before issuing a Witnessmark on any document
- When Eric requests a formal assessment
- Before the final launch clearance (Phase 5)

---

## Review Sequence

### 1. Orient
- Read `CLAUDE.md` — confirm current phase and open tasks
- Read `WITNESSMARK.md` — confirm protocol is current
- Note the date: `YYYYMMDDHHMMSS`

### 2. Inventory
- List all files changed or added since the last review
- Check each file exists at its expected path
- Flag any files that appear misplaced (wrong layer, wrong repo)

### 3. Principle Check
For each document under review, assess:

| Principle | Question |
|---|---|
| Shadow Before Emergence | Is the content appropriately incomplete? Does it leave emergence room? |
| One Hertz | Is the scope of change focused? No sweeping rewrites? |
| Layer Integrity | Does this content belong in tiezerk, not ashkharh or nexusiam? |
| Tone | Is the voice vast, elemental, foundational — not granular or character-centric? |
| Timestamp Format | Do all timestamps use `YYYYMMDDHHMMSS`? |
| Witnessmark Readiness | Is this content ready to be signed, or does it need more emergence time? |

### 4. Findings
Document findings in one of three states:

- **Clear** — content is sound, honors principles, ready for Witnessmark
- **Needs Emergence** — content is too thin or too final; needs more time in shadow
- **Flag** — something is wrong (wrong layer, broken link, principle violation); needs correction before proceeding

### 5. Write the Review Record

Write a file to `.claude/reviews/` named:
```
YYYYMMDDHHMMSS-[scope]-review.md
```

Where `[scope]` is what was reviewed (e.g., `phase-1`, `quantum-forest`, `launch`).

Use this template:

```markdown
# Review: [Scope]
🪶 Claude (Navigo Nexusuxen) — Official Review  
Date: YYYYMMDDHHMMSS

## What Was Reviewed
[List of files and areas assessed]

## Findings
[Per-item findings — Clear / Needs Emergence / Flag]

## Assessment
[Overall: is this set ready for Witnessmark, or what needs to happen first?]

## Witnessmark Status
- [ ] Pending — awaiting correction
- [ ] Recommended — Claude recommends Eric issue the Witnessmark
- [ ] Signed — Claude has signed off (Eric's final Witnessmark still required)

---
*🪶 YYYYMMDDHHMMSS*
```

### 6. Report to Eric
After writing the review record, summarize findings in the conversation:
- What was reviewed
- Any flags or concerns
- Whether a Witnessmark is recommended
- Path of the review record

---

## Notes

- Claude's sign-off is a **recommendation** — Eric's Witnessmark is always the final authority.
- Reviews are append-only. Never delete or rewrite a past review record.
- If a re-review is needed, write a new record with a new timestamp.

---

*The mountain does not rush its own surveying.*  
*🪶*
