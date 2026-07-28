Task: Finalize mb-align-docs skill files — close all remaining
inconsistencies before the first real run.
Scope is strictly limited to:
C:\projects-reference\custom-skills-store\mb-align-docs\
C:\dev\dev-root\mb-align-docs-README.md
Do not touch any other repo or folder. Do not invent, extend, or
"improve" anything beyond what is explicitly described below. If anything
encountered doesn't match what's described here, stop and report it — do
not resolve it by inventing a solution.

---

## Part 0 — Duplicate file check (report-only, do first)

Several files in the skill folder were delivered in this conversation with
filenames ending in a trailing hyphen before the extension (e.g.
`alignment-log-template-.md`, `mb-align-docs-logger-.md`,
`mb-align-docs-writer-text-.md`), alongside versions without the trailing
hyphen. It's unclear whether this is an artifact of file transfer or
whether duplicate files genuinely exist on disk.

Step 0 — List every file in the skill folder exactly as it exists on disk
right now. For each of: alignment-log-template, mb-align-docs-logger,
mb-align-docs-writer-text — report whether one file or two exist for each
name (i.e. is there a trailing-hyphen variant actually present on disk).
If duplicates are found, report their exact filenames and confirm whether
their content is identical or diverges. Do not delete, merge, or rename
anything in this step — report only. If genuine duplicates are found,
stop after reporting and wait for instruction before any part below
proceeds on that specific file.

---

## Part A — Fix writer-text contradiction (blocking)

File: mb-align-docs-writer-text.md

Current text states: "Only acts on findings of type `reference-healing`.
Any other finding type reaching this subagent is a routing error and must
be rejected back to the orchestrator, not executed."

This directly contradicts SKILL.md, which assigns writer-text to also
execute approved `missing-front-matter` and `incomplete-front-matter`
findings (both are content additions, not structural actions).

Step A1 — Propose corrected text for the Responsibilities and Constraints
sections of mb-align-docs-writer-text.md: writer-text executes
`reference-healing`, `missing-front-matter`, and `incomplete-front-matter`
findings. Update the "Only acts on findings of type..." constraint to
list all three types. Update the Responsibilities section to describe the
front-matter-insertion and front-matter-completion actions (matching what
SKILL.md's Missing-front-matter check section already describes), not
just reference repoints. Show the exact proposed text before writing
anything.

---

## Part B — Document the templates exclusion rule (blocking)

Files: mb-align-docs-function-scope.md, SKILL.md

Decision already made and already applied to real files: content in
`templates-global` and `templates-local` (any file, anywhere under a
folder of either name) never gets front matter or a register entry.
Templates are reusable stencils, not documents with identity or
lifecycle — this is a categorical rule, not specific to any one file
type.

Step B1 — Propose a new subsection in mb-align-docs-function-scope.md
(numbered consistently with existing sections — check current numbering
before proposing a number) stating this rule plainly: any file under a
`templates-global` or `templates-local` folder is permanently out of
scope for front matter and register entries. Show the exact proposed text
and insertion point before writing anything.

Step B2 — Propose an addition to SKILL.md's "Missing-front-matter check"
section (or a new short "Scope exclusions" note near it) stating that
`templates-global`/`templates-local` content is excluded from that check
entirely — not a recurring gap to flag, by design. Show the exact
proposed text before writing anything.

---

## Part C — Document the historical-log exclusion rule (blocking)

Files: mb-align-docs-function-scope.md, SKILL.md

Decision already made: any file named exactly `devlog-index.md` or
`judgement-trail.md`, anywhere within a project-library (not only at
project root), is a historical log and is excluded from front-matter
scope — regardless of which folder it sits in.

Step C1 — Propose this as an addition to the same subsection drafted in
Step B1 (or its own adjacent subsection, whichever reads more naturally
in context) in mb-align-docs-function-scope.md. Show the exact proposed
text before writing anything.

Step C2 — Propose the corresponding addition to SKILL.md alongside the
Step B2 addition, so both exclusion rules are documented in the same
place. Show the exact proposed text before writing anything.

---

## Part D — Update alignment-log-template.md for the two new finding types

File: alignment-log-template.md

The inline `finding-type` comment and "Notes by finding-type" section
still only list the original three types
(reference-healing | identifier-change | register-mismatch).

Step D1 — Propose updating the inline comment to include all five current
finding types: reference-healing | identifier-change | register-mismatch
| missing-front-matter | incomplete-front-matter.

Step D2 — Propose two new entries under "Notes by finding-type":
  - **missing-front-matter** — `action-taken` states the full front-matter
    block that was written.
  - **incomplete-front-matter** — `action-taken` states which specific
    field(s) were added; pre-existing fields are never listed as changed.
Show the exact proposed text before writing anything.

---

## Part E — Update mb-align-docs-detector.md for the two new finding types

File: mb-align-docs-detector.md

The Responsibilities section's finding-classification line only names
the original three finding types, and doesn't mention that Detect also
runs the missing-front-matter / incomplete-front-matter check described
in SKILL.md.

Step E1 — Propose updating the Responsibilities section: add a bullet
describing that Detect also runs the missing-front-matter and
incomplete-front-matter check (per SKILL.md's Missing-front-matter check
section), and update the finding-classification bullet to list all five
current finding types. Show the exact proposed text before writing
anything.

---

## Part F — Minor completeness fix in SKILL.md's writer-text bullet

File: SKILL.md

Step F1 — In the "## Subagents" section, the writer-text bullet currently
mentions "missing-front-matter findings" but not "incomplete-front-matter
findings," even though both route to writer-text. Propose adding
"incomplete-front-matter" to that bullet. Show the exact proposed text
before writing anything.

---

## Part G — Replace folder-table shorthand with full literal paths

File: SKILL.md, "## Folders" table

Current table uses `...\` shorthand for four rows. Replace with the full
literal paths, exactly as follows:

| Folder | Holds |
|---|---|
| `C:\mybizz\logs\mb-align-docs\` | Permanent history, one record per run |
| `C:\mybizz\logs\mb-align-docs\learnings\` | Judgment calls from past runs |
| `C:\mybizz\logs\mb-align-docs\in-progress\` | Current run only — resume source if interrupted |
| `C:\mybizz\logs\mb-align-docs\last-completed-run\` | Full detail of most recent finished run |
| `C:\mybizz\logs\mb-align-docs\abandoned-runs\` | Declined-resume runs, kept, never deleted |

Step G1 — Propose this exact table replacement (only these five rows —
leave every other row in the Folders table untouched). Show the exact
proposed text before writing anything.

---

## Part H — Fix stale note in mb-align-docs-README.md

File: C:\dev\dev-root\mb-align-docs-README.md, Section B

Current text for the `dev-root-README.md` row reads: "Covers docmap.md
and project-inventory.md only. Pending rewrite by OpenCode from live
filesystem/doc research — no reliable original content exists to restore
from." This is stale — that rewrite is done; dev-root-README.md now
carries a "Verified/corrected 2026-07-27" note, not a pending-rewrite
warning.

Step H1 — Propose corrected text for that table row, describing
dev-root-README.md as covering docmap.md and project-inventory.md,
without the stale pending-rewrite language. Show the exact proposed text
before writing anything.

---

Step 1 — Precondition check.
Confirm the git working tree is clean for both repos in scope (the
skill-store folder's repo, and the dev-root repo) before proceeding. If
either is dirty, stop and report — do not proceed on that repo, but
report both.

Step 2 — Backup.
Take a full backup of both repos before any write. Save to
C:\backups-general\backup-mb-align-docs_<timestamp>\, one backup per
repo, timestamp per the mandatory method in
C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md,
format YYYY-MM-DDTHHMMSS+0200.

Step 3 — Present all proposals (Parts A through H, plus the Part 0
report) together, organized by part, before any write.

Step 4 — Approval.
Each part gets its own separate explicit approval — do not bundle unless
two parts touch the exact same file and insertion point (e.g. B2 and C2
may be shown and approved together since both land in the same SKILL.md
location).

Step 5 — Apply.
Only after approval, apply each approved change, one file at a time.
Re-read each file immediately after writing to confirm the change was
applied correctly, in the correct location, and that no other content in
the file was altered.

Step 6 — Report.
Confirm every part's outcome, quote the final inserted/changed text for
each, and confirm no other content in any file was altered beyond what
was approved. Explicitly confirm the Part 0 duplicate-file findings one
more time in this final report.

---

Hard constraints:
  - No writes before Step 1, Step 2, and Part 0 (duplicate check) are
    complete.
  - No writes without the Step 4 approval for each part.
  - Never alter any content in any file other than the specific additions
    described in Parts A–H.
  - Do not touch any file other than the ones named in Scope above.
  - Do not invent, add, or "improve" anything beyond what is explicitly
    described. If something else looks like it needs fixing, report it —
    do not act on it in this task.
  - If Part 0 finds genuine on-disk duplicates for any of the three
    filenames, stop and report before proceeding with any part of this
    task that touches that specific file.
