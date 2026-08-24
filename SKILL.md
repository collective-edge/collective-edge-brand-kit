---
name: collective-edge-brand-guidelines
description: Applies the Collective Edge brand standard to any artifact carrying the CE name, covering palette, logo, layout and the shared house type system. Collective Edge is the parent of Apex Paramedics and Royal Ambulance, runs monochrome black to white with no hue of its own, sets everything in Montserrat, and reaches most surfaces through the “Powered by Collective Edge” co-brand where the Edge wedge takes the partner’s color. Use when producing or reviewing a Collective Edge email, slide, deck, one-pager, report, letterhead, flyer, document, web page, table, diagram, dashboard or PDF. Defaults to the restrained white document treatment and keeps the black band for headers, title slides and section dividers.
---

# Collective Edge

Collective Edge is a holding and operating company that partners with regional healthcare-transportation providers and brings them shared systems, leadership and long-term capital while local ownership stays in place. It is the parent of Apex Paramedics and Royal Ambulance, it owns the house type system both operating companies inherit unchanged, and it carries no hue of its own: black, white and a grey ramp, with color arriving only from a partner.

Default to the restrained white document treatment. Black is a header band, a title slide or a section divider. It is never the reading surface of a document. Most of what you generate is an internal document. The hero treatment, black `#000000` under the `CE_Background.jpeg` grain wave, belongs on a title or section-divider surface, and even there, once. The two treatments are set side by side in [reference/brand.md](reference/brand.md).

Full color, logo, co-brand and voice detail: [reference/brand.md](reference/brand.md).

## Asset loading

Load in this order. `type-system.css` is identical in every kit and is served from this repo because the type layer belongs to Collective Edge. `palette.css` is the only stylesheet that differs between brands.

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/type-system.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/palette.css">
```

For PDF pipelines (weasyprint, wkhtmltopdf, Chrome print) inline the face so it embeds in the file:

```css
@font-face {
  font-family: "Montserrat";
  src: url("https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/fonts/Montserrat-VariableFont_wght.ttf") format("truetype-variations");
  font-weight: 400 800;
  font-style: normal;
}
body { font-family: "Montserrat", "Helvetica Neue", Arial, sans-serif; }
```

Ask for a logo by role. Partner kits map the same five roles to different filenames, so never carry a filename across brands.

| Role | URL | Use |
|---|---|---|
| horizontal-on-light | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-black.svg` | Primary lockup on white and light greys |
| horizontal-on-dark | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-white.svg` | Primary lockup on the black band |
| mark-on-light | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/mark-black.svg` | Favicon, avatar, badge, the CE half of a lockup, on light |
| mark-on-dark | `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/mark-white.svg` | Same, on dark |
| stacked-on-dark | none | Collective Edge ships no stacked lockup. Use horizontal-on-dark. |

The horizontal lockup reads `CE │ COLLECTIVE EDGE`. That vertical bar is drawn geometry inside the artwork, not typed punctuation, and it is reused as a 1px rule wherever CE is paired with a partner, a customer or a section name.

Co-brand marks carry the partner’s hue in the Edge wedge and ship as files: `mark-black-royal.svg`, `mark-white-royal.svg`, `mark-black-apex.svg`, `mark-white-apex.svg`, same base URL. Never hand-recolor a mark.

Machine-readable color for python-pptx, python-docx, matplotlib and reportlab: `tokens.json`. Machine-readable type: `snippets/type-tokens.json`. `assets/colors.json` and `snippets/brand-base.css` are the pre-v1.0 files. Both still ship for pages already fetching them from the CDN. Never read either one for a new artifact.

## Color

| Token | Hex | Use |
|---|---|---|
| `--ce-white` | `#FFFFFF` | Document canvas. The default surface. |
| `--ce-black` | `#000000` | Header bands, title slides, section dividers. |
| `--ce-ink` | `#111111` | Body text on light. `--fg-1` |
| `--ce-graphite` | `#2A2A2A` | Deep neutral, button hover. |
| `--ce-slate` | `#4A4A4A` | Secondary text. `--fg-2` |
| `--ce-steel` | `#6E6E6E` | Tertiary text, metadata. `--fg-3` |
| `--ce-mute` | `#9A9A9A` | Dimmed non-text marks. Never text. `--fg-4` |
| `--ce-fog` | `#C8C8C8` | The Edge wedge when CE stands alone. |
| `--ce-mist` | `#E2E2E2` | Hairlines and dividers. `--border-1` |
| `--ce-paper` | `#F4F4F4` | Off-white surface tint. |
| `--ce-bone` | `#FAFAFA` | Lightest surface. `--bg-surface` |

On dark: `#FFFFFF` primary, `#D6D6D6` secondary, `#9E9E9E` tertiary.

Three rules agents break most often.

1. **There is no CE accent hue and there never will be.** Do not add a blue, a gold or a teal to a CE surface. Color on a CE surface belongs to a partner and enters through the Edge wedge or a functional accent, never as decoration.
2. **`#C8C8C8`, `#E2E2E2` and `#9A9A9A` are never text.** They measure 1.67:1, 1.30:1 and 2.81:1 on white. `#9A9A9A` fails at every size, large included, so it never sets a footer, a caption or a column label. The floor for text on white is `#6E6E6E` at 5.10:1. Body text is `#111111` on white and `#FFFFFF` on black.
3. **A bright partner color is never ink.** Apex gold `#f9ad16` measures 1.91:1 on white and fails as text or a thin chart line. Use the partner kit’s text-safe step, `#B77808` at 3.68:1, and only at 700 or at large sizes. A brand accent is never a status color.

## Co-brand

CE rarely stands alone. It comes in beside an operating company or a partner and says so in words. If CE’s mark is on a surface with another brand, “Powered by Collective Edge” is on it too. Pick the mode by asking whose name is on the door.

| Mode | Whose surface | What CE contributes |
|---|---|---|
| A, partner led | The partner’s logo heads it, their palette runs the chrome | Structure and finish, no hue. Montserrat, hairlines, whitespace, tabular figures, the type scale. CE shows as the “Powered by” lockup. |
| B, CE led | White canvas, CE grey ramp, CE type scale | The partner’s color is the only hue on the page and it is functional. Active nav, live indicator, one chart series. |

When in doubt, mode A. Lockup construction, order, the “POWERED BY” eyebrow and the partner color rules are in [reference/brand.md](reference/brand.md).

## Type

Type is shared, identical across Collective Edge, Apex and Royal, and never forked for one brand. Read [reference/type-system.md](reference/type-system.md) and follow the fifteen rules in its section 10. The scale, leading, tracking, measure and spacing tables live there. Do not restate them from memory.

Three things that are never correct.

- **No italic.** Not at any weight, not in any brand. The heavy-italic Collective Edge signature exists only inside the drawn wordmark SVG, where the letterforms are real.
- **No weight outside 400, 600, 700, 800.** Never 100, 200, 300 or 900 at document sizes. Maximum three weights in one piece.
- **No px tracking.** Tracking is always em. Large type negative, small caps positive.

## Layout

Patterns, all copy-pasteable: [reference/layout.md](reference/layout.md). It carries the header band, sub-banner, co-brand lockup, flowchart nodes, stat callouts, tables and footer, plus the hairline, card, button and motion conventions.

Ready-to-fill files: `templates/document.html` for a printable report, `templates/internal-doc.html` for a memo, `templates/deck.html` for slides. `Examples/ce-one-pager.html` is a filled reference.

The header band opens nearly every deliverable. `.bk-on-dark` on the container drops display from 800 to 700 and adds 0.005em to every step under it. Do not restate either value inline. The band title is a masthead, not the document heading, so it is a `<p>` and the one `<h1>` stays on the page title.

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

## Verify before shipping

```bash
python3 scripts/validate.py path/to/output.html
```

It checks rules 1, 2, 5, 9, 10, 13 and 14 mechanically and exits non-zero on a violation. Then confirm by eye.

- [ ] Rendered, not just written. Open it and look. Overlap, clipping and overflow are invisible in source. If your environment cannot render, say so plainly instead of claiming it looks clean.
- [ ] Montserrat actually rendered, not a fallback. For PDF, actually embedded.
- [ ] No italic anywhere.
- [ ] The dark band is one weight lighter than its light-surface equivalent.
- [ ] Body text sits at `#111111` on white, `#FFFFFF` on black, and clears 4.5:1.
- [ ] Correct logo role for the background. Not stretched, not skewed, not recolored past the wedge.
- [ ] On a co-brand surface, “Powered by Collective Edge” is present, the two marks are separate, and the CE block and letters are still black or white.
- [ ] Every hue on the surface has a job you can name. No decorative tints, no invented hexes.
- [ ] No helper text, no caption restating the thing above it, no parenthetical after a heading.

State which brand choices you applied when you hand the work back: treatment, co-brand mode, logo role, font-embedding method.

`@main` serves the latest. Pin `@v1.0` for production.
