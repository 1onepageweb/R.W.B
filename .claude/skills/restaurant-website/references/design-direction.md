# Design direction for restaurant sites

The goal: a visitor should be able to guess the cuisine, price tier, and mood from the
design alone, before reading a word. Design from the specific restaurant outward, never
from a template inward.

## Method

1. **Write the aesthetic thesis first.** One sentence, e.g. "A third-generation taqueria:
   hand-painted-sign energy, market colors, nothing corporate." Every palette, type, and
   layout decision must defend itself against this sentence.
2. **Pull the palette from the food and the room.** Sample from the actual cuisine:
   masa yellow and salsa roja for a taqueria; nori green, rice white, and lacquer black
   for sushi; burnt crust and semolina for a pizzeria; espresso and cream for a cafe.
   Use 1 dominant neutral, 1–2 brand hues, 1 accent reserved exclusively for CTAs.
3. **Type carries the vibe.** Pick one display face with genuine character for the name
   and section heads, one workhorse for menu/body text. Sources of character: humanist
   serifs for trattorias and bistros, sturdy grotesques or slab for BBQ and burgers,
   high-contrast didones for fine dining, rounded or hand-drawn faces for bakeries and
   ice cream. Menu prices and dish names must stay effortlessly legible — the display
   face never sets body text.
4. **Take one justified risk.** An oversized typographic hero instead of a photo; a menu
   set like a broadsheet; a single loud color everyone will remember. One risk, executed
   cleanly — not five.

## Price-tier calibration

- **Fast-casual / counter service**: bright, high-energy, generous type sizes, bold color
  blocking. Ordering CTA dominates.
- **Mid-range / neighborhood**: warm and personal; texture and photography of the room,
  not just plates. Reservation and directions share top billing.
- **Fine dining**: restraint — abundant whitespace, refined type, muted palette, minimal
  UI chrome. But restraint is a choice made from the brief, not the automatic
  charcoal-and-gold cliché.

## Anti-template rules

- No layout decided before the thesis sentence exists.
- No stock photography posing as the restaurant's own food or room. Missing photos →
  typographic/illustrated art direction (use `canvas-design` for original hero art,
  menu ornaments, OG images).
- No dark-overlay-on-hero-photo with centered white text as a reflex. If used, justify it.
- No more than two typefaces, no default-blue links inside the designed surface.
- Photography treatment must be consistent (same warmth/crop discipline throughout).

## Imagery

- Food photography sells; use the restaurant's real photos whenever provided, cropped
  tight and served responsive (`srcset`, modern formats, correct aspect ratios).
- Alt text describes the dish ("charred octopus with romesco"), not "food image" —
  this is both accessibility and SEO.
- If the client has no photography, say so and design around it; recommend a shoot as a
  follow-up, and generate original non-photographic art in the meantime.
