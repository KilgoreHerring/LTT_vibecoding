Restyle the group's app with the **Worker Bee** preset - a bold, confident, industrial look - charcoal and bee-yellow, heavy geometric type, blocky shapes and hard-edged shadows.

## How to apply
1. Apply this to the app the group built - normally `index.html` in the project root. If there are several app HTML files, ask which one (default `index.html`).
2. Find the `:root { ... }` design-token block and **replace the token values** with the block below, keeping the variable names identical so every component that uses them reskins automatically.
3. Sweep the file for **hardcoded default hex values** (`#2563EB`, `#141A22`, `#3A4250`, `#F59E0B`, `#F7F8FA`, `#E4E7EC`, `#6B7280`, etc.) and map each to the nearest preset colour.
4. Apply the preset **font stack, radii and shadows**, plus the **heading and component notes** below.
5. Add the **decorative touches** described - subtly, never hurting readability.
6. Change **visuals only**: keep all text, structure, layout and behaviour. Keep it self-contained (no external fonts/CDNs) so it still runs from a `file://` URL.
7. When done, tell the group to refresh the app, and that they can switch look any time with another `/style-...` command (or revert to the default Base Design System in `docs/DESIGN.md`).

## Design tokens
```css
:root {
  --text:          #24262B;   /* body text - charcoal */
  --accent:        #F4B400;   /* primary actions - bee yellow */
  --accent-hover:  #D89E00;
  --accent-2:      #1A1C20;   /* accent - black blocks */
  --ink:           #1A1C20;   /* headings, nav bar - near-black */
  --muted:         #6B6E73;   /* secondary text */
  --border:        #DAD8D2;   /* borders, dividers */
  --border-light:  #ECEAE5;
  --surface:       #F3F2EF;   /* page background - concrete off-white */
  --card:          #FFFFFF;   /* cards, inputs */
  --success:       #3F9D52;   /* success */
  --info:          #2E7DA8;   /* info */
  --error:         #B5443A;   /* error - brick */
  --warning:       #F4B400;   /* warning - bee yellow */
  --accent-soft-1: #FBE7A6;
  --accent-soft-2: #E8E6E0;
  --accent-soft-3: #FBE7A6;
  --font: "Segoe UI", "Arial Black", Arial, sans-serif;
  --radius-sm: 4px; --radius-md: 4px; --radius-lg: 6px;
  --shadow-card:   0 3px 0 #1A1C20;   /* hard offset, no blur */
  --shadow-raised: 0 5px 0 #1A1C20;
}
```

## Heading & component notes
- **Headings are heavy and loud:** weight 800, UPPERCASE, tight letter-spacing: `h1, h2, h3 { text-transform: uppercase; letter-spacing: -0.01em; font-weight: 800; }`, in near-black.
- **Bold borders, hard shadows.** Cards and buttons get a 2px charcoal border (`border: 2px solid #1A1C20`) and a **hard offset shadow with no blur** (already in the tokens) for a confident, blocky feel.
- **Primary buttons** are bee-yellow with **black** text and a black border: `.btn-primary { color: #1A1C20; border: 2px solid #1A1C20; font-weight: 700; }`. (The yellow needs dark text - never white.)
- **Nav / header** is a solid near-black bar (`#1A1C20`) with bee-yellow brand text.
- **Focus ring:** `box-shadow: 0 0 0 3px rgba(244,180,0,0.5)`.

## Decorative touches
- Add a faint **honeycomb hexagon pattern** (charcoal or yellow, very low opacity) as a background behind the header or page edges - inline SVG, `pointer-events: none`, well behind content.
- Use the occasional **hazard-stripe divider** (diagonal yellow/charcoal stripes) as a bold section break - sparingly.
- Geometry over softness: square-ish corners, strong blocks of colour, confident contrast.
