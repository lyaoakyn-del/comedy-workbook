# Comedy Workbook — AI-Powered Stand-Up System

A practical file-based system for developing stand-up comedy material with AI as your creative partner. Built and tested in real open-mic practice.

> 🇷🇺 [Русская версия](README.ru.md)

---

## What This Is

A folder structure + prompt system that turns your daily observations into polished stand-up material. No apps, no subscriptions — just Markdown files and an AI comedy buddy that knows your voice.

The system follows a natural creative pipeline:

```
Morning notes → Raw ideas → Joke development → Polished material → Set lists
     ↓                                                                  ↓
                      Weekly compile pass
                             ↓
              wiki/ — AI-readable index of everything
```

Each stage has its own folder, templates, and a clear criterion for moving material forward. The wiki layer keeps the AI oriented without it having to read hundreds of source files.

**Easily adaptable** to other creative disciplines with regular content production: podcasting, songwriting, fiction writing.

---

## Why the Wiki Layer Matters

After a few months of daily writing, you'll have 200+ files. Without a compiled index, two things happen:

1. **The AI gets lost** — it reads random source files and misses the bigger picture. It doesn't know which bits are ready, which themes you've overused, or where the callback opportunities are.
2. **You get lost** — you forget what's in development, lose track of shelved material, and rebuild the same set every time instead of building on what works.

The `wiki/` folder solves both. It's a compiled, always-current map of your material that both you and the AI can navigate in seconds.

```
workbook/  →  compile  →  wiki/
(200+ files,               (5 index files,
 raw and personal)          AI-readable)
```

The AI reads `wiki/INDEX.md` first, then the relevant section hub — and already knows the state of your entire material library before you've asked a single question.

---

## Structure

```
comedy-workbook/
├── CLAUDE.md                    ← AI comedy buddy instructions
├── templates/                   ← Reusable file templates
│   ├── morning-note.md
│   ├── joke-development.md
│   ├── set-list.md
│   ├── performance-analysis.md
│   └── audio-transcription.md
├── guide/                       ← System methodology
│   ├── system-overview.md       ← Start here
│   ├── joke-structure.md
│   ├── ai-workflow.md
│   └── compile.md               ← How to run a compile pass
├── workbook/                    ← Your actual working files (private)
│   ├── 1-exercises/
│   ├── 2-ideas/
│   │   ├── morning-notes/
│   │   └── audio-notes/
│   ├── 3-in-development/
│   ├── 4-ready/
│   ├── 5-setlists/
│   └── 6-performance-analysis/
├── wiki/                        ← Compiled indexes (AI entry point)
│   ├── INDEX.md                 ← Always read first
│   ├── material-index.md        ← All bits by stage and theme
│   ├── morning-notes-hub.md     ← Patterns from raw notes
│   ├── theme-index.md           ← Cross-cutting themes + callback map
│   ├── setlist-index.md         ← Performance history + set templates
│   └── intake.md                ← Buffer for new items
└── examples/                    ← Sample files to get started
```

---

## Quick Start

**1. Clone the repo**
```bash
git clone https://github.com/YOUR_USERNAME/comedy-workbook.git
cd comedy-workbook
```

**2. Open in your editor**

Works with any Markdown editor. [Obsidian](https://obsidian.md) is recommended — it renders links between files and gives a graph view of your material connections.

**3. Set up your AI buddy**

Copy the contents of `CLAUDE.md` into your AI system prompt (Claude Projects, ChatGPT custom instructions, or any LLM interface).

**4. Start your first morning note**

```bash
cp templates/morning-note.md workbook/2-ideas/morning-notes/$(date +%Y-%m-%d)_morning.md
```

Open the file, write for 10 minutes without editing. That's it.

**5. Read the guide**

Start with [`guide/system-overview.md`](guide/system-overview.md).

---

## The Daily Workflow

| Time | Activity | Where |
|------|----------|-------|
| Morning | Stream-of-consciousness writing | `workbook/2-ideas/morning-notes/` |
| Afternoon | Transcribe voice memos | `workbook/2-ideas/audio-notes/` |
| Evening | Develop promising material | `workbook/3-in-development/` |
| Weekly | Compile pass + set list review | `wiki/` + `workbook/5-setlists/` |
| After show | Log performance, promote ready bits | `wiki/setlist-index.md` |

---

## The Weekly Compile Pass

Once a week (~20 minutes), update the wiki to reflect the current state of your material.

**Manual:** follow [`guide/compile.md`](guide/compile.md) step by step.

**With AI:** paste this prompt:

```
Read this week's morning notes in workbook/2-ideas/morning-notes/
and any updated files in workbook/3-in-development/.

Update the wiki/ section hubs:
- wiki/morning-notes-hub.md: add new recurring themes and promising observations
- wiki/material-index.md: add new bits, update statuses
- wiki/intake.md: process any unhandled items

Then update wiki/INDEX.md with today's date.
Do not invent material. Only compile what exists.
```

The AI does the work. You review and commit.

---

## Tag System

| Tag | Meaning |
|-----|---------|
| `#draft` | Raw idea, not yet developed |
| `#in-progress` | Actively working on it |
| `#tested` | Performed on stage |
| `#callback` | Can link to another bit |
| `#shelved` | Not working now, keep for later |

---

## Joke Quality Criteria

Before moving from `3-in-development` to `4-ready`:
- [ ] Got a genuine laugh at least 3 times
- [ ] Setup is clear and concise
- [ ] Punchline lands without explanation
- [ ] Timing is worked out

---

## Tools

| Tool | Role | Required? |
|------|------|-----------|
| Any Markdown editor | Writing | Yes |
| [Obsidian](https://obsidian.md) | Navigation + graph view | Optional but recommended |
| Claude / GPT-4 / any LLM | AI comedy buddy + compiler | Optional but powerful |
| Git | Version control + backup | Optional |

---

## License

MIT — use freely, adapt for your own creative process.

---

*Built by a stand-up comic who got tired of losing good ideas.*

*Joke structure principles informed by [The Comedy Bible](https://www.judycarter.com/) (Judy Carter) and standard stand-up craft.*
