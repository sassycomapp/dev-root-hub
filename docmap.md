# Mybizz Division — Docmap

**Purpose:** Single canonical navigation map for the Mybizz division — where every folder lives, what it is for, and where new files should go. Agents read this to understand the territory.

**Date:** 2026-07-20

**Companion:** `project-inventory.md` (same folder) — project-level paths, GitHub repos, GBrain sources, GStack artifact paths.

---

## 1. Division Root — `C:\mybizz\`

```
C:\mybizz\
├── archive/                    ← Long-term reference store (not backup, not WIP)
│   ├── Anvil_Methods/          ← Original Anvil specifications
│   ├── Model Assessments/      ← Historical model confidence reports
│   ├── artifact-saving-issue/  ← Resolved GStack investigation (11 files + resolution report)
│   ├── ci-based-checks-format/ ← Archived check specs
│   ├── local-testing-example/  ← Archived testing example
│   ├── mybizz-core-methods/    ← Archived ADRs + methods
│   └── prompts-example/        ← Archived prompt examples
├── backup-mybizz/              ← BACKUP ONLY. Agents may read (with caution) but never edit or delete.
├── Desktop/                    ← Active working desktop environment
│   ├── Notebooks/              ← OneNote notebooks
│   ├── Notebooks-look for good/ ← Additional notebooks
│   ├── pc-mapping/             ← PC hierarchy diagrams (HTML)
│   └── wip/                    ← Personal daily scratchpad (contains todo.txt)
├── gbrain/                     ← Installed tool (not user-managed)
├── gstack/                     ← Installed tool (not user-managed)
├── logs/                       ← System and tool logs
│   ├── docs-manager/           ← docs-manager skill run logs
│   └── gbrain-logs/            ← GBrain sync per-source logs
├── Mgt/                        ← Business documents ONLY (financial, planning, management)
│   ├── Davids Management .xlsx
│   ├── namecheap-order-196053207.pdf
│   └── obsolete/               ← Mgt-level obsolete items. Developer purges only.
├── scripts/                    ← Global utility scripts for this PC
└── skills/                     ← Installed tool (not user-managed)
```

---

## 2. Development Hub — `C:\dev\`

Where projects are developed. Active projects have the `dev-` prefix. Folders without `dev-`
prefix are support folders, including `dev-root/` which holds division-level inventory and
mapping documents.

```
C:\dev\
├── dev-mb-3-cs/                ← ACTIVE PROJECT (mb-3-cs)
│   ├── mb-3-cs/                ← Code repo
│   ├── project-library/        ← Docs repo
│   └── wip/                    ← Project WIP (contains todo.md)
├── dev-mb4ecom/                ← ACTIVE PROJECT (mb4ecom)
│   ├── mb4ecom/                ← Code repo
│   ├── mb4ecom-project-library/ ← Docs repo
│   └── wip/                    ← Project WIP (contains todo.md)
├── dev-mb5pdlf/                ← ACTIVE PROJECT (mb5pdlf)
│   ├── mb5pdlf/                ← Code repo
│   ├── mb5pdlf-project-library/ ← Docs repo
│   └── wip/                    ← Project WIP (contains todo.md)
├── dev-pdlf/                   ← ACTIVE PROJECT (PDLF — docs-only, no separate code repo)
│   ├── pdlf/                   ← Main project docs
│   ├── wip/                    ← Project WIP (contains todo.md)
│   └── (many subfolders — see dev-pdlf/docs-local/docmap.md)
├── docmap.md                   ← THIS FILE — full division hierarchy map
├── dev-root/                    ← Division-level inventory and mapping docs
│   ├── docmap.md                ← Full division hierarchy map
│   └── project-inventory.md     ← Project registry (paths, repos, GBrain, GStack)
├── obsolete/                   ← Dev-level obsolete. Developer purges only.
├── project-library-global/     ← Shared standards and reference for all projects
│   ├── adr-global/             ← Global architectural decision records
│   ├── checklists-global/      ← Global checklists
│   ├── docs-standard-global/   ← Standard doc templates
│   ├── guides/                 ← Global how-to guides
│   ├── policy-global/          ← Global policies
│   ├── specifications-global/  ← Global specifications
│   ├── standard-operating-procedures-global/ ← Global SOPs
│   └── templates-global/       ← Global templates
└── project-template/           ← Skeleton for new projects (import into new dev-* folder)
```

---

## 3. PDLF Framework — `C:\pdlf\`

The deployed PDLF tool. Not a project — it's the product. References `project-library-global` via absolute path.

```
C:\pdlf\
├── .scratch/
├── docs/
├── registry/
└── skill/
```

---

## 4. Reference Library — `C:\projects-reference\`

Reference documents, custom skills, and completed projects. NOT a git repo (`.git` removed 2026-07-20).

```
C:\projects-reference\
├── custom-skills-store/        ← Custom skills (built or planned)
├── deployed-projects/          ← Completed project storage (currently empty)
└── workspace-reference/        ← How-to references for tools, apps, custom methods
    ├── Anvil-reference/
    ├── cloudflare-reference/
    ├── gbrain-reference/
    ├── gstack-reference/
    ├── hotkeys- reference/
    ├── markdown reference/
    ├── matt-skills reference/
    ├── model selection reference/
    ├── namecheap reference/
    ├── opencode reference/
    ├── system config reference/
    └── workflow reference/
        ├── daily-ops.md        ← Daily operations quick reference
        └── session-opening-prompt.md
```

---

## 5. Excluded from mapping

- `C:\_Data-not mybizz\` — personal interests, not Mybizz, not managed
- `C:\_ BIG BACKUP\` — read-only backup archive, never edited

---

## 6. File Placement Rules

### Where do new files go?

| File type | Destination |
|---|---|
| Project code | `C:\dev\dev-{project}\{slug}\` |
| Project docs | `C:\dev\dev-{project}\{slug}-project-library\` |
| Project WIP / todo | `C:\dev\dev-{project}\wip\todo.md` |
| Global standards (ADRs, policies, specs, SOPs) | `C:\dev\project-library-global\{category}\` |
| Global how-to guides | `C:\dev\project-library-global\guides\` |
| Business documents (financial, planning) | `C:\mybizz\Mgt\` |
| Daily working files / scratchpad | `C:\mybizz\Desktop\` or `C:\mybizz\Desktop\wip\` |
| Completed work for long-term reference | `C:\mybizz\archive\` |
| Temporary trash during a session | `C:\dev\obsolete\` (dev items) or `C:\mybizz\Mgt\obsolete\` (mgt items) |
| Custom skills | `C:\projects-reference\custom-skills-store\` |
| Reference docs (how-to, tool docs) | `C:\projects-reference\workspace-reference\` |
| Completed projects | `C:\projects-reference\deployed-projects\` |
| Backups | `C:\mybizz\backup-mybizz\` (new folder per backup exercise) |
| System and tool logs | `C:\mybizz\logs\{tool}\` (e.g., `C:\mybizz\logs\gbrain-logs\`) |

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

## 7. Tool Installations (not user-managed)

| Tool | Location | Purpose |
|---|---|---|
| GStack | `C:\mybizz\gstack\` | Skill framework, binaries, browse daemon |
| GBrain | `C:\mybizz\gbrain\` | Knowledge base, search, embeddings |
| Skills | `C:\mybizz\skills\` | Skill definitions (~70 entries) |
| GStack runtime (OpenCode) | `~/.config/opencode/skills/gstack/` | Runtime root with bin/, browse/dist/, design/dist/ |

---

## 8. Key Companion Documents

| Document | Location | Purpose |
|---|---|---|---|
| `docmap.md` | `C:\dev\dev-root\docmap.md` | THIS FILE — full division hierarchy map |
| `project-inventory.md` | `C:\dev\dev-root\project-inventory.md` | Project registry (paths, repos, GBrain, GStack) |
| `scaffold-system.html` | `C:\mybizz\Desktop\pc-mapping\scaffold-system.html` | Visual hierarchy diagram of the division |
| `README.md` | `C:\mybizz\README.md` | Division workspace overview |
| Global AGENTS.md | `~/.config/opencode/AGENTS.md` | Global agent behavior rules |
| Project AGENTS.md | `C:\dev\dev-{project}\AGENTS.md` | Per-project agent rules |
| daily-ops.md | `C:\projects-reference\workspace-reference\workflow reference\daily-ops.md` | Daily operations quick reference |
| dev-pdlf docmap | `C:\dev\dev-pdlf\docs-local\docmap.md` | PDLF project document map |
| docs-manager skill | `~/.config/opencode/skills/docs-manager/SKILL.md` | Skill definition — document inventory, update rules, workflow |
| | Windows: `\\wsl.localhost\Ubuntu\home\dev-p\.config\opencode\skills\docs-manager\SKILL.md` | |
| docs-manager agent | `~/.config/opencode/agents/docs-manager.md` | Sub-agent — Phase 1 scan prompts, read-only |
| | Windows: `\\wsl.localhost\Ubuntu\home\dev-p\.config\opencode\agents\docs-manager.md` | |
