---
name: collective-edge-brand-guidelines
description: Applies Collective Edge's brand standards to ANY output representing Collective Edge. A monochrome-by-default black-to-white system, Montserrat bold-italic display type, the CE block mark and "CE │ COLLECTIVE EDGE" wordmark, and the "Powered by Collective Edge" co-brand model, which is how CE appears on almost everything. Color is allowed and expected on co-brand surfaces, in data, and on the CE gold wedge. Use whenever generating CE materials: internal documents, memos, one-pagers, reports, slides, emails, web content, product UI, dashboards, tables, or any visual artifact, and when reviewing materials for brand compliance. Defaults to the restrained internal-document treatment; the dark-grain hero treatment is reserved for marketing and title surfaces.
---

# Collective Edge, Brand Guidelines

Collective Edge ("CE") is a holding and operating company that partners with regional healthcare-transportation providers and brings them shared systems, leadership, and long-term capital while preserving local ownership. The brand runs on a **"Powered by Collective Edge"** co-brand model: every partner keeps its own logo, and CE shows up beside them as the connective tissue.

**The brand in one line:** restrained, confident, operational, adult. Bold-italic display type used sparingly, generous whitespace, hairline dividers, no decorative flourish. It reads as a senior operator giving a direct briefing, the opposite of consumer-tech playfulness.

**Read this first.** CE's restraint is about *discipline*, not the absence of color. Most CE work is a co-brand, and a co-brand surface is expected to carry color. See section 2 before you assume a surface should be grey.

**This skill is the authoritative reflection of the CE Design System** (source of truth lives in the "Collective Edge Design System" project on claude.ai/design). Tokens here mirror its `colors_and_type.css`.

## Two treatments, pick the restrained one by default

| | **Internal documents (DEFAULT)** | Hero and marketing |
|---|---|---|
| Surface | **White `#FFFFFF`** canvas | Black `#000000` plus grain-wave background |
| Display type | Small, sparing; sentence-case headings do most work | Big bold-italic ALL-CAPS statements |
| Feel | Quiet, dense, legible, printable | Cinematic, full-bleed, declarative |
| Use for | Memos, one-pagers, reports, SOPs, tables, internal comms | Title slides, section dividers, the marketing site |

**Most of what you generate is an internal document.** The marketing-site look (dark, big italic, full-bleed hero) is overkill for internal material. Reach for it only on a title or section-divider surface, and even then, once.

## CRITICAL: Asset loading

This kit is cloud-hosted on a public CDN (jsDelivr, backed by GitHub). **Do not look for local files.** Use these URLs directly in generated HTML, CSS, or markdown.

**Base CDN URL:** `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/`

| Asset | URL (prefix with the base above) |
|---|---|
| Montserrat (variable TTF) | `assets/fonts/Montserrat-VariableFont_wght.ttf` |
| Wordmark lockup on light | `assets/logos/horizontal-black.svg` |
| Wordmark lockup on dark | `assets/logos/horizontal-white.svg` |
| CE block mark on light | `assets/logos/mark-black.svg` |
| CE block mark on dark | `assets/logos/mark-white.svg` |
| Brand colors (JSON) | `assets/colors.json` |
| Base CSS (tokens plus type styles) | `snippets/brand-base.css` |

**Drop-in base CSS** (Montserrat @font-face, every design-system token, and the `.ce-*` type styles):
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/snippets/brand-base.css">
```

**For PDF rendering** (weasyprint, wkhtmltopdf, Chrome print), inline the @font-face so the font embeds in the file:
```css
@font-face {
  font-family: "Montserrat";
  src: url("https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/fonts/Montserrat-VariableFont_wght.ttf") format("truetype-variations");
  font-weight: 100 900;
}
body { font-family: "Montserrat", "Helvetica Neue", Arial, sans-serif; }
```

**Partner brand kits** (the source of truth for any partner's color and logos, never a copy kept here). Same layout as this kit, but **the logo filenames differ**, so check before you hardcode a path:

| Partner | Kit base URL (jsDelivr, same shape as above) | Lockup on light | Lockup on dark |
|---|---|---|---|
| Apex Paramedics | `https://cdn.jsdelivr.net/gh/collective-edge/apex-brand-kit@main/` | `assets/logos/horizontal-color.svg` | `assets/logos/horizontal-white.svg` |
| Royal Ambulance | `https://cdn.jsdelivr.net/gh/collective-edge/royal-brand-kit@main/` | `assets/logos/horizontal-purple.svg` | `assets/logos/horizontal-white.svg` |

---

## 1. Color

**Monochrome is CE's default, not a law.** Pure black, pure white, and a precise grey ramp between them carry CE's own material: documents, decks, chrome, body copy. That restraint is the brand and it is what you reach for when nothing tells you otherwise.

It is not a ban on color, and this kit used to read like one. The real rule is narrower and easier to hold:

> **Every hue on a CE surface has a job you can name.** Ownership, state, meaning, or data. Nothing is colored for decoration.

### Where the color comes from

| What you are making | What the palette is |
|---|---|
| CE's own documents, decks, memos, reports, one-pagers | The grey ramp. Monochrome. |
| The CE mark, anywhere | Grey ramp, plus **CE gold `#FFD630`** on the Edge wedge |
| A partner-led co-brand surface (mode A, section 2) | **The partner's palette leads.** CE adds structure and finish, no hue |
| A CE product delivered to a partner or their customer (mode B, section 2) | CE grey ramp, plus **the partner's accent** used functionally |
| Anything carrying operational or clinical status | The four status colors, functionally, never as theme |
| Charts and data visualization, on any surface | **Series colors chosen for legibility**, not pulled from the brand palette |

What stays true in every row: the CE block and its letters are black or white, never a partner's color; nothing is tinted for decoration; and contrast is checked before a color becomes text.

### The CE ramp

| Token | Hex | Role |
|---|---|---|
| `--ce-black` | `#000000` | Brand black; hero and divider surfaces |
| `--ce-ink` | `#111111` | Body text on light (`--fg-1`) |
| `--ce-graphite` | `#2A2A2A` | Deep neutral; button hover |
| `--ce-slate` | `#4A4A4A` | Secondary text (`--fg-2`) |
| `--ce-steel` | `#6E6E6E` | Tertiary text, the "EDGE" grey (`--fg-3`) |
| `--ce-mute` | `#9A9A9A` | Muted and "Not This" labels (`--fg-4`) |
| `--ce-fog` | `#C8C8C8` | **The Edge wedge, restrained treatment.** The quiet half of the pair |
| `--ce-gold` | `#FFD630` | **The Edge wedge, color treatment.** The one hue CE owns. Wedge only |
| `--ce-mist` | `#E2E2E2` | Hairlines, dividers (`--border-1`) |
| `--ce-paper`, `--ce-bone` | `#F4F4F4`, `#FAFAFA` | Off-white and lightest surfaces |
| `--ce-white` | `#FFFFFF` | Brand white; **primary document canvas** |

- **Text on light:** `#111` primary, `#4A4A4A` secondary, `#6E6E6E` metadata.
- **Text on dark:** `#FFFFFF` primary, `#D6D6D6` secondary, `#9E9E9E` tertiary.

### CE gold

CE owns exactly one hue: **`#FFD630` on the Edge wedge.** Prefer gold wherever the mark has to read at small sizes (favicons, browser tabs, avatars) and on co-brand surfaces, where a grey wedge on a light tile is close to invisible. The grey wedge `#C8C8C8` stays correct for restrained document and print work. Gold never moves off the wedge: not onto the block, not onto the letters, not into UI chrome.

### Status colors

`--status-go #1E7A4D`, `--status-warn #B5821A`, `--status-stop #B0322B`, `--status-info #2A5A8C`. These exist because CE works in healthcare operations and some things genuinely mean go, watch, and stop. Use them **functionally and sparingly**, always paired with text or an arrow so meaning never rides on color alone. Never as decoration or theme.

### Data visualization

Charts are the one place where the grey ramp is not enough, and forcing them monochrome makes them worse. Choose series colors for **legibility and colorblind separation first**, then keep them stable so a color means the same thing across every surface in a system. Practices proven on the shipped CE dashboards:

- Give each series a fixed identity and reuse it everywhere in the product.
- Verify contrast (3:1 minimum against the surface) and colorblind separation before shipping a palette. A bright brand color often fails as a chart line on white; use the partner kit's text-safe darkened step instead.
- **Target and reference rules are neutral dashed lines with a label, never green.** Green on a red series fails deuteranopia badly.
- Two or more series always carry a legend or direct labels. Identity never rides on color alone.

---

## 2. Co-branding: "Powered by Collective Edge"

**This is how CE appears on almost everything.** CE rarely stands alone. It comes in beside an operating company, a partner, or that partner's customer, and it says so in words: **"Powered by Collective Edge."** Treat the phrase as non-optional. If CE's mark is on a surface with another brand, the phrase is on it too.

### Pick the mode by asking whose name is on the door

**Mode A. Partner led.** The partner's brand owns the surface. Their logo heads it, their palette runs the chrome, their color carries the accents. CE contributes **structure and finish, not hue**: Montserrat, hairline dividers, generous whitespace, tabular numerals, square-ish corners, quiet fast motion, a disciplined type scale. CE's visible presence is the "Powered by" lockup and the footer caption.

*Shipped reference: the Apex internal dashboards. The sidebar is Apex deep blue `#1D225E` with a gold `#f9ad16` right rule, the whole palette locked to the Apex kit. CE adds zero color and is unmistakably there anyway.*

**Mode B. CE led, partner accented.** CE's system owns the surface: white canvas, grey ramp, hairlines, the CE type scale. The partner's color is **the only hue on the page** and it is functional: active nav, live-data indicator, active filter, one chart series. Reach for this when the artifact is a CE product delivered to a partner or their customer.

*Shipped reference: the Apex customer dashboard. Every surface is the CE ramp; Apex gold marks exactly the live and active states and one chart series, nothing else.*

When in doubt, mode A. CE does not take over a partner's surface.

### Building the lockup

- **Two marks, never merged.** CE and the partner stay separate marks that happen to share a surface. Never combine them into one logo, never nest CE's mark inside a partner's, never build a "CE x Partner" glyph.
- **Separate them with the CE `│`.** The vertical bar from `CE │ COLLECTIVE EDGE` is a brand signature. Render it between marks as a **1px rule at roughly the height of the marks**, in `--ce-mist` on light or `rgba(255,255,255,0.12)` on dark. A rule, not a typed glyph.
- **Order follows ownership.** On a partner-led surface the partner's mark sits first (or above), and the CE lockup sits beneath it, under a hairline, so the two read as two brands rather than one. On a CE-led product the chain reads left to right in order of who built it and who it is for: `CE │ Apex Paramedics │ {Customer}`. Never stack more than three marks in one lockup.
- **The eyebrow.** "POWERED BY" sits above or beside the CE lockup: SemiBold 600, ALL CAPS, tracked 0.08em to 0.16em, roughly 9px to 11px, in the surface's tertiary grey. Where no lockup fits, spell out **"Powered by Collective Edge"** as text at the same weight and tracking.
- **Match the file to the background, on both sides.** CE uses `horizontal-white.svg` on dark and `horizontal-black.svg` on light. The partner uses whatever their kit calls the same two things, and the names differ: Apex ships `horizontal-white.svg` and `horizontal-color.svg` (there is no black variant), Royal ships `horizontal-white.svg` and `horizontal-purple.svg`. **On a light surface the partner appears in their own color logo while CE appears in black.** That asymmetry is correct. It is the partner's brand and CE's restraint, side by side. Never CSS-recolor a lockup to fake a variant, and never drop a lockup on a busy area without a solid backing.
- **Size it to be read.** Keep the CE lockup at or above its **120px** minimum width, and on a panel or sidebar let it fill the available content width rather than hiding in a corner. Clear space stays at least the height of the Edge block.
- **One CE lockup per surface.** Header or footer, not both. The footer caption below is text, not a mark, so it may accompany a header lockup.

### The footer caption

The standing CE signature on any co-branded product. A slim strip with a 1px hairline top rule. Left: `Collective Edge │ {Surface Name}` in the tertiary grey at 600 or 700 weight with slight caps tracking. Right: a revision marker or a scope note.

### Partner color rules

1. **Take the hex from the partner's own brand kit, never from a copy.** Values kept in this kit are a convenience mirror and they go stale. `apex-brand-kit` and `royal-brand-kit` are the source of truth for their own colors and logos.
2. **Check contrast before a partner color becomes ink.** Bright brand colors usually fail as text or small UI on white. Apex gold `#f9ad16` fails 3:1 on white; the Apex kit ships the text-safe deep gold `#B77808` for exactly this. Use the darkened step the partner's kit provides. Do not invent your own darkening, and do not ship the bright value as body text or a thin chart line.
3. **Partner color is functional in mode B.** It marks state and identity. It does not tint surfaces, fill cards, or become a theme.
4. **Never recolor the CE mark to the partner's color.** The block stays black or white, the letters stay the opposite, and the only path that ever changes is the wedge.
5. **CE gold and a partner hue may share a surface.** A gold CE wedge next to Apex gold is fine. They are two marks, and the hairline keeps them distinct.

### Never, on a co-brand surface

- Drop "Powered by Collective Edge."
- Lead with CE on a partner's own surface.
- Merge, nest, or recolor either mark to match the other.
- Use a partner's accent on a CE-only surface.
- Put CE's grey ramp over a partner's palette in mode A, or a partner's palette over CE's chrome in mode B. Pick one mode and hold it.

---

## 3. Typography, Montserrat only

The entire brand is built on weight and italic contrast within one typeface.

- **Display.** ExtraBold (800) **Italic, ALL CAPS**, tracked about 0.01em. Slide titles, section dividers, page-level statements. Use sparingly, especially in documents. (`.ce-display-*`)
- **Headings.** Bold (700) or SemiBold (600) Roman, sentence case. This is what carries internal documents. (`.ce-h1` through `.ce-h4`)
- **Body.** Regular (400) Roman, sentence case, line-height 1.5 to 1.6. (`.ce-body`, `.ce-body-sm`)
- **Emphasis in body.** Bold (700) Roman: `**Proven playbooks.**` then a regular-weight explanation.
- **Eyebrows and labels.** SemiBold (600), ALL CAPS, tracked 0.08em, grey. (`.ce-eyebrow`)
- **Numbers in product UI.** Tabular figures (`font-feature-settings: "tnum" 1`) so columns align. A CE dashboard is read by column.

**The COLLECTIVE and EDGE duality is the signature.** The wordmark sets COLLECTIVE in heavy black italic and EDGE in light-grey (`#C8C8C8`) thin italic. Any headline echoing that heavy-plus-thin, black-plus-grey pairing reads on-brand instantly. Keep "EDGE" grey, never force it to full black or white.

Rules: no more than 3 weights per piece; uppercase always tracked; no italic body text (italics are for display and the `.ce-lede` only); Montserrat everywhere.

---

## 4. Logo

- **Wordmark lockup.** "CE │ COLLECTIVE EDGE" horizontal lockup. Primary logo where there is room. `horizontal-black.svg` on light, `horizontal-white.svg` on dark.
- **CE block mark.** The skewed parallelogram with the Edge wedge. Icon-only contexts (favicons, avatars, badges, the CE half of a co-brand lockup). `mark-black.svg` on light, `mark-white.svg` on dark. Crisp 0px corners: it is a parallelogram, not a rounded badge.
  - The wedge takes either treatment: grey `#C8C8C8` for restrained document and print work, or **gold `#FFD630`** where the mark must read small or sits on a co-brand surface. **Every SVG and PNG shipped in this kit is currently the grey treatment**, so a gold wedge means recoloring that one path by hand until gold variants land here.
  - **On a light tile, check the block is actually black.** The shipped `mark-black.svg` fills the block `#ffffff` and the letters `#000000`, which renders as white-on-white with only the letters visible. Dropped into a favicon this reads as broken. Invert it: block `#000000`, letters `#ffffff`, wedge `#FFD630`.

Rules: match the file to the background, do not CSS-recolor; keep clear space at least the height of the Edge shadow block; minimum lockup about 120px or 1in, minimum mark about 28px; never stretch, skew, rotate, add shadow, glow, or gradient, or split the mark from the wordmark in the lockup. **Recoloring is limited to the wedge, and only to `#C8C8C8` or `#FFD630`.** The block and the letters stay black or white on every surface, including co-brands. The **vertical bar `│` separator** is a brand signature: reuse it as a 1px grey rule whenever pairing CE with a partner, a customer, or a section name.

---

## 5. Voice and content

CE sounds like a senior operator giving a direct briefing: confident, plainspoken, operational. Not a consultant pitching, not a startup hyping.

- **Plain words over jargon.** "We understand what works and scale it." Not "operationalize evidence-based frameworks." Avoid leverage, synergize, unlock.
- **Short sentences, full stops.** Deck headlines run 2 to 4 words. Body rarely exceeds about 12 words per sentence.
- **First person plural** ("we") addressing **"you," the partner.** Never "the customer" or "users."
- **Active verbs:** build, earn, operate, scale, reinvest, develop.
- **Bold-then-explain.** A two-word claim, a period, then a one-line proof:
  > **Proven playbooks.** We understand what works and scale it.
  > **Long-term builders.** We improve organizations for decades.
- **Not this. This.** CE defines itself by what it refuses to be:
  > Not this: Acquire and rebrand overnight.
  > This: Earn trust, then build together.
- **Headlines often end in a period.** It makes claims feel settled, not promotional: "How we operate together."
- **Anti-extraction, long-horizon.** Reinvestment in people and culture. Decades, not quarters.
- **No emoji. No exclamation points. No rhetorical questions.** The voice does not perform enthusiasm.

### Punctuation: no em dashes, no slashes

**Do not use em dashes (`—`), en dashes (`–`), or forward slashes (`/`) in CE copy.** They read as hurried. Recast instead:

- Where you would reach for a dash, use a **period** (two short sentences), a **comma**, a **colon**, or **parentheses**. Write "Confident, plainspoken, operational." Write "We do one thing. We do it for decades." Never join those clauses with a dash.
- Where you would pair or list with a slash, use **"and," "or," a comma,** or a **middot `·`**. "Systems, leadership, capital." Not "systems/leadership/capital." "Internal · Confidential," not "Internal / Confidential."
- The **only** vertical stroke that stays is the **`│` lockup separator** in `CE │ COLLECTIVE EDGE` and `CE │ PARTNER NAME`. That is the logo, not punctuation.

---

## 6. Layout conventions (internal documents)

- **White canvas, generous margins.** Content lives well inside the page edge. CE breathes, so do not fill every pixel.
- **The header motif:** a title (sentence-case `.ce-h*` or a small display line), an optional `.ce-eyebrow` above it, and a **1px `--ce-mist` horizontal rule underneath.** This under-header hairline is a fixed brand motif and it appears under nearly every section title.
- **Hairlines, not boxes.** Prefer a single 1px `#E2E2E2` rule or a 1px vertical column divider over bordered cards. Cards, when used, are flat: `--bg-surface` fill, `--radius-md` (6px) or square, `--shadow-1` only if in a list of equal elevations, 24px to 32px padding.
- **Comparison layouts ("Not this. This."):** split 50 50 with a centered vertical rule. Secondary label in mute grey, primary label in heavy black italic.
- **Corners mostly square** (0px to 6px). No squircles, no pills except tag chips.
- **Buttons:** primary is solid black with white text, 2px or square corners, 600 weight, slight caps tracking, hover to graphite; secondary is white fill with a 1px black border, hover inverts. No gradients, no drop-shadow buttons, no emoji.
- **Footer:** slim strip, 1px `--ce-mist` top rule. Left: "Collective Edge │ {Document Title}" in `--fg-4`. Right: revision marker (for example "Rev. 07.26") in `#111`, Montserrat 700.
- **Motion (if any):** quiet and fast. 200ms, `cubic-bezier(0.2,0,0,1)`, fades and short translates only. No spring, no bounce.
- **Forbidden:** UI gradients, glassmorphism, blurred orbs, illustration systems, brand patterns, drop-shadow decoration.

A ready-to-fill internal-document template lives at `templates/internal-doc.html` (and `examples/` holds rendered references).

---

## 7. Quick-reference snippets

**Under-header motif (the signature):**
```html
<header style="padding:0 0 var(--space-4); border-bottom:1px solid var(--ce-mist);">
  <p class="ce-eyebrow">SECTION · CATEGORY</p>
  <h1 class="ce-h1">How we operate together.</h1>
</header>
```

**Bold-then-explain line:**
```html
<p class="ce-body"><span class="ce-emphasis">Proven playbooks.</span> We understand what works and scale it.</p>
```

**Co-brand lockup, mode A (partner leads, CE beneath a hairline, dark surface):**
```html
<div class="brand-head">
  <img alt="Apex Paramedics" width="158"
       src="https://cdn.jsdelivr.net/gh/collective-edge/apex-brand-kit@main/assets/logos/horizontal-white.svg">
  <div class="ce-powered">
    <span>Powered by</span>
    <img alt="CE │ Collective Edge" width="132"
         src="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-white.svg">
  </div>
</div>
<style>
  .ce-powered {
    display: grid; gap: 6px; margin-top: 16px; padding-top: 15px;
    border-top: 1px solid rgba(255,255,255,0.12);
  }
  .ce-powered span {
    font: 600 9px/1 "Montserrat"; letter-spacing: 0.08em;
    text-transform: uppercase; color: #9AA0C9;
  }
  .ce-powered img { width: 100%; max-width: 204px; display: block; }
</style>
```

**Co-brand lockup, mode B (CE leads, marks divided by the `│` rule, light surface):**
```html
<div style="display:flex; align-items:center; gap:14px;">
  <img alt="Collective Edge" style="height:40px; display:block;"
       src="https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/assets/logos/horizontal-black.svg">
  <span style="width:1px; height:40px; background:rgba(17,17,17,0.14);"></span>
  <img alt="Apex Paramedics" style="height:38px; display:block;"
       src="https://cdn.jsdelivr.net/gh/collective-edge/apex-brand-kit@main/assets/logos/horizontal-color.svg">
</div>
<div style="font:700 9px/1 'Montserrat'; letter-spacing:0.16em; text-transform:uppercase;
            color:var(--fg-4); margin-top:14px;">Powered by Collective Edge</div>
```

**Footer:**
```html
<footer style="border-top:1px solid var(--ce-mist); padding:8px 0; display:flex; justify-content:space-between;">
  <span class="ce-caption">Collective Edge &nbsp;│&nbsp; Document Title</span>
  <span style="font:700 12px 'Montserrat'; color:#111;">Rev. MM.YY</span>
</footer>
```

---

## Verify before you ship

A CE deliverable fails on details a spell-check cannot catch. Overlapping text, a clipped logo, an accent you cannot read, a font that quietly fell back to Arial. Before you call a CE deliverable done, verify the **rendered** result, not the source:

1. **Render it and look.** Render the output to an image or PDF, or open the HTML in a browser, and visually inspect what actually renders. Text overlap, clipping, and overflow are invisible in the source and only show up in pixels. If your environment cannot render, say so plainly instead of claiming it looks clean.
2. **No collisions.** Nothing overlapping, colliding, clipped, or overflowing. No text running past its container, off the page, or into the mark.
3. **Legibility.** Contrast holds. Mid greys fail as body text on white, so keep body copy in ink or near black and reserve the light greys for hairlines and captions. Light text only on dark backgrounds. Any partner or chart color used as text or a thin line clears 3:1 against its surface.
4. **Logo integrity.** Correct variant for the background, meaning the white variant on dark. Never stretched, skewed, or recolored beyond the wedge. Clear space respected. Never on a busy area without a solid backing.
5. **Co-brand check.** "Powered by Collective Edge" is present. The two marks are separate, divided by the `│` rule, in the right order for the mode. The CE block and letters are still black or white.
6. **Type.** Montserrat actually rendered, not a system fallback. For PDFs, actually embedded in the file. Confirm it before you call the job done.
7. **On-brand color.** Every hue on the surface has a job you can name, and every one is either CE's, the partner's own kit value, a status color, or a chart series. No decorative tints, no invented hexes.
8. **State what you applied.** When you hand it back, name the brand choices you made (which treatment, which co-brand mode, which logo variant, how the font embedded) so the user can verify at a glance.

---

## 8. Versioning and sign-off

`@main` serves the latest; pin `@v1.0` for production. When you finish a CE deliverable, state the brand choices you applied (internal-doc or hero treatment, co-brand mode A or B, which logo variant, font-embedding method) so the user can verify at a glance.
