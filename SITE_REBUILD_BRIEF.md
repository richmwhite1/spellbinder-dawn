# Spellbinder Full Site Rebuild Brief

## For Claude Code

This document is the complete content + structure specification for rebuilding the entire Spellbinder Shopify site on Dawn. All visual styling decisions reference `assets/spellbinder.css` and `DESIGN_NOTES.md`. Every section must be Liquid with proper `{% schema %}` blocks so it's editable in the Shopify theme editor.

**Brand voice:** confident, evocative, where ancient herbalism meets clinical credibility. The line is "Ancient Alchemy. Modern Science." — write to that tension. Never gimmicky, never woo-woo. Compton Rom (microbiologist + founder) is the credibility anchor — name him directly when relevant.

**Conversion priority:** first-time buyers. Every page should reduce friction for someone who's never bought before. That means: social proof early, clear pricing, risk reversal (30-day guarantee) visible, and a single dominant CTA per page.

**Build order (in this document):**
1. Homepage
2. Product page — Awaken Brew
3. Product page — Golden Latte
4. Collection page (Shop)
5. Our Formula
6. About
7. FAQ
8. Journal (blog index)
9. Contact
10. Shipping
11. Returns
12. Cart page

---

# 1. HOMEPAGE

**Section order:**
1. Announcement bar
2. Hero
3. Trust strip
4. The Problem
5. The Solution (Remove. Replenish. Regenerate.)
6. Comparison table
7. Product showcase
8. Reviews carousel
9. The Method
10. What's Inside (ingredient categories)
11. Formulator story (Compton Rom)
12. FAQ (condensed)
13. Email capture
14. Footer

## 1.1 Announcement Bar
**File:** Use Dawn's existing `announcement-bar.liquid`.
**Content:** `Buy 2+ get 20% off · Free shipping over $75 · 30-day money-back guarantee`

Three rotating messages, or one combined line on mobile.

## 1.2 Hero
**File:** `sections/sb-hero.liquid`

- Eyebrow: `ANCIENT ALCHEMY. MODERN SCIENCE.`
- Headline (H1): `The morning ritual your body was built for.`
- Subhead: `Forty-plus botanicals. Spagyric-fermented. Microbiologist-formulated. One cup that removes what shouldn't be there, replenishes what's been stripped away, and regenerates from the cellular level up.`
- Rating: `★★★★★  500+ five-star reviews`
- Primary CTA: `Begin your ritual` → `/products/awaken-brew`
- Secondary link: `How it works →` → `/pages/our-formula`
- Risk reversal microcopy below CTA: `30-day money-back guarantee · Free shipping over $75`
- Hero image: existing Awaken Brew golden cup image

**Schema:** All text fields editable, image picker, CTA label + link, secondary link.

## 1.3 Trust Strip
**File:** `sections/sb-trust-strip.liquid`

Four stat blocks, divided by thin vertical lines. Mobile: 2x2 grid.

- `40+ BOTANICALS` / *Spagyric-extracted, never isolated*
- `8 MEDICINAL MUSHROOMS` / *Lion's mane, reishi, chaga, cordyceps + 4 more*
- `MICROBIOLOGIST FORMULATED` / *By Compton Rom, where Eastern herbalism meets Western biochemistry*
- `ZERO FILLERS` / *No gums, seed oils, or proprietary blends*

**Schema:** Repeating stat block, headline + subline editable.

## 1.4 The Problem
**File:** `sections/sb-problem.liquid`

Two-column layout. Image left (use `pexels-sedanur-kunuk` or similar quiet/contemplative image), copy right.

- Eyebrow: `THE MORNING TRAP`
- Headline: `Your morning is working against you.`
- Body:

  *Most of us start the day the same way. A cup of coffee. Maybe two. A jolt of cortisol, a spike in blood sugar, and three hours later — the crash.*

  *Energy drinks promise more and deliver less. Wellness teas are under-dosed or taste like lawn clippings. Supplement stacks feel like a medical protocol. And most of what's marketed as "healthy" hides behind seed oils, gum fillers, and proprietary blends that tell you nothing.*

- Closing line (larger, italic, accent color): *You deserve a little magic in your morning.*

## 1.5 The Solution — Three Pillars
**File:** `sections/sb-three-pillars.liquid`

Three columns. Mobile: stacked.

- Eyebrow: `THREE PRINCIPLES · ONE SYSTEM`
- Headline: `Remove. Replenish. Regenerate.`

**Pillar 1 — Remove**
*Start with a clean slate. Spagyric extracts and plant compounds support your body's natural detoxification pathways — sweeping away what shouldn't be there so your cells can do their best work.*

**Pillar 2 — Replenish**
*Feed what matters. Spellbinder floods your biology with the nutrient density modern diets have stripped away — restoring the cellular richness your body was built to run on.*

**Pillar 3 — Regenerate**
*Build for the long game. Daily use means daily renewal — supporting cellular health, hormonal rhythm, gut integrity, and cognitive clarity from the inside out.*

## 1.6 Comparison Table
**File:** `sections/sb-comparison.liquid`

Mobile: collapses to stacked cards.

- Eyebrow: `WHY SPELLBINDER`
- Headline: `Don't just start your day. Awaken the wizard within.`
- Subhead: `While others use synthetic vitamins and proprietary blends, we use whole-plant spagyric extracts and 50+ synergistic ingredients. No fillers. No junk. Just magic.`

**Columns:** Drink | What You Get | The Cost | Long-Term Effect

**Rows:**
1. Coffee (2–3 cups) | Fast energy then crash | Cortisol spike, blood sugar swing | Adrenal stress over time
2. Energy Drinks | Quick stimulation | Artificial ingredients, chronic inflammation | Metabolic disruption
3. Standard Wellness Tea | Mild comfort, vague benefits | Under-dosed, often sweetened | Little meaningful change
4. Popular All-in-Ones | Broad-spectrum coverage | Premium price, conventional extraction | Maintenance without depth
5. **Awaken Brew** *(highlighted row, accent background)* | Sustained energy, cellular nourishment | Zero junk — spagyric-extracted, clean by design | Biological intelligence compounding daily

**CTA below:** `Try Awaken Brew →` → `/products/awaken-brew`

## 1.7 Product Showcase
**File:** `sections/sb-product-showcase.liquid`

- Eyebrow: `CHOOSE YOUR RITUAL`
- Headline: `Two elixirs. One complete system.`

**Card 1 — Awaken Brew**
- Tag: `FLAGSHIP FORMULA`
- Description: *Forty-plus prayerfully curated ingredients — spagyric adaptogens, medicinal mushrooms, ancient longevity herbs, and algae superfoods. Microbiologist-formulated by Compton Rom. Nothing wasted.*
- Price: `$50 · 30 servings`
- Subscribe price: `$42 · save 16% · cancel anytime`
- CTA: `Begin Your Ritual →` → `/products/awaken-brew`

**Card 2 — Golden Latte**
- Tag: `FAN FAVOURITE`
- Description: *Warming. Rich. Restorative. Turmeric, ginger, eight medicinal mushrooms, and aromatic spices. Caffeine-free. Hot or iced. The ritual that repairs you while you enjoy it.*
- Price: `$50 · 30 servings`
- Subscribe price: `$42 · save 16% · cancel anytime`
- CTA: `Discover Yours →` → `/products/golden-latte`

**Bundle bar:** `Complete the system — Save 20% on the Ritual Bundle →` → `/collections/bundles`

**Schema:** Pull product data dynamically. Allow override of description per card.

## 1.8 Reviews Carousel
**File:** `sections/sb-reviews.liquid`

- Eyebrow: `FROM THE COMMUNITY`
- Headline: `Your morning, transformed.`

Use existing reviews (Richard C., Ted, Zwest, Haley F.). Add aggregate stat above carousel: `★★★★★ 4.9 average · 500+ reviews`

**Schema:** Repeating review block with rating, quote, name, product, verified badge.

## 1.9 The Method
**File:** `sections/sb-method.liquid`

Four-up grid. Mobile: 2x2.

- Eyebrow: `THE ART BEHIND THE SCIENCE`
- Headline: `Ancient method. Modern result.`

1. **Spagyric Extraction** — *An ancient alchemical process that captures the full spectrum of each plant — not just isolated fragments.*
2. **The Power of Fermentation** — *Fermentation breaks down cellular walls, unlocks deeper compounds, and produces beneficial postbiotics that support your gut.*
3. **Bioavailability by Design** — *Every formulation decision maximizes absorption. What gets in is what works — nothing wasted.*
4. **Regenerative Sourcing** — *Organic, biodynamic, and wildcrafted wherever possible. Clean soil produces clean ingredients.*

**CTA:** `Explore the full formula →` → `/pages/our-formula`

## 1.10 What's Inside
**File:** `sections/sb-ingredients.liquid`

3x2 grid of expandable category cards. Mobile: stacked, collapsed by default.

- Eyebrow: `WHAT'S INSIDE`
- Headline: `Over 50 ingredients. Every one earns its place.`
- Subhead: `Six ancient systems. One complete formula.`

**Categories** (keep existing — they're working):
1. Adaptogenic Intelligence — Ashwagandha, Reishi, Astragalus, Cordyceps, Siberian Ginseng, Ginseng, Epimedium, Eucommia Bark, He Shou Wu, Schisandra
2. Ancient Tea Matrix — Yerba Mate, Puerh, Jiaogulan, Long Jing, Oolong, Rooibos, Darjeeling, Liu Bao, Gyokuro, White Peony
3. Detox & Cellular Clean — Spirulina, Chlorella, Marine Phytoplankton, Spagyric Fermented Extracts, Broccoli Sprouts, Alfalfa Sprouts, Dandelion Root, Milk Thistle, Barley Grass, Aloe Vera
4. Longevity & Hormonal — Eucommia Bark, Epimedium, He Shou Wu, Ginkgo Biloba, Turmeric, Resveratrol, Astragalus, Rehmannia, Schisandra, Pine Pollen, Shilajit
5. Medicinal Fungi — Lion's Mane, Chaga, Turkey Tail, Maitake, Shiitake, Royal Agaricus, Reishi, Cordyceps, Tremella, Poria
6. Recovery & Repair — Bovine Collagen, Turmeric Juice Extract, Ginger Juice Extract, Cardamom, Cinnamon, Cacao, Black Pepper, Carob, Bromelain, Quercetin

**CTA:** `Explore every ingredient →` → `/pages/our-formula`

## 1.11 Formulator Story
**File:** `sections/sb-formulator.liquid`

Two-column. Image left (Compton Rom or formulation imagery), copy right.

- Eyebrow: `THE FORMULATOR`
- Headline: `Where science becomes alchemy.`
- Body:

  *Every ingredient in Spellbinder is prayerfully curated by Compton Rom — a microbiologist who spent years at the crossroads of ancient Eastern herbalism and Western biochemistry, asking one question: what does the body actually need?*

  *His answer was a system built on spagyric extraction — an ancient alchemical process that captures the full spectrum of each plant. Remove. Replenish. Regenerate. Not a tagline. A biological protocol, built into every dose.*

- CTA: `Read Compton's story →` → `/pages/about`

## 1.12 FAQ (Condensed Homepage Version)
**File:** `sections/sb-faq.liquid`

Six questions, accordion. (Full FAQ lives at `/pages/faq`.)

- Eyebrow: `FREQUENTLY ASKED`
- Headline: `Questions, answered.`

1. **How does Awaken Brew taste?** *Earthy, rich, slightly malty — like a sophisticated tea with depth. Most people drink it with a splash of oat or whole milk.*
2. **When will I notice results?** *Sustained energy and clearer focus typically within the first week. Deeper benefits — gut health, cellular renewal — compound over 30–90 days.*
3. **Will it replace my coffee?** *Yes — without the crash. Awaken Brew uses naturally caffeinated ancient teas (yerba mate, puerh, oolong) for sustained energy without cortisol spikes.*
4. **Is it safe to take every day?** *Yes. Built for daily ritual use. Food-grade, third-party tested, and dosed for sustained intake. Pregnant, nursing, or on medication? Consult your physician.*
5. **What makes spagyric extraction different?** *Standard extraction pulls one or two compounds. Spagyric captures the full spectrum — water-soluble, oil-soluble, and mineral salts — so your body recognizes and absorbs the whole plant.*
6. **What's your return policy?** *If you don't love it within 30 days, we refund your first order in full. No questions, no return shipping required.*

**Link below:** `See all questions →` → `/pages/faq`

## 1.13 Email Capture
**File:** `sections/sb-email-capture.liquid`

Full-width band, accent background.

- Headline: `Get 10% off your first ritual.`
- Subhead: `Plus a short guide on building your morning ritual the Spellbinder way.`
- Input: `Your email`
- Button: `Send my code`
- Microcopy: `No spam. Unsubscribe anytime.`

**Schema:** Form posts to Klaviyo if connected, else Shopify customer list.

## 1.14 Footer
Keep Dawn's existing footer columns (Shop / Learn / Support). Apply spellbinder.css styling.

---

# 2. PRODUCT PAGE — AWAKEN BREW

**URL:** `/products/awaken-brew`
**Template file:** `templates/product.awaken.json`
**Section files:** `sections/sb-product-main.liquid`, `sections/sb-product-benefits.liquid`, `sections/sb-product-ingredients.liquid`, `sections/sb-product-howto.liquid`, `sections/sb-product-faq.liquid`, plus shared review section.

**Section order:**
1. Main product (image gallery + buy box)
2. Sticky add-to-cart (mobile)
3. Benefits grid
4. Comparison block (Awaken Brew vs your morning drink)
5. How it works (Remove. Replenish. Regenerate. — product-specific)
6. Ingredients deep-dive
7. How to use
8. Reviews
9. Subscribe & Save
10. FAQ
11. Footer

## 2.1 Main Product Block

**Layout:** Image gallery left (5 images: hero shot, lifestyle pour shot, ingredients flat-lay, label/back panel, before-after-energy chart). Buy box right.

**Buy box content:**

- Tag (above title): `FLAGSHIP FORMULA · 40+ BOTANICALS`
- Title (H1): `Awaken Brew`
- Star rating + review count (clickable, scrolls to reviews)
- Short description: *The all-in-one daily ritual. Spagyric-fermented adaptogens, medicinal mushrooms, ancient teas, and longevity botanicals — formulated by microbiologist Compton Rom to remove what doesn't belong, replenish what's depleted, and regenerate at the cellular level.*

**Purchase options (radio toggle):**
- ⚪ One-time purchase — `$50` / 30 servings
- 🔘 **Subscribe & Save 16%** — `$42` / 30 servings · *delivered every 30 days · cancel anytime* **(default selected)**

**Quantity selector:** 1 (with stepper)

**Add to cart button:** `Add to cart — $42`

**Trust microcopy below button (3 lines, with small icons):**
- ✓ Free shipping over $75
- ✓ 30-day money-back guarantee
- ✓ Third-party tested · Made in USA

**Quick benefit bullets (above-the-fold reasons to buy):**
- Sustained energy without the coffee crash
- 8 medicinal mushrooms · 40+ botanicals · zero fillers
- Spagyric extraction for full-spectrum absorption
- Caffeinated by ancient teas, not synthetics

## 2.2 Sticky Add-to-Cart (Mobile)

Appears once main buy box scrolls out of view. Shows: thumbnail, product name, price, "Add to cart" button.

## 2.3 Benefits Grid
**File:** `sections/sb-product-benefits.liquid`

3x2 grid (mobile 1 column).

- Eyebrow: `WHAT IT DOES`
- Headline: `What one cup actually delivers.`

1. **Sustained Energy** — *Naturally caffeinated by yerba mate, puerh, and oolong. No cortisol spike. No 3 PM crash.*
2. **Cognitive Clarity** — *Lion's mane and ancient adaptogens support focus, memory, and mental sharpness.*
3. **Cellular Renewal** — *Spagyric-fermented extracts deliver compounds your body actually absorbs.*
4. **Gut Health** — *Fermented postbiotics and 8 medicinal mushrooms support microbiome and digestion.*
5. **Stress Resilience** — *Adaptogens like ashwagandha, reishi, and schisandra help regulate the HPA axis.*
6. **Hormonal Balance** — *Eucommia bark, He Shou Wu, and pine pollen support endocrine rhythm.*

## 2.4 Comparison Block

Same comparison table as homepage but shorter — 3 rows instead of 5.

- Headline: `One ritual replaces three things in your kitchen.`

| Your Morning | Awaken Brew |
|---|---|
| Coffee + sweetener | Sustained energy, no crash |
| Daily multivitamin | 50+ whole-plant compounds |
| Adaptogen powder | Spagyric-extracted, fully absorbable |

## 2.5 How It Works
**File:** Reuse `sections/sb-three-pillars.liquid` with product-specific copy.

Headline: `What Awaken Brew does, biologically.`

**Remove** — *Chlorella, milk thistle, dandelion, and broccoli sprouts support your liver and detox pathways.*
**Replenish** — *Spirulina, marine phytoplankton, and 40+ adaptogens flood your cells with bioavailable nutrients.*
**Regenerate** — *Lion's mane, reishi, cordyceps, and longevity botanicals rebuild over time.*

## 2.6 Ingredients Deep-Dive
**File:** `sections/sb-product-ingredients.liquid`

Same 6-category accordion as homepage. Add a small note at top: `Click any category to explore.`

## 2.7 How to Use
**File:** `sections/sb-product-howto.liquid`

Three-step horizontal layout. Mobile: stacked.

- Eyebrow: `YOUR DAILY RITUAL`
- Headline: `Three steps. One transformation.`

1. **Scoop** — *One tablespoon (≈8g) into your favorite mug.*
2. **Pour** — *6–8 oz hot water. Stir or froth. Add a splash of milk if you like.*
3. **Sip** — *Replace coffee, sip slowly, and let the ritual begin.*

**Pro tip:** *For an iced version, dissolve in 2 oz hot water first, then pour over ice and milk.*

## 2.8 Reviews
**File:** Reuse `sections/sb-reviews.liquid` — but pull product-specific reviews only.

If using Judge.me / Yotpo / Loox / Stamped, integrate the live widget here.

## 2.9 Subscribe & Save
**File:** `sections/sb-subscribe-cta.liquid`

Full-width band, accent background.

- Headline: `Make it a daily ritual. Save 16% forever.`
- Body: *Subscribe and never run out. Skip, pause, or cancel anytime — no fees, no friction.*
- Bullet list:
  - Save 16% on every order
  - Free shipping on every subscription
  - Skip or cancel from your account
  - First delivery ships in 1–3 business days
- CTA: `Subscribe & save →` (scrolls back to buy box with subscribe option pre-selected)

## 2.10 FAQ
**File:** `sections/sb-faq.liquid` — product-specific 8 questions.

1. How does it taste?
2. Does it have caffeine?
3. When will I feel results?
4. Can I take it with other supplements?
5. Is it safe during pregnancy or while nursing?
6. How is it different from a regular adaptogen blend?
7. How does the subscription work?
8. What if I don't like it?

(Use the same answers as the FAQ page section 7 below.)

---

# 3. PRODUCT PAGE — GOLDEN LATTE

**URL:** `/products/golden-latte`

Same template structure as Awaken Brew. Different copy.

## Key copy changes:

**Buy box:**
- Tag: `FAN FAVOURITE · CAFFEINE-FREE`
- Title: `Golden Latte`
- Short description: *The recovery ritual. Eight medicinal mushrooms, turmeric, ginger, collagen, and warming spices — formulated by Compton Rom to quiet inflammation, ease your body into rest, and restore your evening rhythm. Caffeine-free. Hot or iced.*

**Quick benefits:**
- Caffeine-free recovery ritual
- 8 medicinal mushrooms + turmeric + ginger
- Anti-inflammatory and gut-soothing
- Works hot or poured over ice

**Benefits grid headline:** `What it does while you rest.`

1. **Inflammation Support** — *Turmeric, ginger, and curcumin work synergistically.*
2. **Deep Recovery** — *8 medicinal mushrooms — reishi, chaga, lion's mane and more — support cellular repair.*
3. **Joint & Skin** — *Bovine collagen for connective tissue and skin elasticity.*
4. **Gut Soothing** — *Warming spices and fermented compounds calm the digestive tract.*
5. **Sleep Support** — *Reishi and adaptogens help quiet the nervous system before bed.*
6. **Pure Comfort** — *Tastes like a chai-spiced golden milk. Pure ritual.*

**How to use:**
1. **Scoop** — *One tablespoon into your favorite mug.*
2. **Steam** — *Warm 6–8 oz of milk (oat, whole, almond — your call). Stir or froth.*
3. **Sip** — *Best as an evening wind-down. Excellent iced in summer.*

**FAQ specific to Golden Latte:**
- Does it have caffeine? *No — it's deliberately caffeine-free for evening or recovery use.*
- Can I drink it in the morning? *Yes, especially if you don't tolerate caffeine.*
- Can I drink Golden Latte AND Awaken Brew? *Yes — they're built as a complete system. Awaken in the morning, Golden Latte at night. The Ritual Bundle saves 20%.*

---

# 4. COLLECTION PAGE — SHOP

**URL:** `/collections/all`
**Template file:** `templates/collection.json`

## Layout:

**Hero band** at top:
- Eyebrow: `THE COLLECTION`
- Headline: `Two elixirs. One complete ritual.`
- Subhead: *Awaken in the morning. Restore at night. Save when you take both.*

**Filter/sort bar** (Dawn default, styled to match brand).

**Product grid** — 3 cards on desktop, 1 on mobile:

1. Awaken Brew — `$50` (subscribe `$42`)
2. Golden Latte — `$50` (subscribe `$42`)
3. Ritual Bundle — `$80` (save 20%, both products)

Each card: image, name, tag (`FLAGSHIP` / `FAN FAVOURITE` / `BEST VALUE`), star rating, price, hover-reveals "Add to cart" quick-buy button.

**Below grid — Bundle CTA band:**
- Headline: `Save 20% when you take both.`
- Body: *The Ritual Bundle gives you Awaken Brew for your mornings and Golden Latte for your nights — at 20% off forever.*
- CTA: `Shop the Ritual Bundle →` → `/collections/bundles`

**Below that — reviews aggregate band:**
- `★★★★★ 4.9 average across 500+ reviews`
- 3 short pull-quotes
- Link: `Read all reviews →`

---

# 5. OUR FORMULA

**URL:** `/pages/our-formula`
**Template file:** `templates/page.our-formula.json`

This is your credibility close-page. Skeptics come here to be convinced. Build trust through specificity.

**Section order:**
1. Hero
2. The Method (4 pillars expanded)
3. Spagyric Extraction explainer
4. Fermentation explainer
5. Sourcing & Testing
6. Full ingredient list (all 50+, organized by category)
7. What's NOT in it
8. Formulator quote (Compton Rom)
9. CTA to shop

## 5.1 Hero
- Eyebrow: `THE FORMULA`
- Headline: `Every ingredient earns its place.`
- Subhead: *50+ whole-plant compounds. Spagyric-fermented. Microbiologist-formulated. Built on six ancient systems and one obsession with absorption.*

## 5.2 The Method (Expanded)

Four sections, each with eyebrow + headline + 2–3 paragraphs of body. Image accompanying each.

**5.2.1 Spagyric Extraction**

*Spagyric is alchemy's word for "separate and recombine." It's a three-step process that captures the full spectrum of a plant — not just the showy compounds.*

*Step one separates the plant's volatile oils. Step two ferments and distills what remains, releasing water-soluble actives. Step three calcines the remaining mineral salts. All three are recombined into a single extract that contains the entire plant — body, soul, and spirit, in alchemical terms. Bioavailable plant chemistry, in scientific terms.*

*Most supplements use one extraction method and capture maybe 30% of a plant's compounds. Spagyric captures upwards of 90%. That's the difference between a fragment and a whole.*

**5.2.2 Fermentation**

*Fermentation is biology's pre-digestion. It breaks down cellular walls, releases bound compounds, and produces postbiotics — the metabolic byproducts that nourish your gut microbiome directly.*

*Every fermented ingredient in Spellbinder is more bioavailable than its raw counterpart. Your body recognizes it. Your gut welcomes it. Nothing is wasted.*

**5.2.3 Sourcing**

*Clean soil produces clean ingredients. Every botanical in Spellbinder is sourced organic, biodynamic, or wildcrafted — never sprayed, never synthetic. Our medicinal mushrooms are grown on whole-food substrates (not grain), so what you get is fruiting body, not filler.*

*We test every batch. Heavy metals. Microbiology. Active compound concentration. If a batch doesn't meet spec, it doesn't ship.*

**5.2.4 Bioavailability**

*An ingredient your body can't absorb might as well not be in the bottle. Every formulation choice — extraction method, particle size, compound pairings — is made to maximize what gets into your bloodstream.*

*Black pepper extract for piperine. Turmeric paired with healthy fats. Fermented adaptogens for gut absorption. Synergy isn't decoration — it's design.*

## 5.3 Sourcing & Testing
Quick-scan trust block:

- ✓ Organic & biodynamic where available
- ✓ Wildcrafted from native ecosystems
- ✓ Mushroom fruiting bodies, never mycelium-on-grain
- ✓ Third-party tested for heavy metals & microbiology
- ✓ cGMP-certified facility
- ✓ Made in USA

## 5.4 Full Ingredient List

All six categories from homepage, but expanded — each ingredient gets a one-sentence "what it does" note. Example for the first one:

**Adaptogenic Intelligence**
- *Ashwagandha — root that helps regulate cortisol and stress response*
- *Reishi — "queen of mushrooms," supports immune balance and calm*
- *Astragalus — Chinese tonic herb for energy and immune resilience*
- *Cordyceps — endurance, oxygen utilization, athletic performance*
- *Siberian Ginseng — adaptogen for stamina and cognitive function*
- *Ginseng — classic energy and longevity tonic*
- *Epimedium (Yin Yang Huo) — traditional vitality and circulation herb*
- *Eucommia Bark — kidney and adrenal support*
- *He Shou Wu — longevity, hair, and connective tissue*
- *Schisandra — five-flavor berry for liver and stress adaptation*

(Repeat structure for all 6 categories. ~50–60 short ingredient notes total.)

## 5.5 What's NOT in It
**Headline:** `What we leave out matters too.`

- ✗ No proprietary blends
- ✗ No artificial sweeteners
- ✗ No seed oils
- ✗ No gum fillers (xanthan, guar, etc.)
- ✗ No synthetic vitamins
- ✗ No mycelium-on-grain mushroom extracts
- ✗ No "natural flavors" hiding chemistry
- ✗ No GMOs

## 5.6 Formulator Quote
Pull-quote band. Compton Rom photo + quote.

> *"Most supplements ask one question: how do I get a compound out of this plant? I asked a different one: how do I get the whole plant into the body, the way nature intended? Everything in Spellbinder follows from that."*
> — **Compton Rom**, Microbiologist & Founder

## 5.7 CTA
- Headline: `Ready to feel the difference?`
- Buttons: `Shop Awaken Brew →` and `Shop Golden Latte →` and `Save 20% on the Bundle →`

---

# 6. ABOUT

**URL:** `/pages/about`
**Template file:** `templates/page.about.json`

Optimized for first-time buyer trust. Story-driven. Compton Rom is the protagonist.

**Section order:**
1. Hero
2. The Origin
3. Compton's Story
4. Our Principles
5. The Promise
6. Press / Credentials (if any)
7. CTA

## 6.1 Hero
- Eyebrow: `OUR STORY`
- Headline: `Built where ancient alchemy meets modern science.`
- Subhead: *Spellbinder began with a microbiologist asking a simple question: what does the body actually need to thrive?*

Image: Compton Rom in lab/kitchen/foraging — something that conveys both science and nature.

## 6.2 The Origin

**Headline:** `A different kind of morning ritual.`

*Modern life depletes us in ways our ancestors never imagined. Cortisol-spiking coffee on an empty stomach. Soil stripped of minerals. Foods engineered for shelf life, not vitality. Most of what's marketed as "wellness" is just another form of the same shortcut economy.*

*Spellbinder was built as the alternative. Not another supplement. Not another energy drink. A complete morning ritual — formulated to do what coffee, multivitamins, and adaptogen powders only pretend to do, all in a single cup that actually tastes good.*

## 6.3 Compton's Story

**Headline:** `Meet Compton Rom.`

*Compton spent years at the crossroads of two traditions that rarely speak to each other: Eastern herbalism, with its 3,000-year track record of using whole plants for whole-body health, and Western biochemistry, with its rigorous understanding of how compounds actually work in the body.*

*He saw what each tradition got right — and where each fell short. Eastern formulas often lacked dosing precision. Western supplements often missed the synergistic intelligence of how ingredients work together. So he built a process that captures both: spagyric extraction for full-spectrum plant chemistry, fermentation for bioavailability, and synergistic formulation guided by both ancient texts and modern lab work.*

*Spellbinder is the result. Not a compromise between the two worlds — a bridge between them.*

[Image of Compton in his element — formulating, foraging, working with ingredients]

## 6.4 Our Principles

Three-column layout.

1. **Whole Plant. Whole Body.** — *We don't isolate. We don't fragment. We use the full spectrum of every botanical we source.*
2. **Bioavailability First.** — *If your body can't absorb it, it doesn't belong in the formula.*
3. **Tradition + Evidence.** — *Every ingredient earns its place by passing both tests: ancient use and modern science.*

## 6.5 The Promise

**Headline:** `What you'll never find in a Spellbinder cup.`

Reuse the "What's NOT in it" list from Our Formula page.

## 6.6 Press / Credentials

If you have any: a row of logos (publications, podcasts, awards). If not, a row of certifications (USDA Organic, cGMP, third-party tested icons).

## 6.7 CTA
- Headline: `Begin your ritual.`
- Subhead: *Try Awaken Brew risk-free for 30 days. If you don't feel the difference, we'll refund your first order.*
- CTA: `Shop the morning ritual →` → `/products/awaken-brew`

---

# 7. FAQ PAGE

**URL:** `/pages/faq`
**Template file:** `templates/page.faq.json`

Organized by category with anchor links at top. Mobile: full-width accordion.

**Categories:**
1. Products & Formulation
2. Taste & Preparation
3. Results & Usage
4. Subscriptions
5. Shipping & Returns
6. Health & Safety

## 7.1 Products & Formulation

**Q: What's the difference between Awaken Brew and Golden Latte?**
*Awaken Brew is your morning ritual — naturally caffeinated by ancient teas, formulated for sustained energy and cognitive clarity. Golden Latte is caffeine-free and built for recovery — turmeric, ginger, mushrooms, and collagen for inflammation, gut health, and evening wind-down. Many customers take both: Awaken in the morning, Golden Latte at night.*

**Q: What is spagyric extraction?**
*An ancient alchemical process that captures the full spectrum of a plant — water-soluble compounds, oil-soluble compounds, and mineral salts — recombined into a single, fully bioavailable extract. Most supplements use one extraction method and capture about 30% of the plant. Spagyric captures upwards of 90%.*

**Q: Are the mushrooms fruiting bodies or mycelium?**
*Fruiting body only. Never mycelium-on-grain. Fruiting bodies contain the active beta-glucans and triterpenes; mycelium-on-grain is mostly starch filler.*

**Q: Are your products organic?**
*Every botanical is sourced organic, biodynamic, or wildcrafted wherever possible. We test every batch for heavy metals, microbiology, and active compound concentration.*

**Q: Where are your products made?**
*Made in the USA in a cGMP-certified facility. Third-party tested. Every batch is documented.*

## 7.2 Taste & Preparation

**Q: How does Awaken Brew taste?**
*Earthy, rich, slightly malty — like a sophisticated tea with depth. Most people drink it with a splash of oat or whole milk. Excellent on its own, even better frothed.*

**Q: How does Golden Latte taste?**
*Like a chai-spiced golden milk. Warming, lightly sweet from the spices, deeply comforting. Tastes good with any milk you prefer.*

**Q: Can I sweeten it?**
*Yes. Honey, maple syrup, monk fruit, or a date all work beautifully. We leave sweetening to you so the formula stays clean.*

**Q: Can I drink it iced?**
*Yes. Dissolve the powder in 2 oz hot water first, then pour over ice and milk.*

**Q: Can I blend it with coffee?**
*You can — but you don't need to. Awaken Brew is built to replace coffee with sustained, crash-free energy.*

## 7.3 Results & Usage

**Q: When will I notice results?**
*Most customers report sustained energy and clearer focus within the first week. Deeper benefits — gut health, cellular renewal, hormonal balance — compound over 30–90 days of daily use.*

**Q: How much should I take?**
*One tablespoon (≈8g) per day. Most people take it in the morning. Golden Latte can be taken any time, often in the evening.*

**Q: Can I take both products in one day?**
*Yes — they're designed as a complete system. Awaken in the morning, Golden Latte at night.*

**Q: Will it replace my coffee?**
*Yes, and without the crash. Naturally caffeinated by yerba mate, puerh, and oolong — sustained energy without cortisol spikes or afternoon slumps.*

**Q: How much caffeine does Awaken Brew have?**
*About 60–80mg per serving — roughly half a cup of coffee. Smooth, sustained energy from ancient teas, not synthetic caffeine.*

**Q: Does Golden Latte have caffeine?**
*No. Deliberately caffeine-free for evening or recovery use.*

## 7.4 Subscriptions

**Q: How does the subscription work?**
*Pick your delivery frequency (most choose every 30 days). You save 16% on every order, get free shipping, and can skip, pause, or cancel anytime from your account.*

**Q: Can I cancel anytime?**
*Yes. No fees, no friction. Cancel from your account or email us.*

**Q: Can I change my delivery frequency?**
*Yes. Edit your subscription anytime from your account.*

**Q: When am I charged?**
*The day each subscription order ships. We email you 3 days before to remind you and give you a chance to skip if needed.*

## 7.5 Shipping & Returns

**Q: How long does shipping take?**
*Orders ship within 1–3 business days. US delivery typically arrives in 3–7 business days.*

**Q: Do you offer free shipping?**
*Free shipping on US orders over $75 and on all subscription orders.*

**Q: Do you ship internationally?**
*Currently US only — we're working on expanding.*

**Q: What's your return policy?**
*30-day money-back guarantee on your first order. If you don't love it, we refund you in full. No return shipping required.*

## 7.6 Health & Safety

**Q: Is it safe to take every day?**
*Yes. Every ingredient is food-grade and dosed for sustained daily use.*

**Q: Is it safe during pregnancy or while nursing?**
*Some ingredients (adaptogens, certain mushrooms) aren't recommended during pregnancy or nursing. Please consult your physician before use.*

**Q: Can I take it with medications?**
*Some adaptogens and herbs can interact with medications (especially blood thinners, immunosuppressants, and SSRIs). Please consult your physician if you're on any medication.*

**Q: Are there any allergens?**
*Awaken Brew and Golden Latte both contain bovine collagen. They are gluten-free, dairy-free, and contain no soy or nuts. See full ingredient list on each product page.*

**Q: I have a question that's not here. How do I reach you?**
*Email hello@shopspellbinder.com or use the contact form. We typically reply within 24 hours.*

---

# 8. JOURNAL (Blog Index)

**URL:** `/blogs/journal`
**Template file:** `templates/blog.json`

## Layout:

**Hero band:**
- Eyebrow: `THE JOURNAL`
- Headline: `Field notes on biology, ritual, and the slow work of feeling well.`
- Subhead: *Essays from Compton Rom and the Spellbinder team on the science and soul of daily wellness.*

**Featured post** (most recent or pinned): full-width card, large image, title, excerpt, "Read more" CTA.

**Post grid:** 3 columns desktop, 1 mobile. Each card: image, category tag, title, date, short excerpt.

**Categories** (filter pills above grid):
- The Science
- Ancient Wisdom
- The Ritual
- Compton's Notes

**Below grid:** Email capture band — *"Get new essays in your inbox. Plus 10% off your first order."*

**Individual post template** (`templates/article.json`): standard editorial layout. Large hero image, title, byline (Compton Rom or team), date, body. Sticky table-of-contents on desktop. Related posts below. CTA band at bottom: *"Ready to begin? Shop Awaken Brew →"*

---

# 9. CONTACT

**URL:** `/pages/contact`
**Template file:** `templates/page.contact.json`

Short, warm, conversion-conscious page.

## Layout:

- Eyebrow: `GET IN TOUCH`
- Headline: `We're here. Tell us how we can help.`
- Subhead: *Real humans answer every email — usually within 24 hours.*

**Two-column:**

**Left — Contact form:**
- Name
- Email
- Order # (optional)
- What can we help with? (dropdown: Order question / Product question / Subscription / Other)
- Message
- Button: `Send message`

**Right — Quick links:**
- 📧 **Email us:** hello@shopspellbinder.com
- ⏰ **Reply time:** Within 24 hours, Mon–Fri
- 📦 **Shipping question?** [See shipping policy →]
- ↩️ **Return question?** [See returns policy →]
- ❓ **Common questions:** [Visit FAQ →]

**Below:** Brief reassurance band — *"We're a small team obsessed with this work. Your question matters."*

---

# 10. SHIPPING

**URL:** `/pages/shipping`
**Template file:** `templates/page.policy.json` (shared with returns)

## Layout:

- Eyebrow: `SHIPPING`
- Headline: `Fast, free, and tracked.`

**Three-column quick facts:**
- 🚚 **Free shipping** on US orders over $75 and all subscriptions
- 📦 **Ships in 1–3 business days** from our US fulfillment partner
- 📍 **Delivered in 3–7 business days** via USPS or UPS

**Detailed sections (accordion):**

1. **Where do you ship?** *Currently US only. We're working on expanding to Canada and the UK.*
2. **How much does shipping cost?** *Free over $75 and on all subscriptions. Otherwise $6.95 flat rate within the contiguous US. Alaska & Hawaii: $14.95.*
3. **How long does it take?** *Orders ship within 1–3 business days. Delivery typically takes another 3–7 days. You'll get tracking by email.*
4. **Can I track my order?** *Yes. Tracking info is emailed when your order ships.*
5. **What if my package is lost or damaged?** *Email hello@shopspellbinder.com with your order number. We'll make it right.*

**CTA band at bottom:**
- *Have another question? [Contact us →]*

---

# 11. RETURNS

**URL:** `/pages/returns`
**Template file:** `templates/page.policy.json`

## Layout:

- Eyebrow: `RETURNS`
- Headline: `30-day money-back guarantee.`
- Subhead: *If you don't love it, we'll make it right. No questions, no return shipping required.*

**Three-step explainer:**
1. **Email us** within 30 days of receiving your first order at hello@shopspellbinder.com
2. **No need to ship anything back.** We trust you.
3. **Get refunded** to your original payment method within 5–7 business days.

**Detailed sections (accordion):**

1. **Who qualifies?** *Every first-time customer. We want you to try Spellbinder risk-free.*
2. **How do I start a return?** *Email hello@shopspellbinder.com with your order number and a quick note. We'll handle the rest.*
3. **What about subscriptions?** *Cancel or skip anytime from your account. No fees, no friction.*
4. **What if my order arrives damaged?** *Email us with a photo. We'll send a replacement at no charge.*
5. **What if I want to exchange products?** *Just let us know — we'll handle the swap.*

**CTA band:**
- *Ready to begin? [Shop Awaken Brew →]*

---

# 12. CART PAGE

**URL:** `/cart`
**Template file:** `templates/cart.json`
**Section file:** `sections/sb-cart.liquid`

## Layout:

**Top: Free shipping progress bar**
- If under $75: `You're $XX away from free shipping. 🚚`
- If over $75: `🎉 You've unlocked free shipping!`

**Cart items** (Dawn default structure, restyled to brand):
- Image, name, variant (subscription / one-time), quantity stepper, price, remove

**Recommended upsell band** (above checkout):
- Headline: `Complete your ritual — save 20%`
- If only Awaken in cart: suggest Golden Latte
- If only Golden in cart: suggest Awaken Brew
- If both in cart: suggest the Bundle for greater savings
- One-click "Add to cart" buttons

**Trust strip** (above checkout button):
- ✓ 30-day money-back guarantee
- ✓ Free shipping over $75
- ✓ Secure checkout

**Order summary:**
- Subtotal
- Shipping (calculated at checkout)
- **Total**
- Discount code field (collapsed by default)

**Checkout button:** Primary brand color, full-width on mobile.

**Below checkout:** Payment method icons (Visa, MC, Amex, Apple Pay, Shop Pay, PayPal).

**Bottom band — risk reversal reinforcement:**
> *Not sure yet? Every first-time order is backed by our 30-day money-back guarantee. If you don't love it, we make it right.*

---

# GLOBAL NOTES FOR CLAUDE CODE

1. **Every section needs a complete `{% schema %}` block.** No hardcoded copy that should be editable.

2. **Use design tokens from `assets/spellbinder.css`.** Never hardcode colors, fonts, or spacing.

3. **Match Dawn's class naming conventions.** Use `.sb-` prefix for custom classes (e.g. `.sb-hero__title`, `.sb-product__buybox`).

4. **Mobile-first.** Every section must look excellent on mobile.

5. **Accessibility:**
   - Semantic HTML (`<section>`, `<article>`, `<nav>`)
   - One H1 per page (the hero or page title)
   - Alt text on every image
   - ARIA labels on interactive elements
   - Keyboard navigation for accordions, carousels, dropdowns

6. **Performance:**
   - Lazy-load images below the fold
   - Use Shopify's `image_url` and `image_tag` filters with `widths` and `sizes`
   - Inline critical CSS, defer the rest

7. **SEO:**
   - Every page gets a unique title tag and meta description (set in template JSON)
   - Use semantic heading hierarchy
   - Add structured data (JSON-LD) for products (Product schema) and reviews (AggregateRating)

8. **Build order:**
   1. Homepage (hero first, then trust strip, then problem, etc.)
   2. Awaken Brew product page
   3. Golden Latte product page
   4. Collection page
   5. Our Formula
   6. About
   7. FAQ
   8. Journal index + article template
   9. Contact, Shipping, Returns
   10. Cart page

   Build one section at a time. After each section, run `shopify theme dev` and confirm before moving on.

9. **Before writing any code, confirm you've read:**
   - `DESIGN_NOTES.md`
   - `assets/spellbinder.css`
   - This brief
   - The relevant Dawn template you're modifying

10. **Reviews integration:** Confirm with the user which review app they use (Judge.me / Yotpo / Loox / Stamped) and integrate the live widget where this brief specifies "reviews."

11. **Email integration:** Confirm with the user whether they use Klaviyo. If yes, all email capture forms should post to Klaviyo's API. If no, use Shopify's default customer/marketing list.

12. **Subscription integration:** Confirm which subscription app the store uses (Shopify Subscriptions, Recharge, Bold, Stay AI, etc.) and ensure the buy-box subscription toggle integrates with that app's product widget.
