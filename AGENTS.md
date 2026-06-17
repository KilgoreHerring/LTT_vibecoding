# Vibe Coding Hackathon - Build Kit

You're building a real, working app over the next day or so, using an AI coding agent. You don't need to be a developer. You describe what you want, the agent writes the code, you steer. This repo is an optional kickstart: a starting scaffold, a design system, sample data, and a few commands to keep you organised. Use it, or strip it out and go your own way.

This file is your agent's standing instructions. This is the ChatGPT Codex copy. (If you are using Claude Code, the same content is in `CLAUDE.md`.)

---

## The Two Days

| When | What's happening |
|---|---|
| Day 1, morning | Everyone together: a couple of talks, demos, and mentors on hand. Pick an idea. |
| Day 1 to Day 2 | Build. Roughly 24 hours, self-serve, at your own pace. Mentors around for advice. Keep going into the evening if you want to. |
| Day 2, afternoon | Present back: what you built, a live demo, and what it would take to ship. |

You have far more time than a typical hackathon taster, and an AI agent doing the typing. The limit on what you build is how clearly you can describe it, not how fast you can code. Aim higher than one tiny feature.

---

## Commands

| Command | When | What it does |
|---|---|---|
| `/kickoff` | Start of your build | Turns your idea into a `PLAN.md` with phased milestones |
| `/handover` | Before you stop or close the chat | Saves session state to `HANDOVER.md` so you can resume cleanly |
| `/pickup` | When you come back / start a new chat | Reloads `PLAN.md` + `HANDOVER.md` + `DECISIONS.md` and briefs you |
| `/onepager` | Demo prep | Generates `onepager.html` - a one-page summary you can hand round |
| `/present` | Demo prep | Generates `presentation.html` - a slide deck for presenting back |
| `/styles` | Polish | Lists 6 visual style presets to give your app a distinct look |

`/handover` and `/pickup` are the backbone of a two-day build. Context doesn't survive forever in a single chat, and you'll likely work across several sessions (and maybe overnight). Run `/handover` before you break, `/pickup` when you return, and the agent picks up exactly where you left off.

---

## Working with an AI coding agent

If this is your first time, a few things that make it go well:

- **Give a clear opening brief.** Who it's for, the one main thing it does, the two or three features it needs. Specific beats vague every time.
- **Build the core first, then add.** Get one thing working end to end before you describe the next. Test each change before moving on.
- **One change per message.** Asking for five things at once gives muddled results.
- **Describe problems precisely.** "When I click submit nothing happens, I expected a confirmation" is far more useful than "it's broken".
- **You can always ask the agent to explain or to undo.** "That's not what I meant, revert that and try a different approach" is a normal thing to say.
- **Save your progress.** If you know git, commit as you go. If you don't, just run `/handover` before you stop so nothing is lost.

`docs/BUILDING_GUIDE.md` goes deeper on all of this.

---

## Core Principles

**Get something working end to end early.** A thin slice that actually runs beats a half-built grand design. Then layer features on top.

**Scope an MVP first, then build out.** You have time for a real, multi-feature tool, but earn it: pick the core, make it work, then add. The plan from `/kickoff` is built this way.

**Design for a real user.** Name them, give them a specific moment they'd use this. Specific beats general.

**Show, don't tell.** Have a demo story ready: "Imagine Priya, an analyst staring at a 40-page export she has to summarise by Friday..."

**Stick to the house style.** Every app uses the Base Design System (`docs/DESIGN.md`) by default. Don't invent a bespoke colour scheme. The only alternative looks are the six `/style-*` presets. If you want a different feel, run `/styles`.

---

## Build Stack

You're building over a day or two, so use whatever stack fits the idea. There's no single-file rule here.

- **A real framework is a fine default.** Next.js or Vite with React gives you a proper app with a dev server, components, and a clear path to deploying it (Vercel) if you want to take it further. If you go this route, scaffold it early (`npm create vite@latest`, or a Next.js app) so you have a live preview from the start. The Base Design System tokens drop straight into a `globals.css` or a Tailwind theme.
- **No-build single-file HTML is the lightweight option.** One `index.html` opened in the browser, no install, no server. Genuinely good for a focused tool, and the fastest way to see something on screen. `/kickoff` sets this up by copying `starter.html` to `index.html`. Inline any data you need so it runs from a `file://` URL.

Either way: get it running early, keep it runnable, and don't add a backend or database unless the idea genuinely needs one. `localStorage` or in-memory state covers a lot.

---

## Guides & Resources

| When you need... | Go to |
|---|---|
| What this is and how the days work | [docs/SCENE_SETTER.md](docs/SCENE_SETTER.md) |
| Help figuring out what to build | [docs/DISCOVERY.md](docs/DISCOVERY.md) |
| Planning the app before you build | [docs/DESIGN_BRIEF.md](docs/DESIGN_BRIEF.md) |
| Use case ideas to spark something | [docs/USE_CASES.md](docs/USE_CASES.md) |
| Tips on working with the agent | [docs/BUILDING_GUIDE.md](docs/BUILDING_GUIDE.md) |
| Colours, fonts, components, CSS starter block | [docs/DESIGN.md](docs/DESIGN.md) |
| A distinct visual style (6 presets) | Run `/styles`, or see the presets in [docs/DESIGN.md](docs/DESIGN.md) |
| Sample data to build against | [docs/MOCK_DATA.md](docs/MOCK_DATA.md) |
| Demo prep / shipping reflection | [docs/SHIPPING_CHECKLIST.md](docs/SHIPPING_CHECKLIST.md) |
| What it would take to ship for real | [docs/SHIPPING.md](docs/SHIPPING.md) |

## APIs and Keys

This kit ships with **no API keys**. If your idea calls a language model or another API:

- Copy `.env.example` to `.env` and add your own keys (or any the organisers provide). `.env` is gitignored and must **never** be committed or pasted into chat.
- Anthropic, OpenAI and Google all work for text tasks. Default to the small/fast model tier (for example Claude Haiku, GPT mini, Gemini Flash) - fast, cheap, and good enough for a demo. Step up only if you hit a real quality wall.
- For a no-build browser app, the simplest pattern is a key-entry box in the UI. For a framework app, keep the key server-side (an API route), never in client code. Either way, don't ship a key baked into the source.

---

## What Goes Where

**`docs/`** - Setup and reference material. Read it, don't rely on changing it.

**Root folder** - Your live workspace. Everything you generate lands here: `PLAN.md`, your app code, `onepager.html` / `presentation.html`, `HANDOVER.md`.

**`materials/`** - Anything you bring in: sample documents, spreadsheets, exports, your own content. Drop files here and tell the agent "there are reference documents in materials/". Optional - only if you have source material to work from.

**`mockdata/`** - Pre-built fake data for a fictional professional-services firm (people, clients, matters, emails, a calendar, documents, news, a clause library). If your idea needs realistic data and you don't have your own, start here rather than asking the agent to invent it. See [docs/MOCK_DATA.md](docs/MOCK_DATA.md). Everything in it is invented - never replace it with real or confidential information.
