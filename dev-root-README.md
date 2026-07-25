# dev-root — README

**This file covers `C:\dev\dev-root\` only** — the two division-map documents that give a
top-level view across all projects under `C:\dev\`. It does not cover Docs Manager or
mb-align-docs themselves; those have their own READMEs in this same folder
(`docs-manager-README.md`, `mb-align-docs-README.md`).

> Note: this file is a reconstruction. The original was overwritten during Docs Manager's setup.
> Review closely and correct anything that doesn't match what was actually here before.

---

## What lives here

| File | What it is |
|---|---|
| `docmap.md` | The map of the `C:\dev\` folder structure itself — divisions, standard project layout, global vs. local folders |
| `project-inventory.md` | The list of active projects under `C:\dev\`, one row per project, kept current |
| `docs-manager-README.md` | Short-form guide to Docs Manager, which keeps `docmap.md`, `project-inventory.md`, and per-project README/AGENTS/INDEX files accurate against the real filesystem |
| `mb-align-docs-README.md` | Short-form guide to mb-align-docs, which keeps document *content* (terminology, requirements, cross-references, identifiers) internally consistent within a project's documentation |

## How the two skills relate to this folder

- **Docs Manager** reads and corrects `docmap.md` and `project-inventory.md` directly — they are
  part of its five tracked file types.
- **mb-align-docs** does not touch either file — its scope is document content within a project's
  `project-library`, not top-level structure maps. The two skills do not interoperate.

## If something looks wrong here

- For a structural/index problem (a project missing from `project-inventory.md`, `docmap.md` out
  of date) → run Docs Manager.
- For a content/reference problem inside a specific project's documentation → run mb-align-docs
  against that project.
- For anything about this file itself → this was reconstructed and may be incomplete; correct it
  directly rather than treating it as authoritative history.
