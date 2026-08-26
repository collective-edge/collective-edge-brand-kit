# Collective Edge, brand reference

Everything about this brand that does not fit in `SKILL.md`. Color, logo, co-brand, voice. Type is not here. Type is shared and lives in `reference/type-system.md`.

**The brand in one line.** Restrained, confident, operational, adult. Sparing display type, generous whitespace, hairline dividers, no decorative flourish. It reads as a senior operator giving a direct briefing, the opposite of consumer-tech playfulness.

**Provenance.** This kit is the authoritative reflection of the CE Design System. The source of truth lives in the “Collective Edge Design System” project on claude.ai/design, and the color tokens here mirror its `colors_and_type.css`. Type is the exception: the type layer is `reference/type-system.md` and `snippets/type-system.css`, shared unchanged with Apex and Royal, and it supersedes anything the design system says about type.

---

## Two treatments, pick the restrained one by default

| | Internal documents, the default | Hero and marketing |
|---|---|---|
| Surface | White `#FFFFFF` canvas | Black `#000000` under the grain-wave background, `assets/imagery/CE_Background.jpeg` |
| Display type | Small and sparing. Sentence-case headings do most of the work | Big ALL-CAPS statements at `.bk-display-lg` or `.bk-display-xl` |
| Feel | Quiet, dense, legible, printable | Cinematic, full-bleed, declarative |
| Use for | Memos, one-pagers, reports, SOPs, tables, internal comms | Title slides, section dividers, the marketing site |

Most of what you generate is an internal document. The marketing-site look, dark and full-bleed, is overkill for internal material. Reach for it only on a title or section-divider surface, and even then, once. The grain wave is the only texture in the system. It never sits under body copy and it never appears on a document page.

---

## 1. Color

Collective Edge has no color of its own. Pure black, pure white and a precise grey ramp between them. That is the entire CE palette and it is not going to grow.

That is not the same as saying a CE surface is always grey. CE almost never appears alone. It appears beside a partner, and those surfaces carry color. The rule that holds both facts:

> **CE stays monochrome. The color belongs to the partner.**

There is no CE gold, no CE accent, no CE brand hue waiting to be used.

### The CE ramp

| Token | Hex | RGB | Semantic | Use |
|---|---|---|---|---|
| `--ce-black` | `#000000` | 0, 0, 0 | `--bg-inverse`, `--bg-band` | Header bands, title slides, section dividers |
| `--ce-ink` | `#111111` | 17, 17, 17 | `--fg-1`, `--fg-accent` | Body text on light |
| `--ce-graphite` | `#2A2A2A` | 42, 42, 42 | | Deep neutral, button hover |
| `--ce-slate` | `#4A4A4A` | 74, 74, 74 | `--fg-2` | Secondary text |
| `--ce-steel` | `#6E6E6E` | 110, 110, 110 | `--fg-3` | Tertiary text, metadata. The palette equivalent of the EDGE grey |
| `--ce-mute` | `#9A9A9A` | 154, 154, 154 | `--fg-4` | Dimmed non-text marks only. At 2.81:1 it is never text |
| `--ce-fog` | `#C8C8C8` | 200, 200, 200 | `--wedge-standalone` | The Edge wedge when CE stands alone |
| `--ce-mist` | `#E2E2E2` | 226, 226, 226 | `--border-1` | Hairlines, dividers |
| `--ce-paper` | `#F4F4F4` | 244, 244, 244 | | Off-white surface tint |
| `--ce-bone` | `#FAFAFA` | 250, 250, 250 | `--bg-surface` | Lightest surface, flat cards |
| `--ce-white` | `#FFFFFF` | 255, 255, 255 | `--bg-canvas`, `--bg-elevated` | The primary document canvas |

Reversed text, on any dark ground:

| Semantic | Hex | RGB | Use |
|---|---|---|---|
| `--fg-on-dark-1` | `#FFFFFF` | 255, 255, 255 | Primary text and headings |
| `--fg-on-dark-2` | `#D6D6D6` | 214, 214, 214 | Body and lede |
| `--fg-on-dark-3` | `#9E9E9E` | 158, 158, 158 | Captions, eyebrows, small text |
| `--border-2` | `#D0D0D0` | 208, 208, 208 | Stronger hairline on light |
| `--border-on-dark` | `rgba(255,255,255,0.12)` | | Rules inside a dark band |

### Contrast, measured against white

| Value | Ratio on `#FFFFFF` | Verdict |
|---|---|---|
| `#111111` | 18.88:1 | Body text |
| `#4A4A4A` | 8.86:1 | Secondary text |
| `#6E6E6E` | 5.10:1 | Tertiary text, the floor for body-size copy |
| `#9A9A9A` | 2.81:1 | Never text, at any size. Below the 3:1 large-text floor |
| `#C8C8C8` | 1.67:1 | Never text |
| `#E2E2E2` | 1.30:1 | Never text |
| `#572E72` Royal purple | 10.30:1 | Passes as text |
| `#2B338D` Apex blue | 10.71:1 | Passes as text |
| `#B77808` Apex text-safe gold | 3.68:1 | Bold or large only. Never body copy |
| `#B5821A` status amber | 3.40:1 | Bold or large only. Never running copy |
| `#9699C7` Apex light | 2.74:1 | Never text |
| `#FDB61C` Apex gold | 1.77:1 | Never text, never a thin line |

### What each color must never do

- `#C8C8C8`, `#E2E2E2`, `#F4F4F4` and `#FAFAFA` are never text at any size. They are wedges, hairlines and surfaces.
- `#9A9A9A` is never text. Not body copy, not a footer, not a caption, not a column label, not at large size. It measures 2.81:1 on white, under the 3:1 floor that large text has to clear. The dimmest text on white is `#6E6E6E` at 5.10:1. `--fg-4` is for dimmed rules, disabled fills and non-text marks. On a dark ground the dim step is `--fg-on-dark-3` `#9E9E9E`, which is legible there.
- `#000000` is never the reading surface of a document. It is a band, a title slide or a divider. Long body copy reversed out of black is a marketing choice, not a document choice.
- A partner’s hue never colors the CE block or the CE letters. It colors the Edge wedge and nothing else in the mark.
- A status color is never a theme, a fill, or a decorative accent.
- A brand accent is never a status color, in either direction.
- No color is introduced that is not in this file, a partner kit, the status set or a chart series.

### Where the color comes from

| What you are making | What the palette is |
|---|---|
| CE’s own documents, decks, memos, reports, one-pagers | The grey ramp. Monochrome. |
| The CE mark, standing alone | Black or white block and letters, grey `#C8C8C8` wedge |
| The CE mark, on a co-brand surface | Same black or white block and letters, wedge in the partner’s color |
| A partner-led co-brand surface, mode A | The partner’s palette leads. CE adds structure and finish, no hue |
| A CE product delivered to a partner or their customer, mode B | CE grey ramp, plus the partner’s accent used functionally |
| Anything carrying operational or clinical status | The four status colors, functionally, never as theme |
| Charts and data visualization, on any surface | Series colors chosen for legibility, not pulled from the brand palette |

### Status colors

Identical in every brand so an operational signal never changes meaning between documents.

| Token | Hex | RGB | Meaning |
|---|---|---|---|
| `--status-go` | `#1E7A4D` | 30, 122, 77 | Operational green |
| `--status-warn` | `#B5821A` | 181, 130, 26 | Attention amber |
| `--status-stop` | `#B0322B` | 176, 50, 43 | Alert red |
| `--status-info` | `#2A5A8C` | 42, 90, 140 | Info blue |

CE works in healthcare operations and some things genuinely mean go, watch and stop. Use these functionally and sparingly, always paired with text or an arrow so meaning never rides on color alone.

### Diagram roles

Identical across every brand so a diagram reads the same regardless of whose document it sits in. Rectangles, 6px radius. Role is communicated by fill, never by shape.

| Role | Fill | Border | Use |
|---|---|---|---|
| decision | `#4a8e3a` | `#3a7029` | Decision boxes, questions, branch points |
| warning | `#f57c00` | `#cc6600` | Warnings, advisories |
| process | `#3e3e3e` | `#2a2a2a` | Neutral process steps, context boxes |
| connector | `#3e3e3e` stroke, 1.8pt | | Every line between nodes |

**The white node labels on two of these fills do not clear 4.5:1.** `#FFFFFF` measures 2.70:1 on `#f57c00` and 4.02:1 on `#4a8e3a`, so the green passes only as large or bold text and the orange fails outright. The fills and their white text are inherited from the original kits and are frozen pending an owner decision, so do not recolor them. Until that decision lands, never let a diagram carry meaning in the label alone: repeat the outcome in the connector label or in the prose beside the figure. `#3e3e3e` is the only fill here that holds white body-size text.

### Data visualization

Charts are the one place where the grey ramp is not enough, and forcing them monochrome makes them worse.

- Give each series a fixed identity and reuse it everywhere in the product.
- Verify 3:1 minimum against the surface and colorblind separation before shipping a palette. A bright brand color often fails as a chart line on white. Use the partner kit’s darkened step.
- Target and reference rules are neutral dashed lines with a label, never green. Green on a red series fails deuteranopia badly.
- Two or more series always carry a legend or direct labels. Identity never rides on color alone.

---

## 2. The Edge wedge

The Edge wedge is the one part of the block mark that carries color, and that color is the partner’s.

| Wedge | Hex | When |
|---|---|---|
| Grey | `#C8C8C8` | CE standing alone. The default, and the only treatment on a CE-only surface |
| Royal purple | `#572E72` | A surface co-branded with Royal Ambulance |
| Apex gold | `#FDB61C` | A surface co-branded with Apex Paramedics, Pantone 1235 C, their kit value |

CE does not have a color, so when CE co-brands it takes the partner’s into its own mark. The partner enters CE through the wedge and nothing else about the mark moves. As CE takes on more operating companies, each one gets a wedge color and nothing else changes.

The wedge color never moves off the wedge. Not onto the block, not onto the letters, not into UI chrome. It works there because the wedge is a shape inside a mark, not something anyone has to read. Apex gold at 1.77:1 against white is fine on the wedge and not fine anywhere else.

One honest limitation. On a CE-only surface the grey wedge nearly disappears at favicon sizes on a white tile. There is no CE color to reach for instead. Give the mark a dark backing at small sizes, or accept it. Do not invent a hue to solve it.

---

## 3. Logo

### Files and roles

| Role | File | The logo is | Put it on |
|---|---|---|---|
| horizontal-on-light | `assets/logos/horizontal-black.svg` | Black COLLECTIVE, `#666666` EDGE, black block, `#CCCCCC` wedge | A light background |
| horizontal-on-dark | `assets/logos/horizontal-white.svg` | White letters, white block, `#CCCCCC` wedge | A dark background |
| mark-on-light | `assets/logos/mark-black.svg` | Majority black, white letters, `#C8C8C8` wedge | A light background |
| mark-on-dark | `assets/logos/mark-white.svg` | Majority white, black letters, `#C8C8C8` wedge | A dark background |
| stacked-on-dark | none | Collective Edge ships no stacked lockup | Use horizontal-on-dark |

Co-brand marks. Two axes, and they are independent: black or white picks the background, the suffix picks the co-brand.

| File | The logo is | Put it on |
|---|---|---|
| `assets/logos/mark-black-royal.svg` | Majority black, `#572E72` wedge | A light background, Royal co-brand |
| `assets/logos/mark-black-apex.svg` | Majority black, `#FDB61C` wedge | A light background, Apex co-brand |
| `assets/logos/mark-white-royal.svg` | Majority white, `#572E72` wedge | A dark background, Royal co-brand |
| `assets/logos/mark-white-apex.svg` | Majority white, `#FDB61C` wedge | A dark background, Apex co-brand |

The drawn files carry their own fills and those fills are final. The horizontal lockup sets EDGE at `#666666` and its wedge at `#CCCCCC`; the block mark sets its wedge at `#C8C8C8`. These are the artwork values, not palette tokens. Read them, do not override them.

The name is the logo’s own color, used on the opposite background. Same convention as the `CE_Block_Dark` and `CE_Block_Light` PNGs. Every combination ships as a file. Never hand-recolor a mark.

### Specifications

| Property | Value |
|---|---|
| Horizontal lockup viewBox | `0 0 450 74.999997` |
| Block mark viewBox | `0 0 375 262.499992` |
| Minimum lockup width | 120px, or 1in in print |
| Minimum mark width | 28px. `brands.json` carries no CE entry; it sets 32px for Apex and Royal, so a shared component sized from the registry lands at 32px |
| Clear space | At least the height of the Edge shadow block on every side |
| Vector master | The SVGs in `assets/logos/`. There is no separate .eps or .ai in this kit |
| Raster derivatives | `assets/png/CE.png`, `CE_Block_Dark.png`, `CE_Block_Light.png`, `CE_Block_Lockup.png`, `CE_Word_Mark.png`. Never the master, never the file you ship to web |

### Do not

- Do not stretch, skew or rotate the mark.
- Do not add a shadow, glow, gradient or outline.
- Do not recolor by CSS filter to fake a variant that already ships as a file.
- Do not color anything but the wedge. The block and the letters stay black or white on every surface, co-brands included.
- Do not split the mark from the wordmark inside the horizontal lockup.
- Do not place a lockup over a busy area without a solid backing.
- Do not force EDGE to full black or full white. It is grey, and the heavy-plus-thin, black-plus-grey pairing is the signature.
- Do not merge, nest or combine the CE mark with a partner’s into one glyph.
- Do not put two CE lockups on one surface. Header or footer, not both.

The pairing is reusable, and it is weight and color, never slant. A headline that sets its first phrase at 800 in `--fg-1` and its continuation at 400 in `--fg-3` echoes the wordmark and reads as CE on sight. That is the one stated way to make a headline read as Collective Edge.

The vertical bar in `CE │ COLLECTIVE EDGE` is a brand signature. Reuse it as a 1px rule when pairing CE with a partner, a customer or a section name. It is drawn geometry, not typed punctuation. In running text, separate items with `·`.

---

## 4. Co-branding, “Powered by Collective Edge”

This is how CE appears on almost everything. CE rarely stands alone. It comes in beside an operating company, a partner or that partner’s customer, and it says so in words. Treat the phrase as non-optional. If CE’s mark is on a surface with another brand, the phrase is on it too.

**Mode A, partner led.** The partner’s brand owns the surface. Their logo heads it, their palette runs the chrome, their color carries the accents. CE contributes structure and finish, not hue: Montserrat, hairline dividers, generous whitespace, tabular numerals, square-ish corners, quiet fast motion, a disciplined type scale. CE’s visible presence is the “Powered by” lockup and the footer caption. Shipped reference: the Apex internal dashboards. The sidebar is Apex deep blue `#1D225E` with a gold `#FDB61C` right rule, the whole palette locked to the Apex kit, and CE adds zero color and is unmistakably there anyway.

**Mode B, CE led, partner accented.** CE’s system owns the surface: white canvas, grey ramp, hairlines, the CE type scale. The partner’s color is the only hue on the page and it is functional: active nav, live-data indicator, active filter, one chart series. Reach for this when the artifact is a CE product delivered to a partner or their customer. Shipped reference: the Apex customer dashboard. Every surface is the CE ramp, and Apex gold marks exactly the live and active states and one chart series, nothing else.

When in doubt, mode A. CE does not take over a partner’s surface.

### Building the lockup

- **Two marks, never merged.** CE and the partner stay separate marks that happen to share a surface.
- **Separate them with the CE bar.** Render it between marks as a 1px rule at roughly the height of the marks, in `--border-1` on light or `--border-on-dark` on dark. A rule, not a typed glyph.
- **Order follows ownership.** On a partner-led surface the partner’s mark sits first or above, and the CE lockup sits beneath it under a hairline, so the two read as two brands rather than one. On a CE-led product the chain reads left to right in order of who built it and who it is for: `CE │ Apex Paramedics │ {Customer}`. Never stack more than three marks in one lockup.
- **The eyebrow.** “POWERED BY” sits above or beside the CE lockup. Use `.bk-eyebrow`, which is 600 uppercase at 12px web and 9pt print with 0.080em tracking, in the surface’s tertiary grey. Where no lockup fits, spell out “Powered by Collective Edge” as text at 700 and open the tracking to 0.160em. That wide step is lockup artwork standing in for a mark, not a type-scale eyebrow, and 0.080em to 0.160em is its whole range.
- **Match the file to the background, on both sides.** CE uses horizontal-on-dark on dark and horizontal-on-light on light. The partner uses whatever their kit maps to the same two roles, and the filenames differ, so never carry a filename across brands.

| Partner | Kit base URL | Lockup on light | Lockup on dark |
|---|---|---|---|
| Apex Paramedics | `https://cdn.jsdelivr.net/gh/collective-edge/apex-brand-kit@main/` | `assets/logos/horizontal-color.svg` | `assets/logos/horizontal-white.svg` |
| Royal Ambulance | `https://cdn.jsdelivr.net/gh/collective-edge/royal-brand-kit@main/` | `assets/logos/horizontal-purple.svg` | `assets/logos/horizontal-white.svg` |

  Apex ships no black variant. On a light surface the partner appears in their own color logo while CE appears in black. That asymmetry is correct. It is the partner’s brand and CE’s restraint, side by side.
- **Size it to be read.** Keep the CE lockup at or above 120px wide. On a panel or sidebar let it fill the available content width rather than hiding in a corner.
- **One CE lockup per surface.** The footer caption is text, not a mark, so it may accompany a header lockup.

### The footer caption

The standing CE signature on any co-branded product. A slim strip with a 1px `--border-1` top rule. Left: `Collective Edge · {Surface Name}` in `--fg-3`. It sets at 9pt, so it takes the 5.10:1 grey and never `--fg-4`. Right: a revision marker or a scope note in `--fg-1` at 700.

### Partner values

Take the hex from the partner’s own brand kit, never from a copy. `apex-brand-kit` and `royal-brand-kit` are the source of truth, and `brands.json` in this repo resolves each brand to its CDN root. The mirror below is a convenience and it goes stale. As of 2026-08-24 it reads:

| Partner | Primary | Deep | Light | Accent | Text-safe accent |
|---|---|---|---|---|---|
| Apex Paramedics | `#2B338D` | `#1D225E` | `#9699C7` | `#FDB61C` | `#B77808` |
| Royal Ambulance | `#572e72` | `#2f193b` | `#8260a2` | `#43205b` logo fill | `#572e72` passes on white |

Stadium and LifeWest have no kit. `#E0143C`, `#1E4FA3` and `#1E3A8A` are unreconciled placeholders inherited from an original design export. Confirm with the partner before shipping, and publish a kit when one of them becomes real work.

Rules that hold on every partner value:

1. Check contrast before a partner color becomes ink. Use the darkened step the partner’s kit provides. Do not invent your own darkening.
2. Partner color is functional in mode B. It marks state and identity. It does not tint surfaces, fill cards or become a theme.
3. The wedge takes the partner’s color and nothing else in the mark does.
4. The wedge and the partner’s own mark carry the same hue, and that is the point. An Apex gold wedge beside the Apex logo reads as one system, and the hairline keeps them two marks.

### Never, on a co-brand surface

- Drop “Powered by Collective Edge.”
- Lead with CE on a partner’s own surface.
- Merge, nest or recolor either mark to match the other.
- Use a partner’s accent on a CE-only surface.
- Put CE’s grey ramp over a partner’s palette in mode A, or a partner’s palette over CE’s chrome in mode B. Pick one mode and hold it.

---

## 5. Voice and content

CE sounds like a senior operator giving a direct briefing. Confident, plainspoken, operational. Not a consultant pitching, not a startup hyping.

- **Plain words over jargon.** “We understand what works and scale it.” Not “operationalize evidence-based frameworks.” Avoid leverage, synergize, unlock.
- **Short sentences, full stops.** Deck headlines run two to four words. Body rarely exceeds twelve words per sentence.
- **First person plural, addressing the partner.** “We” and “you.” Never “the customer” or “users.”
- **Active verbs.** Build, earn, operate, scale, reinvest, develop.
- **Bold-then-explain.** A two-word claim, a period, then a one-line proof. “**Proven playbooks.** We understand what works and scale it.” “**Long-term builders.** We improve organizations for decades.”
- **Headlines often end in a period.** It makes a claim feel settled rather than promotional. “How we operate together.”
- **Anti-extraction, long-horizon.** Reinvestment in people and culture. Decades, not quarters.
- **No emoji, no exclamation points, no rhetorical questions.** The voice does not perform enthusiasm.
- **Never define by negation.** Do not build a claim out of a refusal and its correction, in copy or in layout. “It is not X. It is Y.” is out, and so is the paired “Not this / This” panel. Say the thing you mean, once. A plain negation inside a single sentence is fine: “You do not pay any of it.” The construction reads as performance, and a document that performs stops being a briefing.

### Punctuation

Do not use em dashes, en dashes or forward slashes in CE copy. They read as hurried.

- Where you would reach for a dash, use a period, a comma, a colon or parentheses. Write “Confident, plainspoken, operational.” Write “We do one thing. We do it for decades.”
- Where you would pair or list with a slash, use “and”, “or”, a comma, or a middot. “Systems, leadership, capital.” Not “systems/leadership/capital.” “Internal · Confidential”, not “Internal / Confidential.”
- The only vertical stroke that stays is the lockup bar in `CE │ COLLECTIVE EDGE` and `CE │ PARTNER NAME`. That is the logo, not punctuation.
- Date ranges are the one place an en dash is correct, per rule 14 of the type system, because that is typography rather than copy voice.

Content density, from the type system: a label, a value, and nothing between them. No helper text under a field. No caption restating the number above it. No parenthetical after a heading. No caveat sentence under a table.
