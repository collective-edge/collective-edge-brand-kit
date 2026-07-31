# Collective Edge Brand Kit

Cloud-hosted brand assets and Claude skill for Collective Edge: a monochrome black-to-white system with no brand hue of its own, Montserrat bold-italic display type, the CE block mark and "CE │ COLLECTIVE EDGE" wordmark, and the **"Powered by Collective Edge"** co-brand model, which is how CE appears on almost everything. A `SKILL.md` teaches Claude to apply the brand to any document, slide, one-pager, dashboard, or UI.

This kit is the CDN-hosted, agent-facing reflection of the **Collective Edge Design System** (source of truth: the "Collective Edge Design System" project on claude.ai/design). Its tokens mirror that system's `colors_and_type.css`.

**It defaults to the restrained internal-document treatment:** white canvas, hairline dividers, sentence-case headings, sparing display type. The dark-grain hero look is reserved for marketing and title surfaces. Anyone with this repo URL or the CDN links below can produce on-brand CE materials from any machine, with only a working Claude session.

**CE is monochrome. The color belongs to the partner.** CE rarely stands alone. It comes in beside an operating company or a partner's customer, and those surfaces do carry color, the partner's. There is no CE accent hue. See "Co-branding" below and section 2 of `SKILL.md`.

## What's in here

```
collective-edge-brand-kit/
├── SKILL.md                 # The brand skill Claude reads (design-system aligned)
├── assets/
│   ├── colors.json          # Full token set: grey ramp, semantic, status, partners
│   ├── fonts/
│   │   └── Montserrat-VariableFont_wght.ttf
│   ├── logos/
│   │   ├── horizontal-black.svg          # wordmark lockup, light backgrounds (doc default)
│   │   ├── horizontal-white.svg          # wordmark lockup, dark backgrounds
│   │   ├── mark-black.svg                # block mark, majority black, USE ON LIGHT
│   │   ├── mark-black-royal.svg          #   same, purple wedge (Royal co-brand)
│   │   ├── mark-black-apex.svg           #   same, gold wedge (Apex co-brand)
│   │   ├── mark-white.svg                # block mark, majority white, USE ON DARK
│   │   ├── mark-white-royal.svg          #   same, purple wedge (Royal co-brand)
│   │   └── mark-white-apex.svg           #   same, gold wedge (Apex co-brand)
│   ├── png/                 # PNG fallbacks of the marks + lockups
│   └── imagery/             # CE_Background (grain-wave hero), CE_Coach
├── snippets/
│   ├── brand-base.css       # Drop-in CSS: @font-face + every DS token + .ce-* type styles
│   └── header-band.html     # Drop-in header markup
├── templates/
│   └── internal-doc.html    # Restrained, printable internal-document template
└── examples/                # Approved on-brand collateral (reference library)
```

## CDN base URL

All assets are served via [jsDelivr](https://www.jsdelivr.com/) from the `main` branch. Fast, free, and globally cached:

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/
```

Append the path inside this repo to fetch any file. Example for the white horizontal logo:

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-white.svg
```

## Quick start: using the brand in any HTML

Add this to the top of any HTML document and you have Montserrat plus all the brand color variables:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/brand-base.css">
```

For embedding Montserrat into a printed PDF, include the `@font-face` declaration inline so the font travels with the file. See `SKILL.md` for the snippet.

## Quick start: installing the Claude skill

So Claude automatically applies the brand whenever you ask for Collective Edge materials, install the skill into your local Claude skills folder:

```bash
git clone https://github.com/collective-edge/collective-edge-brand-kit ~/.claude/skills/collective-edge-brand-guidelines
```

Claude picks up `SKILL.md` and applies the brand standards automatically. To update:

```bash
cd ~/.claude/skills/collective-edge-brand-guidelines && git pull
```

## Color reference

**Collective Edge has no color of its own.** A single black-to-white grey ramp carries CE's documents, decks, chrome and body copy, and that restraint is the brand. That is not the same as saying a CE surface is always grey:

> **CE stays monochrome. The color belongs to the partner.**

Color appears in four places, and none of them is a CE hue: **the Edge wedge in the mark**, which is grey `#C8C8C8` when CE stands alone and **the partner's color on a co-brand surface**; a partner's palette leads on a partner-led co-brand surface; a partner's accent is the one functional hue on a CE-led product for that partner; and charts pick series colors for legibility and colorblind separation rather than from this palette. White is the primary document canvas; black is reserved for hero, section-divider and title surfaces. See `assets/colors.json` for the full machine-readable token set (grey ramp, semantic foreground and background, borders, status, partner accents).

| Name | Hex | Use |
|---|---|---|
| White | `#FFFFFF` | Primary document canvas |
| Ink | `#111111` | Body text on light |
| Steel | `#6E6E6E` | Tertiary text; the "EDGE" wordmark grey |
| Fog | `#C8C8C8` | The "Edge" wedge when CE stands alone |
| Mist | `#E2E2E2` | Hairlines, dividers, card borders |
| Black | `#000000` | Hero, section-divider and title surfaces |

## Co-branding

CE rarely stands alone. It comes in beside a partner and it says so in words: **"Powered by Collective Edge."** Treat the phrase as non-optional whenever CE's mark shares a surface with another brand. Two modes, picked by asking whose name is on the door:

| | **Mode A. Partner led (default)** | **Mode B. CE led, partner accented** |
|---|---|---|
| Whose surface | The partner's own product or material | A CE product delivered to a partner or their customer |
| Palette | The **partner's palette** runs everything | CE grey ramp, plus the partner's accent as the one hue |
| What CE contributes | Structure and finish, no hue: Montserrat, hairlines, whitespace, tabular numerals, quiet motion | The whole system; partner color marks state (active nav, live data, one chart series) |
| CE's presence | "Powered by" lockup under a hairline, plus the footer caption | The lockup leads the chain: `CE │ Operator │ Customer` |
| Shipped reference | Apex internal dashboards | Apex customer dashboard |

**The wedge is the co-brand mechanism.** CE has no color of its own, so when CE co-brands it takes the partner's into its own mark. The Edge wedge is the one part that carries it: Royal `#572E72` purple, Apex `#f9ad16` gold. The block stays black or white and the letters stay the opposite, always. Every combination ships as a file, so never hand-recolor:

```
assets/logos/mark-black{,-royal,-apex}.svg   majority black  -> use on LIGHT
assets/logos/mark-white{,-royal,-apex}.svg   majority white  -> use on DARK
```

Constants in both modes: two marks, never merged, divided by the CE `│` rendered as a **1px rule**; the file matches the background (never CSS-recolor a lockup); the CE lockup stays at or above **120px** wide; the CE block and letters stay black or white, and the wedge is the only path that ever changes color. Partner hexes come from the partner's **own** brand kit ([apex-brand-kit](https://github.com/collective-edge/apex-brand-kit), [royal-brand-kit](https://github.com/collective-edge/royal-brand-kit)), and where a bright brand color fails 3:1 as text you use that kit's text-safe darkened step (Apex gold `#f9ad16` becomes `#B77808`). Full rules, snippets, and the "never" list are in section 2 of `SKILL.md`.

## Versioning

`@main` always serves the latest version. To pin to a stable release in production HTML, use a tag: `@v1.0`.

## License

Brand assets are property of Collective Edge. Use only for Collective Edge and partner-related materials.
