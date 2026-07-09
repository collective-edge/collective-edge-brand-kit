---
name: collective-edge-brand-guidelines
description: Applies Collective Edge's brand standards — a monochromatic black-to-white system, Montserrat bold-italic display type, the CE block mark and "CE | COLLECTIVE EDGE" wordmark, and the "Powered by CE" partner co-brand model — to ANY output representing Collective Edge. Use whenever generating CE materials: internal documents, memos, one-pagers, reports, slides, emails, web content, product UI, tables, or any visual artifact. Also use when reviewing materials for brand compliance. Defaults to the restrained internal-document treatment; the flashy dark-grain hero treatment is reserved for marketing/title surfaces.
---

# Collective Edge — Brand Guidelines

Collective Edge ("CE") is a holding/operating company that partners with regional healthcare-transportation providers and brings them shared systems, leadership, and long-term capital while preserving local ownership. The brand runs on a **"Powered by CE"** co-brand model: every partner keeps its own logo; CE shows up beside them as the connective tissue.

**The brand in one line:** monochromatic, confident, operational, adult. Bold-italic display type used sparingly, generous whitespace, hairline dividers, no decorative flourish. It reads as a senior operator giving a direct briefing — the opposite of consumer-tech playfulness.

**This skill is the authoritative reflection of the CE Design System** (source of truth lives in the "Collective Edge Design System" project on claude.ai/design). Tokens here mirror its `colors_and_type.css` exactly.

## Two treatments — pick the restrained one by default

| | **Internal documents (DEFAULT)** | Hero / marketing |
|---|---|---|
| Surface | **White `#FFFFFF`** canvas | Black `#000000` + grain-wave background |
| Display type | Small, sparing; sentence-case headings do most work | Big bold-italic ALL-CAPS statements |
| Feel | Quiet, dense, legible, printable | Cinematic, full-bleed, declarative |
| Use for | Memos, one-pagers, reports, SOPs, tables, internal comms | Title slides, section dividers, the marketing site |

**Most of what you generate is an internal document.** The marketing-site look (dark, big italic, full-bleed hero) is overkill for internal material — reach for it only on a title or section-divider surface, and even then, once.

## CRITICAL: Asset loading

This kit is cloud-hosted on a public CDN (jsDelivr, backed by GitHub). **Do not look for local files.** Use these URLs directly in generated HTML/CSS/markdown.

**Base CDN URL:** `https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/`

| Asset | URL (prefix with the base above) |
|---|---|
| Montserrat (variable TTF) | `assets/fonts/Montserrat-VariableFont_wght.ttf` |
| Wordmark lockup — on light | `assets/logos/horizontal-black.svg` |
| Wordmark lockup — on dark | `assets/logos/horizontal-white.svg` |
| CE block mark — on light | `assets/logos/mark-black.svg` |
| CE block mark — on dark | `assets/logos/mark-white.svg` |
| Brand colors (JSON) | `assets/colors.json` |
| Base CSS (tokens + type styles) | `snippets/brand-base.css` |

**Drop-in base CSS** (Montserrat @font-face + every design-system token + the `.ce-*` type styles):
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

---

## 1. Color

**Fundamentally monochromatic** — pure black, pure white, and a precise grey ramp between. CE itself never introduces a hue; color enters only through a partner co-brand surface.

| Token | Hex | Role |
|---|---|---|
| `--ce-black` | `#000000` | Brand black; hero / divider surfaces |
| `--ce-ink` | `#111111` | Body text on light (`--fg-1`) |
| `--ce-graphite` | `#2A2A2A` | Deep neutral; button hover |
| `--ce-slate` | `#4A4A4A` | Secondary text (`--fg-2`) |
| `--ce-steel` | `#6E6E6E` | Tertiary text / "EDGE" grey (`--fg-3`) |
| `--ce-mute` | `#9A9A9A` | Muted / "Not This" labels (`--fg-4`) |
| `--ce-fog` | `#C8C8C8` | **The iconic "Edge" shadow grey** — the one unambiguous CE color |
| `--ce-mist` | `#E2E2E2` | Hairlines, dividers (`--border-1`) |
| `--ce-paper` / `--ce-bone` | `#F4F4F4` / `#FAFAFA` | Off-white / lightest surfaces |
| `--ce-white` | `#FFFFFF` | Brand white; **primary document canvas** |

- **Text on light:** `#111` primary, `#4A4A4A` secondary, `#6E6E6E` metadata.
- **Text on dark:** `#FFFFFF` primary, `#D6D6D6` secondary, `#9E9E9E` tertiary.
- **Status colors** (`--status-go #1E7A4D`, `--status-warn #B5821A`, `--status-stop #B0322B`, `--status-info #2A5A8C`) exist for the healthcare/operational context. Use **sparingly and functionally** — never as decoration or theme.
- **Partner accents** (`--partner-apex #F2C82F`, `--partner-royal #5B2A8C`, etc.) appear **only inside that partner's own co-brand surface** — never as a CE accent.

---

## 2. Typography — Montserrat only

The entire brand is built on weight + italic contrast within one typeface.

- **Display** — ExtraBold (800) **Italic, ALL CAPS**, tracked ~0.01em. Slide titles, section dividers, page-level statements. Use sparingly, especially in documents. (`.ce-display-*`)
- **Headings** — Bold (700) / SemiBold (600) Roman, sentence case. This is what carries internal documents. (`.ce-h1`–`.ce-h4`)
- **Body** — Regular (400) Roman, sentence case, line-height 1.5–1.6. (`.ce-body`, `.ce-body-sm`)
- **Emphasis in body** — Bold (700) Roman: `**Proven playbooks.**` then a regular-weight explanation.
- **Eyebrows / labels** — SemiBold (600), ALL CAPS, tracked 0.08em, grey. (`.ce-eyebrow`)

**The COLLECTIVE / EDGE duality is the signature.** The wordmark sets COLLECTIVE in heavy black italic and EDGE in light-grey (`#C8C8C8`) thin italic. Any headline echoing that heavy+thin / black+grey pairing reads on-brand instantly. Keep "EDGE" grey — never force it to full black/white.

Rules: no more than 3 weights per piece; uppercase always tracked; no italic body text (italics = display + the `.ce-lede` only); Montserrat everywhere.

---

## 3. Logo

- **Wordmark lockup** — "CE | COLLECTIVE EDGE" horizontal lockup. Primary logo where there's room. `horizontal-black.svg` on light, `horizontal-white.svg` on dark.
- **CE block mark** — the iconic skewed parallelogram with the light-grey Edge shadow. Icon-only contexts (favicons, avatars, badges, the left half of a co-brand lockup). `mark-black.svg` on light, `mark-white.svg` on dark. Crisp 0px corners — it is a parallelogram, not a rounded badge.

Rules: match the file to the background (don't CSS-recolor); keep clear space ≥ the height of the Edge shadow block; min lockup ~120px / 1in, min mark ~28px; never stretch, skew, rotate, add shadow/glow/gradient, recolor to a hue, or split the mark from the wordmark in the lockup. The **vertical bar `│` separator** in `CE | COLLECTIVE EDGE` is a brand signature — reuse it (as a 1px grey rule, not a literal glyph) whenever pairing CE with a partner or section name.

---

## 4. Voice & content

CE sounds like a senior operator giving a direct briefing — confident, plainspoken, operational. Not a consultant pitching, not a startup hyping.

- **Plain words over jargon.** "We understand what works and scale it." Not "operationalize evidence-based frameworks." Avoid leverage, synergize, unlock.
- **Short sentences, full stops.** Deck headlines run 2 to 4 words. Body rarely exceeds about 12 words per sentence.
- **First person plural** ("we") addressing **"you," the partner.** Never "the customer" or "users."
- **Active verbs:** build, earn, operate, scale, reinvest, develop.
- **Bold-then-explain.** A two-word claim, period, then a one-line proof:
  > **Proven playbooks.** We understand what works and scale it.
  > **Long-term builders.** We improve organizations for decades.
- **Not this. This.** CE defines itself by what it refuses to be:
  > Not this: Acquire and rebrand overnight.
  > This: Earn trust, then build together.
- **Headlines often end in a period.** It makes claims feel settled, not promotional: "How we operate together."
- **Anti-extraction, long-horizon.** Reinvestment in people and culture. Decades, not quarters.
- **No emoji. No exclamation points. No rhetorical questions.** The voice does not perform enthusiasm.

### Punctuation: no em dashes, no slashes

**Do not use em dashes (`—`) or forward slashes (`/`) in CE copy.** They read as hurried. Recast instead:

- Where you'd reach for an em dash, use a **period** (two short sentences), a **comma**, or a **colon**. "Confident, plainspoken, operational." Not "confident — plainspoken — operational."
- Where you'd pair or list with a slash, use **"and," "or," a comma,** or a **middot `·`**. "Systems, leadership, capital." Not "systems/leadership/capital." "Internal · Confidential," not "Internal / Confidential."
- The **only** vertical stroke that stays is the **`│` lockup separator** in `CE │ COLLECTIVE EDGE` (and `CE │ PARTNER NAME`). That is the logo, not punctuation.

---

## 5. Layout conventions (internal documents)

- **White canvas, generous margins.** Content lives well inside the page edge. CE breathes — do not fill every pixel.
- **The header motif:** a title (sentence-case `.ce-h*` or a small display line), an optional `.ce-eyebrow` above it, and a **1px `--ce-mist` horizontal rule underneath.** This under-header hairline is a fixed brand motif — it appears under nearly every section title.
- **Hairlines, not boxes.** Prefer a single 1px `#E2E2E2` rule or a 1px vertical column divider over bordered cards. Cards, when used, are flat: `--bg-surface` fill, `--radius-md` (6px) or square, `--shadow-1` only if in a list of equal elevations, 24–32px padding.
- **Comparison layouts ("Not this. This."):** split 50/50 with a centered vertical rule. Secondary label in mute grey, primary label in heavy black italic.
- **Corners mostly square** (0–6px). No squircles, no pills except tag chips.
- **Buttons:** primary = solid black, white text, 2px/square corners, 600 weight, slight caps tracking, hover → graphite; secondary = white fill + 1px black border, hover inverts. No gradients, no drop-shadow buttons, no emoji.
- **Footer:** slim strip, 1px `--ce-mist` top rule. Left: "Collective Edge | {Document Title}" in `--fg-4`. Right: revision marker (e.g., "Rev. 07.26") in `#111`, Montserrat 700.
- **Motion (if any):** quiet and fast — 200ms, `cubic-bezier(0.2,0,0,1)`, fades and short translates only. No spring, no bounce.
- **Forbidden:** UI gradients, glassmorphism, blurred orbs, illustration systems, brand patterns, drop-shadow decoration.

A ready-to-fill internal-document template lives at `templates/internal-doc.html` (and `examples/` holds rendered references).

---

## 6. Quick-reference snippets

**Under-header motif (the signature):**
```html
<header style="padding:0 0 var(--space-4); border-bottom:1px solid var(--ce-mist);">
  <p class="ce-eyebrow">SECTION / CATEGORY</p>
  <h1 class="ce-h1">How we operate together.</h1>
</header>
```

**Bold-then-explain line:**
```html
<p class="ce-body"><span class="ce-emphasis">Proven playbooks.</span> We understand what works and scale it.</p>
```

**Footer:**
```html
<footer style="border-top:1px solid var(--ce-mist); padding:8px 0; display:flex; justify-content:space-between;">
  <span class="ce-caption">Collective Edge &nbsp;│&nbsp; Document Title</span>
  <span style="font:700 12px 'Montserrat'; color:#111;">Rev. MM.YY</span>
</footer>
```

---

## 7. Versioning & sign-off

`@main` serves the latest; pin `@v1.0` for production. When you finish a CE deliverable, state the brand choices you applied (internal-doc vs hero treatment, which logo variant, font-embedding method) so the user can verify at a glance.
