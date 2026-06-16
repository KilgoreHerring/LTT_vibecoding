List the available visual style presets for the group's app and help them pick one. Show this menu, then tell them to run the matching command.

The default Base Design System (from `docs/DESIGN.md`) is the baseline. These presets let a group make their app look visually distinct from everyone else's.

| Command | Preset | Look |
|---|---|---|
| `/style-chelsea` | Chelsea in Bloom | Soft pastel florals - blush, lilac, sage, butter. Botanical and airy, serif headings. |
| `/style-platinum` | Platinum | Sleek minimalist - whites, silvers, hairline borders, lots of whitespace. Premium and professional. |
| `/style-midnight` | Midnight | Dark mode - near-black charcoal with electric teal and violet glow. Modern AI/SaaS feel. |
| `/style-broadsheet` | Broadsheet | Editorial/legal - cream paper, serif type, ink black, oxblood red. Looks like a printed legal opinion. |
| `/style-workerbee` | Worker Bee | Charcoal and bee-yellow, blocky and geometric. Bold, industrial and geometric. |
| `/style-citrus` | Citrus Pop | Energetic startup - coral / magenta / orange gradients, big rounded corners, playful. |

Notes to pass on:
- Each preset restyles the app the group has built (normally `index.html`) - **visuals only**, content and functionality are unchanged.
- Presets are **swappable**: run a different `/style-...` command any time to switch look.
- Running none keeps the **default Base Design System** from `docs/DESIGN.md`.
- If the group hasn't built anything yet, suggest they build the app first, then apply a style near the end as part of polish.
