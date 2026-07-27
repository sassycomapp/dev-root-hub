---
document: Handover — mb-align-docs and Related System State
date-created: 2026-07-25
status: handover snapshot, not a decision record
---

# Handover — mb-align-docs and Related System State

Read this first in any new session before assuming anything about current state. This
reflects corrections made after prior errors in tracking — trust this over conversation
memory, and trust the actual filesystem over this document if the two ever disagree.

---

## 1. Done — confirmed, don't redo

- **mb-align-docs function scope** — locked (V1). Path:
  `C:\projects-reference\custom-skills-store\mb-align-docs\mb-align-docs-function-scope.md`
- **Full mb-align-docs skill package delivered**, in
  `C:\projects-reference\custom-skills-store\mb-align-docs\`:
  `SKILL.md`, `mb-align-docs-function-scope.md`, `front-matter-schema.md`,
  `register-template.md`, `quarantine-provenance-template.md`,
  `alignment-log-template.md`, `finding-report-format.md`,
  `mb-align-docs-detector.md`, `mb-align-docs-writer-text.md`,
  `mb-align-docs-writer-structural.md`, `mb-align-docs-logger.md`, `learnings\`
- **`mb-align-docs-README.md`** — at `C:\dev\dev-root\`, full inventory included.
- **All supporting folders created and correctly named:**
  - `C:\backups-general\` — new unified backup convention
    (`backup-mb-align-docs_<timestamp>`, `backup-docs-manager_<timestamp>`)
  - `C:\mybizz\logs\mb-align-docs\learnings\`, `in-progress\`, `last-completed-run\`,
    `abandoned-runs\`
  - `register-local\` per project, `register-global\` at
    `project-library-global\` only (never the reverse)
  - `Quarantine\` (capital Q) per project and at `project-library-global\`
  - `output-staging\` and `pdlf-temp\` added to every project-library and to
    `project-template`
- **dev-pdlf → dev-makepdlf rename**, fully completed: folder renamed, code repo and
  docs repo renamed (`makepdlf`, `makepdlf-project-library`), content repair run via
  OpenCode (identifiers, AGENTS.md title, wip todo filename, obsolete file left
  untouched), GitHub remote renamed, GBrain source renamed. GStack registration rename
  prompt was sent — **completion not explicitly confirmed in this conversation, verify
  before assuming done.**
- **`project-library` → `mb-3-cs-project-library` rename** — completed system-wide, 19
  files across 4 repos, confirmed via rename report. `mb-3-cs-project-library` (with
  hyphens, matching the Anvil.works code-repo name) is the **correct**, final name —
  not an inconsistency to fix.
- **`docmap.md` and `project-inventory.md`** — both updated and correct for the pdlf
  rename and the mb-3-cs rename. `wip\` folder confirmed present for dev-makepdlf and
  included. Both at `C:\dev\dev-root\`.
- **Timestamp standard ADR** — `global-0037`, at
  `C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md`.
  Hardened after multiple corrections:
  - Format: `YYYY-MM-DDTHHMMSS+0200` (Filename-Safe ISO 8601, UTC+2, seconds included)
  - Applies to build artefacts only (front matter, registers, logs, backups) — never
    to client-facing data, which keeps its own IANA-timezone rule (unchanged, separate
    section of the same ADR)
  - **One mandatory conversion method, no fallback:**
    `TZ="Africa/Johannesburg" date -d "@<unix-timestamp>" '+%Y-%m-%dT%H%M%S%z'`
  - If that method can't be used, the agent must stop and ask — never substitute
    another method on its own judgment
- **`project-library-global`** — front-matter retrofit done, AND the date-format
  correction pass done (all `date-created` values now conform to the ADR format
  above, sourced from the actual retrofit commit's timestamp).
- **AGENTS.md, system-wide** — updated with the Timestamp Standard section,
  referencing the ADR above by its real file path. Covers the global AGENTS.md, every
  existing project's AGENTS.md, and `project-template`'s AGENTS.md (so new projects
  inherit it automatically). Confirmed done by the developer.

---

## 2. Still open — do not assume done

- **Docs Manager v9** — needs the datestamp fix and the `C:\backups-general\` backup
  mandate applied. This is the developer's own build/versioning process (Docs Manager
  isn't mb-align-docs' file), but it's an explicitly outstanding item raised in this
  conversation.
- **mb-align-docs skill files still cite the ADR by doc-id (`global-0037`) only, not
  by real file path.** Agreed fix, not yet applied: update `SKILL.md`,
  `front-matter-schema.md`, `register-template.md`, `alignment-log-template.md`,
  `quarantine-provenance-template.md` to reference
  `C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md`
  directly, so an agent doesn't need a working register lookup to find the mechanism.
- **Front-matter retrofit still needed for four repos, in this order:**
  1. `mb-3-cs-project-library` — prompt already built and corrected, ready to run,
     not yet run. File (if still present in a prior session's outputs):
     prompt for `C:\dev\dev-mb-3-cs\mb-3-cs-project-library\`.
  2. `mb4ecom-project-library` — prompt not yet built.
  3. `mb5pdlf-project-library` — prompt not yet built.
  4. `makepdlf-project-library` — deliberately last, since it already went through
     heavy rework (rename + content repair) and should sit settled before another
     bulk edit lands on it. Prompt not yet built.
  Each prompt should mirror the corrected mb-3-cs prompt: cite the ADR by real path,
  use the mandatory TZ conversion method, back up to `C:\backups-general\`, batch
  approval after a full detect-and-report pass, per-file write-then-verify.
- **Registers remain empty placeholders** (`register-template-placeholder.md`) in
  every project and globally. Population follows each repo's front-matter retrofit —
  a register entry needs the front-matter fields to exist first. Not started for any
  project.
- **mb-align-docs startup check for missing front matter** — agreed in principle:
  every Detect pass should scan for any document lacking front matter and route it
  through the same approval path as a register-mismatch finding (propose identity,
  batch-approve, apply, verify). **Not yet written into `SKILL.md`.**
- **`instructions.md` for every folder** — explicitly the developer's own
  responsibility, not something to build or draft unprompted.
- **mb-align-docs has never actually executed, end to end.** Everything above is
  specification and scaffolding. Resume/checkpoint, the second confirmation gate on
  structural writes, and the writer-text/writer-structural split are all untested in
  a real run.

---

## 3. Standing rules to carry forward without re-deciding

- `register-global` is reserved for `project-library-global` only. Every per-project
  register is `register-local`. Never the reverse — this was corrected once already.
- `Quarantine` (capital Q) is the standard casing, global and per-project.
- Two operations never share a remediation path: reference-healing (routes to
  `writer-text`) vs. identifier-change (routes to `writer-structural`, triggers a
  corpus-wide sweep on approval).
- Front matter is identity-only — `document`, `doc-id`, `state`, `date-created` (plus
  conditional `superseded-by`, `source`). Never references or cross-links. Set once
  at creation, never edited — a new version is a new document.
- `doc-id` format: `{project-slug}-####` (4-digit sequential), e.g. `mb-3-cs-0001`.
  Global documents use `global-####`.
- No live reference may resolve to a non-`Live` document (`Retired` or `Quarantine`)
  — always a drift item, must be healed or removed.
- Cross-project references and old-but-wanted versions both route through
  `Quarantine`, with provenance front matter — never a live cross-project link.

## 4. Working conventions with this developer — do not drift from these

- **No artifacts without explicit approval.** Clarifying questions answered are not
  approval to produce a file. Wait for an explicit go-ahead.
- **No deferrals, no hedged "worth noting for later."** If something needs deciding,
  decide it now or ask a direct question now — don't park it.
- **Full paths, plain language, no abbreviations assumed understood.** The developer
  uses voice-to-text and has dyslexia; compressed or jargon-heavy phrasing causes real
  confusion, not just style friction. Spell things out fully, one point at a time if
  needed, and check understanding before stacking more on top.
- **Verify before asserting.** Several of the errors in this conversation came from
  assuming instead of checking (assuming a register/Quarantine naming convention,
  assuming a fallback clause was harmless, assuming a shell command was correct
  without tracing the actual logic). Trace the actual mechanism before presenting it
  as correct, especially for anything technical like the timestamp conversion.
- The developer will catch inconsistencies and push back hard when something's wrong
  — treat that as the system working correctly, not as friction to smooth over.
