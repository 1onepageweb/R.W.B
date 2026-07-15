---
name: restaurant-website
description: End-to-end playbook for building high-converting, uniquely designed, SEO-optimized restaurant websites. Use whenever the task involves a website for a restaurant, cafe, bar, bakery, food truck, pizzeria, or any food-service business — new builds, redesigns, menu pages, reservation/order flows, or local SEO for a restaurant. Trigger on "restaurant website", "cafe site", "menu page", "online ordering", "reservations", "food truck site", or a named food business.
argument-hint: "<restaurant name, cuisine, city> [goal: reservations | orders | catering]"
---

# Restaurant Website Skill

Build a restaurant website that does three jobs, in priority order:
1. **Convert** — a hungry visitor on a phone reaches the menu, the address, or the reserve/order action in one tap.
2. **Rank** — the site wins local search ("<cuisine> near me", "<cuisine> <city>") through structured data and local SEO.
3. **Distinguish** — the design tastes like this restaurant, not like a template.

Work through the five phases below. Each phase names the companion skill to lean on
and the reference file with the niche-specific details.

## Phase 0 — Brief

Before designing anything, establish (ask, or research the business if given a name):
- Cuisine, price tier, neighborhood/city, and the dining vibe (fast-casual? date-night? family?).
- **The one primary conversion goal**: reservations, online orders, phone calls, or catering inquiries. Everything on the page ranks below this action.
- Reservation/ordering platforms already in use (OpenTable, Resy, Toast, Square, DoorDash, phone-only) — the CTA must deep-link to the real system, never a dead button.
- Hours, address(es), phone, and whether a Google Business Profile exists. The site must match it exactly (see NAP rules in `references/local-seo.md`).
- **Asset intake is mandatory, not optional**: logo/mascot, food photography, and real reviews are the three things that make the site feel like *this* restaurant. Hunt for them before designing. Client-provided screenshots of their Google/Yelp gallery are a valid source — crop, straighten, and optimize the best tiles (trim any app UI from the edges). Never fabricate photos of dishes; only when nothing exists, use non-photographic art direction (color, typography, illustration via `canvas-design`) and flag a photo shoot as follow-up.
- **Link verification is a hard gate.** Include an external link (ordering, delivery, reviews, socials) only after confirming it points to THIS business: the URL slug or the fetched page must match the business name AND address. A search-result title is not verification — similarly named restaurants are common in the same city. If a link cannot be verified, leave it out and list it as a question for the client; a dead button is bad, but a button that opens a competitor is fatal to trust.

## Phase 1 — Design direction (unique aesthetic)

Use the `frontend-design` skill for the discipline; apply `references/design-direction.md`
for the restaurant-specific method. Non-negotiables:
- Derive palette and typography from the cuisine, the room, and the price tier — not from a "restaurant template" memory. State the aesthetic thesis in one sentence before writing CSS.
- Banned defaults: generic hero + three-column features layout, Lorem ipsum menu items, stock-photo look, and the reflexive dark-charcoal-plus-gold "upscale" cliché unless the brief genuinely earns it.
- One real aesthetic risk per site (typographic scale, unusual menu layout, distinctive color) that you can justify from the brief.

## Phase 2 — Structure & copy (conversion)

Apply `references/conversion.md` for layout and CTA rules; use the `content-creation`
skill for voice and headline craft. The skeleton that converts:
- **Above the fold (mobile-first)**: restaurant name, one-line positioning, open-now status or hours, and the primary CTA. Address or neighborhood visible without scrolling.
- **Menu is content, not a PDF.** Render the menu as HTML text (crawlable, accessible, translatable). A downloadable PDF may exist *in addition*, never instead.
- Sticky mobile action bar: call, directions, reserve/order.
- Social proof near the CTA, sourced from real reviews only — never invent quotes, ratings, or press mentions. Build the reviews module even with one verified quote: real quote(s) with platform attribution + live links to the business's Google/Yelp pages; more quotes get pulled with the owner at final. Match dish photos to menu items only when the dish is unambiguous — a mislabeled photo is as damaging as a wrong link.

## Phase 3 — Build

Use `web-artifacts-builder` for multi-page/React builds, or hand-rolled semantic HTML/CSS
for one-pagers (often the better choice: faster, simpler, easier to rank). Either way:
- Semantic landmarks (`header/nav/main/footer`), one `h1`, menu sections as `h2`/`h3` with real text.
- Performance budget: hero image optimized and compressed, fonts ≤ 2 families with `font-display: swap`, no blocking scripts. Slow sites lose both rankings and dinner rushes.
- Every external action (reserve, order, maps, socials) is a real, working link.

## Phase 4 — SEO & structured data

Apply `references/local-seo.md` in full — it contains ready-to-adapt JSON-LD for
`Restaurant`, `Menu`, and FAQ schema, plus title/meta patterns and GBP alignment rules.
Minimum bar before calling the site done:
- `Restaurant` JSON-LD with NAP, `geo`, `openingHoursSpecification`, `servesCuisine`, `priceRange`, `menu` URL, and `acceptsReservations`.
- Title/meta description following the local pattern: `<Name> — <Cuisine> in <Neighborhood, City>`.
- Open Graph + Twitter card tags with a real image, so shares look appetizing.

## Phase 5 — Verify

- `webapp-testing`: load the site with Playwright, screenshot mobile (390px) and desktop, click every CTA, check the console for errors.
- Validate JSON-LD (paste into a validator or check structure against `references/local-seo.md`).
- `accessibility-review`: contrast (menus over photography are the usual failure), touch targets on the sticky bar, alt text on food imagery.
- `design-critique` as a final pass, then run through `references/launch-checklist.md`.

## Reference files

- `references/design-direction.md` — cuisine-to-aesthetic mapping, typography and palette method, anti-template rules.
- `references/conversion.md` — page skeleton, CTA hierarchy, menu presentation, mobile patterns, trust signals.
- `references/local-seo.md` — JSON-LD templates, meta patterns, NAP/GBP rules, local keyword strategy.
- `references/launch-checklist.md` — the final gate before handoff or deploy.
