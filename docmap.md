# Mybizz Division — Docmap

**Purpose:** Single canonical navigation map for the Mybizz division — where every folder lives, what it is for, and where new files should go. Agents read this to understand the territory.

**Date:** 2026-07-23
**Verified:** 2026-08-12

**Companion:** `projects-config-register.md` (`C:\mybizz\config\`) — register of every project's `{slug}-config.yaml`. See Section 8.

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
├── backups-general/            ← General backup destination. Agents may read (with caution) but never edit or delete.
├── backup-wsl/                 ← WSL-originated script backups (OpenCode DB cleanup, session prune)
├── config/                     ← Config reference documents, one folder per tool
│   ├── opencode/
│   ├── gstack/
│   ├── gbrain/
│   ├── postgresql/
│   ├── matt-skills/
│   ├── anvil-skills/
│   ├── magdoub-wireframe/
│   ├── graphify/
│   ├── README.md               ← Explains this folder's structure and governing principles
│   └── projects-config-register.md  ← Register of every project's {slug}-config.yaml
├── WIP/                        ← Active work-in-progress
│   ├── desktop/                 ← Personal desktop workspace — daily-ops.md, master-task-list.md, mybizz-todo.md live here
│   ├── Pending/                 ← Deferred sub-project design specs
│   └── review-for-mybizz-(new-import)/ ← Imported reference content under review
├── gbrain/                     ← GBrain source clone (not the live install — see Section 7)
├── gstack/                     ← GStack source clone (installed tool)
├── skills-collective/          ← Browsable symlink hub — one folder per skill set, each pointing at its real source
│   ├── matt-pocock-skills/
│   ├── anvil-skills/
│   ├── gstack-skills/
│   └── magdoub-claude-wireframe-skill/
├── logs/                       ← System and tool logs
│   ├── docs-manager/           ← docs-manager skill run logs
│   │   ├── Learnings/          ← docs-manager institutional memory, one file per learning
│   │   ├── in-progress/        ← live record of the currently-active run only
│   │   ├── last-completed-run/ ← single slot, full record of the most recent completed run
│   │   └── abandoned-runs/     ← discarded incomplete runs, never deleted
│   ├── github-logs/            ← Commit/push reports and closing git-status snapshots
│   └── gbrain-logs/            ← GBrain sync per-source logs
├── Mgt/                        ← Business documents ONLY (financial, planning, management)
│   ├── Davids Management .xlsx
│   ├── namecheap-order-196053207.pdf
│   └── obsolete/               ← Mgt-level obsolete items. Developer purges only.
├── scripts/                    ← Global utility scripts for this PC
├── mybizz-os/                  ← System describer/explainer documents (narrative, not config reference)
├── matt-skills-teach/           ← Matt Pocock teach skill output
└── anvil-agent-references/     ← Anvil skills source clone (installed tool)
```

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
├── dev-mb-3-cs\                ← PROJECT (mb-3-cs) — see mb-3-cs-config.yaml for status
│   ├── mb-3-cs/                ← Code repo
│   ├── mb-3-cs-project-library/        ← Docs repo
│   └── wip/                    ← Project WIP (contains todo.md)
├── dev-mb4ecom\                ← PROJECT (mb4ecom) — see mb4ecom-config.yaml for status
│   ├── mb4ecom/                ← Code repo
│   ├── mb4ecom-project-library/ ← Docs repo
│   └── wip/                    ← Project WIP (contains todo.md)
├── dev-mb5pdlf\                ← PROJECT (mb5pdlf) — see mb5pdlf-config.yaml for status
│   ├── mb5pdlf/                ← Code repo
│   ├── mb5pdlf-project-library/ ← Docs repo
│   └── wip/                    ← Project WIP (contains todo.md)
├── dev-makepdlf\               ← PROJECT (PDLF framework development) — see makepdlf-config.yaml
│   ├── makepdlf-project-library/ ← Docs repo
│   ├── makepdlf/               ← Code repo (empty shell, no remote yet)
│   ├── wip/                    ← Project WIP (contains todo.md)
│   └── (many subfolders — see dev-makepdlf/makepdlf-project-library/docs-local/docmap.md)
├── dev-root\                    ← Division-level inventory and mapping docs
│   └── docmap.md                ← Full division hierarchy map
├── obsolete\                   ← Dev-level obsolete. Developer purges only.
├── project-library-global\     ← Shared standards and reference for all projects
│   ├── adr-global/             ← Global architectural decision records
│   ├── checklists-global/      ← Global checklists
│   ├── docs-standard-global/   ← Standard doc templates
│   ├── guides/                 ← Global how-to guides
│   ├── policy-global/          ← Global policies
│   ├── specifications-global/  ← Global specifications
│   ├── standard-operating-procedures-global/ ← Global SOPs
│   └── templates-global/       ← Global templates
└── project-template\           ← Skeleton for new projects (import into new dev-* folder)
```

---

## 3. PDLF Framework — `C:\pdlf\` — **excluded from Docs Manager, see note**

**Current status: placeholder, not live.** This is the remains of a first, aborted attempt at
building PDLF — implemented halfway, then abandoned. It is not the deployed product yet; it may
have reference value in showing how that earlier attempt was structured, but nothing here
should be treated as current. dev-makepdlf is where the real framework is being built; once that
concludes, the finished framework will be deployed here.

**Deliberately excluded from Docs Manager's walk root** (SKILL.md Section 1.1) — scanning a
placeholder that nobody is maintaining would just generate drift noise about content that isn't
meant to be current. **This should be revisited once dev-makepdlf actually deploys here** — at that
point `C:\pdlf\` becomes live and belongs back in scope as a fourth walk root.

```
C:\pdlf\
├── .scratch/
├── docs/
├── registry/
└── skill/
```

---

## 4. (Removed — see note)

`C:\projects-reference\` is confirmed personal content, outside the Mybizz/PDLF operating
system entirely, kept only for reasons unrelated to this work. Not part of this docmap, not
part of any project, and does not get a `{slug}-config.yaml` or `README.md` under the config-YAML
rule in Section 6 — that rule applies to system folders, not personal ones.

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
| Project config (single source of truth) | `C:\dev\dev-{project}\{slug}-config.yaml` |
| Project explainer | `C:\dev\dev-{project}\README.md` |
| Project WIP / todo | `C:\dev\dev-{project}\wip\todo.md` |
| Global standards (ADRs, policies, specs, SOPs) | `C:\dev\project-library-global\{category}\` |
| Global how-to guides | `C:\dev\project-library-global\guides\` |
| Tool config reference documents | `C:\mybizz\config\{tool}\` |
| System describer/explainer documents | `C:\mybizz\mybizz-os\` |
| Business documents (financial, planning) | `C:\mybizz\Mgt\` |
| Daily working files / scratchpad | `C:\mybizz\WIP\desktop\` |
| Completed work for long-term reference | `C:\mybizz\archive\` |
| Temporary trash during a session | `C:\dev\obsolete\` (dev items) or `C:\mybizz\Mgt\obsolete\` (mgt items) |
| Custom skills | `C:\mybizz\skills-collective\custom-skills\` |
| Backups | Docs Manager: `C:\backup-docs-manager\<timestamp>\`. mb-align-docs: `C:\backup-mb-align-docs\<timestamp>\`. WSL-originated: `C:\backup-wsl\{script}\<timestamp>\`. All other/general backups: `C:\backups-general\` (new folder per backup exercise). |
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
| GStack | `C:\mybizz\gstack\` | Skill framework, binaries, browse daemon | `C:\mybizz\config\gstack\` |
| GStack runtime (OpenCode) | `~/.config/opencode/skills/gstack/` | Runtime root — `bin` symlinks back to the source clone above | |
| GBrain (source clone) | `C:\mybizz\gbrain\` | GBrain's own source repository | `C:\mybizz\config\gbrain\` |
| GBrain (live install) | `/home/dev-p/gbrain/src/` (WSL) | The actual running CLI — separate from the source clone above | |
| Matt Pocock skills (source) | `C:\mybizz\matt-pocock-skills-source\` | Authoritative clone — all 35 skills symlinked from here | `C:\mybizz\config\matt-skills\` |
| Matt Pocock skills (live) | `~/.agents/skills/` (WSL) | Symlinks into the source clone above | |
| Anvil skills (source) | `C:\mybizz\anvil-agent-references\` | Official Anvil-maintained skill repo | `C:\mybizz\config\anvil-skills\` |
| Magdoub Claude Wireframe (source) | `~/.claude/skills/wireframe/` (WSL) | Real git clone, official install location | `C:\mybizz\config\magdoub-wireframe\` |
| Graphify | `/home/dev-p/.local/bin/graphify` (WSL, via pip) | Code/document knowledge-graph builder | `C:\mybizz\config\graphify\` |
| PostgreSQL (GBrain's instance) | WSL-native, port 5432 | GBrain's database — separate from PDLF's own ledger instance | `C:\mybizz\config\postgresql\` |

**Retired:** `C:\mybizz\skills\` no longer exists — confirmed a stale, disconnected duplicate of the GStack source clone, one version behind, removed. Do not reference this path; use `C:\mybizz\gstack\` directly, or `C:\mybizz\skills-collective\` for the browsable symlink hub.

---

## 8. Key Companion Documents

| Document | Location | Purpose |
|---|---|---|
| `docmap.md` | `C:\dev\dev-root\docmap.md` | THIS FILE — full division hierarchy map |
| Per-project config | `C:\dev\dev-{project}\{slug}-config.yaml` | Single source of truth for that project's configuration — see Section 6 |
| Per-project explainer | `C:\dev\dev-{project}\README.md` | Narrative context for that project |
| `projects-config-register.md` | `C:\mybizz\config\projects-config-register.md` | Register of every project's `{slug}-config.yaml` |
| `README.md` | `C:\mybizz\README.md` | Division workspace overview |
| Global `AGENTS.md` | `~/.config/opencode/AGENTS.md` | Global agent behavior rules — authoritative, live |
| Project `AGENTS.md`/`agents.md` | **Varies per project — see that project's `{slug}-config.yaml`.** No single fixed path pattern exists: some projects have it in the docs repo only, `mb-3-cs` has it in both repos (lowercase `agents.md` in the code repo specifically), some projects have none yet. Do not assume a pattern — check the YAML. |
| `daily-ops.md` | `C:\mybizz\WIP\desktop\daily-ops.md` | Daily operations quick reference |
| `master-task-list.md` | `C:\mybizz\WIP\desktop\master-task-list.md` | Current active task list |
| `mybizz-todo.md` | `C:\mybizz\WIP\desktop\mybizz-todo.md` | Deferred tasks and the OS Setup Task List |
| `config-changelog.md` | `C:\mybizz\WIP\config-changelog.md` | Full audit trail of every configuration change |
| dev-makepdlf docmap | `C:\dev\dev-makepdlf\makepdlf-project-library\docs-local\docmap.md` | PDLF project document map |
| docs-manager skill | `~/.config/opencode/skills/docs-manager/SKILL.md` | Skill definition — document inventory, update rules, workflow |
| | Windows: `\\wsl.localhost\Ubuntu\home\dev-p\.config\opencode\skills\docs-manager\SKILL.md` | |
| docs-manager sub-agents (5 files) | `~/.config/opencode/skills/docs-manager/docs-manager-backup.md`, `docs-manager-scan.md`, `docs-manager-apply.md`, `docs-manager-filesystem.md`, `docs-manager-commit.md` | One sub-agent per phase (0 backup, 1 scan, 4a text edits, 4b file-system operations, 6 commit/push), each with only the permissions its phase needs |
| | Windows: `\\wsl.localhost\Ubuntu\home\dev-p\.config\opencode\skills\docs-manager\` | |

**Retired:** `scaffold-system.html` — archived to `C:\mybizz\archive\` as a historical record, no longer actively maintained. `session-opening-prompt.md` — confirmed empty, deleted; its purpose is tracked as `master-task-list.md` Section 5 instead. `C:\dev\AGENTS-global-standard-reference.md` — its real content (hard rules, definitions, certainty levels, language restrictions, prescribed standards) has been fully merged into the live global `AGENTS.md`; the file itself is superseded. `C:\dev\dev-root\project-inventory.md` — deleted 2026-08-13; every real fact it held now lives in one of the 9 project `{slug}-config.yaml` files (see `projects-config-register.md`), or was confirmed genuinely obsolete. `C:\mybizz\config\workspace-docmap.md` — deleted 2026-08-13, substantially stale (dated 2026-07-08); its two genuinely useful, not-yet-captured details (GStack's per-project subdirectory structure, standard per-project artifact directories) were preserved in `gstack-reference.md` before removal.
