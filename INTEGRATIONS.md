# Integrations

## Reviews — Judge.me

Judge.me is installed on this store. All review-related sections must use Judge.me's widget tags, not static testimonials.

**Where to use:**
- Homepage reviews carousel (`sb-reviews.liquid`)
- Product page review section
- Collection page aggregate stars
- Anywhere the brief references "★★★★★ rating" or "review count"

**Implementation:**
- Use Judge.me's official Liquid snippets and shortcodes (e.g., `<div class='jdgm-widget jdgm-review-widget'>`, `<div class='jdgm-widget jdgm-preview-badge'>`).
- For homepage carousel: use Judge.me's "Reviews Carousel" widget.
- For product pages: place the standard Judge.me review widget below the product description, and the preview badge in the buy box near the title.
- For aggregate stars: use Judge.me's All Reviews Page widget or the JSON API.
- Reference Judge.me's official Shopify documentation for current widget syntax: https://judge.me/help

**Fallback:** if a Judge.me widget can't be embedded for any reason, leave a clear `<!-- TODO: Judge.me widget here -->` comment so I can fix it later.

---

## Subscriptions — Shopify Subscriptions (free, native)

This store uses **Shopify Subscriptions**, the free official subscription app made by Shopify.

**Where to use:**
- Product pages: "Subscribe & Save" toggle in the buy box
- Cart page: subscription line items must display correctly with frequency

**Implementation:**
- Use Shopify's native `selling_plan_groups` Liquid objects (`product.selling_plan_groups`, `selling_plan.name`, `selling_plan.price_adjustments`).
- The buy box should default to the subscription option when a selling plan exists on the product. One-time purchase should be the second option.
- Use the `selling_plan_id` form input so the cart correctly captures the subscription choice.
- If a product has no selling plan attached yet, the buy box should still render — just hide the subscription toggle and show only "One-time purchase" pricing.

**Reference:** https://shopify.dev/docs/api/liquid/objects/selling_plan

---

## Email Capture — Klaviyo (coming soon, placeholder for now)

Klaviyo is **not yet installed**. Build all email capture forms now with a clean structure that can be swapped to Klaviyo later in one place.

**Where to use:**
- Homepage email capture section (`sb-email-capture.liquid`)
- Footer newsletter signup
- Journal page bottom CTA
- Any other "Get 10% off" capture mentioned in the brief

**Implementation for now:**
- Use Shopify's default `{% form 'customer' %}` newsletter signup so emails are captured into Shopify customers.
- Wrap the form action endpoint in a single Liquid variable or snippet (e.g., `{% render 'email-form' %}`) so when Klaviyo is added, only one snippet needs updating to point at Klaviyo's API.
- Mark the snippet clearly with a `{% comment %} TODO: swap to Klaviyo when installed {% endcomment %}` note.

---

## What to do if you're unsure

If any integration question comes up that isn't covered here, leave a `<!-- TODO -->` comment in the Liquid file and flag it in your summary at the end of the page. Don't guess at integration details — flag and continue.
