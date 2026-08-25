# Collective Edge, layout patterns

House patterns for Collective Edge, on type system v1.0. Every block below is copy-pasteable and assumes `type-system.css` and `palette.css` are loaded. Style through `.bk-*` classes and the semantic `--fg-*` / `--bg-*` / `--border-*` variables. Reach for a raw `--ce-*` value only where the brand color is the point.

**What changed at v1.0.** Uppercase caps labels and table headers moved from 800 to 600. Stat numerals moved from 800 to 700. Dark bands drop one weight, so display sets at 700 there, not 800. Every letter-spacing is em, never px. Every size comes from the scale table in `reference/type-system.md`. Every vertical value is a multiple of 4.

---

## 1. Header band

Opens nearly every deliverable. Black ground, white logo. `.bk-on-dark` on the container drops display from 800 to 700 and adds 0.005em to every step under it. Never restate either value inline: the container already resolved it, and an inline copy goes stale the moment a token moves. The band title is a masthead, not the document heading. Set it as a `<p>` and leave the one `<h1>` for the page title.

```html
<header class="bk-on-dark" style="background:var(--bg-band); padding:32px 48px; display:flex; align-items:center; justify-content:space-between; gap:48px;">
  <div>
    <p class="bk-eyebrow" style="margin:0 0 8px;">INTERNAL · CONFIDENTIAL</p>
    <p class="bk-display-md bk-caps" style="margin:0;">HOW WE OPERATE TOGETHER</p>
  </div>
  <img src="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-white.svg"
       alt="Collective Edge" style="width:204px; height:auto; display:block; flex:none;">
</header>
```

On a co-brand surface, swap the single logo for the partner mark above the CE lockup under a `--border-on-dark` rule, and keep “Powered by Collective Edge” in a `.bk-eyebrow`.

## 2. Co-brand lockup

The most common Collective Edge surface. Two marks, never merged, separated by a 1px rule at roughly the height of the marks. Mode A when the partner’s name is on the door, mode B when the artifact is a CE product delivered to them. Filenames differ between partner kits, so read the role table in `reference/brand.md` section 4 rather than carrying a path across brands.

**Mode A, partner led.** The partner’s mark heads the surface, the CE lockup sits beneath it under a hairline. Dark ground. The CSS is [`snippets/cobrand.css`](../snippets/cobrand.css), shared and byte-identical in every kit. Load it after the palette. Do not restate the geometry inline.

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/cobrand.css">

<div class="brand-head bk-on-dark">
  <img alt="Apex Paramedics" width="158"
       src="https://cdn.jsdelivr.net/gh/collective-edge/apex-brand-kit@main/assets/logos/horizontal-white.svg">
  <div class="ce-powered">
    <span>Powered by</span>
    <img alt="CE · Collective Edge" width="204" height="34"
         src="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-white.svg">
  </div>
</div>
```

The label takes the surface’s tertiary grey from `--fg-on-dark-3`, which each palette supplies. On the black CE band that resolves to `#9E9E9E` at 7.84:1. On the Apex deep ground `#1D225E` it resolves to `#9EA5C4` at 5.98:1. The pre-v1.0 dashboards hardcoded `#9AA0C9` there, which measures 5.72:1 on the same ground and 2.55:1 on white; it is never text on light and there is no reason to type it now that the token exists.

**Mode B, CE led.** CE first, the partner second, the bar between them. Light ground, so the partner appears in their own color file while CE appears in black.

```html
<div style="display:flex; align-items:center; gap:14px;">
  <img alt="Collective Edge" style="height:40px; display:block;"
       src="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-black.svg">
  <span style="width:1px; height:40px; background:rgba(17,17,17,0.14);"></span>
  <img alt="Apex Paramedics" style="height:38px; display:block;"
       src="https://cdn.jsdelivr.net/gh/collective-edge/apex-brand-kit@main/assets/logos/horizontal-color.svg">
</div>
<p class="bk-eyebrow" style="margin:16px 0 0;">POWERED BY COLLECTIVE EDGE</p>
```

The caption is `.bk-eyebrow`: 600 uppercase at `--fs-eyebrow` with `--tr-caps-small`, on `--fg-3`. CE sits at 40px and the partner at 38px so the two optical heights match. Three marks read `CE │ Apex Paramedics │ {Customer}`, left to right by who built it and who it is for. Never a fourth.

### The shipped lockup, “Powered by Collective Edge”

This is the pattern the operating companies are asked to apply, and it is already running in three places: the Apex website footer, the Apex internal dashboard sidebar, and the Apex partner page. The parent book carries it so the parent and the partners agree.

The rule, and it is the whole rule: **the CE lockup rides beside the partner brand, never inside it, so a hairline keeps the two marks distinct.** The two read as two brands rather than one combined mark.

204px is the shipped width in both the footer and the sidebar. The lockup is sized to read at a glance rather than sit quietly in a corner, which is why it runs wider than the partner mark above it: 204px of CE under 158px of Apex. The 120px minimum in section 4 of `reference/brand.md` is a floor, not a target. The artwork is 450 x 75, a 6:1 ratio, so 204px wide renders 34px tall.

**Light ground.** The shipped lockup only ever ran on dark. A white one-pager or report footer needs the other half: the black lockup, the label in `--fg-3`, the hairline in `--border-1`. Same geometry, same 204px.

```html
<div class="ce-powered ce-powered-light">
  <span>Powered by</span>
  <img alt="CE · Collective Edge" width="204" height="34"
       src="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-black.svg">
</div>
```

**Text only.** Where no lockup fits, `.ce-powered-text` sets the phrase at `.bk-eyebrow` values: `--fs-eyebrow` 12px web and 9pt print, weight 600, `--tr-caps-small` 0.080em. The Apex customer dashboard ships it at 9px and 700, under the 9pt floor and heavier than the caps-label step. Use the class.

```html
<p class="ce-powered-text">Powered by Collective Edge</p>
```

**The mirror, on a CE-led surface.** `templates/document.html` and `templates/deck.html` already carry the CE mark, so the slot beneath the hairline holds the partner instead. Same class, same 204px slot, same hairline. The label names the relationship rather than repeating it. Height changes with the partner: the Apex horizontal lockup is 687.72 x 289.25, so 204px wide renders 86px tall, and the Royal horizontal lockup is 735.76 x 179.54, so 204px wide renders 50px tall.

```html
<div class="ce-powered ce-powered-light">
  <span>Operating company</span>
  <img alt="Apex Paramedics" width="204" height="86"
       src="https://cdn.jsdelivr.net/gh/collective-edge/apex-brand-kit@main/assets/logos/horizontal-color.svg">
</div>
```

| Part | Value on CE’s own ground |
|---|---|
| Lockup width | 204px, rendering 34px tall |
| Label | `--fs-caption` 12px web and 9pt print, weight 600, `--tr-caps-small` 0.080em, uppercase |
| Label on dark | `--fg-on-dark-3` `#9E9E9E` on `--bg-band` `#000000`, 7.84:1 |
| Label on light | `--fg-3` `#6E6E6E` on `--bg-canvas` `#FFFFFF`, 5.10:1 |
| Hairline on dark | 1px `--border-on-dark` `rgba(255,255,255,0.12)` |
| Hairline on light | 1px `--border-1` `#E2E2E2` |
| Spacing | 24px above the hairline and 24px below it, 12px between label and lockup |

The light lockup goes on `--bg-canvas`. On `--bg-surface` `#FAFAFA` the same grey measures 4.89:1, which still clears 4.5:1 for CE but not for Apex, where the tint takes it to 4.31:1. Keep the whole house on the canvas so one block serves all three.

**Where it belongs.** The footer of any site or printed document. The sidebar header of any dashboard. The closing slide of a deck. The foot of a report. A data page or a methodology page. Anywhere a number was computed rather than typed.

**Where it does not.** On the partner’s own mark or inside their lockup. On a clinical instruction. On a patient-facing consent or safety document. Twice on one surface. Set as type where the mark fits.

## 3. Sub-banner

The strip under the header band. Carries scope, date and audience. Light ground, hairline bottom rule, no color.

```html
<div style="background:var(--bg-surface); border-bottom:1px solid var(--border-1); padding:12px 48px; display:flex; justify-content:space-between; align-items:baseline; gap:24px;">
  <p class="bk-eyebrow" style="margin:0;">OPERATING BRIEF · Q3 2026</p>
  <p class="bk-caption" style="margin:0;">Prepared for partner leadership</p>
</div>
```

## 4. Section head, the under-header hairline

The signature motif. An eyebrow, a sentence-case heading, a 1px `--border-1` rule underneath. It appears under nearly every section title.

```html
<header style="padding:0 0 12px; border-bottom:1px solid var(--border-1); margin:48px 0 16px;">
  <p class="bk-eyebrow" style="margin:0 0 4px;">EDGE</p>
  <h2 class="bk-h2" style="margin:0;">What we bring.</h2>
</header>
```

Space above a heading is three times the space below it. 48px above, 16px below.

## 5. Bold-then-explain

The house claim line. A two-word claim at 700, a period, then a regular-weight proof.

```html
<p class="bk-body"><span class="bk-emphasis">Proven playbooks.</span> We understand what works and scale it.</p>
```

## 6. Not this. This.

Split 50 50 with a centered vertical rule. Secondary label in `--fg-3`, primary label in `--fg-1`. The secondary label is dimmer, not unreadable: `--fg-4` `#9A9A9A` measures 2.81:1 on white and fails at every size, so `--fg-3` `#6E6E6E` at 5.10:1 is the dim end of the ramp for anything anyone reads.

```html
<div style="display:grid; grid-template-columns:1fr 1px 1fr; gap:32px; align-items:start;">
  <div>
    <p class="bk-h4" style="margin:0 0 12px; color:var(--fg-3);">Not this</p>
    <p class="bk-body-sm" style="margin:0 0 8px;">Acquire and rebrand overnight.</p>
    <p class="bk-body-sm" style="margin:0;">Financial extraction.</p>
  </div>
  <div style="background:var(--border-1); align-self:stretch;"></div>
  <div>
    <p class="bk-h4" style="margin:0 0 12px;">This</p>
    <p class="bk-body" style="margin:0 0 8px;">Earn trust, then build together.</p>
    <p class="bk-body" style="margin:0;">Reinvestment in people and culture.</p>
  </div>
</div>
```

## 7. Flowchart nodes

Rectangles, 6px radius. Role is communicated by fill, never by shape. The three role colors and the connector are identical across every brand and come from `brands.json`. Node text sits on a dark fill, so the label is 600, not 700 or 800.

**Two of these fills do not hold white text.** `#FFFFFF` measures 2.70:1 on `#f57c00` and 4.02:1 on `#4a8e3a`. The green passes as large or bold text only, the orange fails outright, and the labels below sit at 14px 600, which is neither. The fills and their white text are inherited from the original kits and are frozen pending an owner decision, so do not recolor them here. Carry the meaning in the connector label or the prose beside the figure as well, never in the node label alone. `#3e3e3e` is the only fill in the set that holds white body-size text.

```html
<div style="display:flex; align-items:center; gap:16px; flex-wrap:wrap;">

  <div class="bk-on-dark" style="background:#3e3e3e; border:1px solid #2a2a2a; border-radius:6px; padding:16px 24px;">
    <p class="bk-body-sm" style="margin:0; max-width:28ch; font-weight:600; color:var(--fg-on-dark-1);">Intake received</p>
  </div>

  <svg width="48" height="12" aria-hidden="true"><line x1="0" y1="6" x2="40" y2="6" stroke="#3e3e3e" stroke-width="1.8"/><path d="M40 2 L48 6 L40 10 Z" fill="#3e3e3e"/></svg>

  <div class="bk-on-dark" style="background:#4a8e3a; border:1px solid #3a7029; border-radius:6px; padding:16px 24px;">
    <p class="bk-body-sm" style="margin:0; max-width:28ch; font-weight:600; color:var(--fg-on-dark-1);">Coverage confirmed?</p>
  </div>

  <svg width="48" height="12" aria-hidden="true"><line x1="0" y1="6" x2="40" y2="6" stroke="#3e3e3e" stroke-width="1.8"/><path d="M40 2 L48 6 L40 10 Z" fill="#3e3e3e"/></svg>

  <div class="bk-on-dark" style="background:#f57c00; border:1px solid #cc6600; border-radius:6px; padding:16px 24px;">
    <p class="bk-body-sm" style="margin:0; max-width:28ch; font-weight:600; color:var(--fg-on-dark-1);">Hold for authorization</p>
  </div>

</div>
```

Node roles: `#4a8e3a` on `#3a7029` for decisions, questions and branch points. `#f57c00` on `#cc6600` for warnings and advisories. `#3e3e3e` on `#2a2a2a` for neutral process steps and context. Connector stroke `#3e3e3e` at 1.8pt. Never invent a fourth hue for a fourth role.

## 8. Stat callouts

The numeral is `.bk-stat`, which is 700 and tabular. It was 800 before v1.0. ExtraBold at that size reads as a slab rather than a number. The label above it is `.bk-eyebrow`, 600 uppercase. A label, a value, and nothing between them.

The unit goes in the label. Setting it in a heading class beside the numeral adds a fourth size above body and breaks rule 3.

```html
<div style="display:grid; grid-template-columns:repeat(auto-fit, minmax(160px, 1fr)); gap:32px; border-top:1px solid var(--border-1); padding-top:24px;">
  <div>
    <p class="bk-eyebrow" style="margin:0 0 4px;">RESPONSE · MINUTES</p>
    <p class="bk-stat" style="margin:0;">12</p>
  </div>
  <div>
    <p class="bk-eyebrow" style="margin:0 0 4px;">FACILITIES SERVED</p>
    <p class="bk-stat" style="margin:0;">148</p>
  </div>
</div>
```

Do not write a caption under a stat restating what the number is. The label already did that.

## 9. Tables

`.bk-table` sets the header row to 600 uppercase with 0.080em tracking, and puts tabular figures on every cell. Hairlines, not boxes. No zebra fill.

**Size the header to the body it labels.** The shared `.bk-table th` rule ships at `--fs-caption`, 12px web and 9pt print. Where cells set at `--fs-body-sm`, as they do below, that puts an uppercase header one step under the copy it heads, which is the failure the caps-label rule in `reference/type-system.md` section 4 exists to prevent. Set `th` to the cell size explicitly until the shared rule changes.

```html
<table class="bk-table" style="width:100%;">
  <!-- th matches the cell size. The shared rule ships one step smaller. -->
  <caption class="bk-eyebrow" style="margin:0 0 8px;">WHERE THE VALUE GOES</caption>
  <thead>
    <tr style="border-bottom:1px solid var(--border-2);">
      <th style="padding:8px 16px 8px 0; font-size:var(--fs-body-sm);">Line</th>
      <th style="padding:8px 16px 8px 0; font-size:var(--fs-body-sm);">Owner</th>
      <th style="padding:8px 0 8px 16px; text-align:right; font-size:var(--fs-body-sm);">Share</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom:1px solid var(--border-1);">
      <td style="padding:8px 16px 8px 0; font-size:var(--fs-body-sm); line-height:var(--lh-body-sm); color:var(--fg-1);">Crew wages</td>
      <td style="padding:8px 16px 8px 0; font-size:var(--fs-body-sm); line-height:var(--lh-body-sm); color:var(--fg-2);">Operating company</td>
      <td style="padding:8px 0 8px 16px; font-size:var(--fs-body-sm); line-height:var(--lh-body-sm); color:var(--fg-1); text-align:right;">62%</td>
    </tr>
    <tr style="border-bottom:1px solid var(--border-1);">
      <td style="padding:8px 16px 8px 0; font-size:var(--fs-body-sm); line-height:var(--lh-body-sm); color:var(--fg-1);">Fleet and equipment</td>
      <td style="padding:8px 16px 8px 0; font-size:var(--fs-body-sm); line-height:var(--lh-body-sm); color:var(--fg-2);">Shared</td>
      <td style="padding:8px 0 8px 16px; font-size:var(--fs-body-sm); line-height:var(--lh-body-sm); color:var(--fg-1); text-align:right;">21%</td>
    </tr>
  </tbody>
</table>
```

A dark table header row takes `.bk-on-dark` on the `<thead>` and `--bg-inverse` as its fill. The header weight stays 600 there. Any run number, unit ID or authorization number inside a cell goes in `.bk-code`, never Montserrat. A count, a percentage and a median are measurements and stay Montserrat, with `.bk-tnum` so they align down the column.

## 10. Footer

Slim strip, 1px `--border-1` top rule. Left: the document signature in `--fg-3`. A footer signature sets at 12px web and 9pt print, the smallest step on the ladder, so it takes the 5.10:1 grey and never `--fg-4`. Right: the revision marker at 700 in `--fg-1`, wrapped in `.bk-code`. A revision marker is dictated, so it is a record identifier and takes the mono face. It is one of the four kinds the face is whitelisted for. The separator in text is a middot. The vertical bar belongs to the logo, not to typed copy.

```html
<footer style="border-top:1px solid var(--border-1); margin-top:48px; padding:12px 0; display:flex; justify-content:space-between; align-items:baseline; gap:24px;">
  <span class="bk-caption">Collective Edge · How we operate together</span>
  <span class="bk-caption bk-emphasis"><span class="bk-code">Rev.&nbsp;08.26</span></span>
</footer>
```

---

## Conventions that hold across every pattern

- **White canvas, generous margins.** Content lives well inside the page edge. CE breathes. Do not fill every pixel.
- **Hairlines, not boxes.** Prefer a single 1px `--border-1` rule or a 1px vertical column divider over bordered cards.
- **Cards are flat.** `--bg-surface` fill, `--radius-md` 6px or square, `--shadow-1` only when in a list of equal elevations, 24px to 32px padding.
- **Corners mostly square.** 0px to 6px. No squircles, no pills except tag chips.
- **Buttons.** Primary is `--ce-black` fill with `#FFFFFF` text, 2px or square corners, 600 weight, 0.080em caps tracking, hover to `--ce-graphite`. Secondary is white fill with a 1px `--ce-black` border, hover inverts. No gradients, no drop-shadow buttons, no emoji.
- **Measure.** Body never runs the full width of a wide container. 54ch. Captions 40ch. Headings 28ch.
- **Motion.** Quiet and fast. `--dur-base` 200ms on `--ease-standard`. Fades and short translates only. No spring, no bounce.
- **Forbidden.** UI gradients, glassmorphism, blurred orbs, illustration systems, brand patterns, drop-shadow decoration.

Ready-to-fill starting points.

| File | What it is |
|---|---|
| `templates/document.html` | Printable multi-section report. Header band, sub-banner, prose, table, stat row, footer |
| `templates/internal-doc.html` | Memo and one-pager |
| `templates/deck.html` | Slides, title through closing |
| `Examples/ce-one-pager.html` | A filled reference, not a starting point |

---

## Legacy classes, `.ce-*`

Anything written before type system v1.0 styles through `.ce-*` from `snippets/brand-base.css`. That file is deprecated and is now a shim over `type-system.css` and `palette.css`, so an old page keeps rendering and picks up the corrected type. Write `.bk-*` in new work. When you meet a legacy document, translate it:

| Legacy | Current |
|---|---|
| `.ce-display-xl` `.ce-display-lg` `.ce-display-md` | `.bk-display-xl` `.bk-display-lg` `.bk-display-md`, add `.bk-caps` for uppercase |
| `.ce-display-sm` | No v1.0 step between display-md and h1. Use `.bk-h1` |
| `.ce-h1` `.ce-h2` `.ce-h3` `.ce-h4` | `.bk-h1` `.bk-h2` `.bk-h3` `.bk-h4` |
| `.ce-body-lg` `.ce-body` `.ce-body-sm` `.ce-caption` | `.bk-body-lg` `.bk-body` `.bk-body-sm` `.bk-caption` |
| `.ce-eyebrow` | `.bk-eyebrow` |
| `.ce-emphasis` | `.bk-emphasis` |
| `.ce-lede` | `.bk-body-lg` |

Two things changed under those names and both are corrections, not style preferences. `.ce-display-*` and `.ce-lede` were italic and there is no italic face in this system. The old token set carried `--weight-medium: 500` and `--weight-black: 900`, neither of which the ladder admits.
