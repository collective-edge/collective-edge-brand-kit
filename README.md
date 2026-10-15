# Collective Edge brand kit

Cloud-hosted brand assets plus the `collective-edge-brand-guidelines` skill. Written for agents and humans: an agent loads `SKILL.md` and applies the brand on its own, and a person reads the same file start to finish and gets the same standard. Collective Edge is the parent of Apex Paramedics and Royal Ambulance. It runs monochrome, black to white with no hue of its own, sets everything in Montserrat with the CE block mark and the `CE │ COLLECTIVE EDGE` wordmark, and reaches most surfaces through the **“Powered by Collective Edge”** co-brand, where the Edge wedge takes the partner’s color.

The kit runs on **house type system v1.0**, shared byte for byte with `apex-brand-kit` and `royal-brand-kit`. Type is the layer that makes the three read as one house. Only palette and logo differ between them.

The kit is the CDN-hosted, agent-facing reflection of the CE Design System. Source of truth for color: the “Collective Edge Design System” project on claude.ai/design. Source of truth for type: `reference/type-system.md` in this repo.

**Default to the restrained white document treatment.** White canvas, hairline dividers, sentence-case headings, sparing display type. Black is a header band, a title slide or a section divider, never the reading surface of a document. The dark grain-wave hero belongs to marketing and title surfaces.

**CE is monochrome. The color belongs to the partner.** CE rarely stands alone. It appears beside an operating company or that partner’s customer, and those surfaces carry color, the partner’s. There is no CE accent hue. Full rules: [`reference/brand.md`](reference/brand.md) section 4.

## What is in here

```
collective-edge-brand-kit/
├── SKILL.md                       The brand standard. Everything an agent or a person needs every time
├── reference/
│   ├── data-color.md         # Chart and reporting color. Series, magnitude, polarity, direction. Shared
│   ├── type-system.md             The house type standard. Identical in all three kits
│   ├── brand.md                   Color, logo, co-brand, voice
│   └── layout.md                  Copy-pasteable layout patterns
├── snippets/
│   ├── data-color.css        # The data color layer. Shared
│   ├── type-system.css            The type layer. Identical in all three kits
│   ├── palette.css                The Collective Edge palette. The only file that differs by brand
│   ├── type-tokens.json           Machine-readable type scale
│   ├── header-band.html           Drop-in header band
│   ├── hero-dark.css              The grain-wave hero and title surface
│   └── brand-base.css             DEPRECATED, pre-v1.0. Now a shim over the two stylesheets above
├── templates/
│   ├── document.html              Printable multi-section report
│   ├── internal-doc.html          Memo and one-pager
│   └── deck.html                  Slides, title through closing
├── Examples/
│   └── ce-one-pager.html          A filled reference, not a starting point
├── scripts/
│   ├── validate.py                Mechanical check of generated HTML against the type standard
│   └── check-sync.py              Confirms the shared files match across the three kits
├── tokens.json                    Machine-readable color for python-pptx, python-docx, matplotlib, reportlab
├── brands.json                    Registry resolving every brand in the house to its CDN root
├── NEW-BRAND.md                   How to stand up a kit for a new operating company
└── assets/
    ├── fonts/                     Montserrat variable, woff2 and TTF
    ├── logos/                     Six block marks and two horizontal lockups, SVG
    ├── png/                       Raster derivatives. Never the master
    ├── imagery/                   CE_Background, the grain wave. CE_Coach
    └── colors.json                DEPRECATED, pre-v1.0. Superseded by tokens.json
```

## CDN base URL

All assets serve from [jsDelivr](https://www.jsdelivr.com/) off the `main` branch.

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/
```

Append the path inside this repo to fetch any file.

## Quick start, any HTML

Load the type layer first, the palette second. That order matters.

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/type-system.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/palette.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/data-color.css">
```

For a PDF pipeline (weasyprint, wkhtmltopdf, Chrome print) inline the `@font-face` so the font embeds in the file. The snippet is in [`SKILL.md`](SKILL.md).

Style through the `.bk-*` classes and the semantic `--fg-*`, `--bg-*` and `--border-*` variables. Reach for a raw `--ce-*` value only where the brand color is the point.

## Install the skill

Clone the kit into the skills directory your agent reads. The directory name differs by tool, so substitute your own.

```bash
git clone https://github.com/collective-edge/collective-edge-brand-kit ~/skills/collective-edge-brand-guidelines
```

The agent picks up `SKILL.md` and applies the brand from then on. Working without one, open `SKILL.md` and follow it in order. To update:

```bash
cd ~/skills/collective-edge-brand-guidelines && git pull
```

## Verify before shipping

```bash
python3 scripts/validate.py path/to/output.html
```

It checks no italic, the weight ladder, em tracking, body measure, text wrapping, codes in the mono face and micro-typography, and exits non-zero on a violation. `scripts/check-sync.py` confirms the shared files still match across the three kits.

## Color reference

Collective Edge has no color of its own. A single black-to-white ramp carries its documents, decks, chrome and body copy, and that restraint is the brand.

> **CE stays monochrome. The color belongs to the partner.**

Color reaches a CE surface in four ways, none of them a CE hue. The Edge wedge in the mark, `#C8C8C8` when CE stands alone and the partner’s color on a co-brand surface. A partner’s palette leading a partner-led surface. A partner’s accent as the one functional hue on a CE-led product. Chart series chosen for legibility. The full machine-readable set is `tokens.json`.

| Token | Hex | Use | On `#FFFFFF` |
|---|---|---|---|
| `--ce-white` | `#FFFFFF` | Document canvas, the default surface | |
| `--ce-black` | `#000000` | Header bands, title slides, section dividers | |
| `--ce-ink` | `#111111` | Body text on light | 18.88:1 |
| `--ce-slate` | `#4A4A4A` | Secondary text | 8.86:1 |
| `--ce-steel` | `#6E6E6E` | Tertiary text, metadata. The floor for text on white | 5.10:1 |
| `--ce-mute` | `#9A9A9A` | Dimmed non-text marks. Never text, at any size | 2.81:1 |
| `--ce-fog` | `#C8C8C8` | The Edge wedge when CE stands alone | 1.67:1 |
| `--ce-mist` | `#E2E2E2` | Hairlines, dividers | 1.30:1 |

## Co-branding

CE rarely stands alone. Where its mark shares a surface with another brand, **“Powered by Collective Edge”** is on that surface too. Pick the mode by asking whose name is on the door.

| | Mode A, partner led. The default | Mode B, CE led, partner accented |
|---|---|---|
| Whose surface | The partner’s own product or material | A CE product delivered to a partner or their customer |
| Palette | The partner’s palette runs everything | CE gray ramp, plus the partner’s accent as the one hue |
| What CE contributes | Structure and finish, no hue. Montserrat, hairlines, whitespace, tabular figures, the type scale | The whole system. Partner color marks state: active nav, live data, active filter. Not a chart series |
| CE’s presence | The “Powered by” lockup under a hairline, plus the footer caption | The lockup leads the chain, `CE │ Apex Paramedics │ {Customer}` |

**The wedge is the co-brand mechanism.** CE has no color of its own, so when CE co-brands it takes the partner’s into its own mark. The wedge is the one part that carries it: Royal `#572E72`, Apex `#FDB61C`. The block stays black or white and the letters stay the opposite. Every combination ships as a file, so never hand-recolor.

```
assets/logos/mark-black{,-royal,-apex}.svg   majority black, use on LIGHT
assets/logos/mark-white{,-royal,-apex}.svg   majority white, use on DARK
```

Constants in both modes. Two marks, never merged, separated by the CE bar rendered as a 1px rule. The file matches the background on both sides, never a CSS recolor. The CE lockup stays at or above 120px wide. Partner hexes come from the partner’s own kit, [apex-brand-kit](https://github.com/collective-edge/apex-brand-kit) and [royal-brand-kit](https://github.com/collective-edge/royal-brand-kit), and where a bright brand color fails 3:1 as text you use that kit’s text-safe step. Apex gold `#FDB61C` measures 1.77:1 on white; its text-safe step `#B77808` measures 3.68:1 and holds only at 700 or at large sizes. Copy-pasteable lockups: [`reference/layout.md`](reference/layout.md) section 2.

## Versioning

`@main` serves the latest. Pin `@v1.1` in production HTML.

## License

Brand assets are property of Collective Edge. Use only for Collective Edge and partner-related materials.
