Restyle the group's app with the **Chelsea in Bloom** preset - a soft, botanical, pastel look - blush, lilac, sage and butter, airy whitespace, elegant serif headings and gentle flower motifs.

## How to apply
1. Apply this to the app the group built - normally `index.html` in the project root. If there are several app HTML files, ask which one (default `index.html`).
2. Find the `:root { ... }` design-token block and **replace the token values** with the block below, keeping the variable names identical so every component that uses them reskins automatically.
3. Sweep the file for **hardcoded default hex values** (`#2563EB`, `#141A22`, `#3A4250`, `#F59E0B`, `#F7F8FA`, `#E4E7EC`, `#6B7280`, etc.) and map each to the nearest preset colour.
4. Apply the preset **font stacks, radii and shadows**, plus the **heading and component notes** below.
5. Add the **decorative touches** described - subtly, behind content, never hurting readability.
6. Change **visuals only**: keep all text, structure, layout and behaviour. Keep it self-contained (no external fonts/CDNs) so it still runs from a `file://` URL.
7. When done, tell the group to refresh the app, and that they can switch look any time with another `/style-...` command (or revert to the default Base Design System in `docs/DESIGN.md`).

## Design tokens
```css
:root {
  --text:          #5B4A53;   /* body text - soft aubergine */
  --accent:        #D97FA4;   /* primary actions - rose */
  --accent-hover:  #C66B91;
  --accent-2:      #F2C94C;   /* accent / CTA - daffodil */
  --ink:           #4E5D44;   /* headings, nav, dark surfaces - garden green */
  --muted:         #9A8A93;   /* secondary text - mauve grey */
  --border:        #ECDDE8;   /* borders, dividers - pale lilac */
  --border-light:  #F3E9F0;
  --surface:       #FBF5F7;   /* page background - blush cream */
  --card:          #FFFFFF;   /* cards, inputs */
  --success:       #7FB08A;   /* success - sage */
  --info:          #9CC4DA;   /* info - powder blue */
  --error:         #E58A86;   /* error - soft coral */
  --warning:       #EBBF6A;   /* warning - apricot */
  --accent-soft-1: #D6EAF2;
  --accent-soft-2: #E3D4F0;
  --accent-soft-3: #F7DCE6;
  --font:         "Segoe UI", -apple-system, "Helvetica Neue", Arial, sans-serif;
  --font-heading: "Georgia", "Times New Roman", serif;
  --radius-sm: 12px; --radius-md: 16px; --radius-lg: 22px;
  --shadow-card:   0 2px 10px rgba(150, 110, 140, 0.12);
  --shadow-raised: 0 8px 24px rgba(150, 110, 140, 0.18);
}
```

## Heading & component notes
- **Headings** use `var(--font-heading)` (serif), in garden green (`#4E5D44`), normal weight 600, relaxed letter-spacing. Add this rule: `h1, h2, h3 { font-family: var(--font-heading); }`
- **Buttons** are pill-shaped (`border-radius: 999px`), generous padding. Primary = rose; gold/daffodil for CTAs.
- **Cards** are white with soft rounded corners and the gentle pink-tinted shadow. Lots of whitespace - increase padding if it feels tight.
- **Inputs** have soft lilac borders; focus ring in rose: `box-shadow: 0 0 0 3px rgba(217,127,164,0.18)`.

## Decorative touches
- Replace any watercolour/teal gradient with a **pastel watercolour**: `linear-gradient(135deg, #F7DCE6 0%, #E3D4F0 35%, #CBE7D0 70%, #FBEFC4 100%)` at low opacity (~0.5) as a soft banner/hero or behind the header.
- Scatter a few simple inline **flower SVGs** (five-petal blossoms in blush, lilac and butter, ~0.4-0.6 opacity) in page corners or behind the header. Keep them decorative and non-interactive (`pointer-events: none`), well behind the content.
- Favour soft, airy spacing over dense layouts - this theme should feel like a garden, not a dashboard.
