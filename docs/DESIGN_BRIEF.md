# Design Brief

Once you've completed the discovery questions, turn your answers into a design brief. It's your contract with yourself before building starts: it stops scope creep, keeps you focused, and makes your prompts to the AI coding agent much better.

Work through each step in order. Then run `/kickoff` to create your build plan.

---

## Step 1 - Write Your One-Liner

Complete this sentence before anything else:

> "This app lets **[user]** **[do specific thing]** without **[painful current process]**."

Example: *"This app lets a project lead see status across a team without chasing 12 people over email."*

If you can't finish that sentence clearly, you're not ready to build yet. Keep talking.

---

## Step 2 - Define Your User

Give your user a name and a moment. The more specific, the better.

> **[Name]** is a **[role]** at your organisation. It's **[time of day / situation]**. They need to **[task]** but right now they have to **[painful current process]**. They're **[feeling]**. They would love a tool that **[outcome]**.

Example: *"Sarah runs a cross-team project. It's 5pm before a Monday deadline. She needs status updates from 14 people but has to chase each one manually over email. She's stressed and worried she'll miss someone. She'd love a tool that showed her at a glance who has responded and who hasn't."*

---

## Step 3 - Write 3 User Stories

User stories are the language of product design. Each one defines a piece of real user value.

Format: **"As a [user], I want to [action] so that [benefit]."**

Keep to 3 maximum. These become your build checklist.

| # | User story | Priority |
|---|---|---|
| 1 | As a [user], I want to... so that... | Must have |
| 2 | As a [user], I want to... so that... | Must have |
| 3 | As a [user], I want to... so that... | Nice to have |

---

## Step 4 - Map Your Screens

List every screen or view in your app before the agent builds anything. Map the screens your MVP needs first. You can add more views in later phases once the core works.

| Screen | What the user does here |
|---|---|
| Home / Landing | |
| [Screen 2] | |
| [Screen 3] | |

---

## Step 5 - Set Your MVP Scope

Be ruthless about the first version. Your MVP is the smallest thing that works end to end - that's what you build and get running first. It's good discipline even with a long build ahead of you, because a working core is the thing everything else hangs off.

You have around 24 hours, so the MVP can be substantial and you'll plan to build out in phases once it's solid. Put the first wave of additions in "Nice to have" - they get built after the must-haves are done and working.

| Must have (MVP, build first) | Nice to have (build out after) | Out of scope |
|---|---|---|
| | | |

---

## Step 6 - Make Your Key Technical Decisions

The agent will suggest options, but decide these before the build starts.

- Language / framework: what will the app be built in? Over a build of this length, a framework like Next.js or Vite is a sensible default - it gives you room to grow as you add features. No-build HTML/CSS/JS that runs straight from `index.html` with nothing to install is the lightweight option if you want to keep things simple. The agent will suggest an option based on what you're building.
- Data: does the app need to save anything? If so, how? Browser local storage works for simple apps; a JSON file or lightweight database for anything more.
- Style: you don't need to decide this - every app uses the Base Design System by default. If you want a different look, apply one of the six style presets later in polish (run `/styles`). Don't design a bespoke style from scratch.
- Hosting: where will it run for the demo? Running it locally in the browser is fine for the presentation.

---

Once you've worked through these steps, run `/kickoff` in the chat and the agent will build your `PLAN.md`.
