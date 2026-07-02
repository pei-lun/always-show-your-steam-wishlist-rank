# CLAUDE.md

## Reading `always-show-your-steam-wishlist-rank.user.js`

The `@icon` line in the UserScript metadata block embeds an icon as a
base64 `data:` URI. That single line is tens of thousands of tokens and
will blow up any full-file read.

**Before reading the file, locate the `@icon` line and skip it.** Its line
number is not fixed — the metadata block may change — so find it each time
rather than assuming a position:

```bash
grep -n "@icon" always-show-your-steam-wishlist-rank.user.js | cut -c1-60
```

Then read the ranges around it (e.g. the metadata header above it and the
script body below it) with `Read` using `offset`/`limit`, avoiding that line.
