Restyle the group's app with the **Midnight** preset - a dark-mode look. Near-black charcoal surfaces, light text, and electric teal + violet accents with a soft neon glow. Modern AI / SaaS feel; a strong contrast to the lighter presets.

## How to apply
1. Apply this to the app the group built - normally `index.html` in the project root. If there are several app HTML files, ask which one (default `index.html`).
2. Find the `:root { ... }` design-token block and **replace the token values** with the block below, keeping the variable names identical so every component that uses them reskins automatically.
3. Sweep the file for **hardcoded default hex values** (`#2563EB`, `#141A22`, `#3A4250`, `#F59E0B`, `#F7F8FA`, `#E4E7EC`, `#6B7280`, `#FFFFFF` surfaces, etc.) and map each to the nearest preset colour.
4. Apply the preset **font stack, radii and shadows**, plus the **heading and component notes** below - the dark-mode contrast fixes are essential here.
5. Add the **decorative touches** described - subtly, never hurting readability.
6. Change **visuals only**: keep all text, structure, layout and behaviour. Keep it self-contained (no external fonts/CDNs) so it still runs from a `file://` URL.
7. When done, tell the group to refresh the app, and that they can switch look any time with another `/style-...` command (or revert to the default Base Design System in `docs/DESIGN.md`).

## Design tokens
```css
:root {
  --text:          #C3CAD6;   /* body text - light grey (reads on dark) */
  --accent:        #1FD8C5;   /* primary actions - electric teal */
  --accent-hover:  #14B7A7;
  --accent-2:      #A78BFA;   /* accent / CTA - electric violet */
  --ink:           #0B0E13;   /* nav / deepest surface */
  --muted:         #7E8795;   /* secondary text */
  --border:        #252B36;   /* borders, dividers (dark) */
  --border-light:  #1B2027;
  --surface:       #0E1116;   /* page background - near-black */
  --card:          #161A22;   /* cards, inputs - raised dark surface */
  --success:       #34D399;   /* success */
  --info:          #38BDF8;   /* info */
  --error:         #FB7185;   /* error */
  --warning:       #FBBF24;   /* warning */
  --accent-soft-1: #1FD8C5;
  --accent-soft-2: #A78BFA;
  --accent-soft-3: #F472B6;
  --font: "Segoe UI", -apple-system, "Helvetica Neue", Arial, sans-serif;
  --radius-sm: 8px; --radius-md: 10px; --radius-lg: 14px;
  --shadow-card:   0 2px 12px rgba(0, 0, 0, 0.5);
  --shadow-raised: 0 8px 30px rgba(0, 0, 0, 0.6);
}
```

## Heading & component notes (dark-mode contrast - important)
Because surfaces are now dark, any text that was dark-on-light will become invisible. After remapping tokens, add/override these:
- **Headings to light:** `h1, h2, h3 { color: #F4F6FA; }` (the default system maps headings to `--ink`, which is now near-black - this override is required).
- **Body text** is light grey (`--text` = `#C3CAD6`); make sure no element still sets a dark text colour on a dark surface. Map any leftover dark text to `#C3CAD6` or `#F4F6FA`.
- **Primary buttons** use the electric teal with **dark** text for contrast: `.btn-primary { color: #06231F; }` plus a soft glow `box-shadow: 0 0 18px rgba(31,216,197,0.35);`. Violet (`--accent-2`) CTAs likewise use dark text `#1E1133`.
- **Cards/inputs** sit on `--card` (`#161A22`) with `--border` (`#252B36`) borders. **Focus ring:** `box-shadow: 0 0 0 3px rgba(31,216,197,0.30)`.
- **Nav** uses the deepest surface `#0B0E13`; brand text light.
- Tune scrollbars to dark: thumb `#3A4150` on transparent track.

## Decorative touches
- Replace decorative gradients with an **electric duotone**: `linear-gradient(135deg, #1FD8C5 0%, #A78BFA 100%)`, used at low opacity for hero/banner glows.
- Add subtle glow to primary/active elements (teal or violet `box-shadow` blur). Keep it tasteful - a hint of neon, not a rave.
- Optional faint radial glow behind the header: `radial-gradient(circle at 30% 0%, rgba(31,216,197,0.15), transparent 60%)`.
