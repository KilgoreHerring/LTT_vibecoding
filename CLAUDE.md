# Vibe Coding Hackathon

You're about to build a real working app in about 90 minutes. You don't need to know how to code - your ideas do the work, Claude writes the code. Your facilitator is here to help.

---

## Session Timeline

| Time | What's happening |
|---|---|
| 0-15 min | Discovery - work through [docs/DISCOVERY.md](docs/DISCOVERY.md) as a group |
| 15-20 min | Design brief - complete [docs/DESIGN_BRIEF.md](docs/DESIGN_BRIEF.md), then run `/kickoff` |
| 20-55 min | Build - iterate with Claude |
| 55-70 min | Polish - tighten the UI, handle edge cases, no new features. Run `/styles` to give your app a distinct look |
| 70-75 min | Run `/onepager` (fast) for a one-page summary - or `/present` for a full slide deck if time allows - and open it in the browser |
| 75-90 min | Present - 5 minutes per group to the wider room |

**If your group arrives with a clear idea already formed**, skip Discovery and Design Brief entirely. Describe your idea to Claude and run `/kickoff` straight away. Don't lose 20 minutes on process when you're already ready to build.

---

## Commands

| Command | When | What it does |
|---|---|---|
| `/kickoff` | Start of build | Creates `PLAN.md` with your app spec |
| `/handover` | Before closing a chat | Saves session state to `HANDOVER.md` |
| `/pickup` | Start of a new chat | Restores full context from saved files |
| `/onepager` | Demo time | Generates `onepager.html` - a fast one-page summary (the quick demo option) |
| `/present` | Demo time | Generates `presentation.html` - a fuller slide deck if you have time |
| `/styles` | Polish | Lists 6 visual style presets you can apply to your app to make it look distinct |

---

## Core Principles

**Keep it simple.** Build the smallest version that solves the real problem. Every extra feature is scope that might not get done.

**One screen, one job.** Don't build 12 tabs. Build one thing that works really well.

**Design for the actual user.** Name your user, give them a specific moment. Specific beats general every time.

**Show, don't tell.** Have a demo story ready: "Imagine Priya, an analyst on her first day with a new dataset..."

**Working beats perfect.** A rough app that demos is worth more than a polished one that doesn't exist.

**Stick to the house style.** Every app uses the Base Design System (docs/DESIGN.md) by default. Don't invent a bespoke colour scheme or theme. The only alternative looks are the six `/style-*` presets, applied only when a group runs one (or `/styles` to choose). If a group wants a different look, point them to `/styles` rather than designing something from scratch.

---

## Build Stack

The goal is a working demo in 90 minutes, driven mostly by people who don't code. The stack should get out of the way.

**Default: no build, no install.** A single `index.html` (or a small set of HTML/CSS/JS files) opened directly in the browser. No npm, no server, no framework. This is the fastest path and the right choice for almost every group. Inline any data you need (see mock data below) so it runs straight from a `file://` URL. `/kickoff` sets this up by copying `starter.html` to `index.html`.

**Frameworks are allowed when a group wants them.** If a group has a real reason to use Next.js, Vite, React, a Python backend, or anything else, that's fine, as long as the facilitator is comfortable with the tooling and the group accepts that setup time eats into the 90 minutes. If you go this route:

- Scaffold with the standard tool (`npm create vite@latest`, a Next.js app, a small Python script, whatever fits) and get the dev server running early so there's a live preview from minute one.
- Keep the same discipline: smallest thing that demos, one job done well, the Base Design System tokens drop straight into a `globals.css` or Tailwind theme.
- Make sure it actually runs for the demo. A framework app that won't start at minute 88 is worse than a single HTML file that does.

**Rails for either path:** avoid databases and real backends unless the idea genuinely needs one - `localStorage` or in-memory state covers most demos. Don't add a build step the group didn't ask for. Prefer the boring, reliable option over the clever one.

---

## Guides & Resources

| When you need... | Go to |
|---|---|
| Pre-session briefing for participants | [docs/SCENE_SETTER.md](docs/SCENE_SETTER.md) |
| Help figuring out what to build | [docs/DISCOVERY.md](docs/DISCOVERY.md) |
| Planning the app before you build | [docs/DESIGN_BRIEF.md](docs/DESIGN_BRIEF.md) |
| Use case ideas to spark something | [docs/USE_CASES.md](docs/USE_CASES.md) |
| Tips on prompting and iterating | [docs/BUILDING_GUIDE.md](docs/BUILDING_GUIDE.md) |
| Colours, fonts, components, CSS starter block | [docs/DESIGN.md](docs/DESIGN.md) |
| A distinct visual style for your app (6 presets) | Run `/styles`, or see the presets section in [docs/DESIGN.md](docs/DESIGN.md) |
| Sample firm data (emails, matters, calendar, documents...) | [docs/MOCK_DATA.md](docs/MOCK_DATA.md) |
| End-of-session shipping checklist | [docs/SHIPPING_CHECKLIST.md](docs/SHIPPING_CHECKLIST.md) |
| What it would take to ship for real | [docs/SHIPPING.md](docs/SHIPPING.md) |
| Facilitator notes | [docs/FACILITATOR_GUIDE.md](docs/FACILITATOR_GUIDE.md) |

## APIs and Keys

The kit ships with **no API keys**. If your idea calls a language model or another API, the facilitator supplies the keys for the day.

- Copy `.env.example` to `.env` and paste in the keys the organisers give you. `.env` is gitignored and must **never** be committed or pasted into chat.
- The common providers (Anthropic, OpenAI, Google) all work for text tasks. Default to the small/fast model tier (for example Claude Haiku, GPT mini, Gemini Flash) for every build - they are fast, cheap, and good enough for a demo. Only step up to a larger model if you hit a real quality wall, and ask the facilitator first.
- For a single-file browser demo, the simplest pattern is a key-entry box in the UI so nothing is hardcoded. For anything more substantial, load the key from `.env` server-side. Either way, do not ship code with a real key baked into it.

---

## What Goes Where

**`docs/`** - Setup and reference material. Read it before the session, don't change it during.

**Root folder** - Your live workspace. Everything generated during the session lands here: `PLAN.md`, app code, `onepager.html` / `presentation.html`, `HANDOVER.md`.

**`materials/`** - Anything your group brings in: sample documents, spreadsheets, emails, scenario data. Drop files here before the session and tell Claude "there are reference documents in materials/" when you kick off. Nothing in this folder is required - only use it if you have source material to work from.

**`mockdata/`** - Pre-built fake data for a fictional professional-services firm. If your idea needs emails, a matter list, a calendar, a fake inbox, sample documents, news or a clause library, **start here** rather than asking Claude to invent data on the fly. Read [docs/MOCK_DATA.md](docs/MOCK_DATA.md) for the full catalogue and how to use it. The default pattern is to tell Claude to inline the relevant JSON into your app so the demo works from a `file://` URL. Anchor "today" is 15 May 2026. Everything in it is invented - never replace it with real or confidential information.

**`example/`** - A complete worked example session, built end to end (a litigation simulator), with its `PLAN.md`, materials, generated app and presentation. Look at it to see what a finished session looks like. It was built across more than one session, so don't treat its polish as the 90-minute bar.
