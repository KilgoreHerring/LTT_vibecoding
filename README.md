# Vibe Coding Hackathon - Build Kit

A starting scaffold for building a real, working app over a day or two using an AI coding agent. You don't need to be a developer. You describe what you want, the agent writes the code, you steer.

This repo is an **optional kickstart**. Clone it, open it in your agent, and you get a design system, sample data, a starter template, and a few commands to keep a multi-session build organised. If you'd rather start from a blank folder, that's fine too.

Built for **Claude Code** or **ChatGPT Codex**. It won't add much in Replit or Google AI Studio - it relies on an agent that reads the repo's files (`CLAUDE.md` for Claude Code, `AGENTS.md` for Codex) and can run commands.

---

## How the event works

| When | What's happening |
|---|---|
| Day 1, morning | Everyone together: a couple of talks, demos, and mentors on hand. Pick an idea. |
| Day 1 to Day 2 | Build. Roughly 24 hours, self-serve, at your own pace. Mentors around for advice. |
| Day 2, afternoon | Present back: what you built, a live demo, and what it would take to ship. |

You have real time and an agent doing the typing, so aim higher than one tiny feature. Scope a core you can get working, then build out.

---

## Getting started

1. Install [Claude Code](https://claude.com/claude-code), or use ChatGPT Codex.
2. Clone or download this repo and open the folder in your agent. `CLAUDE.md` (or `AGENTS.md`) loads as the standing instructions.
3. Read [docs/SCENE_SETTER.md](docs/SCENE_SETTER.md) and [docs/BUILDING_GUIDE.md](docs/BUILDING_GUIDE.md) if you're new to this.
4. Work out what you're building ([docs/DISCOVERY.md](docs/DISCOVERY.md), [docs/DESIGN_BRIEF.md](docs/DESIGN_BRIEF.md)), then run `/kickoff` to turn it into a plan.
5. If your build needs API keys, copy `.env.example` to `.env` and add them. Never commit `.env`.
6. Build. Run `/handover` before you stop, `/pickup` when you come back.

---

## What's in here

```
/
├── CLAUDE.md              Standing instructions - loaded by Claude Code
├── AGENTS.md              The same instructions for ChatGPT Codex
├── starter.html           Blank HTML template with the Base Design System pre-loaded
├── docs-viewer.html       Open locally to browse the docs in a browser
├── .env.example           Template for API keys - copy to .env (gitignored) and fill in
├── .claude/commands/      Slash commands that drive the build
├── docs/                  Reference: scene-setter, discovery, design brief, building guide, design system, shipping
└── mockdata/              Sample data for a fictional firm to build against
```

### docs/

| File | Purpose |
|---|---|
| `SCENE_SETTER.md` | What this is and how the two days work |
| `DISCOVERY.md` | Questions to work out what you're building |
| `DESIGN_BRIEF.md` | Turn the idea into a plan before building |
| `BUILDING_GUIDE.md` | How to work with an AI coding agent (start here if it's your first time) |
| `USE_CASES.md` | Ideas to spark something |
| `DESIGN.md` | The Base Design System: colours, typography, CSS starter block, 6 style presets |
| `MOCK_DATA.md` | What's in `mockdata/` and how to use it |
| `SHIPPING_CHECKLIST.md` | Demo-prep reflection on what it would take to ship |
| `SHIPPING.md` | A generic prototype-to-production reference |
| `DAY_PLAN.md` | One-page participant handout for the event |
| `OPENING_DECK.html` | An editable opening deck for the day-1 session |

---

## Slash commands

| Command | What it does |
|---|---|
| `/kickoff` | Turns your idea into a phased `PLAN.md` and starts the build |
| `/handover` | Saves session state to `HANDOVER.md` before you stop |
| `/pickup` | Reloads full context when you come back or start a new chat |
| `/onepager` | Generates `onepager.html` - a one-page summary |
| `/present` | Generates `presentation.html` - a slide deck for presenting back |
| `/styles` | Lists 6 visual style presets (`/style-chelsea`, `/style-midnight`, ...) to reskin your app |

`/handover` and `/pickup` matter most over a two-day build: they carry context across sessions (and overnight) so the agent always knows where you left off.

---

## Build stack

Use whatever fits the idea. A real framework (Next.js, Vite + React) is a fine default over a day or two and gives you a clear path to deploying. No-build single-file HTML is the lightweight option and the fastest way to see something on screen. See the "Build Stack" section of `CLAUDE.md`.

---

## Design system

All apps use the Base Design System in [docs/DESIGN.md](docs/DESIGN.md). When prompting the agent, say "Use the Base Design System from docs/DESIGN.md", or start from `starter.html`. Want a distinct look? Run `/styles` for six presets, best applied during polish.

---

## Mock data and API keys

`mockdata/` holds invented data for a fictional professional-services firm (people, clients, matters, emails, a calendar, documents, news, a clause library), so you can build a realistic demo without touching anything confidential. Bring your own domain data via a `materials/` folder if you prefer.

The kit ships with **no API keys**. If a build needs a model or API, copy `.env.example` to `.env` and add your own. `.env` is gitignored - never commit it or paste keys into chat.
