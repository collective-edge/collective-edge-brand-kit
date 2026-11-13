# Collective Edge · for agents

You are producing something for Collective Edge. This page is the shortest correct path. [`SKILL.md`](../SKILL.md) is the full standard, and it wins any disagreement with this page.

Collective Edge is the parent of Apex Paramedics and Royal Ambulance. Monochrome, black to white, no hue of its own. It owns the house type system and reaches most surfaces through the “Powered by Collective Edge” co-brand.

Working for a person instead? Send them to [`for-humans/`](../for-humans/).

## 1. Load the brand

Every file is public on jsDelivr. No auth, no install.

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/
```

HTML takes these stylesheets, in this order:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/type-system.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/palette.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/cobrand.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/data-color.css">
```

`type-system.css` and `data-color.css` are served from the Collective Edge kit for every brand. `palette.css` is the only file that differs. Load `data-color.css` only when the page has a chart, a dashboard tile or a reported number.

For print or PDF, add the face inline and select it:

```css
@font-face {
  font-family: "Montserrat";
  src: url("https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/fonts/Montserrat-VariableFont_wght.woff2") format("woff2-variations"),
       url("https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/fonts/Montserrat-VariableFont_wght.ttf") format("truetype-variations");
  font-weight: 400 800;
  font-style: normal;
}
html, body { font-family: "Montserrat", "Helvetica Neue", Helvetica, Arial, sans-serif; }
```

Style through the `.bk-*` classes and the `--fg-*`, `--bg-*` and `--border-*` variables. Those names are identical in all three brands. Start from [`templates/`](../templates/) and [`snippets/header-band.html`](../snippets/header-band.html) instead of a blank page.

## 2. Get a logo by role

Ask for a role, never a filename. Filenames differ between brands. `-on-light` is the file you place on a light background.

| Role | URL | Place on |
|---|---|---|
| `horizontal-on-light` | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-black.svg` | A light background |
| `horizontal-on-dark` | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-white.svg` | A dark background |
| `mark-on-light` | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/mark-black.svg` | A light background |
| `mark-on-dark` | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/mark-white.svg` | A dark background |

`stacked-on-dark` does not exist for this brand. Use `horizontal-on-dark`.

Embed with `<img src="...">`. Do not inline a copied SVG path, because it drifts from the master.

Transparent PNG, for generators that cannot place SVG:

| Role | URL |
|---|---|
| `horizontal-on-light` | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/for-humans/logos/png/Collective-Edge-horizontal-black-1200w.png` |
| `horizontal-on-dark` | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/for-humans/logos/png/Collective-Edge-horizontal-white-1200w.png` |
| `mark-on-light` | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/for-humans/logos/png/Collective-Edge-mark-black-512w.png` |
| `mark-on-dark` | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/for-humans/logos/png/Collective-Edge-mark-white-512w.png` |

Each PNG also ships at double width. Replace the width in the filename: `1200w` to `2400w`, `512w` to `1024w`.

## 3. Color

| Name | Variable | Hex | Use |
|---|---|---|---|
| White | `--ce-white` | `#FFFFFF` | Document canvas. The default surface |
| Black | `--ce-black` | `#000000` | Header bands, title slides, section dividers |
| Ink | `--ce-ink` | `#111111` | Body text on light |
| Slate | `--ce-slate` | `#4A4A4A` | Secondary text |
| Steel | `--ce-steel` | `#6E6E6E` | Tertiary text. The floor for text on white |
| Mute | `--ce-mute` | `#9A9A9A` | Dimmed non-text marks. Never text |
| Fog | `--ce-fog` | `#C8C8C8` | The wedge when CE stands alone |
| Mist | `--ce-mist` | `#E2E2E2` | Hairlines, dividers |

Every value, including the semantic, status and on-dark sets, as JSON:

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/tokens.json
```

## 4. The rules that get broken

1. Default to the white document treatment. Black is a band, a title slide or a divider, never the reading surface.
2. There is no CE accent hue. Do not add one.
3. If the CE mark shares a surface with another brand, “Powered by Collective Edge” is on that surface. Load `cobrand.css` and use the `.ce-powered` classes. Do not rebuild the lockup.
4. Only the wedge takes a partner color, and only through the shipped files `mark-{black,white}-{royal,apex}.svg`. Never hand-recolor.
5. Steel `#6E6E6E` is the lightest gray that carries text on white. Mute `#9A9A9A` is never text.
6. When in doubt on a co-brand surface, the partner leads. Take their palette from their kit, not from a copy.
7. Chart and dashboard color comes from `data-color.css`, in series order. A brand color is never a chart series.
8. Match the logo file to the background. Never recolor or invert a logo with CSS.
9. Montserrat only, weights 400 to 800. No italic, at any weight.
10. No em dashes in copy. A period, a comma, or `·`.
11. For print or PDF, inline the `@font-face` block. A locally installed font renders right on one machine and wrong everywhere else.

## 5. Not writing HTML

| Output | Read |
|---|---|
| python-pptx, python-docx, matplotlib, reportlab | `tokens.json` for color, [`snippets/type-tokens.json`](../snippets/type-tokens.json) for sizes, weights and tracking |
| A font file to embed | [`for-humans/fonts/static/`](../for-humans/fonts/static/) · Regular 400, SemiBold 600, Bold 700, ExtraBold 800 |
| A raster logo | The PNG table above |
| A chart | [`reference/data-color.md`](../reference/data-color.md). The hex values are in `snippets/data-color.css` |

The grain wave and the title card are in [`assets/imagery/`](../assets/imagery/). The wave goes behind a title or divider, once, never under body text. This kit ships no photography.

## 6. Read next, by task

| Making | Read |
|---|---|
| Anything | [`SKILL.md`](../SKILL.md), start to finish. It ends with the pre-ship check |
| A header band, table, stat callout, flowchart, footer | [`reference/layout.md`](../reference/layout.md) |
| A chart, dashboard or scorecard | [`reference/data-color.md`](../reference/data-color.md) |
| Buttons, inputs, product UI | [`reference/ui.md`](../reference/ui.md) |
| Long-form type decisions | [`reference/type-system.md`](../reference/type-system.md) |
| A contrast or logo question | [`reference/brand.md`](../reference/brand.md) |
| CE appears beside a partner | [`reference/brand.md`](../reference/brand.md) section 4, then [`reference/layout.md`](../reference/layout.md) |
| A title or hero surface | [`snippets/hero-dark.css`](../snippets/hero-dark.css) |

## 7. Verify before you report done

```bash
python3 scripts/validate.py path/to/output.html
python3 scripts/ui-audit.py path/to/output.html
python3 scripts/validate-palette.py --series
```

`validate.py` exits non-zero on a mechanical rule violation. None of the scripts can see overlap, clipping or a fallback font. Render the file and look at it. If you cannot render, say so instead of reporting it clean.

## 8. Install as a skill

Clone the kit into the skills directory your agent reads. The path differs by tool.

```bash
git clone https://github.com/collective-edge/collective-edge-brand-kit ~/skills/collective-edge-brand-guidelines
```

`SKILL.md` at the root carries the frontmatter. `git pull` updates it.

## 9. The other brands

One registry resolves every brand in the house to its CDN root, palette, tokens and logo roles. It is identical in all three kits.

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/brands.json
```

| Brand | Kit | Entry point |
|---|---|---|
| Royal Ambulance | [`royal-brand-kit`](https://github.com/collective-edge/royal-brand-kit) | [for agents](https://github.com/collective-edge/royal-brand-kit/tree/main/for-agents) |
| Apex Paramedics | [`apex-brand-kit`](https://github.com/collective-edge/apex-brand-kit) | [for agents](https://github.com/collective-edge/apex-brand-kit/tree/main/for-agents) |
