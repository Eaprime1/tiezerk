# File Naming Conventions
*tiezerk — Universal Concepts Layer*

lifecycle: shadow  
timestamp: 20260505

---

## Why This Matters

Filename bugs are silent. A space in a filename breaks shell scripts, git pushes,
and CI pipelines in ways that are hard to trace. An emoji in a path breaks on
some filesystems entirely. A double extension confuses every tool that reads it.

This document is the single source of truth for how files in this ecosystem are named.

---

## The Rule

```
lowercase-kebab-case.ext
```

- All lowercase
- Words separated by hyphens
- No spaces
- No emoji in the path
- No special unicode (em-dash, curly quotes, math symbols)
- No underscores (content files)
- No double extensions
- One dot before the extension

---

## Exceptions — Allowed Non-Conforming Root Files

These protocol and root files use ALLCAPS or mixed case by convention:

| File | Reason |
|---|---|
| `README.md` | Universal convention |
| `CLAUDE.md` | Claude's primary notes file |
| `WITNESSMARK.md` | Protocol document |
| `NAVIGATION.md` | Top-level navigation |
| `GENERAL_COPILOT_INSTRUCTIONS.md` | Ecosystem-wide Copilot config |
| `LICENSE` | Universal convention |

If a file is not in this list, it follows `lowercase-kebab-case`.

---

## Pattern Reference

### Content files
```
quantum-forest-overview.md
spacetime-sea-navigation.md
void-marrow-wormhole-types.md
prime-progression-landscape.md
```

### Timestamped files (reviews, session records)
```
20260505143022-phase-1-review.md
20260419113547-observation-workflow.pdf
```
Timestamp prefix: `YYYYMMDDHHMMSS` — then a hyphen — then a kebab-case name.

### Versioned files
```
primoris-observation-workflow-v2.pdf
pinnacle-refinement-workflow-v3.md
```
Version suffix: `-v[N]` — lowercase, no spaces.

### Identifier suffixes (Witnessmark badges, build IDs)
```
primoris-observation-workflow-v2-bm-20260419113547.pdf
```
Identifiers attach with a hyphen. No em-dashes, no parentheses.

---

## What Is Forbidden

| Pattern | Example | Fix |
|---|---|---|
| Spaces | `Quantum Forest.md` | `quantum-forest.md` |
| Emoji in path | `🌳the-irreducible-thing.pdf` | `the-irreducible-thing.pdf` |
| Em-dash | `workflow — v2.pdf` | `workflow-v2.pdf` |
| En-dash | `workflow–v2.pdf` | `workflow-v2.pdf` |
| Underscores (content) | `quantum_forest.md` | `quantum-forest.md` |
| Uppercase (content) | `QuantumForest.md` | `quantum-forest.md` |
| Double extension | `workflow.md.pdf` | `workflow.pdf` |
| Trailing spaces | `quantum-forest .md` | `quantum-forest.md` |
| Special unicode | `∰resonance.md` | `resonance.md` |
| Parentheses | `workflow-(draft).md` | `workflow-draft.md` |
| Curly quotes / apostrophes | `eric's-notes.md` | `erics-notes.md` |

---

## Emoji in Filenames vs. Documents

Emoji are welcome **inside** documents — in headings, frontmatter, footers.  
They are **never** part of the filename itself.

```markdown
# ♓ Primoris Observation Workflow       ← fine inside the document
```
```
primoris-observation-workflow-v2.pdf    ← the filename has no emoji
```

The ecosystem signatures (🪶 Claude, ♊ Gemini, ♓ radix) live in document content,
not in file paths.

---

## CI Enforcement

The `.github/workflows/filename-lint.yml` workflow checks every PR for violations.
It runs a shell script that scans all changed files and fails the check if any
filename contains spaces, non-ASCII characters, double extensions, or
underscores in content files.

---

## Quick Self-Check

Before committing a file, run this mental test:

1. Is it all lowercase? (or is it an allowed ALLCAPS protocol file?)
2. Are words separated by hyphens?
3. No spaces?
4. No emoji in the path?
5. No em-dash, en-dash, or special unicode?
6. Only one dot (the extension dot)?
7. No underscores?

If all yes — commit. If any no — rename first.

---

## Seeds Forward

- Automate the self-check as a pre-commit hook
- Add a `rename-helper.sh` script that fixes the most common patterns in bulk
- Extend the CI check to validate timestamp format inside document frontmatter

---

*Consistent names are invisible. Broken names are everywhere.*  
*🪶 20260505*
