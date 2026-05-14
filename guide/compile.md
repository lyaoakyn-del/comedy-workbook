# Compile Guide

## What Compilation Is

Compilation is a regular pass where you (or an AI) reads the source layer (`workbook/`) and updates the wiki layer (`wiki/`) to reflect the current state of your material.

Without compilation, the wiki becomes stale and loses its value as a navigation tool. With it, the AI always has an accurate map of your material without needing to read hundreds of source files.

```
workbook/ (source, live, personal)
    ↓  compile
wiki/ (compiled, navigable, AI-readable)
    ↓  query
Set lists, development decisions, callback maps
```

---

## What Goes Where

### `workbook/` — Source Layer

Everything goes here first. Raw, personal, unfiltered.
- Morning notes, voice transcriptions → `2-ideas/`
- Joke drafts and iterations → `3-in-development/`
- Tested, working bits → `4-ready/`
- Set plans and post-show notes → `5-setlists/`, `6-performance-analysis/`

**Rule:** never put compiled summaries in the source layer. Keep it raw.

### `wiki/` — Compiled Layer

Synthesized overviews. Not copies of source files — distillations.
- `INDEX.md` — always-first-read entry point
- `material-index.md` — all bits by theme, status, stage
- `morning-notes-hub.md` — patterns from raw notes
- `theme-index.md` — cross-cutting theme and callback map
- `setlist-index.md` — performance history and set templates
- `intake.md` — buffer for new items not yet in canonical wiki

**Rule:** wiki files should be readable without opening any source file.

---

## Compile Frequency

| Trigger | What to compile |
|---------|----------------|
| After every writing session | Update `intake.md` with anything new |
| Weekly (Sunday or Monday) | Full compile pass — all section hubs |
| After every show | Update `setlist-index.md` + promote bits to `4-ready/` if earned |
| Monthly | Theme audit — is your material balanced? |

---

## The Weekly Compile Pass (Manual)

**Takes ~20 minutes.**

1. **Open `intake.md`** — process all `new` items. Promote or reject.

2. **Scan `2-ideas/morning-notes/`** — read the week's notes. Add to `morning-notes-hub.md`:
   - Any new recurring themes
   - 2-3 most promising raw observations

3. **Scan `3-in-development/`** — update `material-index.md`:
   - Add any new files
   - Update status (any bits ready to move to `4-ready/`?)
   - Update callback map

4. **Check `4-ready/`** — confirm the list in `material-index.md` is accurate.

5. **Update `theme-index.md`** — add emerging themes from this week's notes.

6. **Update `wiki/INDEX.md`** — update file counts and date.

---

## The AI Compile Pass

Ask your AI buddy to run the compile. Give it this prompt:

```
Read the files in workbook/ that have changed this week and update the wiki/ layer.

Specifically:
1. Scan this week's morning notes in workbook/2-ideas/morning-notes/
   → Update wiki/morning-notes-hub.md with new recurring themes and promising observations

2. Scan workbook/3-in-development/ for new or updated files
   → Update wiki/material-index.md (add new bits, update statuses)

3. Check wiki/intake.md for unprocessed items
   → Promote done items to the relevant hub

4. Update wiki/INDEX.md with today's date and accurate file counts

Do not invent material. Only compile what exists in the source files.
Flag anything that looks stale or inconsistent.
```

---

## Frontmatter Rules

Every wiki file needs frontmatter for machine readability:

```yaml
---
id: wiki-[slug]
title: [Human-readable title]
type: index | section-hub | theme-hub | intake
domain: comedy
status: active | stale | archived
source_paths:
  - workbook/[relevant-folder]/
related:
  - [other-wiki-file-id]
updated: YYYY-MM-DD
---
```

**Required fields:** `id`, `title`, `type`, `status`, `updated`
**Optional but useful:** `source_paths`, `related`

---

## What Not to Compile

- **Every morning note** — only patterns and promising observations go in `morning-notes-hub.md`
- **Every joke draft** — only the summary table row goes in `material-index.md`
- **Full joke text** — stays in source, wiki only has title + status + theme
- **Personal details** — compile the theme, not the specifics

---

## Health Check

Run this monthly. Ask AI:

```
Read wiki/INDEX.md and all wiki/ section hubs.
Run a health check:
1. Which bits in material-index.md haven't moved stage in 30+ days?
2. Are there themes in theme-index.md with no ready material?
3. Are there morning note patterns that never became bits?
4. Is any wiki file stale (updated date > 30 days)?

Give me a short action list.
```
