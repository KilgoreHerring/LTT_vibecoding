Restyle the group's app with the **Platinum** preset - a sleek, minimalist, premium look. Whites and silvers, hairline borders, restrained type and lots of whitespace. Think Apple keynote / high-end SaaS: confident, quiet, professional.

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
  --text:          #2A2D31;   /* body text - graphite */
  --accent:        #2C3036;   /* primary actions - charcoal */
  --accent-hover:  #15171A;
  --accent-2:      #8A929C;   /* accent - steel */
  --ink:           #16181B;   /* headings, nav, dark surfaces - near-black */
  --muted:         #8A929C;   /* secondary text */
  --border:        #E7E9EC;   /* hairline borders, dividers */
  --border-light:  #F1F2F4;
  --surface:       #FAFBFC;   /* page background - near-white */
  --card:          #FFFFFF;   /* cards, inputs */
  --success:       #4B9E84;   /* success - muted */
  --info:          #6E7B8B;   /* info - steel blue */
  --error:         #C5705F;   /* error - muted clay */
  --warning:       #C9A24B;   /* warning - muted brass */
  --accent-soft-1: #E3E7EB;
  --accent-soft-2: #DDE1E6;
  --accent-soft-3: #EAECEF;
  --font: "Helvetica Neue", "Segoe UI", Arial, sans-serif;
  --radius-sm: 4px; --radius-md: 6px; --radius-lg: 8px;
  --shadow-card:   0 1px 2px rgba(20, 23, 26, 0.05);
  --shadow-raised: 0 6px 24px rgba(20, 23, 26, 0.08);
}
```

## Heading & component notes
- **Headings** are near-black, *lighter* than usual (weight 500-600) with tight letter-spacing: `h1, h2, h3 { letter-spacing: -0.02em; }`. Body text weight 400; consider weight 300 for large display text.
- **Whitespace is the feature.** Increase padding and margins; let elements breathe. Sharpen corners (small radii) and keep everything flat and quiet.
- **Buttons**: primary is solid charcoal with white text; secondary is a thin 1px hairline border in `--border`. Avoid bright colour - this theme is near-monochrome.
- **Cards** are white with a 1px hairline border and a barely-there shadow. **Inputs** have hairline borders; focus ring is a thin neutral: `box-shadow: 0 0 0 2px rgba(42,45,49,0.12)`.

## Decorative touches
- No blobs, no busy gradients. At most a single **thin silver gradient line** as a divider or top accent bar: `linear-gradient(90deg, #C8CDD3, #EAECEF)`.
- Restraint is the aesthetic - if in doubt, remove decoration rather than add it.
