# CLAUDE.md

When starting work on this project, read `README.md` first to build context: what the project is, how to run it, and how to contribute. You don't need to re-read it for every task — refer back when needed.

This file supplements `README.md` with information AI agents need close at hand while working: concise commands, coding conventions, project gotchas, and invariants that are not obvious from the code. Some overlap with `README.md` is intentional, so agents can act without searching the full README.

## Documentation sync

Whenever you change code, check and update the following in the same commit:

- `README.md` (audience: anyone — human or AI): update if the change affects what the project is, how to run it, environment setup, public behavior, or contribution workflow.
- `CLAUDE.md` (audience: Claude / agents): update if the change affects build/test/run commands listed here, coding conventions, project gotchas, invariants, or any other rule described in this file.

## Reading `always-show-steam-wishlist-rank.user.js`

The `@icon` line in the UserScript metadata block embeds an icon as a
base64 `data:` URI. That single line is tens of thousands of tokens and
will blow up any full-file read.

**Before reading the file, locate the `@icon` line and skip it.** Its line
number is not fixed — the metadata block may change — so find it each time
rather than assuming a position:

```bash
grep -n "@icon" always-show-steam-wishlist-rank.user.js | cut -c1-60
```

Then read the ranges around it (e.g. the metadata header above it and the
script body below it) with `Read` using `offset`/`limit`, avoiding that line.
