---
title: "README"
doc-id: "mb-386ec6b4"
updated: "2026-10-23"
---

# dev-root — README

`C:\dev\dev-root\` is the hub of the development folder. It holds one document.

| File | What it is |
|---|---|
| `docmap.md` | The navigation map of the Mybizz division: where every folder lives, what it is for, and where new files go. Its folder trees are rebuilt by `build-docmap.py` (see [[[mybizz-os-docs:operating-procedures/daily-ops\|Daily Ops]]](C:/mybizz/mybizz-os-docs/operating-procedures/daily-ops.md)). |

## If something looks wrong here

- Folder trees out of date: run `python3 /mnt/c/mybizz/scripts/build-docmap.py --write`, then give every entry marked "(new — add a description)" its description.
- Anything else in `docmap.md`: correct it directly.
