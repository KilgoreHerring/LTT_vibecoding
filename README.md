# Vibe Coding Hackathon - Facilitator Kit

A 90-minute workshop where people build real working apps using Claude Code - no programming experience needed. This repo is everything you need to run it, for any organisation and any domain.

Each group copies this folder, opens it in Claude Code, and `CLAUDE.md` loads automatically as the session instructions. Designed to be run across many groups in parallel, with one facilitator per group acting as a guide rather than a builder.

---

## Folder structure

```
/
├── CLAUDE.md              Session instructions - loaded automatically by Claude Code
├── starter.html           Blank HTML template with the Base Design System pre-loaded
├── docs-viewer.html       Open locally to browse the docs in a browser
├── .env.example           Template for API keys - copy to .env (gitignored) and fill in
├── .claude/commands/      Slash commands that drive the session
├── docs/                  Facilitator reference - read before, don't edit during
├── mockdata/              Sample data for a fictional firm to build against
└── example/               A complete example session, built during a test run
```

The root folder is the **session template** - copy it fresh for each group. The `example/` folder shows what a finished session looks like.

---

## What's in docs/

| File | Purpose |
|---|---|
| `SCENE_SETTER.md` | Pre-session briefing for participants |
| `DISCOVERY.md` | Discovery questions to work through as a group |
| `DESIGN_BRIEF.md` | Design brief template to complete before building |
| `USE_CASES.md` | App ideas to spark something |
| `BUILDING_GUIDE.md` | Tips for prompting Claude during the build |
| `DESIGN.md` | The Base Design System: colours, typography, CSS starter block, 6 style presets |
| `MOCK_DATA.md` | What's in `mockdata/` and how to use it |
| `SHIPPING_CHECKLIST.md` | Post-build reflection on what it would take to ship |
| `SHIPPING.md` | A generic prototype-to-production reference |
| `FACILITATOR_GUIDE.md` | Notes for the people running each table |
| `DAY_PLAN.md` | One-page participant handout for the day |
| `RUN_SHEET.md` | Organiser choreography for running many groups in parallel |
| `OPENING_DECK.html` | An editable opening deck to set the room before groups split out |

---

## How to run a session

**Before the day:**
1. Copy this folder - one copy per group.
2. Install [Claude Code](https://claude.com/claude-code) on each machine.
3. Open the folder in Claude Code - `CLAUDE.md` loads automatically.
4. Read [docs/FACILITATOR_GUIDE.md](docs/FACILITATOR_GUIDE.md) and [docs/RUN_SHEET.md](docs/RUN_SHEET.md).
5. If you're using API keys for the day, copy `.env.example` to `.env` and fill them in (never commit `.env`).
6. If running a scenario-based session, drop source documents into a `materials/` folder.
7. Fill in the `[bracketed placeholders]` in `docs/OPENING_DECK.html` and `docs/DAY_PLAN.md` with your hackathon name, date and venue.

**On the day**, run the session in five phases:

| Time | Phase |
|---|---|
| 0-15 min | Discovery - work through [docs/DISCOVERY.md](docs/DISCOVERY.md) |
| 15-20 min | Design brief - complete [docs/DESIGN_BRIEF.md](docs/DESIGN_BRIEF.md), then run `/kickoff` |
| 20-55 min | Build - iterate with Claude |
| 55-70 min | Polish - tighten the UI, no new features |
| 70-75 min | Run `/onepager` (fast) - or `/present` for a full slide deck if time allows - and open it in the browser |
| 75-90 min | Present - 5 minutes per group |

**If a group arrives with a clear idea**, skip Discovery and Design Brief. Describe the idea to Claude and run `/kickoff` straight away.

---

## Build stack

The default is **no build and no install**: a single `index.html` opened directly in the browser. It is the fastest path for a 90-minute session driven by non-coders, and the right choice for almost every group.

Frameworks (Next.js, Vite, React, a Python backend) are allowed when a group wants one and the facilitator is comfortable with the tooling - just remember that setup time eats into the 90 minutes. See the "Build Stack" section of `CLAUDE.md` for the full guidance.

---

## Slash commands

| Command | What it does |
|---|---|
| `/kickoff` | Creates `PLAN.md` from the design brief - starts the build |
| `/handover` | Saves session state to `HANDOVER.md` before closing the chat |
| `/pickup` | Restores full context at the start of a new chat |
| `/onepager` | Generates `onepager.html` - a fast one-page summary (the quick demo option) |
| `/present` | Generates `presentation.html` - a fuller slide deck if you have time |
| `/styles` | Lists 6 visual style presets (`/style-chelsea`, `/style-midnight`, ...) to reskin a group's app |

---

## Design system

All apps use the Base Design System defined in [docs/DESIGN.md](docs/DESIGN.md). When prompting Claude, include:

> "Use the Base Design System from docs/DESIGN.md"

Or copy `starter.html` as your starting point - it has the full CSS already loaded.

Want a group's app to stand out? Six **style presets** can reskin it (visuals only) - run `/styles` for the menu, or see the presets section in [docs/DESIGN.md](docs/DESIGN.md). Best applied during polish, near the end.

---

## Mock data and API keys

`mockdata/` contains invented data for a fictional professional-services firm (people, clients, matters, emails, a calendar, documents, news, a clause library). It lets groups build realistic demos without touching anything confidential. See [docs/MOCK_DATA.md](docs/MOCK_DATA.md). Bring your own domain data via `materials/` if you prefer.

The kit ships with **no API keys**. If a build needs a model or API, copy `.env.example` to `.env` and add the keys the organisers provide for the day. `.env` is gitignored - never commit it or paste keys into chat.
