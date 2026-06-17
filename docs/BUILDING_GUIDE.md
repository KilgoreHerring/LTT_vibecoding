# Building Guide

How to work with an AI coding agent (Claude Code or ChatGPT Codex) over a long build. Read this before you start, and come back to it whenever you get stuck or things aren't going the way you expected.

You're driving. The agent does the typing, but you decide what gets built, in what order, and whether it's right. The whole skill is describing what you want clearly and steering when it drifts.

---

## Starting the Build

Give the agent a clear opening brief. A good brief says who the app is for, the one main thing it does, and the handful of features that make up your first working version. Don't try to describe the whole thing - describe the core.

Use this as your opening prompt template:

> "I want to build a web app for [user]. The main thing it does is [core function]. To start, it should have [feature 1], [feature 2], and [feature 3]. Build this core version first and we'll add more once it works. Use the Base Design System from docs/DESIGN.md."

The more specific you are, the better the first version will be. Name the user. Say what the app is actually for. Be concrete about the first features.

---

## Build the Core First, Then Build Out

The single most useful habit: get the smallest working version running end to end before you add anything.

- Build the core feature first. Test that it actually works in the browser.
- Only then ask for the next feature. One feature at a time.
- After each addition, test again before moving on.

This sounds slow. It's the opposite. When something breaks, you'll know it was the last thing you added, so it's easy to find and fix. If you describe ten features at once and the result is broken, you have no idea which one did it.

Think of your build in phases: get the MVP working, confirm it holds together, then layer on the nice-to-haves one at a time.

---

## Talking to the Agent

- **One change per message.** Multiple requests at once often produce mixed results. Ask for one thing, see it work, then ask for the next.
- **Describe expected vs. actual when something's wrong.** "When I click submit, nothing happens. I expected the form to save and show a confirmation message." That tells the agent far more than "it's broken".
- **Be specific about what you want changed.** "Make the button bigger and change it to dark blue" beats "make it better".
- **Ask it to explain anything you don't understand.** It won't judge you, and understanding what it did helps you steer next time.
- **If it uses vague names** like "button1" or "div3", ask it to use names that describe what they do. It makes everything afterwards easier.

---

## When Things Go Wrong

Things will break. That's normal, and it's recoverable.

**If you get an error,** paste the full error message back and say "please fix this". The full text matters - copy all of it.

**If the app doesn't look right,** describe what you see versus what you want. "The button is in the top left but I want it centred at the bottom of the form."

**If the agent misunderstood,** say "that's not what I meant" and try again with a clearer description. Don't keep building on top of something wrong.

**If a change breaks something that was working,** the quickest fix is usually to undo it. Ask the agent to revert that last change and try a different approach: "that broke the search feature, please undo that change and let's try another way." If you've been committing your work with git as you go (the agent can do this for you - just ask it to commit after each feature works), you can also ask it to roll back to the last working version. Committing little and often gives you safe points to return to.

**If you're properly stuck** and can't get the agent to fix it, mentors are around on day 1 for advice. But the build is yours to drive.

---

## Working Across Two Days and Multiple Sessions

This is a long build, and you won't do it in one sitting. You'll stop for lunch, overnight, or just to think. The agent doesn't automatically remember where you were if you close the chat or start a new session, so use these two commands to carry your progress across:

- **Before you stop or close the chat, run `/handover`.** This writes a short note capturing where you've got to: what's built, what's working, what's next. It means you don't lose the thread.
- **When you come back, run `/pickup`.** This reloads that note so the agent knows where you left off and you can carry straight on.

Get into the rhythm: `/handover` when you pause, `/pickup` when you return. It's the difference between resuming smoothly and re-explaining your whole project from scratch.

---

## Good Prompts vs. Bad Prompts

| Instead of... | Try... |
|---|---|
| "Make it better" | "Make the button bigger and change the colour to dark blue" |
| "Fix the bug" | "When I click submit, nothing happens. I expected the form to save and show a confirmation message." |
| "Add more features" | "Add a way for the user to download the output as a PDF" |
| "Make it look nice" | "Use a clean white background, dark navy text, and a simple card layout" |
| "It's broken" | "When I enter a name with an apostrophe the page goes blank" |

Both columns follow the same logic: describe the specific behaviour you want, or the specific thing that's wrong. Vague in, vague out.
