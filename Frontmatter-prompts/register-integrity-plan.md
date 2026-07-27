# Register Integrity Corrections & Template De-Registration — Plan

Prepared: 2026-07-27
Source: `opencode-register-integrity-and-template-correction.md`
Status: Proposals presented, awaiting per-part approval

---

## Step 1 — Precondition Check: PASSED

All five repos have clean git working trees. No modifications pending.

---

## Part A — Retire template register entries

### A1 — Filename verification for global-0087

The register row shows `templates-global/tmp-custom-component-requirements-matrix).md` with a stray closing parenthesis. **Confirmed**: the file on disk IS named exactly `tmp-custom-component-requirements-matrix).md` (parenthesis included). This is the real filename, not a transcription error. No rename is performed per the task constraint.

### A2 — Proposed register row changes (both rows)

| doc-id | state | date-state-changed | notes (add) |
|---|---|---|---|
| global-0086 | `Live` → **`Retired`** | → **now** | **"Retired: templates are not register-tracked documents; corrected per templates-vs-documents ruling."** |
| global-0087 | `Live` → **`Retired`** | → **now** | **"Retired: templates are not register-tracked documents; corrected per templates-vs-documents ruling."** |

Other fields (`date-registered`, `filename`, `folder`, `type`) remain unchanged.

### A3 — Proposed front-matter stripping

Both files have a front-matter block (lines 1–6) to remove entirely:

**`templates-global/tmp-authoritative-schema.md`:**
```
---
document: "{Project Name} — Authoritative Database Schema"
doc-id: global-0086
state: Live
date-created: 2026-07-25T150027+0200
---
```

**`templates-global/tmp-custom-component-requirements-matrix).md`:**
```
---
document: "{Project Name} — Custom Component Requirements Matrix"
doc-id: global-0087
state: Live
date-created: 2026-07-25T150027+0200
---
```

Content after line 6 in both files is left untouched.

---

## Part B — Retire stale checklists register rows

### B1 — Folder/file existence report

- `checklists-global/` folder: **DOES NOT EXIST** — confirmed.
- Corresponding `tmp-chklist-*` files in `templates-global` exist, but with **mismatches**:

| Original checklist | Expected tmp-chklist name | Actual tmp-chklist name | Front-matter present? |
|---|---|---|---|
| `chk-analytics-DashboardAnalyticsForm.md` (global-0040) | `tmp-chklist-analytics-DashboardAnalyticsForm.md` | `tmp-chklist-wireframe.md` | **YES** (with doc-id global-0040) |
| `chk-anvil-app-testing.md` (global-0041) | `tmp-chklist-anvil-app-testing.md` | `tmp-chklist-anvil-app-testing.md` | **YES** (with doc-id global-0041) |
| `chk-screen-analytics-DashboardAnalyticsForm.md` (global-0042) | `tmp-chklist-screen-analytics-DashboardAnalyticsForm.md` | `tmp-chklist-screen.md` | **YES** (with doc-id global-0042) |

**DISCREPANCY REPORT:** Part B states these files have "no front matter, per the templates rule in Part A." All three tmp-chklist files **do** still have front matter (doc-id, state=Live, date-created). Additionally, two of the three filenames diverge from the expected `tmp-chklist-<original-basename>.md` pattern. Per the task's discipline rule: reported, not resolved — no out-of-scope fix proposed.

### B2 — Proposed register row changes (three rows)

| doc-id | state | date-state-changed | notes (add) |
|---|---|---|---|
| global-0040 | `Live` → **`Retired`** | → **now** | **"Retired: checklists-global discontinued; content migrated to templates-global as untracked template, no longer register-tracked."** |
| global-0041 | `Live` → **`Retired`** | → **now** | (same) |
| global-0042 | `Live` → **`Retired`** | → **now** | (same) |

---

## Part C — Resolve duplicate doc-ids

### C1 — Duplicate pairs enumerated

**mb4ecom:**

| Duplicate # | Member A (original) | Member B (later, to renumber) | Evidence |
|---|---|---|---|
| mb4ecom-0001 | `docs/agents/domain.md` (2026-07-25) | `AGENTS.md` (2026-07-27) | creation dates |
| mb4ecom-0002 | `docs/agents/issue-tracker.md` (2026-07-25) | `README.md` (2026-07-27) | creation dates |

`mb4ecom-0003` (`docs/agents/triage-labels.md`) is unique — no conflict.

**makepdlf:**

| Duplicate # | Member A (original) | Member B (later, to renumber) | Evidence |
|---|---|---|---|
| makepdlf-0001 | `adr-local/adr-global-content-discovery-and-application-discipline.md` (2026-07-19) | `AGENTS.md` (2026-07-27) | creation dates |
| makepdlf-0002 | `adr-local/adr-no-staging-environment-five-app-isolation.md` (2026-07-18) | `INDEX.md` (2026-07-27) | creation dates |
| makepdlf-0003 | `adr-local/postgres-ledger-replaces-flat-files.md` (2026-07-10) | `README.md` (2026-07-27) | creation dates |

In all cases, the agent/ADR docs were created first (earlier date in the front-matter `date-created` field), and the root-level files (AGENTS.md, README.md, INDEX.md) were created later during the front-matter retrofit on 2026-07-27.

### C2 — Proposed resolution

**mb4ecom:**
- `docs/agents/domain.md` **keeps** `mb4ecom-0001`
- `docs/agents/issue-tracker.md` **keeps** `mb4ecom-0002`
- `AGENTS.md` → reassigned to **`mb4ecom-0005`** (next after highest, mb4ecom-0004 = register)
- `README.md` → reassigned to **`mb4ecom-0006`**

Register: update `doc-id` field and `filename` for the two renumbered rows. Update front-matter `doc-id` on disk for both affected files.

**makepdlf:**
- `adr-local/adr-global-content-discovery-and-application-discipline.md` **keeps** `makepdlf-0001`
- `adr-local/adr-no-staging-environment-five-app-isolation.md` **keeps** `makepdlf-0002`
- `adr-local/postgres-ledger-replaces-flat-files.md` **keeps** `makepdlf-0003`
- `AGENTS.md` → reassigned to **`makepdlf-0101`** (next after highest, makepdlf-0100 = register)
- `INDEX.md` → reassigned to **`makepdlf-0102`**
- `README.md` → reassigned to **`makepdlf-0103`**

Same pattern: update register rows and on-disk front-matter for the renumbered files.

---

## Part D — Confirm doc-id gaps

### D1 — Gap reports (report-only)

**mb-3-cs (gap at 0012):**
Register jumps from `mb-3-cs-0011` (CHANGELOG.md) to `mb-3-cs-0013` (DESIGN.md). The front-matter retrofit commit (`a4a452f`) assigned IDs to 64 in-scope documents. A subsequent commit (`d241ffc`) reclassified documents, moving CONTEXT.md and gstack-artifact-governance.md into docs-local from root. Likely explanation: 0012 was reserved for a document that was excluded or moved before registration numbering. Gap is stable — no error found needing correction.

**mb5pdlf (gap at 0003):**
Register jumps from `mb5pdlf-0002` (README.md) to `mb5pdlf-0004` (adr/001-...). The front-matter retrofit added front-matter to 13 documents, but the register was later populated with only 11 entries (commit `1aceb62`), meaning 2 documents were removed between retrofit and register population. 0003 was likely reserved for one of these excluded documents. Gap is stable — no error found needing correction.

---

## Part E — Rename register files

### E1 — Proposed naming convention

| Repo | Current name | Proposed name | Folder |
|---|---|---|---|
| project-library-global | `register-template-placeholder.md` | **`register-global.md`** | `register-global/` |
| mb4ecom-project-library | `register-template-placeholder.md` | **`register-local.md`** | `register-local/` |
| makepdlf-project-library | `register-template-placeholder.md` | **`register-local.md`** | `register-local/` |
| mb-3-cs-project-library | `register-template-placeholder.md` | **`register-local.md`** | `register-local/` |
| mb5pdlf-project-library | `register-template-placeholder.md` | **`register-local.md`** | `register-local/` |

**No other file in any destination folder uses either target name** — confirmed. No external file (script, AGENTS.md, config) in any of the five repos references the old `register-template-placeholder.md` filename — confirmed (only `.git/index` entries are internal git pointers that auto-resolve on rename).

---

## Summary of actions by type

| Part | Action type | Structural? | Changes |
|---|---|---|---|
| A | Register state update + front-matter strip | Yes | 2 register rows + 2 on-disk files |
| B | Register state update | Yes | 3 register rows |
| C | Doc-id reassignment | Yes | 5 register rows + 5 on-disk front-matter updates |
| D | Report-only | No | 0 changes |
| E | File rename | Yes | 5 renames |

---

## Approval required

Each part (A–E) requires separate explicit approval per Step 4 of the process. Parts A, B, C, and E also require a second structural confirmation per Step 5. Part D is report-only.

## Known issues flagged

1. **Part B front-matter discrepancy:** All three tmp-chklist files in `templates-global` still have front matter (with doc-id and state=Live), despite Part B's description stating they have "no front matter, per the templates rule in Part A." Out of scope for this task — flagged as an inconsistency.
2. **Part B filename mismatch:** Two of the three tmp-chklist filenames diverge from the expected `tmp-chklist-<original-basename>.md` pattern. Out of scope for this task — flagged as an inconsistency.
