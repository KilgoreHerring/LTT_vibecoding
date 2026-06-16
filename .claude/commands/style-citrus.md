Restyle the group's app with the **Citrus Pop** preset - an energetic, playful, modern-startup look. Warm coral, magenta and orange gradients, big rounded corners and bright, colourful shadows. The fun consumer-app option - bold and friendly.

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
  --text:          #43303A;   /* body text - warm plum-brown */
  --accent:        #FF6A4D;   /* primary actions - coral */
  --accent-hover:  #F0512F;
  --accent-2:      #FFB23E;   /* accent / CTA - tangerine */
  --ink:           #7A1F4B;   /* headings, nav - deep magenta-plum */
  --muted:         #A18891;   /* secondary text */
  --border:        #FBE0D6;   /* borders, dividers */
  --border-light:  #FFEDE4;
  --surface:       #FFF7F2;   /* page background - warm off-white */
  --card:          #FFFFFF;   /* cards, inputs */
  --success:       #2BB673;   /* success */
  --info:          #3FA9F5;   /* info */
  --error:         #FF5C6C;   /* error */
  --warning:       #FFB23E;   /* warning */
  --accent-soft-1: #FFD9C2;
  --accent-soft-2: #FFC6DE;
  --accent-soft-3: #FF3D8B;
  --font: "Segoe UI", -apple-system, "Helvetica Neue", Arial, sans-serif;
  --radius-sm: 14px; --radius-md: 20px; --radius-lg: 28px;
  --shadow-card:   0 8px 24px rgba(255, 106, 77, 0.18);
  --shadow-raised: 0 14px 36px rgba(255, 61, 139, 0.22);
}
```

## Heading & component notes
- **Headings are bold and friendly:** weight 800, deep magenta-plum (`#7A1F4B`). Big, confident sizes.
- **Big rounded everything.** Generous border-radius (in the tokens) on cards, buttons and inputs - soft, pill-like, approachable.
- **Primary buttons** can use a vibrant gradient with white text: `.btn-primary { background: linear-gradient(135deg, #FF6B5B, #FF3D8B); color: #FFFFFF; }` and a colourful shadow `box-shadow: 0 8px 20px rgba(255,61,139,0.30)`. Tangerine (`--accent-2`) for secondary CTAs.
- **Cards** are white with soft, *colour-tinted* shadows (already in the tokens) rather than flat grey ones.
- **Inputs** have warm peach borders; focus ring in coral: `box-shadow: 0 0 0 3px rgba(255,106,77,0.22)`.

## Decorative touches
- Add bright **gradient blobs** in page corners / behind the header: `linear-gradient(135deg, #FF6B5B 0%, #FF3D8B 50%, #FFB23E 100%)`, large, soft-blurred, low-to-medium opacity, `pointer-events: none`.
- Lean into roundness and warmth - this theme should feel lively and optimistic, like a well-funded consumer app.
