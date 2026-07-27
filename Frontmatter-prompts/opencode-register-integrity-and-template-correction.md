Task: Register integrity corrections and template de-registration.
Five parts, across the global repo and four project repos. Treat each
part independently — do not assume one outcome applies to another. Do not
invent, extend, or "improve" anything beyond what is explicitly described
in each part. If anything encountered doesn't match what's described here,
stop and report it — do not resolve it by inventing a solution.

Scope:
  C:\dev\project-library-global\
  C:\dev\dev-mb4ecom\mb4ecom-project-library\
  C:\dev\dev-makepdlf\makepdlf-project-library\
  C:\dev\dev-mb-3-cs\mb-3-cs-project-library\
  C:\dev\dev-mb5pdlf\mb5pdlf-project-library\
Do not touch any other repo or folder.

---

## Part A — Retire the two templates-global register entries

Repo: C:\dev\project-library-global\

Decision made: templates do not get front matter or register entries —
this applies retroactively to two existing entries that were registered
in error, before this rule was settled.

Affected register rows (in register-global): global-0086
(`templates-global/tmp-authoritative-schema.md`) and global-0087
(`templates-global/tmp-custom-component-requirements-matrix).md`).

Step A1 — Verify the filename on disk for global-0087 exactly. The
register row shows a filename containing a stray closing parenthesis:
`tmp-custom-component-requirements-matrix).md`. Confirm whether this
exact filename (parenthesis included) exists on disk, or whether it's a
transcription error in the register. Report the actual on-disk filename
before doing anything else with this file. Do not rename it as part of
this task regardless of what you find — report only.

Step A2 — Propose the register correction for both rows: flip `state` to
`Retired`, set `date-state-changed` to now (per the mandatory timestamp
method below), and add to `notes`: "Retired: templates are not
register-tracked documents; corrected per templates-vs-documents ruling."
Per the register's own append-only rule, the row itself is never removed
— only these fields update in place. Show the exact proposed row changes
before writing anything.

Step A3 — Propose stripping the front-matter block entirely from both
files on disk (`tmp-authoritative-schema.md` and whatever global-0087's
confirmed real filename is). Show the exact current front matter and
confirm it will be removed in full, leaving the rest of each file's
content untouched.

---

## Part B — Retire the three stale checklists-global register rows

Repo: C:\dev\project-library-global\

The `checklists-global` folder has been discontinued; its contents were
moved to `templates-global` as untracked `tmp-chklist-*.md` files (no
front matter, per the templates rule in Part A). The register was never
updated to reflect this. Affected rows: global-0040
(`checklists-global/chk-analytics-DashboardAnalyticsForm.md`), global-0041
(`checklists-global/chk-anvil-app-testing.md`), global-0042
(`checklists-global/chk-screen-analytics-DashboardAnalyticsForm.md`).

Step B1 — Confirm the `checklists-global` folder no longer exists on
disk, and confirm the corresponding `tmp-chklist-*.md` files exist in
`templates-global`. Report findings before proceeding.

Step B2 — Propose the same register correction pattern as Part A for all
three rows: `state` to `Retired`, `date-state-changed` to now, `notes`:
"Retired: checklists-global discontinued; content migrated to
templates-global as untracked template, no longer register-tracked." Show
the exact proposed row changes before writing anything.

---

## Part C — Resolve duplicate doc-ids

Repos: mb4ecom-project-library, makepdlf-project-library

Known duplicates: mb4ecom has doc-ids 0001 and 0002 each appearing twice;
makepdlf has doc-ids 0001–0003 each appearing on both a root file and an
ADR file.

Step C1 — For each repo, list every document currently sharing a
duplicated doc-id, with its full path, front-matter content, and (if
already registered) its register row. Do not assume which one is
"correct" — report both members of each duplicate pair with enough detail
(creation date, content, git history if available) to judge which was
registered first / is the original.

Step C2 — Propose a resolution per duplicate pair: the document judged to
be the later/incorrect duplicate gets reassigned the next available
sequential doc-id in that repo's numbering (continuing after the highest
existing doc-id, not filling the gap from Part D below — those are
separate). State your reasoning for which document keeps the original
number and which gets renumbered. Show the exact proposed front-matter
change and register update (or new register entry, if not yet registered)
for each affected document before writing anything.

---

## Part D — Confirm doc-id gaps

Repos: mb-3-cs-project-library (gap at 0012), mb5pdlf-project-library
(gap at 0003)

Step D1 — For each gap, check git history and any available logs for why
that number was never assigned (most likely explanation: reserved for a
document later excluded, quarantined, or renamed before registration).
Report findings. This is report-only — do not assign a document to fill
the gap and do not renumber anything unless the findings reveal an actual
error that needs correcting, in which case stop and report the finding
before proposing any fix.

---

## Part E — Rename register files off the "-placeholder" filename

Repos: all five in scope for this task

Every register file (global and per-project) is currently still named
`register-template-placeholder.md`, despite being fully populated.
Proposed convention: rename to `register-global.md` for the global repo,
and `register-local.md` for each project repo — matching the existing
`register-global\` / `register-local\` folder naming.

Step E1 — Propose this naming convention explicitly and confirm no other
file already uses either target name in the destination folder, before
renaming anything.

Step E2 — Rename each of the five register files accordingly. Confirm no
other file references the old `register-template-placeholder.md` filename
(a skill file, a script, an AGENTS.md, etc.) — if any reference is found,
report it, do not silently edit it.

---

Step 1 — Precondition check.
Confirm the git working tree is clean for all five repos in scope before
proceeding. If any is dirty, stop and report that repo — continue
checking the others.

Step 2 — Backup.
Take a full backup of all five repos before any write. Save to
C:\backups-general\backup-mb-align-docs_<timestamp>\, one backup per repo,
timestamp per the mandatory method in
C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md,
format YYYY-MM-DDTHHMMSS+0200.

Step 3 — Present all proposals (Parts A through E) together, organized by
part, before any write.

Step 4 — Approval.
Each part (A, B, C, D, E) gets its own separate explicit approval — do
not bundle unrelated parts into one approval, since they are different
kinds of action (register state changes, front-matter stripping,
doc-id reassignment, report-only findings, file renaming).

Step 5 — Second confirmation for structural actions.
Per SKILL.md's writer-structural gate: register state changes (Parts A,
B), doc-id reassignment (Part C), and file renaming (Part E) each require
one more explicit "about to do this, proceed?" confirmation immediately
before execution, on top of the Step 4 approval. Part D is report-only and
does not require this unless a correction is proposed.

Step 6 — Apply.
Only after both approval and (where applicable) the second confirmation,
apply each approved change, one item at a time. Re-read each affected
file immediately after writing to confirm the change was applied
correctly and nothing else was altered.

Step 7 — Report.
Confirm every action taken per part, quote final register rows and
front-matter states where changed, and confirm no other content in any
file was altered beyond what was approved.

---

Hard constraints:
  - No writes before Step 1 and Step 2 are complete.
  - No writes without both Step 4 approval and, where required, Step 5
    second confirmation.
  - Never delete a register row — only update state/date-state-changed/
    notes in place, per the register's own append-only rule.
  - Never delete any file — front-matter stripping removes only the
    front-matter block, not the file.
  - Do not rename the global-0087 file as part of this task, regardless
    of what Step A1 finds — report only.
  - Do not touch any repo not listed in Scope above.
  - Do not fill the doc-id gaps in Part D with any document — Part D is
    report-only unless an actual error is found, in which case stop and
    ask before proposing a fix.
