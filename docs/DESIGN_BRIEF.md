# Design Brief

Once you've completed the discovery questions, spend 5-10 minutes turning your answers into a design brief. It's your group's shared contract before building starts: it stops scope creep, keeps everyone aligned, and makes your prompts to Claude much better.

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

List every screen or view in your app before Claude builds anything. If you have more than 4 screens, cut some - you have 90 minutes.

| Screen | What the user does here |
|---|---|
| Home / Landing | |
| [Screen 2] | |
| [Screen 3] | |

---

## Step 5 - Set Your MVP Scope

Be ruthless. Anything in "Nice to have" only gets built if the must-haves are done and working.

| Must have (build today) | Nice to have (if time allows) | Out of scope |
|---|---|---|
| | | |

---

## Step 6 - Make Your Key Technical Decisions

Claude will suggest options, but your group should agree on these before the build starts.

- Language / framework: what will the app be built in? The default is no-build HTML/CSS/JS that runs straight from `index.html` with nothing to install. A framework (Next.js, Vite, Python) is fine if your group wants one and has the time, but it's not required. Claude will suggest an option based on what you're building.
- Data: does the app need to save anything? If so, how? Browser local storage works for simple apps; a JSON file or lightweight database for anything more.
- Style: you don't need to decide this - every app uses the Base Design System by default. If you want a different look, apply one of the six style presets later in polish (run `/styles`). Don't design a bespoke style from scratch.
- Hosting: where will it run for the demo? Just locally in the browser is fine for today.

---

Once you've worked through these steps, run `/kickoff` in the chat and Claude will build your `PLAN.md`.
