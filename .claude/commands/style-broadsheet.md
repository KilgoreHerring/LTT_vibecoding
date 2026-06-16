Restyle the group's app with the **Broadsheet** preset - an editorial, document look. Cream paper, serif type, ink-black text and an oxblood-red accent, with rules instead of shadows. It should read like a printed opinion piece or a quality newspaper - authoritative and editorial.

## How to apply
1. Apply this to the app the group built - normally `index.html` in the project root. If there are several app HTML files, ask which one (default `index.html`).
2. Find the `:root { ... }` design-token block and **replace the token values** with the block below, keeping the variable names identical so every component that uses them reskins automatically.
3. Sweep the file for **hardcoded default hex values** (`#2563EB`, `#141A22`, `#3A4250`, `#F59E0B`, `#F7F8FA`, `#E4E7EC`, `#6B7280`, etc.) and map each to the nearest preset colour.
4. Apply the preset **serif font stack, sharp radii and rule-based dividers**, plus the **heading and component notes** below.
5. Add the **decorative touches** described - subtly, never hurting readability.
6. Change **visuals only**: keep all text, structure, layout and behaviour. Keep it self-contained (no external fonts/CDNs) so it still runs from a `file://` URL.
7. When done, tell the group to refresh the app, and that they can switch look any time with another `/style-...` command (or revert to the default Base Design System in `docs/DESIGN.md`).

## Design tokens
```css
:root {
  --text:          #23201B;   /* body text - ink */
  --accent:        #7B2D26;   /* primary actions - oxblood */
  --accent-hover:  #621F1A;
  --accent-2:      #A67C2E;   /* accent - brass */
  --ink:           #14110D;   /* headings, masthead - ink black */
  --muted:         #6E665A;   /* secondary text - warm grey */
  --border:        #D8CFBE;   /* rules, dividers */
  --border-light:  #EAE3D5;
  --surface:       #F5EFE3;   /* page background - cream paper */
  --card:          #FCFAF3;   /* cards - warm paper */
  --success:       #4F6B3A;   /* success - forest */
  --info:          #3C5A6E;   /* info - slate */
  --error:         #A8432F;   /* error - brick */
  --warning:       #B5852B;   /* warning - ochre */
  --accent-soft-1: #E4DBC9;
  --accent-soft-2: #E0D7C6;
  --accent-soft-3: #EFE6D5;
  --font: "Georgia", "Times New Roman", "Times", serif;
  --radius-sm: 2px; --radius-md: 3px; --radius-lg: 4px;
  --shadow-card:   none;
  --shadow-raised: 0 1px 0 #D8CFBE;
}
```

## Heading & component notes
- **Everything is serif** (the `--font` token handles it). Headings are ink-black, bold; consider small-caps and a touch of letter-spacing on section headings: `h2 { text-transform: uppercase; letter-spacing: 0.04em; font-size: 1.3rem; }`.
- **Rules, not shadows.** Cards are warm paper with a 1px `--border` border and no shadow. Use horizontal rules (`border-top: 1px solid var(--border)`) and the occasional **double rule** (`border-top: 3px double #14110D`) to separate sections.
- **Masthead:** give the app title a newspaper masthead feel - large serif title, a thin rule above and a thick/double rule below.
- **Buttons** are restrained: primary = solid oxblood with cream text; secondary = thin ink border on paper. Sharp corners (small radii).
- **Body text** slightly larger with comfortable line-height (~1.7) for that readable, printed feel.

## Decorative touches
- No gradients, no glow - this theme is flat ink-on-paper.
- Optional **drop cap** on the first paragraph of a main column: enlarge and float the first letter in oxblood serif.
- A subtle paper warmth is enough; let the typography and rules carry the look.
