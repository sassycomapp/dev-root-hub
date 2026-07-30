---
title: Project Inventory
description: Certified project registry for all Anvil.works projects — local paths, GitHub repos and branches, GBrain sources, and GStack artifact paths. Merged with the standalone git-repo-inventory.md (2026-07-23) as the single source of truth for repository tracking.
version: 2.5
date: 2026-07-09
updated: 2026-07-30
verified: 2026-07-30
---

## Registered Projects

### mb-3-cs
- Code repo (Local): `/mnt/c/dev/dev-mb-3-cs/mb-3-cs`
- Code repo (Anvil/GitHub): `https://github.com/sassycomapp/mb-3-cs` — branch `master`
- Code repo (GBrain): `mb-3-cs-code`
- Documentation repo (Local): `/mnt/c/dev/dev-mb-3-cs/mb-3-cs-project-library`
- Documentation repo (GitHub): `https://github.com/sassycomapp/mb-3-cs-project-library` — branch `main`
- Documentation repo (GBrain): `mb-3-cs-project-library`
- Documentation repo (GStack) WSL access: `~/.gstack/projects/sassycomapp-project-library`
- Documentation repo (GStack) Windows access: `\\wsl.localhost\Ubuntu\home\dev-p\.gstack\projects\sassycomapp-project-library`

### mb4ecom
- Code repo (Local): `/mnt/c/dev/dev-mb4ecom/mb4ecom`
- Code repo (Anvil/GitHub): `https://github.com/sassycomapp/mb4ecom` — branch `master`
- Code repo (GBrain): `mb4ecom-code`
- Documentation repo (Local): `/mnt/c/dev/dev-mb4ecom/mb4ecom-project-library`
- Documentation repo (GitHub): `https://github.com/sassycomapp/mb4ecom-project-library` — branch `master`
- Documentation repo (GBrain): `mb4ecom-project-library`
- Documentation repo (GStack) WSL access: `~/.gstack/projects/sassycomapp-mb4ecom-project-library`
- Documentation repo (GStack) Windows access: `\\wsl.localhost\Ubuntu\home\dev-p\.gstack\projects\sassycomapp-mb4ecom-project-library`

### mb5pdlf
- Code repo (Local): `/mnt/c/dev/dev-mb5pdlf/mb5pdlf`
- Code repo (Anvil/GitHub): `https://github.com/sassycomapp/mb5pdlf` — branch `master`
- Code repo (GBrain): `mb5pdlf-code`
- Documentation repo (Local): `/mnt/c/dev/dev-mb5pdlf/mb5pdlf-project-library`
- Documentation repo (GitHub): `https://github.com/sassycomapp/mb5pdlf-project-library` — branch `master`
- Documentation repo (GBrain): `mb5pdlf-project-library`
- Documentation repo (GStack) WSL access: `~/.gstack/projects/sassycomapp-mb5pdlf-project-library`
- Documentation repo (GStack) Windows access: `\\wsl.localhost\Ubuntu\home\dev-p\.gstack\projects\sassycomapp-mb5pdlf-project-library`

### dev-makepdlf
- Code repo (Local): `/mnt/c/dev/dev-makepdlf/makepdlf` (empty shell, no remote yet)
- Documentation repo (Local): `/mnt/c/dev/dev-makepdlf/makepdlf-project-library`
- Documentation repo (GitHub): `https://github.com/sassycomapp/makepdlf-project-library` — branch `main`
- Documentation repo (GBrain): `dev-makepdlf`
- Documentation repo (GStack) WSL access: `~/.gstack/projects/sassycomapp-makepdlf-project-library`
- Documentation repo (GStack) Windows access: `\\wsl.localhost\Ubuntu\home\dev-p\.gstack\projects\sassycomapp-makepdlf-project-library`
- Note: Previously docs-only single repo (dev-pdlf). Renamed 2026-07-25. Code repo directory exists but is empty — no GitHub remote assigned yet.

### project-template
- Repo (Local): `/mnt/c/dev/project-template`
- Repo (GitHub): `https://github.com/sassycomapp/project-template` — branch `master`
- GBrain (outer): not registered (path overlaps with inner source)
- Inner template (Local): `/mnt/c/dev/project-template/dev-(SLUG)/(slug)-project-library`
- Inner template (GBrain): `template-project-library`
- Note: Skeleton for new projects. The outer repo is a minimal wrapper. The inner `(slug)-project-library` is the parametrized project-library template with placeholder tokens.

### pdlf
- Local path: `/mnt/c/pdlf`
- GBrain: `pdlf`
- Note: Deployed PDLF framework tool. Not a project PDLF builds. No GitHub remote tracked here.

### project-library-global
- Local path: `/mnt/c/dev/project-library-global`
- GitHub: `https://github.com/sassycomapp/project-library-global` — branch `main`
- GBrain: `project-library-global`
- Note: Shared standards library for all projects.

### dev-root-hub
- Local path: `/mnt/c/dev/dev-root`
- GitHub: `https://github.com/sassycomapp/dev-root-hub` — branch `main`
- GBrain: `dev-root-hub`
- Note: Division-level inventory and mapping documents (docmap.md, project-inventory.md).

### projects-reference
- Local path: `/mnt/c/projects-reference`
- GitHub: `https://github.com/sassycomapp/projects-reference` — branch `main`
- GBrain: not currently tracked here
- Note: `.git` was briefly removed 2026-07-20; a new GitHub repo was created afterward and this
  is now an active repo again, tracked normally as an Active Repository.

---

## Repository Status

This section is the source of truth for the Phase 0 pre-flight git-status check and Phase 6
commit/push (SKILL.md Section 3.1) — every repository in scope falls into exactly one category
below.

### Active Repositories

| Local Path | GitHub Remote | Branch |
|---|---|---|
| `C:\dev\dev-mb-3-cs\mb-3-cs\` | `https://github.com/sassycomapp/mb-3-cs` | `master` |
| `C:\dev\dev-mb-3-cs\mb-3-cs-project-library\` | `https://github.com/sassycomapp/mb-3-cs-project-library.git` | `main` |
| `C:\dev\dev-mb4ecom\mb4ecom\` | `https://github.com/sassycomapp/mb4ecom` | `master` |
| `C:\dev\dev-mb4ecom\mb4ecom-project-library\` | `https://github.com/sassycomapp/mb4ecom-project-library.git` | `master` |
| `C:\dev\dev-mb5pdlf\mb5pdlf\` | `https://github.com/sassycomapp/mb5pdlf.git` | `master` |
| `C:\dev\dev-mb5pdlf\mb5pdlf-project-library\` | `https://github.com/sassycomapp/mb5pdlf-project-library.git` | `master` |
| `C:\dev\dev-makepdlf\makepdlf-project-library\` | `https://github.com/sassycomapp/makepdlf-project-library.git` | `main` |
| `C:\dev\dev-root\` | `https://github.com/sassycomapp/dev-root-hub.git` | `main` |
| `C:\dev\project-library-global\` | `https://github.com/sassycomapp/project-library-global.git` | `main` |
| `C:\dev\project-template\` | `https://github.com/sassycomapp/project-template.git` | `master` |
| `C:\projects-reference\` | `https://github.com/sassycomapp/projects-reference.git` | `main` |

### Inactive / No Remote

Not part of the pre-flight git-status check or Phase 6 commit/push — listed here for a complete
audit trail, not because Docs Manager acts on them.

| Local Path | Status |
|---|---|
| `C:\dev\obsolete\dev-project-template\` | Remote: `sassycomapp/project-library-dev-project-template.git` — obsolete. Also excluded from scanning entirely by the `obsolete` name-pattern rule (SKILL.md Section 1.2.4). |
| `C:\dev\project-template\dev-(SLUG)\(slug)-project-library\` (inner) | `.git` initialized 2026-07-27 — parametrized template library. No remote (by design — placeholders). |

### Installed Tools (Read-Only)

Third-party repos this system never touches — never checked for git status, never staged, never
committed. `C:\mybizz\skills\` was previously unexcluded in `SKILL.md`'s scope rules; it has now
been added to the absolute path exclusions to match `gbrain`/`gstack`, which were already
excluded via the name-pattern rule.

| Local Path | Upstream Remote | Branch |
|---|---|---|
| `C:\mybizz\gbrain\` | `https://github.com/garrytan/gbrain.git` | `master` |
| `C:\mybizz\gstack\` | `https://github.com/garrytan/gstack.git` | `main` |
| `C:\mybizz\skills\` | `https://github.com/garrytan/gstack.git` | `main` |

---

## Companion document

`docmap.md` (at `C:\dev\dev-root\docmap.md`) is the full hierarchy map for the Mybizz division.
