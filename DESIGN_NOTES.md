# Spellbinder — Design Notes for Claude Code
> Plain-English reference for building additional Shopify sections
> and components that stay on-brand. Read this before writing any new Liquid or CSS.

---

## Who is Spellbinder?

High-end nutraceutical brand. Two flagship products:
- **Wizards Brew** (All-n-One daily stirrable) — positioned as "The All-In-One Daily Ritual"
- **Golden Latte** (Recovery & Repair) — positioned as "Recovery & Repair, in a golden cup"

Products are organized around three pillars: **REMOVE → REPLENISH → REGENERATE** (R1/R2/R3).

---

## Color Palette

### Neutrals
| Name           | Hex       | Use                                      |
|----------------|-----------|------------------------------------------|
| Black          | `#000000` | Page background, hero background         |
| Smoke          | `#1F1F1F` | Cards, nav bar, surface backgrounds      |
| Smoke Light    | `#434343` | Blurred/inactive inputs                  |
| Smoke Lightest | `#676767` | Card borders, icon fills, strokes        |
| Light Grey     | `#ABABAB` | Muted body copy on dark backgrounds      |
| Ivory Dim      | `#EEEEE7` | Secondary headline text                  |
| Ivory          | `#F6F5E8` | Primary headline text                    |
| White          | `#FFFFFF` | Button labels, banner text               |

### Brand / Primary
| Name       | Hex       | Use                                           |
|------------|-----------|-----------------------------------------------|
| Gold       | `#BA9971` | Primary CTA buttons, active nav, borders      |
| Gold Light | `#E9D3B7` | Active input border, subtle accents           |

### Accent / Product Palette
| Name           | Hex       | Use                                      |
|----------------|-----------|------------------------------------------|
| Fire           | `#FE8E02` | Banner gradient start, Fire flavor       |
| Lava           | `#FE01CD` | Banner gradient end, logo bolt, Lava     |
| Plum           | `#63149A` | Deep purple accent, Plum flavor          |
| Ocean          | `#03939C` | Teal accent, Ocean flavor                |
| Neon           | `#CAF017` | Lime yellow, Neon flavor                 |
| Electric Green | `#6EE21E` | Electric green accent                    |

### Gradients
- **Banner (primary):** `linear-gradient(to right, #FE8E02, #FE01CD)` — Fire to Lava
- **Hero overlay:** `linear-gradient(#000 10%, rgba(0,0,0,0.55) 45%, rgba(0,0,0,0) 100%)` — always vertical, always left-to-right fade on desktop
- **Ocean → Plum:** `linear-gradient(to right, #03939C, #63149A)`
- **Neon → Electric Green:** `linear-gradient(to right, #CAF017, #6EE21E)`

---

## Typography

### Fonts
- **Display / Headlines:** `"Times New Roman", "Times", Georgia, serif`
  - Used for: H1 hero headlines, H2 section titles, R-pillar names (REMOVE etc.)
  - Weight: Regular (400)
  - Casing: Title Case for hero lines; ALL CAPS for R-pillar names
- **UI / Body:** `"Plus Jakarta Sans", "Gilroy", system-ui, sans-serif`
  - **Gilroy is the brand font** but is a commercial license. Plus Jakarta Sans is the approved substitute until Gilroy `.woff2` files are provided.
  - Used for: nav links, button labels, body copy, banner text, card copy
  - Weights: Bold (700) for nav/buttons/labels; Medium (500) for sub-headlines; Regular (400) for body

### Size Scale
| Token               | Size  | Use                              |
|---------------------|-------|----------------------------------|
| Display XL          | 72px  | Hero H1 (desktop)                |
| Display LG          | 36px  | Section H2 / pillar names        |
| UI XL               | 24px  | Hero subheadline, banner text    |
| UI LG               | 20px  | Nav links                        |
| UI MD               | 18px  | Button labels, card labels       |
| UI SM               | 16px  | Input text, fine print           |

### Line Heights
- Headlines: `1` (tight, 100%)
- Body / subheadlines: `1.5`
- UI labels: fixed `24px`

### Responsive
- On mobile (<750px): Display XL → 36px; Display LG → 28px; body → 17px
- Always use `clamp()` for fluid type on new sections

---

## Spacing Scale

| Token      | Value  | Common use                              |
|------------|--------|-----------------------------------------|
| --sb-space-1 | 4px  | Micro gaps                              |
| --sb-space-2 | 8px  | Tight gaps                              |
| --sb-space-3 | 10px | Nav/banner padding                      |
| --sb-space-4 | 16px | Input padding, tight card gaps          |
| --sb-space-5 | 24px | Card internal padding, component gaps   |
| --sb-space-6 | 32px | Button horizontal padding               |
| --sb-space-7 | 40px | Card bottom padding                     |
| --sb-space-8 | 60px | Card grid gap, nav height               |
| --sb-space-9 | 100px| Section side padding, large element gap |

---

## Border Radius

| Use          | Value   |
|--------------|---------|
| Inputs       | 6px     |
| Cards        | 12px    |
| Buttons      | 300px   | ← full pill, non-negotiable

---

## Component Rules

### Buttons
- **Only one style:** gold pill (`#BA9971`, border-radius 300px, height 50px, Gilroy Bold 18px white text)
- Hover: `filter: brightness(0.88)` — no scale, no shadow
- Ghost variant is acceptable but not in Figma — use `border: 1.5px solid #BA9971`, transparent bg, gold text
- **No rounded-corner accent-border containers** — this is an AI slop trope, do not use it

### Cards
- Background: `#1F1F1F`
- Border: `1px solid #676767` (default) or `5px solid #BA9971` (featured/accent)
- Radius: `12px`
- Padding: `28px 28px 40px`
- No box-shadow — dark-on-dark contrast carries the elevation

### Navigation
- Logo: centered, ~72px tall on desktop
- Nav bar: `#1F1F1F`, 52–60px tall, nav links centered with `80px` gap
- Nav links: Gilroy Bold 20px, `#F9F9F9`, hover → `#BA9971`
- Utility icons (search, cart, profile): top-right of header, `~22px`, `#ABABAB`

### Hero Sections
- Always full-bleed photography, dark and warm-toned
- Always apply the black-to-transparent gradient overlay
- Headline over image, left-aligned, max-width ~680px
- Photo focal point is configurable — default `center center`
- Minimum height 500px mobile, 600px desktop

### Banner / Marquee
- Full-width, 52px tall
- Primary gradient: Fire → Lava
- Text: Gilroy Bold 18px white, 80px gap between items
- Animation: CSS `translateX` marquee, 20s default, doubled content for seamless loop
- Always respect `prefers-reduced-motion`

### Photography
- Always moody, dark, warm: coffee splashes, golden lattes, mountain/nature
- Always mask with vertical gradient overlay (black top, transparent bottom)
- No bright/airy lifestyle photography — brand is nocturnal and premium

---

## Design Rules — What NOT to Do

1. **No gradient backgrounds on cards or buttons** — gradients are only for the marquee banner
2. **No emoji** — brand is premium, zero emoji anywhere
3. **No rounded-corner containers with a left-border accent color** — this is a design anti-pattern
4. **No Inter, Roboto, or Arial** — use Times New Roman + Plus Jakarta Sans / Gilroy only
5. **No invented colors** — all colors must come from the palette above; use `oklch()` only if extending the palette and only in the warm/muted direction
6. **No data slop** — do not add fake stats, dummy icons, or filler numbers to pad sections
7. **No placeholder lorem ipsum** — use real Spellbinder copy or leave blank for client to fill
8. **No drop shadows on cards** — dark-on-dark contrast is intentional
9. **Buttons are always pill-shaped** — never use square or lightly-rounded buttons

---

## Copy Patterns to Reuse

- **Tagline:** "Real energy. Real ingredients. Real results."
- **Sub-tagline:** "No stimulants borrowed from tomorrow."
- **R1:** "Start with a clean slate." — REMOVE
- **R2:** "Feed what matters." — REPLENISH
- **R3:** "Build for the long game." — REGENERATE
- **Product descriptor:** "Forty-plus botanicals, spagyric-fermented and working in perfect synergy — everything your body was designed to run on, in a single magical cup."
- **Golden Latte descriptor:** "Eight medicinal mushrooms, turmeric, collagen, and anti-inflammatory botanicals, working while you rest. Caffeine-free, sugar-free, and deeply restorative."
- **CTA:** "Try Now" (primary) / "Learn More" (secondary)

---

## File Map

```
shopify-export/
  assets/
    spellbinder.css         ← All CSS tokens + Dawn overrides. Load in theme.liquid.
  sections/
    sb-hero.liquid          ← Homepage hero with image, overlay, headline, CTA
    sb-hero.json            ← Default content for sb-hero
    sb-banner.liquid        ← Animated marquee banner (gradient, scrolling text)
    sb-feature-cards.liquid ← R1/R2/R3 three-up feature card grid
  config/
    settings_schema_patch.json ← Block to insert into Dawn's settings_schema.json
  DESIGN_NOTES.md           ← This file
```

---

## How to Load spellbinder.css in Dawn

Add this line to `layout/theme.liquid`, just before `</head>`:

```liquid
{{ 'spellbinder.css' | asset_url | stylesheet_tag }}
```

This is already included inside each section file as a fallback, but loading it globally avoids redundant requests.

---

## Shopify CLI Quick Reference

```bash
# Pull live theme
shopify theme pull --store your-store.myshopify.com --theme-id YOUR_THEME_ID

# Push changes
shopify theme push

# Preview locally
shopify theme dev --store your-store.myshopify.com
```
