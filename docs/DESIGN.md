# Base Design System

A clean, neutral design system for apps and presentations built at the hackathon. It is deliberately understated so any group's app looks tidy and professional out of the box, whatever they build. Want something more distinctive? Apply one of the style presets (see below).

When asking Claude to build anything, say: **"Use the Base Design System from docs/DESIGN.md"** and Claude will apply these styles. Or start from `starter.html`, which already has the full CSS loaded.

---

## Style Presets (make your app look different)

Everything below is the **default** look. Because it is token-based (a `:root` block of CSS variables consumed by the components), a whole app can be reskinned just by swapping those token values, so we have packaged six alternative looks as commands. Run `/styles` to see the menu, then run one of:

| Command | Preset | Look |
|---|---|---|
| `/style-chelsea` | Chelsea in Bloom | Soft pastel florals - blush, lilac, sage, butter. Botanical and airy, serif headings. |
| `/style-platinum` | Platinum | Sleek minimalist - whites, silvers, hairline borders, lots of whitespace. |
| `/style-midnight` | Midnight | Dark mode - near-black with electric teal and violet glow. |
| `/style-broadsheet` | Broadsheet | Editorial - cream paper, serif, ink black, oxblood red. |
| `/style-workerbee` | Worker Bee | Bold and industrial - charcoal and bee-yellow, blocky and geometric. |
| `/style-citrus` | Citrus Pop | Energetic startup - coral / magenta / orange gradients, big rounded corners. |

They restyle the app **visually only** (content and functionality unchanged), they are **swappable** (run another to switch), and running none keeps the default below. Best applied near the end as part of polish.

---

## Colour Palette

### Primary Colours
| Token | Hex | Use it for |
|---|---|---|
| `text` | `#3A4250` | Body text, secondary buttons, borders |
| `accent` | `#2563EB` | Primary actions, links, focus states, key UI elements |
| `accent-2` | `#F59E0B` | Highlights, accents, callouts, badges |

### Neutrals
| Token | Hex | Use it for |
|---|---|---|
| `ink` | `#141A22` | Headers, navbars, slide backgrounds, dark surfaces |
| `muted` | `#6B7280` | Secondary text, placeholders, captions |
| `border` | `#E4E7EC` | Borders, dividers, table stripes |
| `border-light` | `#EEF0F3` | Disabled states, subtle backgrounds |
| `surface` | `#F7F8FA` | Page background, content areas |
| `card` | `#FFFFFF` | Cards, modals, input backgrounds |

### Status / Semantic
| Token | Hex | Use it for |
|---|---|---|
| `success` | `#16A34A` | Success, complete, confirmed |
| `info` | `#0EA5E9` | Information, tips, secondary highlights |
| `error` | `#DC2626` | Errors, warnings, destructive actions |
| `warning` | `#F59E0B` | Warnings, pending states |

### Decorative Accent Palette
Used for soft decorative gradients only, never for text or interactive elements.
| Token | Hex |
|---|---|
| `accent-soft-1` | `#BFD3F2` |
| `accent-soft-2` | `#C9B8F0` |
| `accent-soft-3` | `#F2C0D2` |

---

## Typography

**Font stack:** `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif`

No external fonts needed. It renders well on every device and works offline from a `file://` URL.

| Use | Size | Weight | Colour |
|---|---|---|---|
| Page title / H1 | 2rem (32px) | 700 | `#141A22` |
| Section heading / H2 | 1.5rem (24px) | 600 | `#141A22` |
| Sub-heading / H3 | 1.125rem (18px) | 600 | `#3A4250` |
| Body text | 1rem (16px) | 400 | `#3A4250` |
| Small / caption | 0.875rem (14px) | 400 | `#6B7280` |
| Label | 0.875rem (14px) | 500 | `#3A4250` |

---

## Layout & Spacing

- **Page background:** `#F7F8FA`
- **Max content width:** `1200px`, centred
- **Card background:** `#FFFFFF` with `border: 1px solid #E4E7EC` and `border-radius: 8px`
- **Card shadow:** `box-shadow: 0 1px 3px rgba(20, 26, 34, 0.08)`
- **Base spacing unit:** `8px` - use multiples (8, 16, 24, 32, 48)
- **Border radius:** `6px` for inputs/buttons, `8px` for cards, `12px` for large panels

---

## Components

### Buttons

**Primary (accent)** - main actions
```css
background: #2563EB; color: #FFFFFF; border: none;
padding: 10px 20px; border-radius: 6px; font-weight: 500;
```
Hover: `background: #1D4FD7`

**Secondary (outlined)** - secondary actions
```css
background: transparent; color: #3A4250;
border: 1.5px solid #3A4250; padding: 10px 20px; border-radius: 6px;
```
Hover: `background: #F7F8FA`

**Accent-2** - highlights, CTAs
```css
background: #F59E0B; color: #141A22; border: none;
padding: 10px 20px; border-radius: 6px; font-weight: 600;
```

### Cards
```css
background: #FFFFFF;
border: 1px solid #E4E7EC;
border-radius: 8px;
padding: 24px;
box-shadow: 0 1px 3px rgba(20, 26, 34, 0.08);
```

### Form Inputs
```css
background: #FFFFFF;
border: 1.5px solid #E4E7EC;
border-radius: 6px;
padding: 10px 14px;
color: #3A4250;
font-size: 1rem;
```
Focus: `border-color: #2563EB; outline: none; box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.15)`

### Status Badges
```css
/* Success */   background: #E7F6EC; color: #16A34A; border: 1px solid #16A34A;
/* Warning */   background: #FEF3E2; color: #B5780B; border: 1px solid #F59E0B;
/* Error */     background: #FCEBEB; color: #DC2626; border: 1px solid #DC2626;
/* Info */      background: #E6F6FE; color: #0284C7; border: 1px solid #0EA5E9;
```
All badges: `padding: 3px 10px; border-radius: 999px; font-size: 0.8rem; font-weight: 500`

### Navigation / Header
```css
background: #141A22; color: #FFFFFF;
padding: 16px 32px;
```
Nav links: `color: #E4E7EC;` Active: `color: #F59E0B`

---

## Gradient Patterns

**Soft accent** - subtle decorative background (opacity ~0.12)
```css
background: linear-gradient(135deg, #BFD3F2 0%, #C9B8F0 40%, #F2C0D2 70%, #2563EB 100%);
```

**Soft wash** - stronger hero/banner use (opacity ~0.25)
```css
background: linear-gradient(135deg, #BFD3F2 0%, #C9B8F0 35%, #F2C0D2 65%, #2563EB 100%);
```

**Accent bar** - bars, progress, accents
```css
background: linear-gradient(90deg, #2563EB 0%, #0EA5E9 100%);
```

---

## CSS Starter Block

Paste this `<style>` block into any self-contained HTML app to apply the Base Design System. No Tailwind or external dependencies needed. (Using a framework like Next.js or Vite instead? These same tokens drop straight into a `globals.css` or a Tailwind theme.)

```html
<style>
  /* Base Design System - Design Tokens */
  :root {
    --text:          #3A4250;
    --accent:        #2563EB;
    --accent-hover:  #1D4FD7;
    --accent-2:      #F59E0B;
    --ink:           #141A22;
    --muted:         #6B7280;
    --border:        #E4E7EC;
    --border-light:  #EEF0F3;
    --surface:       #F7F8FA;
    --card:          #FFFFFF;
    --success:       #16A34A;
    --info:          #0EA5E9;
    --error:         #DC2626;
    --warning:       #F59E0B;
    --accent-soft-1: #BFD3F2;
    --accent-soft-2: #C9B8F0;
    --accent-soft-3: #F2C0D2;
    --font: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    --radius-sm: 6px;
    --radius-md: 8px;
    --radius-lg: 12px;
    --shadow-card: 0 1px 3px rgba(20, 26, 34, 0.08);
    --shadow-raised: 0 4px 16px rgba(20, 26, 34, 0.12);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--surface);
    color: var(--text);
    font-family: var(--font);
    font-size: 1rem;
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }

  h1 { font-size: 2rem;     font-weight: 700; color: var(--ink); }
  h2 { font-size: 1.5rem;   font-weight: 600; color: var(--ink); }
  h3 { font-size: 1.125rem; font-weight: 600; color: var(--text); }
  p  { color: var(--text); }
  small, .caption { font-size: 0.875rem; color: var(--muted); }

  /* Navigation */
  nav {
    background: var(--ink);
    color: var(--card);
    padding: 16px 32px;
    display: flex;
    align-items: center;
    gap: 24px;
  }
  nav a { color: var(--border); text-decoration: none; font-size: 0.9rem; }
  nav a:hover, nav a.active { color: var(--accent-2); }
  .nav-brand { font-weight: 700; font-size: 1.1rem; color: var(--card); }

  /* Layout */
  .container { max-width: 1200px; margin: 0 auto; padding: 0 24px; }
  .page { padding: 32px 24px; max-width: 1200px; margin: 0 auto; }

  /* Cards */
  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: var(--radius-md);
    padding: 24px;
    box-shadow: var(--shadow-card);
  }
  .card-raised { box-shadow: var(--shadow-raised); }

  /* Buttons */
  .btn {
    display: inline-flex; align-items: center; gap: 8px;
    padding: 10px 20px; border-radius: var(--radius-sm);
    font-family: var(--font); font-size: 0.95rem; font-weight: 500;
    cursor: pointer; border: none; text-decoration: none;
    transition: background 0.15s, box-shadow 0.15s;
  }
  .btn-primary   { background: var(--accent); color: var(--card); }
  .btn-primary:hover { background: var(--accent-hover); }
  .btn-secondary { background: transparent; color: var(--text); border: 1.5px solid var(--text); }
  .btn-secondary:hover { background: var(--surface); }
  .btn-accent    { background: var(--accent-2); color: var(--ink); font-weight: 600; }
  .btn-accent:hover { background: #E08E08; }
  .btn:disabled  { opacity: 0.45; cursor: not-allowed; }

  /* Forms */
  .form-group { display: flex; flex-direction: column; gap: 6px; margin-bottom: 20px; }
  label { font-size: 0.875rem; font-weight: 500; color: var(--text); }
  input, select, textarea {
    background: var(--card);
    border: 1.5px solid var(--border);
    border-radius: var(--radius-sm);
    padding: 10px 14px;
    color: var(--text);
    font-family: var(--font);
    font-size: 1rem;
    width: 100%;
    transition: border-color 0.15s, box-shadow 0.15s;
  }
  input:focus, select:focus, textarea:focus {
    border-color: var(--accent);
    outline: none;
    box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.15);
  }
  textarea { resize: vertical; min-height: 100px; }

  /* Badges */
  .badge {
    display: inline-block;
    padding: 3px 10px; border-radius: 999px;
    font-size: 0.8rem; font-weight: 500;
  }
  .badge-success { background: #E7F6EC; color: var(--success); border: 1px solid var(--success); }
  .badge-warning { background: #FEF3E2; color: #B5780B;        border: 1px solid var(--warning); }
  .badge-error   { background: #FCEBEB; color: var(--error);   border: 1px solid var(--error); }
  .badge-info    { background: #E6F6FE; color: #0284C7;        border: 1px solid var(--info); }

  /* Dividers */
  hr { border: none; border-top: 1px solid var(--border); margin: 24px 0; }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: transparent; }
  ::-webkit-scrollbar-thumb { background: var(--muted); border-radius: 3px; }
  ::-webkit-scrollbar-thumb:hover { background: var(--text); }

  /* Decorative gradients */
  .soft-accent {
    background: linear-gradient(135deg, #BFD3F2 0%, #C9B8F0 40%, #F2C0D2 70%, #2563EB 100%);
    opacity: 0.12;
  }
  .accent-bar { background: linear-gradient(90deg, #2563EB 0%, #0EA5E9 100%); }
</style>
```

---

## Presentation Colours (for `/present` slides)

The `/present` command uses a dark theme. Map the tokens to slides as follows:

| Slide element | Value |
|---|---|
| Slide background | `#141A22` (ink) |
| Heading text | `#FFFFFF` |
| Body text | `#C9CED6` (light grey) |
| Accent / highlight | `#2563EB` (accent) |
| Callout | `#F59E0B` (accent-2) |
| Decorative gradient | Soft (soft-1 to soft-2 to soft-3 to accent) |
| Progress bar / divider | Accent bar gradient |
