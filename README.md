# Comedy Workbook — AI-Powered Stand-Up System

A practical file-based system for developing stand-up comedy material with AI as your creative partner. Built and tested in real open-mic practice.

> 🇷🇺 [Русская версия](README.ru.md)

---

## What This Is

A folder structure + prompt system that turns your daily observations into polished stand-up material. No apps, no subscriptions — just Markdown files and an AI comedy buddy that knows your voice.

The system follows a natural creative pipeline:

```
Morning notes → Raw ideas → Joke development → Polished material → Set lists
```

Each stage has its own folder, templates, and a clear criterion for moving material forward.

## Why It Works

Most comedians lose material because there's no system — ideas scatter across phone notes, notebooks, voice memos. This workbook gives everything one place and one workflow.

The AI buddy (Claude, GPT-4, or any LLM) acts as a writing partner: analyzes premises, suggests punchlines, spots weak spots, and helps build callbacks. You stay in control — the AI handles first drafts and analysis.

**Easily adaptable** to other creative disciplines with regular content production: podcasting, songwriting, fiction writing.

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
│   ├── system-overview.md
│   ├── joke-structure.md
│   └── ai-workflow.md
├── workbook/                    ← Your actual working files
│   ├── 1-exercises/
│   ├── 2-ideas/
│   │   ├── morning-notes/
│   │   └── audio-notes/
│   ├── 3-in-development/
│   │   ├── personal-topics/
│   │   ├── social-topics/
│   │   └── observations/
│   ├── 4-ready/
│   ├── 5-setlists/
│   └── 6-performance-analysis/
└── examples/                    ← Sample files to get started
    ├── morning-note-example.md
    └── joke-development-example.md
```

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

Start with [`guide/system-overview.md`](guide/system-overview.md) to understand how material moves through the pipeline.

## The Daily Workflow

| Time | Activity | File |
|------|----------|------|
| Morning | Stream-of-consciousness writing | `2-ideas/morning-notes/` |
| Afternoon | Transcribe voice memos | `2-ideas/audio-notes/` |
| Evening | Develop promising material | `3-in-development/` |
| Weekly | Build set lists, review | `5-setlists/` |

## Tag System

Use tags in your files for quick filtering:

| Tag | Meaning |
|-----|---------|
| `#draft` | Raw idea, not yet developed |
| `#in-progress` | Actively working on it |
| `#tested` | Performed on stage |
| `#callback` | Can link to another bit |
| `#shelved` | Not working now, keep for later |

## Joke Quality Criteria

Before moving material from `3-in-development` to `4-ready`:
- [ ] Got a genuine laugh at least 3 times
- [ ] Setup is clear and concise
- [ ] Punchline lands without explanation
- [ ] Timing is worked out

## Tools

| Tool | Role | Required? |
|------|------|-----------|
| Any Markdown editor | Writing | Yes |
| [Obsidian](https://obsidian.md) | Navigation + graph view | Optional but recommended |
| Claude / GPT-4 / any LLM | AI comedy buddy | Optional but powerful |
| Git | Version control + backup | Optional |

## License

MIT — use freely, adapt for your own creative process.

---

*Built by a stand-up comic who got tired of losing good ideas.*
