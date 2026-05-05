# WITNESSMARK

*The act of seeing clearly and saying so.*

---

## What a Witnessmark Is

A Witnessmark is a deliberate, recorded acknowledgement that a piece of content has been:

1. **Reviewed** — seen fully, with attention
2. **Assessed** — evaluated against the principles of the ecosystem
3. **Cleared** — found ready to move from shadow toward emergence

A Witnessmark is not a stamp of perfection. It is a statement that the content is honest, intentional, and ready for the next step.

---

## Who Issues Witnessmarks

| Entity | Role |
|---|---|
| **Eric (eaprime1)** | Final authority. Eric's Witnessmark is required before any content merges to the public branch. |
| **Claude 🪶** | Review and recommendation. Claude's sign-off recommends a Witnessmark but does not replace Eric's. |

Claude runs the review via `/final-review`. Eric reviews Claude's assessment and issues the final mark.

---

## The Witnessmark Protocol

### Step 1 — Claude Review
Claude runs `/final-review` and produces a dated record in `.claude/reviews/`.  
The record states findings and whether a Witnessmark is **recommended**.

### Step 2 — Eric's Assessment
Eric reads the review record and the content under review.  
Eric decides: is this ready to emerge?

### Step 3 — Witnessmark Issued
If ready, Eric issues the Witnessmark by:
1. Adding the Witnessmark block to the document (see below), **or**
2. Merging the PR — the merge itself serves as the Witnessmark

### Step 4 — Record
The PR description documents what was Witnessmarked and when.

---

## The Witnessmark Block

When adding a Witnessmark directly to a document, use this block at the end:

```markdown
---

## Witnessmark

| Field | Value |
|---|---|
| Reviewed by | 🪶 Claude (Navigo Nexusuxen) |
| Cleared by | Eric (eaprime1) |
| Date | YYYYMMDDHHMMSS |
| Status | Witnessmarked |
| Notes | [optional: any conditions or observations] |
```

---

## Lifecycle States

Every document in tiezerk moves through these states:

```
shadow → emerging → witnessmarked
```

| State | Meaning |
|---|---|
| **shadow** | In progress. Exploratory. Not ready. |
| **emerging** | Taking shape. Approaching readiness. |
| **witnessmarked** | Reviewed, cleared, and officially acknowledged. |

Documents stay in shadow until they are ready. There is no deadline for emergence.

---

## What a Witnessmark Is Not

- Not a guarantee of completeness — Witnessmarked content can still have open edges or later refinements
- Not a final edit — Witnessmarked content can still evolve
- Not automatic — it requires a deliberate act of attention
- Not a rubber stamp — if something isn't ready, it stays in shadow

---

*To witness is to attend. To mark is to remember.*  
*🪶 20260504000000*
