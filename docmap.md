---
title: "docmap"
doc-id: "mb-738efe3e"
updated: "2026-10-10"
---
# Mybizz Division — Docmap

**Purpose:** Single canonical navigation map for the Mybizz division — where every folder lives, what it is for, and where new files should go. Agents read this to understand the territory.

**Date:** 2026-07-23
**Verified:** 2026-10-10

**Kept current:** `build-docmap.py` rebuilds the folder trees (`python3 /mnt/c/mybizz/scripts/build-docmap.py --write`); see [[[mybizz-os-docs:operating-procedures/daily-ops|Daily Ops]]](C:/mybizz/mybizz-os-docs/operating-procedures/daily-ops.md).

---

## 1. Division Root — `C:\mybizz\`

```
C:\mybizz\
├── archive/                      ← Long-term reference store (out of scope; holds obsolete-moved records)
├── archify/                      ← archify source clone (scaffold exception)
├── anvil-agent-references/       ← Anvil skills source clone (scaffold exception)
├── gstack/                       ← GStack source clone (scaffold exception)
├── logs/                         ← System and tool logs (scaffold exception)
│   ├── mb-sysdoc-creator/        ← sysdoc-creator run logs + learnings
│   ├── mb-submit-memory/         ← submit-memory logs
│   ├── github-logs/              ← Commit/push reports + git-status snapshots
│   ├── gbrain-logs/              ← GBrain sync logs
│   ├── cupcake/                  ← (new — add a description)
│   └── sunday-backup/            ← (new — add a description)
├── matt-pocock-skills-source/    ← Matt Pocock skills source clone (scaffold exception)
├── memory-audit-reports/         ← Memory audit reports (IN SCOPE)
├── mybizz-config-docs/           ← Canonical tool/component doc suites (IN SCOPE)
├── mybizz-os-docs/               ← System describer/explainer documents (IN SCOPE)
├── scripts/                      ← Global utility scripts (scaffold exception)
├── README.md                     ← Division workspace overview
├── mb-archify-scope/             ← (new — add a description)
├── mb-close-out/                 ← (new — add a description)
├── mb-compile-rules/             ← (new — add a description)
├── mb-memory-system-diagnostic/  ← (new — add a description)
├── mb-project-docs/              ← (new — add a description)
├── mb-sentinel-review/           ← (new — add a description)
├── mb-submit-memory/             ← (new — add a description)
├── mb-sysdoc-creator/            ← (new — add a description)
└── minimax-skills/               ← (new — add a description)
```

### Division management data — `C:\data-mybizz-mgt\` (IN SCOPE, separate root)

The desktop-level operating documents of the Mybizz/PDLF operating system, plus the
developer's budget, model, and prompt working files. Not an Anvil project and not a code
repository. Separate from `C:\pdlf\` — the two must never be merged.

```
C:\data-mybizz-mgt\
├── desktop/                ← Operating documents (daily-ops, master-task-list, deferred-and-unresolved-matters)
├── WIP/                    ← Working files
├── archive/                ← Archived material
├── temp/                   ← Temporary files
├── README.md
├── assets/                 ← (new — add a description)
├── Models/                 ← (new — add a description)
├── obsolete/               ← (new — add a description)
└── Tools and apps/         ← (new — add a description)
```

Note: the folder was renamed from `C:\_data-mybizz-mgt` on 2026-09-14 (underscore dropped).

---

## 2. Development Hub — `C:\dev\`

Where projects are developed. Active projects have the `dev-` prefix. Folders without `dev-`
prefix are support folders, including `dev-root/` which holds division-level inventory and
mapping documents.

**A project's real development status — active or dormant — is defined in that project's own
`{slug}-config.yaml`, not by anything in this docmap.** The labels below describe what
physically exists on disk, nothing more.

```
C:\dev\
├── dev-mb-3-cs\                               ← PROJECT (mb-3-cs) — see mb-3-cs-config.yaml for status
│   ├── mb-3-cs/                               ← Code repo
│   ├── mb-3-cs-project-library/               ← Docs repo
│   ├── wip/                                   ← Project WIP (contains todo.md)
│   └── README.md                              ← (new — add a description)
├── dev-mb4ecom\                               ← PROJECT (mb4ecom) — see mb4ecom-config.yaml for status
│   ├── mb4ecom/                               ← Code repo
│   ├── mb4ecom-project-library/               ← Docs repo
│   ├── wip/                                   ← Project WIP (contains todo.md)
│   ├── mb4ecom-config.yaml                    ← (new — add a description)
│   └── README.md                              ← (new — add a description)
├── dev-mb5pdlf\                               ← PROJECT (mb5pdlf) — see mb5pdlf-config.yaml for status
│   ├── mb5pdlf/                               ← Code repo
│   ├── mb5pdlf-project-library/               ← Docs repo
│   ├── wip/                                   ← Project WIP (contains todo.md)
│   ├── mb5pdlf-config.yaml                    ← (new — add a description)
│   └── README.md                              ← (new — add a description)
├── dev-root\                                  ← Division-level inventory and mapping docs
│   ├── docmap.md                              ← Full division hierarchy map
│   └── README.md                              ← (new — add a description)
├── obsolete\                                  ← Dev-level obsolete. Developer purges only.
├── project-library-global\                    ← Shared standards and reference for all projects
│   ├── adr-global/                            ← Global architectural decision records
│   ├── docs-standard-global/                  ← Standard doc templates
│   ├── guides-global/                         ← Global how-to guides
│   ├── policy-global/                         ← Global policies
│   ├── specifications-global/                 ← Global specifications
│   ├── standard-operating-procedures-global/  ← Global SOPs
│   ├── templates-global/                      ← Global templates
│   ├── anvil-docs/                            ← (new — add a description)
│   ├── obsolete/                              ← (new — add a description)
│   ├── README.md                              ← (new — add a description)
│   ├── rules-cupcake-global/                  ← (new — add a description)
│   ├── security-global/                       ← (new — add a description)
│   ├── sessions/                              ← (new — add a description)
│   └── project-library-global-scaffold.xlsx   ← (new — add a description)
└── project-template\                          ← Skeleton for new projects (import into new dev-* folder)
```

---

## 3. PDLF Framework — `C:\pdlf\` — **In Active Development**

**Current status: in active development.** The home of the PDLF system — the Project
Development Lifecycle Framework — scaffolded live 2026-09-11 (library, app-factory
machinery, output area, GitHub repo re-established). It is a separate repository from
`C:\data-mybizz-mgt\`; do not merge the two. All PDLF work happens here.

```
C:\pdlf\
├── pdlf-library/           ← Canonical technical documentation (ADRs, specs, policies, explainers, register)
├── app-factory/            ← Machinery — one module per pipeline step (placeholders today, populated step by step)
├── output/                 ← Producer-routed artifact safety net (transient)
├── AGENTS.md               ← Standing rules for this location
├── README.md
├── obsolete/               ← (new — add a description)
├── desktop/                ← (new — add a description)
└── stepwise/               ← (new — add a description)
```

---

## 4. (Removed — see note)

`C:\projects-reference\` is confirmed personal content, outside the Mybizz/PDLF operating
system entirely, kept only for reasons unrelated to this work. Not part of this docmap, not
part of any project, and does not get a `{slug}-config.yaml` or `README.md` under the config-YAML
rule in Section 6 — that rule applies to system folders, not personal ones.

---

## 5. Excluded from mapping

- `C:\_data-not mybizz\` — personal interests, not Mybizz, not managed (outside the scaffold scope)

---

## 6. File Placement Rules

### Where do new files go?

| File type | Destination |
|---|---|
| Project code | `C:\dev\dev-{project}\{slug}\` |
| Project docs | `C:\dev\dev-{project}\{slug}-project-library\` |
| Project config (single source of truth) | `C:\dev\dev-{project}\{slug}-config.yaml` |
| Project explainer | `C:\dev\dev-{project}\README.md` |
| Project WIP / todo | `C:\dev\dev-{project}\wip\todo.md` |
| Global standards (ADRs, policies, specs, SOPs) | `C:\dev\project-library-global\{category}\` |
| Global how-to guides | `C:\dev\project-library-global\guides-global\` |
| Tool config reference documents | `C:\mybizz\mybizz-config-docs\{tool}\` |
| System describer/explainer documents | `C:\mybizz\mybizz-os-docs\` |
| Business documents (financial, planning) | `C:\mybizz\Mgt\` (convention — folder not currently present; create on first need) |
| Daily working files / scratchpad | `C:\data-mybizz-mgt\desktop\` |
| Completed work for long-term reference | `C:\mybizz\archive\` |
| Temporary trash during a session | `C:\dev\obsolete\` (dev items) or `C:\mybizz\Mgt\obsolete\` (mgt items — folder created on first need) |
| Custom skills (mb-* family) | `~/.config/opencode/skills/` (WSL) — browsable runtime surface |
| Backups | WSL-originated: `C:\backup-wsl\{script}\<timestamp>\`. General: `C:\backup-general\`. Backup folders are non-entities: not tracked, not registered, never scanned. |
| System and tool logs | `C:\mybizz\logs\{tool}\` (e.g., `C:\mybizz\logs\gbrain-logs\`, `C:\mybizz\logs\github-logs\`) |

### The config-YAML rule

**Any folder with real configuration needs exactly two files: `{slug}-config.yaml` and
`README.md`.** This applies whether or not the folder is a full project (code + docs repo
pair) — a folder with a real git repo and real config, but no code/docs repo pair (e.g.
`project-library-global`, `dev-root-hub`), still needs both. No exceptions — a folder either
has real config and gets both files, or it has none and gets neither.

### archive vs obsolete

| | archive | obsolete |
|---|---|---|
| **Purpose** | Long-term reference store | Temporary trash during a session |
| **Permanence** | Permanent | Purged by developer when session ends and work is stable |
| **Who decides** | Developer | Developer |
| **Location** | `C:\mybizz\archive\` | `C:\dev\obsolete\` or `C:\mybizz\Mgt\obsolete\` |

### Per-project WIP convention

Every active project has `C:\dev\dev-{project}\wip\todo.md`. The todo.md is project-specific — no central todo across all projects. WIP folders are outside both the code repo and the docs repo.

---

## 7. Tool Installations

| Tool | Location | Purpose | Config reference |
|---|---|---|---|
| GStack | `C:\mybizz\gstack\` | Skill framework, binaries, browse daemon | `C:\mybizz\mybizz-config-docs\gstack\` |
| GStack runtime (OpenCode) | `~/.config/opencode/skills/gstack/` | Runtime root — `bin` symlinks back to the source clone above | |
| GBrain (source clone) | `C:\mybizz\gbrain\` | GBrain's own source repository | `C:\mybizz\mybizz-config-docs\gbrain\` |
| GBrain (live install) | `/home/dev-p/gbrain/src/` (WSL) | The actual running CLI — separate from the source clone above | |
| Matt Pocock skills (source) | `C:\mybizz\matt-pocock-skills-source\` | Authoritative clone — all 35 skills symlinked from here | `C:\mybizz\mybizz-config-docs\matt-pocock-skills\` |
| Matt Pocock skills (live) | `~/.agents/skills/` (WSL) | Symlinks into the source clone above | |
| Anvil skills (source) | `C:\mybizz\anvil-agent-references\` | Official Anvil-maintained skill repo | `C:\mybizz\mybizz-config-docs\anvil-agent-references\` |
| Magdoub Claude Wireframe (source) | `~/.claude/skills/wireframe/` (WSL) | Real git clone, official install location | `C:\mybizz\mybizz-config-docs\magdoub-wireframe\` |
| Graphify | `/home/dev-p/.local/bin/graphify` (WSL, via pip) | Code/document knowledge-graph builder | `C:\mybizz\mybizz-config-docs\graphify\` |
| PostgreSQL (GBrain's instance) | WSL-native, port 5432 | GBrain's database — separate from PDLF's own ledger instance | `C:\mybizz\mybizz-config-docs\postgresql\` |

**Retired:** `C:\mybizz\skills\` no longer exists — confirmed a stale, disconnected duplicate of the GStack source clone, one version behind, removed. Do not reference this path; use `C:\mybizz\gstack\` directly. (The former `skills-collective\` hub is retired — the runtime skill surface is `~/.config/opencode/skills/`.)

---

## 8. Key Companion Documents

| Document | Location | Purpose |
|---|---|---|
| `docmap.md` | `C:\dev\dev-root\docmap.md` | THIS FILE — full division hierarchy map |
| Per-project config | `C:\dev\dev-{project}\{slug}-config.yaml` | Single source of truth for that project's configuration — see Section 6 |
| Per-project explainer | `C:\dev\dev-{project}\README.md` | Narrative context for that project |
| `README.md` | `C:\mybizz\README.md` | Division workspace overview |
| Global `AGENTS.md` | `~/.config/opencode/AGENTS.md` | Global agent behavior rules — authoritative, live |
| Project `AGENTS.md`/`agents.md` | **Varies per project — see that project's `{slug}-config.yaml`.** No single fixed path pattern exists: some projects have it in the docs repo only, `mb-3-cs` has it in both repos (lowercase `agents.md` in the code repo specifically), some projects have none yet. Do not assume a pattern — check the YAML. |
| `daily-ops.md` | `C:\data-mybizz-mgt\desktop\daily-ops.md` | Daily operations quick reference |
| [[[data-mybizz-mgt:desktop/master-task-list\|Master Task List]]](C:/data-mybizz-mgt/desktop/master-task-list.md) | `C:\data-mybizz-mgt\desktop\master-task-list.md` | Current active task list |
| [[[mybizz-os-docs:os-reference-docs/mybizz-scope-list\|Mybizz Scope List]]](C:/mybizz/mybizz-os-docs/os-reference-docs/mybizz-scope-list.md) | `C:\mybizz\mybizz-os-docs\os-reference-docs\mybizz-scope-list.md` | Scope scaffold |
| [[[mybizz-os-docs:os-reference-docs/repo-organization\|Repo Organization]]](C:/mybizz/mybizz-os-docs/os-reference-docs/repo-organization.md) | `C:\mybizz\mybizz-os-docs\os-reference-docs\repo-organization.md` | GBrain sources / GitHub repos / local paths correlation table |

**Retired:** `scaffold-system.html` — archived to `C:\mybizz\archive\` as a historical record, no longer actively maintained. `session-opening-prompt.md` — confirmed empty, deleted; its purpose is tracked as [[[data-mybizz-mgt:desktop/master-task-list|Master Task List]]](C:/data-mybizz-mgt/desktop/master-task-list.md) Section 5 instead. `C:\dev\AGENTS-global-standard-reference.md` — its real content (hard rules, definitions, certainty levels, language restrictions, prescribed standards) has been fully merged into the live global `AGENTS.md`; the file itself is superseded. `C:\dev\dev-root\project-inventory.md` — deleted 2026-08-13; every real fact it held now lives in one of the 9 project `{slug}-config.yaml` files, or was confirmed genuinely obsolete. `C:\mybizz\config\workspace-docmap.md` — deleted 2026-08-13, substantially stale (dated 2026-07-08); its two genuinely useful, not-yet-captured details (GStack's per-project subdirectory structure, standard per-project artifact directories) were preserved in [[[mybizz-config-docs:gstack/gstack-reference]]](C:/mybizz/mybizz-config-docs/gstack/gstack-reference.md) before removal.

## Old-material pointers (added 2026-09-20, developer instruction)

Material referenced by this document but not present in the current corpus, with developer-provided locations:
- AGENTS-global-standard-reference.md — superseded (content merged into the live global AGENTS.md); backup snapshot: /mnt/c/backup-daily/2026-09-16/dev/AGENTS-global-standard-reference.md
- workspace-docmap.md — deleted 2026-08-13 (stale); backup snapshot: /mnt/c/backup-daily/2026-09-16/mybizz/archive/workspace-docmap.md
