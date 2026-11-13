# Collective Edge · brand reference

The full tables behind `SKILL.md`: color, logo, co-brand and voice. Type is in `reference/type-system.md`. Layout is in `reference/layout.md`. Chart color is in `reference/data-color.md`.

Collective Edge is a holding and operating company. It partners with regional healthcare-transportation providers and brings them shared systems, leadership and long-term capital while local ownership stays in place. It is the parent of Apex Paramedics and Royal Ambulance.

Collective Edge, Apex Paramedics and Royal Ambulance share one standard. The sections, the order and the rules in this file are the same in all three kits. Color, logo and brand facts differ.

`snippets/palette.css` is authoritative for color and `tokens.json` mirrors it. If this file disagrees with either, this file is stale.

---

## 1. Color

### 1.1 Palette

Collective Edge has no hue. It has no accent color and none is to be added, ever. The brand works in seven named tiers from black to white, far enough apart to see. Emphasis comes from weight, size and the step between tiers.

> **No hue, ever. The color belongs to the partner.**

Collective Edge rarely appears alone. It appears beside a partner, and that surface carries the partner’s color.

| Name | Token | Hex | RGB | Use |
|---|---|---|---|---|
| Tier 1 · Black | `--ce-black` | `#000000` | 0, 0, 0 | The hero and the title, divider and closing slides, as `--bg-inverse`. Accent text, as `--fg-accent`. Never the reading surface of a document |
| Tier 2 · Graphite | `--ce-graphite` | `#23232A` | 35, 35, 42 | The header band, as `--bg-band`. The same value is body ink, `--ce-ink` and `--fg-1` |
| Tier 3 · Iron | `--ce-iron` | `#4E4F58` | 78, 79, 88 | The mid tone, as `--bg-mid`. A filled block between band and surface |
| Tier 4 · Fog | `--ce-fog` | `#C8C8C8` | 200, 200, 200 | The Edge wedge when Collective Edge stands alone. The 2.25pt (3px) rule under the band, as `--border-band-rule`. Never text |
| Tier 5 · Paper | `--ce-paper` | `#E5E6EA` | 229, 230, 234 | Table header fill, as `--bg-surface-2`, with a 1.5pt (2px) `#000000` rule under the header row. Never text |
| Tier 6 · Bone | `--ce-bone` | `#F0F1F4` | 240, 241, 244 | Callout fill, as `--bg-surface`. Never text |
| Tier 7 · White | `--ce-white` | `#FFFFFF` | 255, 255, 255 | The document canvas. The default surface |

Black over graphite. Accent text is `#000000` and body ink is `#23232A`. The two measure 1.35:1 against each other, so black reads as an accent at display size only. Black is kept for display.

Four more `--ce-*` names resolve to the shared neutrals in 1.3: `--ce-slate` `#565860`, `--ce-steel` `#6D6D77`, `--ce-mute` `#8A8B93` and `--ce-mist` `#E4E4E9`.

### 1.2 Grounds

Every brand has the same six grounds, from lightest to darkest. White is the page. The last column lists the only text that sits on each ground.

| Ground | Token | Hex | RGB | Against white | Text on it |
|---|---|---|---|---|---|
| Canvas | `--bg-canvas` | `#FFFFFF` | 255, 255, 255 | | `--fg-1`, `--fg-2`, `--fg-3`, `--fg-accent` |
| Surface | `--bg-surface` | `#F0F1F4` | 240, 241, 244 | 1.13:1 | `--fg-1`, `--fg-2`, `--fg-3`, `--fg-accent` |
| Surface 2 | `--bg-surface-2` | `#E5E6EA` | 229, 230, 234 | 1.25:1 | `--fg-1`, `--fg-2`, `--fg-accent`. Never `--fg-3` |
| Mid | `--bg-mid` | `#4E4F58` | 78, 79, 88 | | `--fg-on-dark-1`, `--fg-on-dark-2`. Never `--fg-on-dark-3` |
| Band | `--bg-band` | `#23232A` | 35, 35, 42 | | `--fg-on-dark-1`, `--fg-on-dark-2`, `--fg-on-dark-3` |
| Hero | `--bg-inverse` | `#000000` | 0, 0, 0 | | `--fg-on-dark-1`, `--fg-on-dark-2`, `--fg-on-dark-3` |

Collective Edge is the one brand where Hero and Band differ. The hero and the title, divider and closing slides are true black `#000000`. The band is graphite `#23232A`. Surface 2 is the table header fill, with a 1.5pt (2px) `#000000` rule under the header row.

### 1.3 Neutrals

One neutral family sets text and rules in all three brands. It leans neither blue nor purple, so it sits beside every brand color. Ratios are on `#FFFFFF`.

| Name | Token | Hex | RGB | On white | Use |
|---|---|---|---|---|---|
| Ink | `--neutral-ink` | `#23232A` | 35, 35, 42 | 15.61:1 | Body text and headings on light |
| Secondary | `--neutral-secondary` | `#565860` | 86, 88, 96 | 7.09:1 | Secondary text |
| Tertiary | `--neutral-tertiary` | `#6D6D77` | 109, 109, 119 | 5.12:1 | Captions and metadata. The dimmest text |
| Dimmed | `--neutral-dimmed` | `#8A8B93` | 138, 139, 147 | 3.39:1 | Marks only. Never text |
| Border | `--neutral-border` | `#D0D0D6` | 208, 208, 214 | 1.54:1 | Borders and table rules. Never text |
| Hairline | `--neutral-hairline` | `#E4E4E9` | 228, 228, 233 | 1.27:1 | Hairlines and dividers. Never text |
| Tint 2 | `--neutral-tint-2` | `#E5E6EA` | 229, 230, 234 | 1.25:1 | Stronger neutral tint |
| Tint | `--neutral-tint` | `#F0F1F4` | 240, 241, 244 | 1.13:1 | Neutral surface tint |
| Mid | `--neutral-mid` | `#4E4F58` | 78, 79, 88 | 8.13:1 | Mid tone fill. Diagram process nodes and connectors |
| On-dark body | `--neutral-on-dark-body` | `#DDDDE3` | 221, 221, 227 | | Body text on a dark ground |
| On-dark caption | `--neutral-on-dark-caption` | `#A3A4AC` | 163, 164, 172 | | Captions on a dark ground |

### 1.4 Semantic layer

Style through these names. They are identical in every brand, so a component built for one brand renders correctly in another with only `palette.css` swapped. `tokens.json` carries the same names under `foreground`, `background` and `border`.

| Token | Hex | Use |
|---|---|---|
| `--fg-1` | `#23232A` | Primary text on light |
| `--fg-2` | `#565860` | Secondary text |
| `--fg-3` | `#6D6D77` | Tertiary text, metadata, captions. The dimmest text |
| `--fg-4` | `#8A8B93` | Dimmed marks. Never text |
| `--fg-accent` | `#000000` | Brand-colored text. Collective Edge has no hue, so the accent is black over graphite ink. 21.00:1 on white |
| `--fg-on-dark-1` | `#FFFFFF` | Headings and primary text on a dark ground |
| `--fg-on-dark-2` | `#DDDDE3` | Body text on a dark ground |
| `--fg-on-dark-3` | `#A3A4AC` | Captions and labels on a dark ground |
| `--bg-canvas` | `#FFFFFF` | The page |
| `--bg-surface` | `#F0F1F4` | Callouts |
| `--bg-surface-2` | `#E5E6EA` | The stronger tint |
| `--bg-elevated` | `#FFFFFF` | Raised surface |
| `--bg-mid` | `#4E4F58` | Filled block |
| `--bg-band` | `#23232A` | Header band |
| `--bg-inverse` | `#000000` | Hero, title slide |
| `--border-1` | `#E4E4E9` | Hairlines and dividers |
| `--border-2` | `#D0D0D6` | Stronger rule |
| `--border-on-dark` | `rgba(255,255,255,0.12)` | Rules on a dark ground |
| `--border-band-rule` | `#C8C8C8` | The 2.25pt (3px) rule under the band. Fog. 9.33:1 on the band |

The focus ring on a control is `#000000` on light and `#FFFFFF` on dark, 2px wide at a 2px offset.

### 1.5 Alerts

Four meanings, one family, identical in every brand, so a signal never changes meaning between documents. Green means good and nothing else. A brand color is never a status color. A word or an icon always travels with the color.

| Meaning | Base | Text | Tint | Text on tint | On dark |
|---|---|---|---|---|---|
| Go · cleared, on time, in service, favorable | `#1E7A4D` | `#1E7A4D` | `#DAF8DF` | `#1E7A4D` | `#56B580` |
| Warn · at risk, pending, watch, caution | `#B5821A` | `#926603` | `#FFEFDD` | `#926603` | `#E9B457` |
| Stop · failed, out of service, blocked, unfavorable | `#B0322B` | `#B0322B` | `#FDE9E6` | `#B0322B` | `#EB685C` |
| Info · neutral notice | `#2A5A8C` | `#2A5A8C` | `#E3F0FF` | `#2A5A8C` | `#5796D9` |

| Step | CSS name | `tokens.json` | Use |
|---|---|---|---|
| Base | `--alert-<name>` | `alert.<name>.base` | A fill, a rule or a dot on a light ground |
| Text | `--alert-<name>-text` | `alert.<name>.text` | Text on white and on Surface |
| Tint | `--alert-<name>-tint` | `alert.<name>.tint` | A pill or a callout fill |
| Text on tint | `--alert-<name>-on-tint` | `alert.<name>.onTint` | Text on the matching tint |
| On dark | `--alert-<name>-on-dark` | `alert.<name>.onDark` | Text, dots and rules on a dark ground |

Worst measured ratio across white, the three brand surfaces and the three brand bands:

| Step | Go | Warn | Stop | Info |
|---|---|---|---|---|
| Text on white and on Surface | 4.71:1 | 4.51:1 | 5.57:1 | 6.33:1 |
| Text on tint | 4.68:1 | 4.52:1 | 5.39:1 | 6.18:1 |
| On dark, on the bands | 5.76:1 | 7.72:1 | 4.62:1 | 4.69:1 |

**Canonical names and aliases.** `--alert-*` is canonical. It holds one value on every ground. Pick the step for the ground. Three sets are aliases of it and resolve to the same values:

| Alias | Resolves to | Note |
|---|---|---|
| `--status-go`, `--status-warn`, `--status-stop`, `--status-info` | The alert base | Under `.bk-on-dark` they move to the on-dark step |
| `--dir-favorable`, `--dir-unfavorable`, `--dir-caution` | Go text, stop text, warn text | The data layer. `--dir-neutral` is Tertiary `#6D6D77` |
| `--diagram-decision`, `--diagram-warning` | Go base, warn base | Section 1.6 |

**Status on a dark ground.** Status works on a band. Use the on-dark step: `#56B580`, `#E9B457`, `#EB685C`, `#5796D9`. The worst case is stop on the Apex band, 4.62:1.

**Warn.** The base `#B5821A` measures 3.40:1 on white. It is a fill, a rule or a dot, never text. Warn text is `#926603`, 5.09:1 on white. Text on an amber fill is `#23232A`, 4.59:1. White on amber measures 3.40:1 and fails.

**Surface 2.** On Surface 2, go text measures 4.27:1 and warn text 4.08:1. Neither sits bare on that ground. Carry them in a tint pill there. Stop and info hold.

### 1.6 Diagram roles

Identical in every brand, so a diagram reads the same in any document. Every node is a rectangle with a 6px radius. Fill carries the role, never shape. Each role names the one text color that clears contrast on its fill.

| Role | Fill | Border | Text | Contrast | Use |
|---|---|---|---|---|---|
| Decision | `#1E7A4D` | `#036139` | `#FFFFFF` | 5.32:1 | Decision boxes, questions, branch points |
| Warning | `#B5821A` | `#926603` | `#23232A` | 4.59:1 | Warnings, advisories. Ink, never white |
| Process | `#4E4F58` | `#23232A` | `#FFFFFF` | 8.13:1 | Neutral process steps, context boxes |
| Connector | `#4E4F58` stroke | | | | Lines between nodes, 1.8pt, with arrow markers |
| Brand role | None | | | | This kit adds no role |

A node carries its own ground, so these values do not change on a band.

### 1.7 Charts

Chart colors come from the house data set, never from the brand palette. A brand color is never a chart series. The standard is [data-color.md](data-color.md). The one chart value that follows the brand is the sequential ramp:

| Step | 100 | 200 | 300 | 400 | 500 | 600 | 700 |
|---|---|---|---|---|---|---|---|
| On light | `#EEEEF2` | `#D3D4D9` | `#B6B7BD` | `#97989F` | `#76777F` | `#51525A` | `#23232A` |
| On dark | `#37383C` | `#4C4D52` | `#626369` | `#7C7D84` | `#9698A0` | `#B6B7BE` | `#DCDDE4` |

Collective Edge has no hue, so its ramp is the neutral and step 700 is `--fg-1` `#23232A`. Steps 100 and 200 are for continuous scales only. On a dark ground the lightest step is the largest value.

### 1.8 Contrast

WCAG 2 relative luminance. Body-size text needs 4.5:1. Large text needs 3:1 and starts at 18pt regular or 14pt bold. Use these figures. Do not restate a different one.

| Pair | Ratio | Verdict |
|---|---|---|
| `#23232A` on `#FFFFFF` | 15.61:1 | Any size |
| `#23232A` on `#F0F1F4` | 13.82:1 | Any size |
| `#23232A` on `#E5E6EA` | 12.52:1 | Any size |
| `#565860` on `#FFFFFF` | 7.09:1 | Any size |
| `#565860` on `#F0F1F4` | 6.28:1 | Any size |
| `#565860` on `#E5E6EA` | 5.69:1 | Any size |
| `#6D6D77` on `#FFFFFF` | 5.12:1 | Any size. The dimmest text |
| `#6D6D77` on `#F0F1F4` | 4.53:1 | Any size |
| `#6D6D77` on `#E5E6EA` | 4.10:1 | Fails. Never on Surface 2 |
| `#8A8B93` on `#FFFFFF` | 3.39:1 | Never text |
| `#C8C8C8` on `#FFFFFF` | 1.67:1 | Never text |
| `#000000` on `#FFFFFF` | 21.00:1 | Any size |
| `#000000` on `#F0F1F4` | 18.59:1 | Any size |
| `#000000` against `#23232A` | 1.35:1 | Accent and body ink separate at display size only |
| `#FFFFFF` on `#23232A` | 15.61:1 | Any size |
| `#DDDDE3` on `#23232A` | 11.54:1 | Any size |
| `#A3A4AC` on `#23232A` | 6.29:1 | Any size |
| `#C8C8C8` on `#23232A` | 9.33:1 | The rule under the band |
| `#FFFFFF` on `#000000` | 21.00:1 | Any size |
| `#DDDDE3` on `#000000` | 15.53:1 | Any size |
| `#A3A4AC` on `#000000` | 8.46:1 | Any size |
| `#FFFFFF` on `#4E4F58` | 8.13:1 | Any size |
| `#DDDDE3` on `#4E4F58` | 6.01:1 | Any size |
| `#A3A4AC` on `#4E4F58` | 3.28:1 | Fails. Never on Mid |

### 1.9 Never

- `#8A8B93`, `#D0D0D6` and `#E4E4E9` are never text.
- A brand color is never a status color and never a chart series.
- A status color is never a theme, a background or a decoration.
- The band is never the reading surface of a document.
- No color enters a document that is not in `tokens.json`.
- Never add a hue to a Collective Edge surface. No accent color and no tinted neutral.
- `#000000` is never the reading surface of a document and never the header band. The band is `#23232A`.
- `#C8C8C8`, `#E5E6EA` and `#F0F1F4` are never text.
- A partner’s hue never colors the block or the letters of the mark. It colors the wedge.
- A partner’s accent never appears on a surface that carries Collective Edge alone.
- The grain wave never sits under body copy and never on a document page.

---

## 2. Logo

### 2.1 Roles and files

Ask for a role, never a filename. Filenames differ between brands. `-on-light` is the file placed on a light background. `-on-dark` is the file placed on a dark one. SVG files are in `assets/logos/`. PNG files are in `for-humans/logos/png/`, each at two widths.

| Role | SVG | PNG | The artwork |
|---|---|---|---|
| `horizontal-on-light` | `horizontal-black.svg` | `Collective-Edge-horizontal-black-1200w.png`, `-2400w.png` | Black block and COLLECTIVE, `#666666` EDGE, `#CCCCCC` wedge |
| `horizontal-on-dark` | `horizontal-white.svg` | `Collective-Edge-horizontal-white-1200w.png`, `-2400w.png` | White block and COLLECTIVE, `#CCCCCC` EDGE and wedge |
| `compact-on-light` | None | None | Collective Edge ships no compact lockup |
| `compact-on-dark` | None | None | Collective Edge ships no compact lockup |
| `mark-on-light` | `mark-black.svg` | `Collective-Edge-mark-black-512w.png`, `-1024w.png` | Black block, white letters, `#C8C8C8` wedge |
| `mark-on-dark` | `mark-white.svg` | `Collective-Edge-mark-white-512w.png`, `-1024w.png` | White block, black letters, `#C8C8C8` wedge |
| `stacked-on-light` | None | None | Collective Edge ships no stacked lockup |
| `stacked-on-dark` | None | None | Collective Edge ships no stacked lockup |
| `app-icon` | None | None | Collective Edge ships no app icon |

The horizontal lockup is the primary logo. The block mark is for favicons, avatars and badges. The file named for its ink goes on the opposite background. The drawn fills are final. Read them, do not override them. The partner marks are in 3.5.

### 2.2 Specifications

| Property | Value |
|---|---|
| Horizontal viewBox | `0 0 450 74.999997`, 6:1 |
| Compact viewBox | None |
| Mark viewBox | `0 0 375 262.499992` |
| Stacked viewBox | None |
| App icon viewBox | None |
| Fill on light | `#000000` block and letters. EDGE `#666666`. Wedge `#CCCCCC` in the lockup and `#C8C8C8` in the block mark |
| Fill on dark | `#FFFFFF` block and letters. EDGE `#CCCCCC`. Wedge `#CCCCCC` in the lockup and `#C8C8C8` in the block mark |
| Minimum, horizontal | 120px on screen, 1in in print |
| Minimum, compact | None |
| Minimum, mark | 28px on screen. No print value is stated |
| Minimum, app icon | None |
| Clear space | The height of the Edge wedge, on all four sides |
| Vector master | The SVG files in `assets/logos/`. No separate vector master ships. `assets/png/` holds raster derivatives, never the master |
| Embedding | Place the PNG in an office document. Reference the CDN URL with `<img>` in HTML. Never inline a copied SVG path |

### 2.3 Do not

- Do not stretch, skew or rotate a logo.
- Do not recolor a logo, and do not invert one with a filter. Pick the file for the ground.
- Do not add a shadow, a glow, an outline or a gradient.
- Do not place a logo on a photograph without a solid backing.
- Do not set a logo below its minimum size.
- Do not crop the clear space. Shrink the logo instead, down to the minimum.
- Do not put one brand’s logo twice on a page or slide.
- Do not color anything but the wedge. The block and the letters stay black or white.
- Do not force EDGE to full black or full white. It is gray.
- Do not split the block mark from the wordmark in the horizontal lockup.
- Do not merge, nest or combine the mark with a partner’s mark.

---

## 3. Co-brand

Apex Paramedics and Royal Ambulance are operating companies under Collective Edge, and the reader should be able to see it. The rules in this section are identical in all three kits.

### 3.1 The lockup

“Powered by Collective Edge” is one lockup. It is the label `POWERED BY` over the Collective Edge horizontal lockup, under a hairline. `cobrand` in `brands.json` carries every value below, and `snippets/cobrand.css` is the HTML implementation.

| Part | Value |
|---|---|
| Label | `POWERED BY`. Weight 600, uppercase, 9pt in print and 12px on screen, tracking 0.080em |
| Label color | `#6D6D77` on white, 5.12:1. `#A3A4AC` on a dark ground |
| Lockup on white | The Collective Edge `horizontal-on-light` file, `assets/logos/horizontal-black.svg` in the Collective Edge kit |
| Lockup on a dark ground | The Collective Edge `horizontal-on-dark` file, `assets/logos/horizontal-white.svg` in the Collective Edge kit |
| Width | 2.125in (204px) wide, 0.354in (34px) tall. The artwork is 6:1 |
| Floor | 120px. A floor, not a target |
| Hairline | 0.75pt (1px) above the label. `#E4E4E9` on white. White at 12 percent on a dark ground |
| Spacing | On a site: 18pt (24px) above the hairline, 18pt (24px) between hairline and label, 9pt (12px) between label and lockup. In a document: `reference/layout.md` section 3.12 |
| Ground | The light lockup sits on white, not on a tint |
| CSS classes | `.ce-powered` on a dark ground. `.ce-powered ce-powered-light` on white. `.ce-powered-text` where no mark fits |

The label measures 6.29:1 on this brand’s band.

### 3.2 Where it goes

1. “Powered by Collective Edge” appears once on every Apex Paramedics and Royal Ambulance document.
2. A Collective Edge document carries the Collective Edge logo in its band and no lockup.
3. Where the Collective Edge mark shares a surface with another brand, the lockup is on that surface, once.

| Surface | Place |
|---|---|
| Memo, one-pager | The footer row, at left |
| Report | The last block of the body on the last page |
| Deck | The closing slide |
| Site | The footer |
| Dashboard | The sidebar header |
| Data page or methodology page | Anywhere a number was computed and not typed |

### 3.3 Never

- Never put the lockup on the partner’s own mark or inside its lockup.
- Never merge, nest or recolor either mark to match the other.
- Never use it twice in one document or on one surface.
- Never set the phrase as type where the mark fits.
- Never design the lockup down to the 120px floor.
- Never put it on a clinical instruction.
- Never put it on a patient-facing consent or safety document.

The last two are the only documents that carry no lockup.

### 3.4 Who leads

Ask whose name is on the door.

| | Partner led | Collective Edge led |
|---|---|---|
| When | The surface belongs to Apex Paramedics, Royal Ambulance or another partner. The default | A Collective Edge product delivered to a partner or its customer |
| Logo | The partner’s logo heads the surface | The Collective Edge logo heads the surface |
| Palette | The partner’s palette runs the band and the accents | White canvas and the Collective Edge tiers |
| Collective Edge adds | Type, hairlines and whitespace. No hue. The lockup, once | The partner’s color as the one hue, on live and active states only. Never a chart series |

When in doubt, the partner leads. Hold one mode on a surface. Never stack more than three marks in one lockup. Take a partner’s hex from `brands.json` or from that partner’s kit, never from a copy. `unreconciled` in `brands.json` lists placeholder colors for brands with no kit. Confirm those with the owner before use.

### 3.5 The wedge

The Edge wedge is the one part of the Collective Edge block mark that takes color, and that color is the partner’s. Every combination ships as a file in the Collective Edge kit, under `assets/logos/`. Never recolor a mark by hand.

| Wedge | Hex | On light | On dark |
|---|---|---|---|
| Alone | `#C8C8C8` | `mark-black.svg` | `mark-white.svg` |
| With Royal Ambulance | `#572E72` | `mark-black-royal.svg` | `mark-white-royal.svg` |
| With Apex Paramedics | `#FDB61C` | `mark-black-apex.svg` | `mark-white-apex.svg` |

The wedge color never leaves the wedge. The block and the letters stay black or white on every surface. When Collective Edge stands alone the wedge is gray `#C8C8C8`. At favicon size on a white tile the gray wedge nearly disappears. Give the mark a dark backing. Do not add a hue to fix it.

---

## 4. Voice

### 4.1 Character

Restrained. Confident. Operational. Adult. Collective Edge sounds like a senior operator giving a direct briefing.

### 4.2 Rules

- Short declarative sentences. Active verbs. No filler and no throat-clearing.
- No em dashes. Use a period, a comma or `·`. An en dash only in a date or number range, per rule 14 of the type system.
- Exact values. The real number, never a rounded one. The hex, never a description of the color.
- A label, a value, and nothing between them. No helper text under a field, no caption restating the thing above it, no parenthetical after a heading.
- Write a caption only when it carries information the thing above it does not.
- Sentence case for every heading. Uppercase for the band title, the title slide title and the lockup label only. Always tracked, never past four words.
- No emoji, no exclamation points, no rhetorical questions.
- Clinical and operational terms stay precise. Never soften a protocol term.
- Name people, partners and facilities exactly as they write themselves.
- When you hand work back, state the brand, the document type, the logo role and how the font embedded.
- Plain words over jargon. “We understand what works and scale it.” Never leverage, synergize or unlock.
- “We” and “you”. Never “the customer” or “users”.
- A two-word claim, a period, then one line of proof. “**Proven playbooks.** We understand what works and scale it.”
- Headlines often end in a period. It makes a claim read as settled.
- Long horizon. Decades, not quarters. Reinvestment in people and culture.
- Never define a thing by what it is not. No “Not this” beside “This”. Say the thing once.
- No forward slash between words. Write “and”, “or”, a comma or `·`.

---

## 5. Only in this kit

### 5.1 The hero treatment

True black `#000000` under the grain wave. It is for the title slide, section dividers and the marketing hero, once per surface. It never sits under body copy and never on a document page. A deck built from `reference/layout.md` does not use it. Its dark slides are flat `#000000`. The grain wave is the only texture in the system.

| Asset | Path |
|---|---|
| Slide background, scrim already composited | `assets/imagery/CE_Title_Card_1920x1080.jpg`, `assets/imagery/CE_Title_Card_3840x2160.jpg` |
| Web background | `assets/imagery/CE_Background_1920.jpg`, `assets/imagery/CE_Background_3840.jpg` |
| Master | `assets/imagery/CE_Background.jpeg` |
| CSS | `snippets/hero-dark.css`, class `bk-hero-dark` |

White type on the wave sits bottom-centre at 15.3:1, bottom-left at 14.4:1 or top-right at 8.6:1. Never centred, middle-left or top-left, where the wave is light. Display weight on the hero is 700. `heroTreatment` in `brands.json` carries every zone.

### 5.2 The wordmark pairing

The wordmark sets COLLECTIVE heavy in black and EDGE in gray. A headline may echo it: the first phrase at 800 in `--fg-1`, the continuation at 400 in `--fg-3`. The pairing is weight and color, never slant. There is no italic.

### 5.3 The bar

The vertical bar in `CE │ COLLECTIVE EDGE` is drawn geometry inside the artwork, not typed punctuation. Reuse it as a 1px rule when pairing Collective Edge with a partner, a customer or a section name. In running text, separate items with `·`.

---

## 6. Files and versions

| What | Path |
|---|---|
| CDN root | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/` |
| Repository | `collective-edge/collective-edge-brand-kit` |
| Palette, authoritative | `snippets/palette.css` |
| Colors as data | `tokens.json`, version 2.0 |
| Type as data | `snippets/type-tokens.json` |
| Registry of every brand | `brands.json` |
| Logos | `assets/logos/` as SVG, `for-humans/logos/png/` as PNG |
| Fonts | `for-humans/fonts/static/` as static files. The variable font is served from the Collective Edge kit |
| Templates | `templates/` |

`@main` serves the latest. Production pins a tag in place of `@main`. Bump the minor version for an additive change. Bump the major version when a palette value or a mark changes.

These files predate the house type system. They stay on the CDN because documents already point at them. New work never loads them.

| Deprecated | Replaced by |
|---|---|
| `snippets/brand-base.css` | `snippets/type-system.css` and `snippets/palette.css` |
| `assets/colors.json` | `tokens.json` |
| The `.ce-*` classes | The `.bk-*` classes |
