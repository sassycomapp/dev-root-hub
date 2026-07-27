Task: Replace UI folder files with the new 6-file scaffold model.
Scope is strictly limited to exactly two repos, each described fully below.
Do not touch any other repo, any other folder, or infer any work beyond
what is explicitly written in this prompt. If anything is unclear or not
explicitly covered here, stop and ask — do not extend, improve, invent, or
"helpfully" add anything not specifically instructed.

---

## Repo 1 — mb-3-cs-project-library (scaffold replacement in existing folders)

Path: C:\dev\dev-mb-3-cs\mb-3-cs-project-library\ui\

This repo's `ui\` folder already contains real, meaningful package and form
folders (e.g. `ui\analytics\DashboardAnalyticsForm\`,
`ui\analytics\RevenueReportForm\`,
`ui\analytics\RevenueReportForm\RevenueReportForm-RowTemplate\`, and any
others that exist under `ui\`).

Do NOT create, rename, move, or delete any package or form folder. Do NOT
touch any folder outside `ui\`. The folder structure itself is correct and
final — only the files inside each existing form-folder are being
replaced.

For every existing form-folder under `ui\` (a form-folder is any folder at
the lowest level under a package, containing — or meant to contain — the
UI file set; this includes nested sub-component form-folders such as
`RevenueReportForm-RowTemplate`), replace its contents with exactly these
six empty files, named using that form-folder's own name as {FORM-NAME}:

  {FORM-NAME}-wireframe-definition.md
  {FORM-NAME}-wireframe.html
  {FORM-NAME}-wireframe-chklist.md
  {FORM-NAME}-screen.html
  {FORM-NAME}-screen-chklist.md
  {FORM-NAME}-screen.png

All six files are created empty (zero content) except for the front-matter
block described below on the three files that require one. Do not write
any body content, placeholder text, comments, or example content into any
file beyond that required front-matter block. Do not invent additional
files. Do not invent additional form-folders. Do not infer or guess at
form-folders that "should" exist but do not currently exist on disk.

If a form-folder currently contains files that do not match this exact
six-file model (e.g. leftover files from the old wireframes/screens
structure), report every such file found before removing or replacing
anything. Do not silently delete unexpected content — list it, then stop
and wait for confirmation before removing it.

---

## Repo 2 — project-template (new parametrized example)

Path: C:\dev\project-template\dev-(SLUG)\(slug)-project-library\ui\

Create exactly one new parametrized example package/form, using these
literal placeholder tokens (do not substitute real names):

  ui\(PACKAGE-NAME)\(FORM-NAME)\
    (FORM-NAME)-wireframe-definition.md
    (FORM-NAME)-wireframe.html
    (FORM-NAME)-wireframe-chklist.md
    (FORM-NAME)-screen.html
    (FORM-NAME)-screen-chklist.md
    (FORM-NAME)-screen.png

Same rule as Repo 1: all six files empty except for front matter on the
three files that require it. Do not create more than this one example
package/form. Do not invent additional example packages or forms.

---

## Front-matter rule — applies identically in both repos

Exactly three of the six files per form-folder get a front-matter block:

  - {FORM-NAME}-wireframe-definition.md
  - {FORM-NAME}-wireframe-chklist.md
  - {FORM-NAME}-screen-chklist.md

Front-matter fields, per front-matter-schema.md
(C:\projects-reference\custom-skills-store\mb-align-docs\front-matter-schema.md):
  - document: the form-name plus a short label identifying which of the
    three file types it is (e.g. "RevenueReport-RowTemplate — Wireframe
    Definition")
  - doc-id: assigned sequentially per repo, continuing that repo's
    existing doc-id sequence (mb-3-cs-#### for Repo 1). For Repo 2
    (project-template), use the same parameterized doc-id convention
    already used elsewhere in that repo's front matter.
  - state: Live
  - date-created: generated using the mandatory method in
    C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md,
    format YYYY-MM-DDTHHMMSS+0200

The following three files never get front matter, in either repo:
  - {FORM-NAME}-wireframe.html
  - {FORM-NAME}-screen.html
  - {FORM-NAME}-screen.png

Do not add front matter to any file not explicitly listed above as
requiring it. Do not apply any judgment about whether a specific file
"seems like" it should have front matter — the three-file / three-file
split above is exact and total.

---

Step 1 — Precondition check.
Confirm the git working tree is clean for both repos before proceeding.
If either is dirty, stop and report — do not proceed on that repo, but
report both.

Step 2 — Backup.
Take a full backup of both repos before any write. Save to
C:\backups-general\backup-mb-align-docs_<timestamp>\, one backup per repo,
timestamp per the mandatory method above.

Step 3 — Detect and propose, no writes yet.
For mb-3-cs: list every existing form-folder found under `ui\`, and for
each, the current files present (flagging anything not matching the
six-file model, per the rule above). List the proposed doc-id, document
title, and date-created for each of the three front-mattered files per
form-folder.
For project-template: state the one example package/form folder to be
created, and the same three proposed front-matter sets.
Present as tables, one per repo. Report total form-folders found in
mb-3-cs and total files to be created/replaced across both repos.

Step 4 — Approval.
Present the full proposal for one batch approval per repo (two approvals
total — do not mix the two repos into a single approval, since they are
different kinds of action: replacement vs. new creation).

Step 5 — Apply.
Only after approval, create/replace files exactly as approved, one
form-folder at a time. Re-read each file immediately after writing to
confirm it was created correctly (empty, or with the exact approved
front-matter block) and that no extra content was added.

Step 6 — Update registers.
Add a register entry for each of the three front-mattered files per
form-folder, in the relevant register (register-local for mb-3-cs;
project-template's parameterized register-local for the example). Follow
register-template.md exactly
(C:\projects-reference\custom-skills-store\mb-align-docs\register-template.md).
Do not add register entries for the three non-front-mattered files
(wireframe.html, screen.html, screen.png) in either repo.

Step 7 — Report.
Confirm total files created/replaced per repo, total register entries
added per repo, and explicitly confirm: no folder was created, renamed,
moved, or deleted anywhere; mb4ecom, mb5pdlf, and makepdlf were not
touched in any way; no file beyond the exact six-file model was created in
any form-folder.

---

Hard constraints:
  - No writes before Step 1 and Step 2 are complete, per repo.
  - No writes without the Step 4 approval, per repo.
  - Do not touch mb4ecom-project-library, mb5pdlf-project-library, or
    makepdlf-project-library in any way — no reading, no writing, no
    folder creation. These are explicitly out of scope for this task.
  - Do not create, rename, move, or delete any folder anywhere, in either
    repo in scope.
  - Do not create more than one example package/form in project-template.
  - Do not invent, guess, or infer any package/form folder in mb-3-cs that
    is not already present on disk.
  - Do not add body content, placeholder text, or examples to any file
    beyond the required front-matter block on the three files that need
    one.
  - Do not add front matter to wireframe.html, screen.html, or screen.png,
    under any circumstance.
  - If anything encountered during Detect does not match what this prompt
    describes, stop and report it — do not resolve it by inventing a
    solution. Wait for explicit instruction.
