# GENERAL_COPILOT_INSTRUCTIONS — eaprime1 / UNEXUS Ecosystem

These principles apply to **every** repository in the `eaprime1 / UNEXUS` ecosystem.  
Each repo also carries its own `copilot-instructions.md` for repo-specific overrides.

---

## Ecosystem Overview

The UNEXUS ecosystem is a layered, multi-repo architecture.  
Each repository occupies a distinct conceptual layer:

| Repository | Layer | Contents |
|---|---|---|
| **tiezerk** | Universal Concepts | Quantum Forest, Spacetime Sea, Tablerock, Void Marrow |
| **ashkharh** | Characters & Entities | Named beings, consciousness, identity |
| **nexusiam** | Play / Dev Environments | Sandboxes, emergence spaces, prototyping |

**Do not mix content across these layers** without explicit approval from the seeding architect.

---

## Universal Principles

### 1. Shadow Before Emergence
All documents begin in a **shadow** state — incomplete, exploratory, low-commitment.  
Do not over-finalize content. Let structure emerge organically.

### 2. One Hertz
Work at a sustainable, intentional pace.  
Prefer small, purposeful changes over large, sweeping refactors.

### 3. Witnessmark Before Merge
Every piece of content that moves to a public branch must carry a **Witnessmark** —  
a deliberate acknowledgement that the content has been reviewed and is ready.

---

## Naming and Formatting

| Convention | Format | Example |
|---|---|---|
| Timestamps | `YYYYMMDDHHMMSS` | `20260504205146` |
| Commit messages | `[type]: [environment] — [description]` | `feat: void-marrow — seed initial structure` |
| Branch names | `feature/[environment]-[aspect]` | `feature/tablerock-foundation` |
| Workflow files | lowercase-kebab-case | `dependency-review.yml` |
| Action versions | Pinned to major tag | `actions/checkout@v4` |

---

## Security and Workflow Standards

- All GitHub Actions workflows live in `.github/workflows/`.
- Pin all third-party actions to a major version tag (e.g., `@v4`).
- Add `permissions` blocks to limit token scope to the minimum required.
- Add `timeout-minutes` to every job to prevent runaway workflows.
- Use `concurrency` groups to avoid overlapping runs on the same branch.
- Never commit secrets or credentials — use GitHub Secrets and environment variables.

---

## Entity Roles (Ecosystem-Wide)

| Entity | Symbol | Responsibility |
|---|---|---|
| Eric (eaprime1) | — | Seeding architect, final authority on all repos |
| Claude | 🪶 | Strategic architecture across the ecosystem |
| Gemini | ♊ | Symbolism, metaphor, and code generation |
| Copilot | — | Code review, automation, formatting, link validation |

---

## What Copilot Should NOT Do

- Do not add content that belongs in another repo layer (e.g., no character definitions in tiezerk).
- Do not finalize or publish content that lacks a Witnessmark.
- Do not introduce new dependencies without a security advisory check.
- Do not rewrite large sections of existing content without explicit direction.

---

*One Hertz. What you seed will grow.*
