---
name: collective-edge-brand-guidelines
description: Applies the Collective Edge brand standard to any document, deck, sheet, PDF or page that carries the Collective Edge name. Collective Edge is the parent of Apex Paramedics and Royal Ambulance. It has no hue and no accent color, ever. It works in seven tiers from black to white, sets black over graphite ink, runs a graphite band, and keeps true black for the hero and the title, divider and closing slides. Type is Montserrat at 400, 600, 700 and 800 with no italic. Covers how to load the kit, logos by role, color, the alert family, chart color, type, the rules for editing an existing file, the working document, sheet, deck, one-pager, report and memo layouts, the “Powered by Collective Edge” co-brand where the Edge wedge takes the partner’s color, voice, and a pre-ship check. Use when producing or reviewing any Collective Edge material.
---

# Collective Edge · brand standard

Collective Edge is a holding and operating company. It partners with regional healthcare-transportation providers and brings them shared systems, leadership and long-term capital while local ownership stays in place. It is the parent of Apex Paramedics and Royal Ambulance.

Collective Edge, Apex Paramedics and Royal Ambulance share one standard. The sections, the order and the rules are the same in all three kits. Color, logo and brand facts differ. Type, layout, alert color, chart color and the co-brand lockup are shared and never forked for one brand.

This file is the whole standard in brief. The references carry the full tables: [reference/brand.md](reference/brand.md) for color, logo, co-brand and voice, [reference/layout.md](reference/layout.md) for every document type in inches and points, [reference/type-system.md](reference/type-system.md) for type, [reference/data-color.md](reference/data-color.md) for charts, [reference/ui.md](reference/ui.md) for controls.

## 1. Brand

| | |
|---|---|
| Role | Parent company. Owns the house type system |
| Character | Restrained. Confident. Operational. Adult. A senior operator giving a direct briefing |
| Palette | No hue, ever. Seven tiers from black to white. Black over graphite |
| Logo | The block mark and the `CE │ COLLECTIVE EDGE` horizontal lockup. The Edge wedge is the one part that takes color, and that color is the partner’s |

## 2. Load

Every file is public on jsDelivr. No auth, no install. Paths in this file are relative to the kit root.

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/
```

| File | Holds |
|---|---|
| `brands.json` | All three brands. CDN roots, logo roles, minimum sizes and the co-brand lockup. Identical in every kit |
| `tokens.json` | This brand’s colors as hex and RGB. One key structure in all three kits |
| `snippets/type-tokens.json` | The type scale, weights, measure, spacing and the static font names. Identical in every kit |
| `for-humans/logos/png/` | Transparent PNG logos, for generators that cannot place SVG |
| `for-humans/fonts/static/` | Montserrat Regular, SemiBold, Bold and ExtraBold, as static files |

**Word, PowerPoint, Excel and PDF.** Read color from `tokens.json` and type from `snippets/type-tokens.json`. Place logos as PNG. Name the family `Montserrat`, and install or register the four static files before rendering so the face embeds. `office` in `snippets/type-tokens.json` gives the menu name for each weight. If the render falls back to another face, say so when you hand the work back.

**HTML.** Four stylesheets, in this order: `snippets/type-system.css`, `snippets/palette.css`, `snippets/cobrand.css`, `snippets/data-color.css`. `palette.css` loads from this kit and is the only one that differs by brand. The other three load from the Collective Edge kit. Load `data-color.css` only when the page has a chart or a reported number. Style through the `.bk-*` classes and the `--fg-*`, `--bg-*` and `--border-*` variables. The link tags and the `@font-face` block that embeds the face in a PDF are in `for-agents/README.md`. `assets/colors.json` and `snippets/brand-base.css` predate the house type system. They still ship for pages already loading them. New work never reads them.

## 3. Logo

Ask for a role, never a filename. Filenames differ between brands. `-on-light` is the file placed on a light background. `-on-dark` is the file placed on a dark one. Collective Edge ships no compact lockup, no stacked lockup and no app icon. Use the horizontal lockup.

| Role | SVG, in `assets/logos/` | PNG, in `for-humans/logos/png/` | Use |
|---|---|---|---|
| `horizontal-on-light` | `horizontal-black.svg` | `Collective-Edge-horizontal-black-1200w.png` | The primary lockup, on white and tints |
| `horizontal-on-dark` | `horizontal-white.svg` | `Collective-Edge-horizontal-white-1200w.png` | The primary lockup, on the band and the hero |
| `mark-on-light` | `mark-black.svg` | `Collective-Edge-mark-black-512w.png` | The block mark, on light. Gray wedge |
| `mark-on-dark` | `mark-white.svg` | `Collective-Edge-mark-white-512w.png` | The block mark, on dark. Gray wedge |

Minimum width: horizontal 120px on screen and 1in in print, mark 28px on screen. Clear space on all four sides: the height of the Edge wedge. Each PNG also ships at double width: replace `1200w` with `2400w`, or `512w` with `1024w`.

1. The brand’s logo appears once in a document and at most once on a slide: in the band of a memo, a one-pager or a report, top left of page 1 on a working-doc.
2. Match the file to the ground. Never recolor a logo and never invert one with a filter.
3. Never stretch, skew, rotate, outline or shadow a logo.
4. Hold the clear space. If it is short, shrink the logo, down to the minimum.
5. Never place a logo on a photograph without a solid backing.
6. Only the Edge wedge takes color. It is `#C8C8C8` when Collective Edge stands alone and the partner’s color on a co-brand surface, through the shipped files only.
7. EDGE in the wordmark stays gray. Never force it to black or white. Never split the block mark from the wordmark in the horizontal lockup.

## 4. Color

### 4.1 Palette

Collective Edge has no hue and no accent color. It works in seven tiers from black to white. Emphasis comes from weight, size and the step between tiers. The color belongs to the partner.

| Name | Token | Hex | Use |
|---|---|---|---|
| Tier 1 · Black | `--ce-black` | `#000000` | The hero and the title, divider and closing slides. Accent text. Never the reading surface |
| Tier 2 · Graphite | `--ce-graphite` | `#23232A` | The header band. The same value is body ink |
| Tier 3 · Iron | `--ce-iron` | `#4E4F58` | The mid tone. A filled block between band and surface |
| Tier 4 · Fog | `--ce-fog` | `#C8C8C8` | The Edge wedge when standing alone. The 2.25pt (3px) rule under the band. Never text |
| Tier 5 · Paper | `--ce-paper` | `#E5E6EA` | Table header fill, with a 1.5pt (2px) `#000000` rule under the header row. Never text |
| Tier 6 · Bone | `--ce-bone` | `#F0F1F4` | Callout fill. Never text |
| Tier 7 · White | `--ce-white` | `#FFFFFF` | The document canvas. The default surface |

### 4.2 Grounds and neutrals

Every brand has the same six grounds, and one neutral family sets text and rules in all three brands. White is the page. The last column lists the only text that sits on each ground.

| Ground | Token | Hex | Text on it |
|---|---|---|---|
| Canvas | `--bg-canvas` | `#FFFFFF` | `#23232A` body, `#565860` secondary, `#6D6D77` captions |
| Surface | `--bg-surface` | `#F0F1F4` | The same three |
| Surface 2 | `--bg-surface-2` | `#E5E6EA` | `#23232A` and `#565860` only |
| Mid | `--bg-mid` | `#4E4F58` | `#FFFFFF` and `#DDDDE3` only |
| Band | `--bg-band` | `#23232A` | `#FFFFFF` headings, `#DDDDE3` body, `#A3A4AC` captions |
| Hero | `--bg-inverse` | `#000000` | The same three |

Ink `#23232A` is `--fg-1`. Secondary `#565860` is `--fg-2`. Tertiary `#6D6D77` is `--fg-3`, the dimmest text. On-dark body `#DDDDE3` is `--fg-on-dark-2`. On-dark caption `#A3A4AC` is `--fg-on-dark-3`. Hairline `#E4E4E9` is `--border-1`. Border `#D0D0D6` is `--border-2`. Dimmed `#8A8B93`, `--fg-4`, is for marks only.

### 4.3 Alerts

Four meanings, one family, identical in every brand. Green means good and nothing else. A brand color is never a status color. A word or an icon always travels with the color.

| Meaning | Base | Text | Tint | Text on tint | On dark |
|---|---|---|---|---|---|
| Go · cleared, on time, in service | `#1E7A4D` | `#1E7A4D` | `#DAF8DF` | `#1E7A4D` | `#56B580` |
| Warn · at risk, pending, watch | `#B5821A` | `#926603` | `#FFEFDD` | `#926603` | `#E9B457` |
| Stop · failed, out of service, blocked | `#B0322B` | `#B0322B` | `#FDE9E6` | `#B0322B` | `#EB685C` |
| Info · neutral notice | `#2A5A8C` | `#2A5A8C` | `#E3F0FF` | `#2A5A8C` | `#5796D9` |

- **Steps.** Base is a fill, a rule or a dot on a light ground. Text is text on white and on a surface. Tint is a pill or a callout fill. On dark is text, dots and rules on a dark ground.
- **Names.** The canonical names are `--alert-<name>`, `-text`, `-tint`, `-on-tint` and `-on-dark` in `palette.css`, and `alert` in `tokens.json`. `--status-*`, `--dir-*` and `--diagram-*` are aliases of this family.
- **Dark grounds.** Status works on a band. Use the on-dark step there. In CSS, `--status-*` moves to that step under `.bk-on-dark`.
- **Warn.** The base `#B5821A` measures 3.40:1 on white and is never text. Warn text is `#926603`. Text on an amber fill is `#23232A`, never white.
- **Diagrams.** Decision `#1E7A4D` with `#FFFFFF` text. Warning `#B5821A` with `#23232A` text. Process `#4E4F58` with `#FFFFFF` text. Connector `#4E4F58` at 1.8pt. Rectangles, 6px radius. Fill carries the role, never shape.

### 4.4 Charts

Chart colors come from the house data set, never from the brand palette. Full standard: [reference/data-color.md](reference/data-color.md).

| Job | Colors |
|---|---|
| Series on light, in order | `#2063e6` `#eb6f32` `#b93388` `#7f3810` `#8a72f7` `#819808` `#259cde` |
| Series on dark, in order | `#0986e4` `#fc803e` `#c4588d` `#ac772e` `#ac94fd` `#b1d454` `#74c8fc` |
| Magnitude, light to dark | `#EEEEF2` `#D3D4D9` `#B6B7BD` `#97989F` `#76777F` `#51525A` `#23232A` |
| Good, bad, caution, neutral | `#1E7A4D` `#B0322B` `#926603` `#6D6D77`, each with an arrow or icon and a word |

- Assign series in order. Never cycle. There is no eighth: fold the tail into “Other” or split the chart. On a scatter, a bubble chart, a map or small multiples, four series at most on light and three on dark.
- Good or bad follows the meaning, never the sign of the number. A cost that falls is good. Never two tints of one hue for two different things: a before and after chart sets a `#D0D0D6` baseline against series 1.

### 4.5 Color rules

1. White is the page. The band opens a document. It is never the reading surface.
2. Body text is `#23232A` on white. On a dark ground, headings are `#FFFFFF` and body is `#DDDDE3`.
3. `#8A8B93`, `#D0D0D6` and `#E4E4E9` are never text.
4. A brand color is never a status color and never a chart series. Every color is an exact hex from `tokens.json`. Never invent one and never tint one.
5. No hue, ever. Collective Edge has no accent color. Never add one. Color on a Collective Edge surface belongs to a partner, to the alert family or to a chart.
6. Black over graphite. Accent text is `#000000` and body ink is `#23232A`. The two measure 1.35:1 against each other, so black reads as an accent at display size only.
7. The band is graphite `#23232A`. True black `#000000` is for the hero and the title, divider and closing slides.
8. `#C8C8C8`, `#E5E6EA` and `#F0F1F4` are never text.

## 5. Type

Montserrat for every word, in every brand. Full standard: [reference/type-system.md](reference/type-system.md).

| Step | pt | px | Weight | Leading | Use |
|---|---|---|---|---|---|
| `bk-display-xl` | 72 | 96 | 800 | 1.05 | Hero and title bands only |
| `bk-display-lg` | 54 | 72 | 800 | 1.08 | Hero and title bands only |
| `bk-display-md` | 42 | 56 | 800 | 1.10 | Slide headlines |
| `bk-h1` | 30 | 40 | 700 | 1.18 | Page title |
| `bk-h2` | 24 | 32 | 700 | 1.25 | Section heading |
| `bk-h3` | 18 | 24 | 600 | 1.35 | Subhead |
| `bk-h4` | 15 | 20 | 600 | 1.45 | Subhead |
| `bk-body-lg` | 15 | 20 | 400 | 1.55 | Lead paragraph, deck body |
| `bk-body` | 12 | 16 | 400 | 1.60 | Body |
| `bk-body-sm` | 10.5 | 14 | 400 | 1.55 | Table cells, secondary body |
| `bk-caption` | 9 | 12 | 400 | 1.45 | Captions, footers. The print floor |
| `bk-eyebrow` | 9 | 12 | 600 | 1.45 | Uppercase labels, tracked 0.080em |

1. No italic, at any weight. Never synthesize one.
2. Weights 400, 600, 700 and 800 only. Three at most in a document. A deck is the one piece that uses all four.
3. On a dark ground, drop one weight where the step is 700 or heavier and add 0.005em tracking. 600 is the floor.
4. Tracking is in em, never px or pt. Uppercase is always tracked and never longer than four words.
5. Sentence case for every heading. Uppercase for the band title and the title slide title only.
6. Flush left, ragged right. Never justify. Never center past three lines. A body line stops at 70 characters, which is 54ch. Captions 40ch. Headings 28ch.
7. Space above a heading is three times the space under it. Subhead 18pt above, 6pt under. Section heading 36pt above, 12pt under.
8. The mono face is for color values, paths and filenames, code, and record identifiers. Everything else is Montserrat.

## 6. Layout

Six types. Take the first that fits: sheet, deck, working-doc, one-pager, report, memo. The working-doc is the default for anything in Google Docs or Word. A memo is only for a request that asks for one by name. Every value, the wording budget and the build for Word, PowerPoint and Google files: [for-agents/README.md](for-agents/README.md) section 5 and [reference/layout.md](reference/layout.md).

1. Editing an existing file comes first. Keep its layout, styles, fonts, sizes, colors, column order and wording. Change only what was asked, in the same file.
2. New content takes the style of its neighbors. A document the person points to is the template, and this kit does not override it.
3. Restyle, shorten or rewrite only when asked. Never delete someone else’s content. Never change spacing, sizes or margins to make an edit fit a page. All eight rules: `for-agents/README.md` section 5.

| | Working-doc | Sheet | Deck | One-pager, report, memo |
|---|---|---|---|---|
| Page | US Letter, portrait, 0.75in margins | One table per tab, from A1 | 13.333 by 7.5in, 16:9 | US Letter, portrait. 0.75in margins, 0.6in on a one-pager |
| Opens on | The logo, top left, then the title at 24pt. No band | The header row, frozen, filter on | A title slide on the dark ground | The band, with the logo |
| Body | 10.5pt, weights 400 and 700 | Montserrat 10pt | 15pt, on white | `bk-body`, 12pt, 70 characters a line |

1. The band is for PDF, print and slides. A document that will live in Google Docs is a working-doc unless the person asks for a designed one-pager. A working-doc is plain: no band, callout, card, icon, uppercase label or stat numeral. A light table header, a hairline under every row, a one-line footer.
2. In a file that becomes a Google file, line spacing is a multiple, 1.15 for headings and 1.35 for body, never an exact point value. Table indent equals the left cell padding, 6pt. An empty paragraph sits between two tables.
3. Keep it short. The first line states the decision, the ask or the status. In an agenda it states what the meeting is for. No restated title, no closing summary. A sentence runs 20 words at most.

## 7. Co-brand

Apex Paramedics and Royal Ambulance are operating companies under Collective Edge, and the reader should be able to see it.

1. “Powered by Collective Edge” appears once on everything Apex Paramedics and Royal Ambulance deliver as a PDF, a deck or an image: memo, one-pager, report, proposal, deck. Never twice. A working-doc and a sheet never carry it, as a lockup or as words. The rule follows the type, not the file format: a working-doc exported to PDF stays as it is.
2. A Collective Edge document carries the Collective Edge logo and no lockup. Where the Collective Edge mark shares a surface with another brand, the lockup is on that surface, once.
3. In a document, a deck or an image the lockup is small and quiet: the words `Powered by` at caption size, 9pt, 400, `#6D6D77`, then on the same line the Collective Edge horizontal logo at its minimum width, 1.25in (120px) wide and 0.208in (20px) tall. On the closing slide the words are 12pt, `#A3A4AC`. The `horizontal-on-light` file on white, `horizontal-on-dark` on a dark ground. On a site or a dashboard it is the 204px lockup in `cobrand` in `brands.json`.
4. A memo and a one-pager carry it in the footer row of page 1, at left. A report carries it as the last line of the body on the last page. A deck carries it in the footer row of the closing slide. A chart or data graphic made on its own carries no logo: one line of words, `Powered by Collective Edge`, bottom right, caption size, `#6D6D77`.
5. It sits beside the brand’s own logo, never inside it. Never merge, nest or recolor either mark.
6. Two exceptions, from `brands.json`: a clinical instruction and a patient-facing consent or safety document carry no lockup.
7. On an Apex Paramedics or Royal Ambulance surface, that company leads. Its logo heads the page and its palette runs the band. Collective Edge adds no hue.
8. Only the Edge wedge takes a partner color: `#572E72` beside Royal Ambulance and `#FDB61C` beside Apex Paramedics, through the shipped files `mark-black-royal.svg`, `mark-white-royal.svg`, `mark-black-apex.svg` and `mark-white-apex.svg`. Full construction: [reference/brand.md](reference/brand.md) section 3.

## 8. Voice

Collective Edge sounds like a senior operator giving a direct briefing. Restrained, confident, operational, adult.

1. Short declarative sentences. Active verbs. No filler and no throat-clearing.
2. No em dashes. Use a period, a comma or `·`. An en dash only in a date or number range.
3. Exact values. The real number, never a rounded one. The hex, never a description of the color.
4. A label, a value, and nothing between them. No helper text, no caption restating the thing above it, no parenthetical after a heading.
5. No emoji, no exclamation points, no rhetorical questions.
6. Clinical and operational terms stay precise. Name people, partners and facilities exactly as they write themselves.
7. Plain words over jargon. “We” and “you”, never “the customer” or “users”.
8. A two-word claim, a period, then one line of proof. Never define a thing by what it is not.

## 9. Check before shipping

Check the finished file, not the code that made it.

- [ ] Every text run names Montserrat. No run is italic. Every weight is 400, 600, 700 or 800. Three at most in a document. Only a deck uses all four.
- [ ] Every size is a step in section 5 and nothing is under 9pt. Every color is a hex from `tokens.json`. No text is set in `#8A8B93`, `#D0D0D6` or `#E4E4E9`.
- [ ] Body text is `#23232A` on white. On a dark ground headings are `#FFFFFF` and body is `#DDDDE3`.
- [ ] An edited file changed only where asked. A Google file has no exact line spacing, a 6pt table indent and a paragraph between two tables.
- [ ] Margins are 0.75in on a working-doc, a memo or a report and 0.6in on a one-pager. A one-pager, an agenda and a status report are one page.
- [ ] Slides are 13.333 by 7.5in with 15pt body. Only the title, divider and closing slides are dark.
- [ ] The brand’s logo appears once in a document and at most once on a slide, in the role for its ground, at or above the minimum, clear space held, aspect ratio unchanged.
- [ ] “Powered by Collective Edge” appears only where the Collective Edge mark shares a surface with another brand, and then exactly once.
- [ ] Every status color is an alert step for its ground and carries a word or an icon. Green marks good only. Every chart color is from the house data set, with series in order.
- [ ] No em dash in any text. No uppercase run is longer than four words. Body lines hold 70 characters. No text is justified.
- [ ] No hue appears outside a partner mark, the wedge, an alert or a chart. True black fills only the hero and the title, divider and closing slides. As ink it is accent text and the table rule.
- [ ] The file was rendered and looked at. Nothing overlaps, clips or overflows. If you could not render it, say so.

For HTML output, also run `python3 scripts/validate.py FILE.html` and `python3 scripts/ui-audit.py FILE.html`. `validate.py` checks type rules 1, 2, 5, 9, 10, 13 and 14 and check L1, retired logo artwork, and exits non-zero on a violation. It cannot see a rendered page. When you hand the work back, state the brand, the document type, the logo role, how the font embedded, and anything you could not verify. `@main` serves the latest. Production pins a tag in place of `@main`.
