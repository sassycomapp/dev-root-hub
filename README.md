# dev-root — README

**This file covers `C:\dev\dev-root\` only** — the two division-map documents that give a
top-level view across all projects under `C:\dev\`. It does not cover Docs Manager or
mb-align-docs themselves; those have their own READMEs in this same folder
([[docs-manager-README|Docs Manager README]], [[mb-align-docs-README|mb-align-docs README]]).

> Note: this file was reconstructed after the original was overwritten during Docs Manager's setup.
> Verified/corrected 2026-07-27 against current state of docmap.md and project-inventory.md.

---

## What lives here

| File | What it is |
|---|---|
| `docmap.md` | The **full Mybizz division hierarchy map** — covers `C:\dev\`, `C:\mybizz\`, `C:\pdlf\`, `C:\projects-reference\` plus file placement rules |
| `projects-config-register.md` (in `C:\mybizz\config\`) | The **central config register** — one `{slug}-config.yaml` per project (paths, GitHub repos, branches, GBrain sources). Supersedes the retired `project-inventory.md`. |
| [[docs-manager-README|Docs Manager README]] | Short-form guide to Docs Manager, which keeps `docmap.md`, `projects-config-register.md`, and per-project README/AGENTS/INDEX files accurate against the real filesystem |
| [[mb-align-docs-README|mb-align-docs README]] | Short-form guide to mb-align-docs, which keeps document *content* (terminology, requirements, cross-references, identifiers) internally consistent within a project's documentation |

## How the two skills relate to this folder

- **Docs Manager** reads and corrects [[docmap|Docmap]] and `projects-config-register.md` (the per-project `{slug}-config.yaml` register) directly — they are
  part of its five tracked file types.
- **mb-align-docs** does not touch either file — its scope is document content within a project's
  `project-library`, not top-level structure maps. The two skills do not interoperate.

## If something looks wrong here

- For a structural/index problem (a project missing from the config register, `docmap.md` out
  of date) → run Docs Manager.
- For a content/reference problem inside a specific project's documentation → run mb-align-docs
  against that project.
- For anything about this file itself → this was reconstructed and may be incomplete; correct it
  directly rather than treating it as authoritative history.
