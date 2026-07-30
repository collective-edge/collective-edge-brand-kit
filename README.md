# Collective Edge Brand Kit

Cloud-hosted brand assets and Claude skill for Collective Edge — a mostly-monochrome black-to-white system, Montserrat bold-italic display type, the CE block mark + "CE | COLLECTIVE EDGE" wordmark, and the "Powered by CE" partner co-brand model. A `SKILL.md` teaches Claude to apply the brand to any document, slide, one-pager, or UI.

This kit is the CDN-hosted, agent-facing reflection of the **Collective Edge Design System** (source of truth: the "Collective Edge Design System" project on claude.ai/design). Its tokens mirror that system's `colors_and_type.css` exactly.

**It defaults to the restrained internal-document treatment** — white canvas, hairline dividers, sentence-case headings, sparing display type. The flashy dark-grain hero look is reserved for marketing / title surfaces. Anyone with this repo URL or the CDN links below can produce on-brand CE materials from any machine, with only a working Claude session.

## What's in here

```
collective-edge-brand-kit/
├── SKILL.md                 # The brand skill Claude reads (design-system aligned)
├── assets/
│   ├── colors.json          # Full token set: grey ramp, semantic, status, partners
│   ├── fonts/
│   │   └── Montserrat-VariableFont_wght.ttf
│   ├── logos/
│   │   ├── horizontal-black.svg   # wordmark lockup → light backgrounds (doc default)
│   │   ├── horizontal-white.svg   # wordmark lockup → dark backgrounds
│   │   ├── mark-black.svg         # CE block mark → light backgrounds
│   │   └── mark-white.svg         # CE block mark → dark backgrounds
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

All assets are served via [jsDelivr](https://www.jsdelivr.com/) from the `main` branch — fast, free, and globally cached:

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/
```

Append the path inside this repo to fetch any file. Example for the white horizontal logo:

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-white.svg
```

## Quick start — using the brand in any HTML

Add this to the top of any HTML document and you have Montserrat plus all the brand color variables:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/brand-base.css">
```

For embedding Montserrat into a printed PDF, include the `@font-face` declaration inline so the font travels with the file. See `SKILL.md` for the snippet.

## Quick start — installing the Claude skill

So Claude automatically applies the brand whenever you ask for Collective Edge materials, install the skill into your local Claude skills folder:

```bash
git clone https://github.com/collective-edge/collective-edge-brand-kit ~/.claude/skills/collective-edge-brand-guidelines
```

Claude picks up `SKILL.md` and applies the brand standards automatically. To update:

```bash
cd ~/.claude/skills/collective-edge-brand-guidelines && git pull
```

## Color reference

Collective Edge is **mostly** monochrome, not strictly. A single black-to-white grey ramp carries documents, decks, UI chrome and body copy, and that restraint is the brand. Two deliberate exceptions: the Edge wedge in the mark may be gold `#FFD630` (preferred wherever the mark has to read small, and on co-brand surfaces), and a partner's accent is expected on that partner's own co-brand surface. White is the primary document canvas; black is reserved for hero / section-divider / title surfaces. See `assets/colors.json` for the full machine-readable token set (grey ramp, semantic fg/bg, borders, status, partner accents).

| Name | Hex | Use |
|---|---|---|
| White | `#FFFFFF` | Primary document canvas |
| Ink | `#111111` | Body text on light |
| Steel | `#6E6E6E` | Tertiary text; the "EDGE" wordmark grey |
| Fog | `#C8C8C8` | The "Edge" wedge, restrained treatment |
| Gold | `#FFD630` | The "Edge" wedge, color treatment. The one hue CE owns; wedge only |
| Mist | `#E2E2E2` | Hairlines, dividers, card borders |
| Black | `#000000` | Hero / section-divider / title surfaces |

## Versioning

`@main` always serves the latest version. To pin to a stable release in production HTML, use a tag: `@v1.0`.

## License

Brand assets are property of Collective Edge. Use only for Collective Edge and partner-related materials.
