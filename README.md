<p><picture><source media="(prefers-color-scheme: dark)" srcset="for-humans/logos/png/Collective-Edge-horizontal-white-1200w.png"><img src="for-humans/logos/png/Collective-Edge-horizontal-black-1200w.png" width="340" alt="Collective Edge"></picture></p>

# Collective Edge brand kit

Collective Edge is the holding and operating company behind Apex Paramedics and Royal Ambulance. This repository is the public source for the brand: logos, color, type and document layouts, with the rules for using them.

**[Read the brand guidelines](https://collective-edge.github.io/collective-edge-brand-kit/)** · the whole standard on one page.

## Start here

| | For people | For agents |
|---|---|---|
| Who | Designers, agencies, printers, staff | An agent or a script that makes branded documents |
| Open | [`for-humans/`](for-humans/) | [`for-agents/README.md`](for-agents/README.md), then [`SKILL.md`](SKILL.md) |
| Get | [Download the pack](https://github.com/collective-edge/collective-edge-brand-kit/archive/refs/heads/main.zip). Logos, fonts and a plain guide in one zip | Asset URLs, logo roles, color tokens and layout rules in inches, points and hex |

## Grab a logo

Pick by the ground the logo sits on. The file named **black** goes on light. The file named **white** goes on dark. Use the SVG wherever the software takes it. Sizes, clear space and the rules are in [`for-humans/`](for-humans/#sizes-and-spacing).

| Lockup | On a light ground | On a dark ground |
|---|---|---|
| Horizontal | [SVG](for-humans/logos/svg/Collective-Edge-horizontal-black.svg) · [PNG](for-humans/logos/png/Collective-Edge-horizontal-black-1200w.png) | [SVG](for-humans/logos/svg/Collective-Edge-horizontal-white.svg) · [PNG](for-humans/logos/png/Collective-Edge-horizontal-white-1200w.png) |
| Block mark | [SVG](for-humans/logos/svg/Collective-Edge-mark-black.svg) · [PNG](for-humans/logos/png/Collective-Edge-mark-black-512w.png) | [SVG](for-humans/logos/svg/Collective-Edge-mark-white.svg) · [PNG](for-humans/logos/png/Collective-Edge-mark-white-512w.png) |
| Block mark · Royal Ambulance wedge | [SVG](for-humans/logos/svg/Collective-Edge-mark-black-royal.svg) · [PNG](for-humans/logos/png/Collective-Edge-mark-black-royal-512w.png) | [SVG](for-humans/logos/svg/Collective-Edge-mark-white-royal.svg) · [PNG](for-humans/logos/png/Collective-Edge-mark-white-royal-512w.png) |
| Block mark · Apex Paramedics wedge | [SVG](for-humans/logos/svg/Collective-Edge-mark-black-apex.svg) · [PNG](for-humans/logos/png/Collective-Edge-mark-black-apex-512w.png) | [SVG](for-humans/logos/svg/Collective-Edge-mark-white-apex.svg) · [PNG](for-humans/logos/png/Collective-Edge-mark-white-apex-512w.png) |

The wedge takes a partner's color only on a surface that partner is on. Each combination is its own file. Never recolor one by hand.

## The system at a glance

### Color

No hue, ever. Black over graphite. There is no accent color. Emphasis comes from weight, size and the step between tiers.

| | Name | Hex | Use |
|---|---|---|---|
| <img src="for-humans/previews/swatches/000000.png" width="18" alt=""> | Black | `#000000` | The hero and the title, divider and closing slides |
| <img src="for-humans/previews/swatches/23232A.png" width="18" alt=""> | Graphite | `#23232A` | The header band. The same value sets body text |
| <img src="for-humans/previews/swatches/4E4F58.png" width="18" alt=""> | Iron | `#4E4F58` | A filled block between band and surface |
| <img src="for-humans/previews/swatches/C8C8C8.png" width="18" alt=""> | Fog | `#C8C8C8` | The wedge when Collective Edge stands alone. The rule under a band. Never text |
| <img src="for-humans/previews/swatches/E5E6EA.png" width="18" alt=""> | Paper | `#E5E6EA` | Table header fill. Never text |
| <img src="for-humans/previews/swatches/F0F1F4.png" width="18" alt=""> | Bone | `#F0F1F4` | Callout fills. Never text |
| <img src="for-humans/previews/swatches/FFFFFF.png" width="18" alt=""> | White | `#FFFFFF` | The page. The default surface |

Text, rules and borders come from one neutral family, the same in all three brands. Ink is `#23232A`. Green means good and nothing else. A brand color is never a status color. Chart colors come from the house data set.

Every value: [`tokens.json`](tokens.json). Every rule: [`reference/brand.md`](reference/brand.md). Charts: [`reference/data-color.md`](reference/data-color.md).

### Type

Montserrat at 400, 600, 700 and 800. No italic. The scale is the same in all three brands.

| Role | Print | Screen |
|---|---|---|
| Headline | 30pt | 40px |
| Section heading | 24pt | 32px |
| Subhead | 18pt | 24px |
| Lead | 15pt | 20px |
| Body | 12pt | 16px |
| Table text | 10.5pt | 14px |
| Caption and footer | 9pt | 12px |

Every rule: [`reference/type-system.md`](reference/type-system.md). Every value: [`snippets/type-tokens.json`](snippets/type-tokens.json).

### Documents

Six types. Most requests change a file that already exists: keep its layout, styles and wording, and change only what was asked.

| Type | For | Page | Body | Template |
|---|---|---|---|---|
| Working document | The default. Anything people keep editing in Google Docs or Word: agendas, plans, status reports, notes | US Letter, portrait, 0.75in margins | 10.5pt | [`templates/working-doc.html`](templates/working-doc.html) |
| Sheet | Trackers and lists in Google Sheets or Excel | One table per tab, from A1 | 10pt | None |
| Deck | Anything on a screen | 13.333 x 7.5in. 0.67in top, 0.83in left and right, 0.42in bottom | 15pt | [`templates/deck.html`](templates/deck.html) |
| One-pager | A designed single page for an outside reader, as a PDF | US Letter, portrait, 0.6in margins, exactly one page | 12pt | [`templates/one-pager.html`](templates/one-pager.html) |
| Report | A designed document of three pages or more, as a PDF | US Letter, portrait, 0.75in margins | 12pt | [`templates/document.html`](templates/document.html) |
| Memo | Only when asked for by name | US Letter, portrait, 0.75in margins | 12pt | [`templates/memo.html`](templates/memo.html) |

A working document is plain: the logo at top left, a title, no band. The band opens a one-pager, a report and a memo, which are made for PDF and print. Content slides are white. The dark ground is for the title, divider and closing slides. “Powered by Collective Edge” appears once, small, on every Apex Paramedics and Royal Ambulance PDF, deck and image. A working document and a sheet never carry it.

Every rule: [`reference/layout.md`](reference/layout.md). The same values as data: [`documents.json`](documents.json).

## The house

Three brands, one standard. The kits differ in color, logo and brand facts.

| Brand | Guidelines | Repository |
|---|---|---|
| Collective Edge · the parent | [collective-edge.github.io/collective-edge-brand-kit](https://collective-edge.github.io/collective-edge-brand-kit/) | [`collective-edge-brand-kit`](https://github.com/collective-edge/collective-edge-brand-kit) |
| Apex Paramedics | [collective-edge.github.io/apex-brand-kit](https://collective-edge.github.io/apex-brand-kit/) | [`apex-brand-kit`](https://github.com/collective-edge/apex-brand-kit) |
| Royal Ambulance | [collective-edge.github.io/royal-brand-kit](https://collective-edge.github.io/royal-brand-kit/) | [`royal-brand-kit`](https://github.com/collective-edge/royal-brand-kit) |

## What is in here

```
collective-edge-brand-kit/
├── index.html        The guidelines page. Built by guidelines/build.py
├── guidelines/       The page builder, its stylesheet, the brand copy and the preview image
├── for-humans/       Logos, fonts, color chips and a plain guide. For people
├── for-agents/       The shortest correct path for an agent
├── AGENTS.md         Agent entry point
├── SKILL.md          The standard in brief
├── reference/        The full standard: brand, layout, type, data color, controls
├── brands.json       Every brand in the house: CDN roots, logo roles, the co-brand lockup
├── documents.json    The document types as data
├── tokens.json       This brand's colors as hex and RGB
├── snippets/         Stylesheets, type tokens and the header band
├── templates/        Working document, deck, one-pager, report and memo
├── Examples/         Filled references
├── assets/           Logo masters, fonts and the hero imagery. Live CDN paths
├── scripts/          The checks and the builders
├── CONTRIBUTING.md   How to change this repository
├── NEW-BRAND.md      How to stand up a kit for a new brand
└── TRADEMARKS.md     What others may do with the names and logos
```

## Use it

### Load

Every file is public on jsDelivr. No auth, no install.

```
https://cdn.jsdelivr.net/gh/collective-edge/collective-edge-brand-kit@main/
```

Colors are in `tokens.json`. Type is in `snippets/type-tokens.json`. Layouts are in `documents.json` and `reference/layout.md`. Logos resolve by role in `brands.json`. The stylesheet link tags for an HTML page are in [`for-agents/README.md`](for-agents/README.md).

### Verify

```bash
python3 scripts/check-sync.py
python3 scripts/validate.py path/to/output.html
python3 scripts/validate-palette.py --series
python3 scripts/ui-audit.py path/to/output.html
```

`check-sync.py` proves the shared files match the other two kits. `validate.py` checks type rules 1, 2, 5, 9, 10, 13 and 14 and check L1, retired logo artwork. `validate-palette.py` checks the chart colors. `ui-audit.py` measures a rendered page. No script reads a page the way a person does. Open the file and look.

### Versions

`main` is live. The CDN serves it and the agent reads it on every request, so a change lands whole. Production material pins a tag in place of `@main`. [`CONTRIBUTING.md`](CONTRIBUTING.md) covers changes.

### License and trademarks

The names, logos and brand colors in this repository belong to Collective Edge. [`TRADEMARKS.md`](TRADEMARKS.md) says what others may do with them. Permission is by request.

Montserrat is licensed under the SIL Open Font License, Version 1.1. The license text is in [`assets/fonts/OFL.txt`](assets/fonts/OFL.txt) and [`for-humans/fonts/OFL.txt`](for-humans/fonts/OFL.txt).
