# DESIGN.md — Peptide Calculator

> A design system for a peptide reconstitution & dosing calculator, derived from the **Wise** design language (`design-md/wise/`). Wise is a currency converter: type a number, choose units, read a result. A peptide calculator has the identical interaction shape — vial strength + diluent volume in, units-on-the-syringe out — so the same visual grammar applies, adapted for clinical legibility and numeric precision.

## 1. Visual Theme & Atmosphere

Warm off-white canvas, near-black text with a green undertone (`#0e0f0c`), and a single lime accent (`#9fe870`) that carries every call to action. The mood is confident and non-clinical — a calculator that feels like a well-made consumer fintech tool rather than a hospital form or a supplement storefront.

The organizing idea is **the result is the hero**. Display type runs at weight 900 with a 0.85 line-height, so the computed answer — "34 units" — is set at billboard scale, dense enough to read across a bathroom at arm's length while holding a syringe. Everything else in the interface recedes to support it: inputs are quiet pills, labels are small and tracked, the accent green appears only on the primary action and on the active state of the unit toggle.

Depth is almost absent. There are no drop shadows — only 1px ring shadows and border hairlines at 12% opacity. Separation comes from generous radii (30–40px on the calculator card) and whitespace, not from stacking planes. Interaction is physical rather than chromatic: buttons grow to `scale(1.05)` on hover and compress to `scale(0.95)` on press.

Two departures from stock Wise, both driven by the dosing context:

- **Tabular figures are mandatory.** Every number in the system — inputs, results, schedule tables, syringe tick labels — uses `font-variant-numeric: tabular-nums`. Proportional digits cause columns of doses to shimmer and misalign, which in a dosing tool is a correctness problem, not a taste problem.
- **The muted gray is darkened.** Wise's `#868685` sits at roughly 3.2:1 on white — acceptable for decorative captions, not for a unit label attached to a dose. Small muted text uses `#454745` (≈8:1) instead. `#868685` is reserved for text at 18px+ or non-essential decoration.

**Key Characteristics:**
- Display type at weight 900, line-height 0.85 — the result number is the largest thing on screen
- Lime Green (`#9fe870`) with Dark Green (`#163300`) text — accent only, never a large surface
- Inter weight 600 as the body default — confident reading weight, not light
- Tabular numerals everywhere a digit appears
- Pill buttons (9999px), large card radii (30–40px), 16px on small cards
- Ring shadows only (`rgba(14,15,12,0.12) 0 0 0 1px`) — no drop shadows
- `scale(1.05)` hover / `scale(0.95)` active on all interactive elements
- OpenType `"calt"` enabled globally
- Safety and out-of-range states are a first-class part of the palette, not an afterthought

## 2. Color Palette & Roles

### Brand
| Token | Hex | Role |
|---|---|---|
| `--near-black` | `#0e0f0c` | Primary text; dark section backgrounds |
| `--wise-green` | `#9fe870` | Primary CTA, active toggle, focus accent |
| `--dark-green` | `#163300` | Text on green surfaces, deep green accents |
| `--light-mint` | `#e2f6d5` | Soft green surface, result-card tint, badges |
| `--pastel-green` | `#cdffad` | Hover state on green interactive surfaces |

### Neutral
| Token | Hex | Role |
|---|---|---|
| `--canvas` | `#ffffff` | Page background |
| `--surface` | `#f7f9f5` | Recessed surface, input fill, table stripe |
| `--surface-alt` | `#e8ebe6` | Green-tinted light surface, dividers |
| `--text-secondary` | `#454745` | Body secondary text and **all small muted text** |
| `--text-tertiary` | `#868685` | Decorative captions at 18px+ only — never small labels |
| `--border` | `rgba(14,15,12,0.12)` | Default hairline border and ring shadow |

### Semantic — dosing states
| Token | Hex | Role |
|---|---|---|
| `--positive` | `#054d28` | Dose within range, confirmed calculation |
| `--positive-bg` | `#e2f6d5` | Success callout background |
| `--warning` | `#ffd11a` | Dose near range limit, rounding notice |
| `--warning-bg` | `#fff6d6` | Caution callout background |
| `--danger` | `#d03238` | Out-of-range dose, invalid input, destructive action |
| `--danger-bg` | `#fdeaea` | Error callout background |
| `--info-bg` | `rgba(56,200,255,0.10)` | Informational tint (safety notes, disclaimers) |
| `--info-fg` | `#0e5a73` | Informational text on `--info-bg` |

Semantic colors are never used decoratively. Green means *this dose is valid*; amber means *check this*; red means *do not draw this*. Because the accent and the success color are both green, a valid-dose confirmation is distinguished by the deep `--positive` (`#054d28`) foreground, never by the lime accent.

### Dark mode
Wise is light-first; dark mode keeps the same accent and warms the neutrals with a green undertone.

| Token | Hex |
|---|---|
| `--canvas` | `#0e0f0c` |
| `--surface` | `#191b16` |
| `--surface-alt` | `#23261f` |
| `--text-primary` | `#f4f7f0` |
| `--text-secondary` | `#b4b8b0` |
| `--border` | `rgba(255,255,255,0.10)` |
| `--light-mint` (surface) | `rgba(159,232,112,0.12)` |
| `--warning-bg` | `rgba(255,209,26,0.12)` |
| `--danger-bg` | `rgba(208,50,56,0.15)` |
| `--danger` | `#ff6b70` (lightened for contrast on dark) |

`--wise-green` and `--dark-green` are unchanged: the green pill with dark green text works identically in both modes, which keeps the primary action visually anchored across themes.

## 3. Typography Rules

### Families
- **Display**: `Wise Sans` if licensed, otherwise `Inter` at weight 900 — fallback stack `Inter, -apple-system, "Helvetica Neue", Arial, sans-serif`
- **Body / UI**: `Inter` — fallback `-apple-system, "Helvetica Neue", Arial, sans-serif`
- **Numeric**: same as body, with `font-variant-numeric: tabular-nums` and `font-feature-settings: "tnum" 1, "calt" 1`

Wise Sans is proprietary. Inter at weight 900 with the same 0.85 line-height is the substitute and holds the identity; do not fall back to a lighter weight to compensate.

### Hierarchy

| Role | Font | Size | Weight | Line Height | Tracking | Notes |
|---|---|---|---|---|---|---|
| Result Mega | Display | 96px | 900 | 0.85 | -2px | The computed dose. Tabular. |
| Result Hero | Display | 64px | 900 | 0.85 | -1.4px | Result on mobile / secondary results |
| Page Title | Display | 48px | 900 | 0.85 | -1px | Tabular off |
| Section Heading | Display | 32px | 900 | 0.90 | -0.6px | |
| Card Title | Inter | 22px | 600 | 1.25 | -0.4px | |
| Body | Inter | 18px | 400 | 1.44 | 0.18px | Long-form copy |
| Body Semibold | Inter | 18px | 600 | 1.44 | -0.11px | Default UI reading weight |
| Input Value | Inter | 22px | 600 | 1.20 | -0.2px | Tabular |
| Table Numeric | Inter | 16px | 600 | 1.40 | 0 | Tabular, right-aligned |
| Label | Inter | 14px | 600 | 1.50 | -0.08px | Field labels, `--text-secondary` |
| Unit / Caption | Inter | 14px | 400 | 1.50 | -0.08px | `--text-secondary`, never `--text-tertiary` |
| Micro | Inter | 12px | 600 | 1.60 | 0.4px | Uppercase eyebrow, tick labels |

### Principles
- Weight 900 for display is the identity — never lighten it.
- Never relax 0.85 on display; the vertical density is the point.
- `"calt"` on all text, `"tnum"` on all numerals.
- Inter 600 is the body default; 400 is for paragraphs of prose only.
- The result number is always the largest element in its viewport. If a heading competes with it, shrink the heading.

## 4. Component Stylings

### Buttons

**Primary (Calculate)**
- Background `--wise-green`, text `--dark-green`, weight 600, 18px
- Padding `14px 28px`, radius `9999px`
- Hover `scale(1.05)` + background `--pastel-green`; Active `scale(0.95)`
- Focus `outline: 2px solid var(--dark-green); outline-offset: 2px`
- Disabled: background `--surface-alt`, text `--text-tertiary`, no scale transform

**Secondary (Reset, Copy dose)**
- Background `rgba(22,51,0,0.08)`, text `--near-black`
- Padding `12px 20px`, radius `9999px`, same scale behavior

**Tertiary / text**
- No background, text `--near-black`, underline on hover, no scale

### Inputs

**Numeric field with unit suffix** — the workhorse of this interface.
- Container: radius `16px`, background `--surface`, border `1px solid var(--border)`, padding `12px 16px`
- Label above at 14px/600 `--text-secondary`
- Value 22px/600, tabular, `--near-black`, right-aligned when paired with a unit suffix
- Unit suffix: 14px/600 `--text-secondary`, non-interactive, inside the container on the right
- Focus: `box-shadow: 0 0 0 2px var(--wise-green) inset`, border transparent
- Invalid: border `1px solid var(--danger)`, message below at 14px `--danger`
- `inputmode="decimal"` on every dose field; no spinner arrows

**Unit toggle (segmented pill)** — mg / mcg / IU, or U-100 / U-40 syringe.
- Track: background `--surface`, radius `9999px`, padding `4px`
- Segment: radius `9999px`, padding `8px 18px`, 14px/600
- Active segment: background `--wise-green`, text `--dark-green`
- Inactive: transparent, text `--text-secondary`; hover `rgba(211,242,192,0.4)`
- Implement as `role="radiogroup"` with arrow-key navigation

### Result Readout
The primary output. A card, not a text node.
- Card: radius `40px`, background `--light-mint`, border `1px solid var(--wise-green)`, padding `40px 32px`
- Eyebrow: Micro, uppercase, `--dark-green` — e.g. "DRAW TO"
- Value: Result Mega, tabular, `--near-black`; the unit rendered at 32px/900 inline, `--text-secondary`
- Supporting line below: 18px/600 `--text-secondary` — the derivation, e.g. "2.5 mg in 1.0 mL · 0.25 mg dose"
- On recalculation, cross-fade the value over 160ms — never slide or count up; an animating number invites a misread

### Syringe Scale
A horizontal bar visualizing the fill point on a U-100 insulin syringe.
- Track: height `44px`, radius `9999px`, background `--surface`, border `1px solid var(--border)`
- Fill: `--wise-green`, radius `9999px`, left-aligned, 200ms ease
- Ticks: 1px `--border` at every 10 units; labels in Micro, tabular, `--text-secondary`
- Out-of-range fill (>100 units or below the smallest readable graduation): fill switches to `--danger`, paired with an error callout — the bar alone must never be the only signal

### Cards & Containers
- Calculator card: radius `40px`, padding `32px`, border `1px solid var(--border)`, background `--canvas`
- Content card: radius `30px`, padding `24px`
- Compact card / list row: radius `16px`, padding `16px`
- Ring shadow `rgba(14,15,12,0.12) 0 0 0 1px`; no drop shadows anywhere

### Dosage Schedule Table
- Container radius `30px`, `overflow: hidden`, border `1px solid var(--border)`
- Header row: background `--surface`, Micro uppercase `--text-secondary`
- Cells: 16px/600, `padding: 14px 20px`; **all numeric columns tabular and right-aligned**, text columns left-aligned
- Row separator `1px solid var(--border)`; hover `rgba(211,242,192,0.4)`
- Below 576px: collapse to stacked label/value rows in 16px cards, never a horizontal scroll

### Callouts (safety, warning, error)
- Radius `16px`, padding `16px 20px`, left border `4px solid` in the semantic color
- Info `--info-bg` / `--info-fg`; caution `--warning-bg` with `--near-black` text; error `--danger-bg` with `--danger` text
- Body 16px/600; each callout leads with a bold noun ("Verify concentration.") rather than a generic "Note:"
- A persistent, non-dismissible informational callout carries the not-medical-advice disclaimer on any page that outputs a dose

## 5. Layout Principles

### Spacing
Base unit 8px. Scale: `4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 96`.

### Radius scale
| Token | Value | Use |
|---|---|---|
| `--r-input` | 10px | Comboboxes, dense inputs |
| `--r-sm` | 16px | Small cards, callouts, input containers |
| `--r-md` | 30px | Content cards, tables |
| `--r-lg` | 40px | Calculator card, result readout |
| `--r-pill` | 9999px | Buttons, toggles, syringe track, badges |

### Grid
- Max content width `1120px`; calculator column capped at `560px` so the result never sets across an uncomfortable measure
- Desktop: two columns — inputs left, result and syringe right, sticky above 992px
- Section padding `64px` desktop / `40px` mobile
- The result must be visible without scrolling after the primary action on every breakpoint

## 6. Depth & Elevation

| Level | Treatment | Use |
|---|---|---|
| 0 — Flat | none | Page canvas, most surfaces |
| 1 — Ring | `rgba(14,15,12,0.12) 0 0 0 1px` | Cards, tables, callouts |
| 2 — Inset | `0 0 0 2px var(--wise-green) inset` | Focused input |
| 3 — Accent ring | `1px solid var(--wise-green)` | Result readout, active state |

Depth comes from the lime accent against the neutral canvas, not from shadow. If an element needs to feel raised, give it the accent ring — do not reach for a shadow.

## 7. Do's and Don'ts

### Do
- Set every digit in tabular figures
- Make the computed dose the largest element on screen
- Keep display type at weight 900 / 0.85 line-height
- Use `--wise-green` with `--dark-green` text for the single primary action per view
- Apply `scale(1.05)` hover and `scale(0.95)` active
- Pair every color-coded state with text — a red bar must come with a written reason
- Use `--text-secondary` (`#454745`) for small labels; reserve `#868685` for 18px+ decoration
- Show the derivation under the result so the user can check the math
- Keep the safety disclaimer visible on any view that outputs a dose

### Don't
- Don't use lime green as a large background surface — it is an accent
- Don't animate the result number by counting up; cross-fade it
- Don't put more than one green pill CTA in a view
- Don't use drop shadows — ring shadows only
- Don't use proportional figures in any table, input, or readout
- Don't signal an out-of-range dose with color alone
- Don't round silently — if a dose is rounded to the nearest readable graduation, say so in a caution callout
- Don't lighten the display weight or relax the 0.85 line-height

## 8. Responsive Behavior

| Name | Width | Key changes |
|---|---|---|
| Mobile | <576px | Single column; Result Hero (64px) replaces Result Mega; table collapses to stacked cards; CTA full-width |
| Tablet | 576–992px | Two-column inputs, result below and full-width |
| Desktop | 992–1440px | Inputs left / sticky result right |
| Large | >1440px | Content capped at 1120px, centered |

- Touch targets minimum `44×44px`; toggle segments minimum `48px` wide
- Numeric keypad via `inputmode="decimal"` on all dose fields
- Respect `prefers-reduced-motion`: drop the scale transforms and the syringe fill transition; keep the result cross-fade at 0ms (instant swap)
- Respect `prefers-color-scheme`, with an explicit override toggle

## 9. Agent Prompt Guide

### Quick reference
- Text `#0e0f0c` · Canvas `#ffffff` · Accent `#9fe870` · Text-on-accent `#163300`
- Muted `#454745` · Border `rgba(14,15,12,0.12)` · Mint surface `#e2f6d5`
- Valid `#054d28` · Caution `#ffd11a` · Error `#d03238`
- Display: Inter 900 / 0.85 line-height · Body: Inter 600 / 18px · Numerals: tabular

### Example prompts
- "Build the calculator card: white background, 40px radius, 1px solid rgba(14,15,12,0.12). Two numeric inputs — 'Vial strength' with an mg/mcg segmented pill toggle, and 'Diluent volume' with a mL suffix. Inputs are 16px-radius, #f7f9f5 fill, value at 22px Inter 600 tabular. Primary pill button #9fe870 with #163300 text, 9999px radius, scale(1.05) on hover."
- "Build the result readout: 40px-radius card, #e2f6d5 background, 1px solid #9fe870 border, 40px padding. Eyebrow 'DRAW TO' at 12px uppercase #163300. Value at 96px Inter weight 900, line-height 0.85, tabular-nums, #0e0f0c, with the unit inline at 32px in #454745. Derivation line below at 18px/600 #454745."
- "Build the syringe scale: 44px-tall pill track, #f7f9f5 fill, ticks every 10 units with 12px tabular labels in #454745. Green (#9fe870) fill bar, 200ms ease. If the value exceeds 100 units, switch the fill to #d03238 and render an error callout below it."
- "Build the dosage schedule table: 30px radius, overflow hidden. Header row #f7f9f5 with 12px uppercase labels. Numeric columns tabular and right-aligned. Row hover rgba(211,242,192,0.4). Below 576px, collapse rows to stacked 16px-radius cards."

### Iteration guide
1. Set the result number first at 96px/900/0.85 tabular — the rest of the layout is built around it
2. One green pill CTA per view, `#163300` text, scale animations on
3. Tabular figures on every digit before anything else is polished
4. Ring shadows and hairline borders — resist adding shadows
5. Every state that uses color also uses words
