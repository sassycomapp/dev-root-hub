Task: Correct stale paths and add the mb-align-docs follow-up rule to
daily-ops.md.

Note: this task originally had a second part (Part B) instructing edits
to Docs Manager's own SKILL.md. That work has already been completed
directly by the developer — Docs Manager's SKILL.md now includes the
mb-align-docs reminder as Step 3a of its Phase 9 Completion Gate, and its
backup-path references have already been corrected to
C:\backups-general\backup-docs-manager_<timestamp>\. Do not touch
Docs Manager's SKILL.md as part of this task — it is already done.

Scope is strictly limited to:
C:\projects-reference\workspace-reference\workflow reference\daily-ops.md
Do not touch any other file. Do not invent, extend, or "improve" anything
beyond what is explicitly described below.

---

## Part A — daily-ops.md: new rule + stale path correction

### A1 — Stale path correction (do first, report before proceeding)

Every command in this file references `/mnt/c/_mb2-cs-app/project-library`,
which does not match the current project structure. Per
project-inventory.md, the current correct path for mb-3-cs's
documentation repo is `/mnt/c/dev/dev-mb-3-cs/mb-3-cs-project-library`
(WSL) / `C:\dev\dev-mb-3-cs\mb-3-cs-project-library` (Windows).

Step A1a — Confirm this is in fact stale (i.e. confirm
`/mnt/c/_mb2-cs-app/project-library` does not exist on disk, and the
correct current path does) before proposing any change. Report findings.

Step A1b — Propose replacing every occurrence of
`/mnt/c/_mb2-cs-app/project-library` in this file with
`/mnt/c/dev/dev-mb-3-cs/mb-3-cs-project-library`. Show every location
found (there appear to be three: under START OPENCODE, AFTER DOING WORK,
and CHECK WHAT'S NOT COMMITTED YET) and the exact proposed replacement
before writing anything.

### A2 — New rule: run mb-align-docs after Docs Manager

Add a new section to this file, placed logically near the top (e.g.
immediately after "AFTER DOING WORK — run every time," since it's a
related housekeeping step), stating:

  After any Docs Manager run that renames, moves, or retires files
  within a project's project-library (or project-library-global), run
  mb-align-docs against that same project next, before considering the
  documentation environment stable. This catches any register or
  front-matter drift that Docs Manager's structural changes may have
  introduced. Not required after a Docs Manager run that made no
  structural changes (text-only corrections).

Step A2a — Propose the exact section heading, placement, and wording
(matching this file's existing terse, command-reference style) before
writing anything.

---

Step 1 — Precondition check.
Confirm the git working tree is clean for the repo containing
daily-ops.md before proceeding. If dirty, stop and report — do not
proceed.

Step 2 — Backup.
Take a full backup of the affected file before any write. Save to
C:\backups-general\backup-mb-align-docs_<timestamp>\, timestamp per the
mandatory method in
C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md,
format YYYY-MM-DDTHHMMSS+0200.

Step 3 — Present all proposals (A1 findings + A2 proposal) together,
before any write.

Step 4 — Approval.
A1 (path correction) and A2 (new rule) each get their own separate
explicit approval.

Step 5 — Apply.
Only after approval, apply each approved change. Re-read the file
immediately after writing to confirm the change was applied correctly and
no other content was altered.

Step 6 — Report.
Confirm what was changed, quote the final corrected/added text for each
change, and confirm nothing else was altered.

---

Hard constraints:
  - No writes before Step 1 and Step 2 are complete.
  - No writes without the Step 4 approval, per part.
  - Do not touch any file other than daily-ops.md.
  - Do not touch Docs Manager's SKILL.md under any circumstance — that
    work is already done.
