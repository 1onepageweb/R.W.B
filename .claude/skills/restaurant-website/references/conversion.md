# Conversion patterns for restaurant sites

A restaurant visitor is usually hungry, on a phone, and deciding between you and two
other tabs. Median decision time is seconds. Every pattern below serves that reality.

## The one primary action

Pick exactly one per site (from the brief): **reserve**, **order online**, **call**, or
**catering inquiry**. It gets the accent color, the top-right header slot, the hero
button, and the dominant position in the sticky mobile bar. Secondary actions exist but
never compete visually.

CTA copy is specific, not generic: "Reserve a table", "Order pickup", "Book the patio" —
not "Learn more", "Get started", or "Submit". Deep-link to the real system (OpenTable,
Resy, Toast, Square, phone `tel:` link). A CTA that opens a dead form kills trust.

## Page skeleton (one-pager default)

1. **Hero (above the fold, 390px-wide test)**: name/logo, one-line positioning
   ("Wood-fired Neapolitan pizza in Five Points"), open-now status or today's hours,
   primary CTA, neighborhood or address line.
2. **Menu** — the most-visited section; put it second. Anchor-link it from the nav.
3. **Social proof** — 2–3 short real quotes with sources, star summary if genuinely held.
4. **Story / room** — one tight paragraph and imagery; personality, not a wall of text.
5. **Visit block** — map embed or static map linking to Google Maps directions, full
   NAP, complete weekly hours, parking/transit note.
6. **Footer** — socials, secondary actions (gift cards, careers, press), schema-relevant
   links.

## Menu presentation

- HTML text, always. PDFs are invisible to search, brutal on phones, and inaccessible.
- Group by course/category with clear headings; dish name, one-line description, price.
- Price alignment: keep price adjacent to the name (no dot-leader spanning full-width
  columns on mobile — it breaks). 
- Flag dietary marks (v, gf, spicy) with a small legend.
- Keep it current-looking: include a "menu changes seasonally" note if the client updates
  rarely — a stale menu is a top complaint in local reviews.

## Mobile patterns

- **Sticky bottom action bar** with 2–3 items max: primary CTA + call + directions.
  Touch targets ≥ 44px, safe-area padding on iOS.
- Hours must answer "are they open *now*?" — render today's hours prominently; the full
  week can live in the visit block.
- Phone number is always a `tel:` link; address always links to a maps app.
- Nothing critical inside a carousel; no autoplaying video with sound; no popup on load
  (email popups on first visit measurably increase bounce for restaurants).

## Trust signals

- Real reviews only, attributed ("— Google review, March 2026"). Never fabricate quotes,
  counts, or awards; fabricated proof is both unethical and a liability for the client.
- Show the room and the people if photos exist — diners are choosing an experience.
- Surface practical answers that block conversion: parking, reservations policy,
  kid-friendliness, dietary accommodation. An FAQ section here also feeds FAQ schema.

## Speed is conversion

- Hero image ≤ ~200KB (AVIF/WebP with fallback), explicit width/height to prevent layout
  shift, lazy-load everything below the fold.
- Target: interactive in under 3 seconds on a mid-range phone. Test with `webapp-testing`
  at 390px; if the menu takes more than one tap from landing, restructure.
