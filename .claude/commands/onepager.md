Look at everything built in this project - the code, any files, and the conversation context - and generate a complete, self-contained HTML one-pager file saved as `onepager.html` in the project root.

The file should be a polished, single-page descriptive summary of the tool the group has built - the kind of one-page document you could hand to a partner or print on A4. It mirrors the `/present` deck but condenses everything onto ONE page, designed to be read rather than presented. Build it as follows:

## Design requirements
Use the Base Design System (docs/DESIGN.md), styled as a clean document on a light page (not dark slides):
- **Page background:** `#FFFFFF` with a generous max-width content column (~820px) centred, so it reads like an A4 sheet
- **Heading text:** `#141A22`
- **Body text:** `#2C3540` (dark slate) on white, comfortable line-height (~1.6)
- **Primary accent:** `#2563EB` - used for section headings, underlines, rules, links
- **Callout:** `#F59E0B` - used for a single key stat or pull-quote emphasis
- **Decorative gradient:** `linear-gradient(135deg, #BFD3F2 0%, #C9B8F0 40%, #F2C0D2 70%, #2563EB 100%)` - soft, used as a subtle accent (e.g. a slim top band or a thin rule), never overpowering the text
- **Font:** `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif`
- A thin accent bar (`linear-gradient(90deg, #2563EB 0%, #0EA5E9 100%)`) across the very top of the page
- Everything on ONE page - no slides, no arrow-key navigation, no slide counter
- Print-friendly: include an `@media print` block so it prints cleanly onto a single A4 sheet (sensible margins, no clipped colours - use `print-color-adjust: exact`). The app mockup adds vertical space, so keep body copy tight and trim the lowest-priority bullets first to hold the one-page layout
- No external dependencies - everything self-contained in one file

## Sections to generate (top to bottom, on one page)

**Header**
- App name (large, ag-deep-navy)
- One-sentence tagline describing what it does
- A small meta line: team members' names · "Vibe Coding Hackathon"

**App mockup (a CSS "screenshot" of the app)**
- Directly under the header, add a visual mockup of the app's main screen so the reader can see what was built at a glance
- Build it as a **pure HTML/CSS faux browser window** (a title bar with three traffic-light dots and a fake URL, framing the app) - NO image files, so the page stays self-contained
- Recreate the **actual UI the group built**, not a generic placeholder: pull the real header/brand, primary navigation or step tabs, the main content area, key controls (buttons, inputs) and any signature feature, using the app's real labels and a representative sample of its content
- Use simple CSS stand-ins for body text (e.g. thin rounded grey bars) rather than full copy, so it reads as a screenshot and stays compact
- Add a one-line italic `figcaption` underneath describing the screen
- Keep it **compact** - it must not break the one-page layout (see print note below); wrap it so it never splits across a page (`break-inside: avoid`)
- If the project genuinely has no visual UI (e.g. a CLI or pure API), skip this section rather than invent one

**The Problem**
- Short heading
- 2-3 tight sentences (or punchy bullets) on who the user is and the painful/slow/manual thing they face, and how significant it is (time, frequency, frustration)

**What We Built**
- Short heading
- One clear sentence saying what the app does
- 3-4 bullet points of the key features that were actually built today
- A one-line "how it works" note if relevant

**How It Works in Practice**
- Short heading
- A brief narrative: "Meet [persona], a [role] who needs to..." followed by 2-3 sentences walking through the key flow
- Keep it concrete and fit the group's context and the hackathon's domain

**From Prototype to Production**
- Short heading
- 3 honest, concise points covering the most relevant considerations from: security/access, data sources, integration with firm systems, ownership/maintenance

**Next Steps**
- Short heading
- One bold statement on what the next step would be if this went further, who would need to be involved, and what a pilot might look like
- End with a closing line that lands the value proposition

## Instructions
- Infer all content from the project that has been built and the conversation context
- Keep it genuinely to one page - be concise; this is a summary, not the full deck
- Where information is unclear, make reasonable assumptions that fit the group's context and the hackathon's domain
- Write the full HTML file to `onepager.html` - do not summarise or describe it, write the complete file
- After writing the file, tell the user to open `onepager.html` in their browser to view or print the one-pager
