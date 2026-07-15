# Local SEO & structured data for restaurants

Restaurants win or lose in local search and the map pack. The site's job is to give
Google unambiguous, consistent signals and to match the Google Business Profile (GBP)
exactly.

## NAP consistency (non-negotiable)

Name, Address, Phone must be **character-identical** across the site footer, the visit
block, the JSON-LD, and the GBP listing ("123 N Main St" vs "123 North Main Street" in
different places dilutes the signal). Confirm the canonical form with the client before
writing it anywhere.

## Title / meta patterns

- Title (≤ 60 chars): `<Name> | <Cuisine> Restaurant in <Neighborhood>, <City>`
- Meta description (≤ 155 chars): what + where + hook + action, e.g.
  `Wood-fired Neapolitan pizza in Five Points, Denver. Housemade dough, natural wine, patio seating. Reserve a table or order pickup.`
- One `h1` containing the name and, ideally, cuisine + place.
- Local keyword strategy: target `<cuisine> <neighborhood>`, `<cuisine> <city>`,
  `<dish> near me` variants naturally in headings and menu copy — never keyword-stuff.
  Each physical location gets its own page with its own NAP and schema.

## Restaurant JSON-LD (adapt every field; delete what isn't true)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Restaurant",
  "name": "Fiamma",
  "image": "https://example.com/img/og-hero.jpg",
  "url": "https://example.com",
  "telephone": "+1-303-555-0142",
  "priceRange": "$$",
  "servesCuisine": ["Neapolitan", "Pizza", "Italian"],
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 N Main St",
    "addressLocality": "Denver",
    "addressRegion": "CO",
    "postalCode": "80205",
    "addressCountry": "US"
  },
  "geo": { "@type": "GeoCoordinates", "latitude": 39.7561, "longitude": -104.9799 },
  "openingHoursSpecification": [
    { "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Tuesday","Wednesday","Thursday","Sunday"],
      "opens": "17:00", "closes": "22:00" },
    { "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Friday","Saturday"],
      "opens": "17:00", "closes": "23:00" }
  ],
  "menu": "https://example.com/#menu",
  "acceptsReservations": "https://www.opentable.com/r/fiamma",
  "hasMap": "https://maps.google.com/?cid=...",
  "sameAs": ["https://www.instagram.com/fiamma"]
}
</script>
```

Rules:
- `acceptsReservations`: URL of the booking system, `"True"` for phone-only, omit if none.
- Only include `aggregateRating` if ratings are collected and displayed on the page
  itself; never copy Google's own rating into schema (against their guidelines).
- Hours in schema must mirror the rendered hours and GBP.

## Menu schema (optional, strengthens dish-level queries)

```json
{
  "@type": "Menu",
  "hasMenuSection": [{
    "@type": "MenuSection",
    "name": "Pizze Rosse",
    "hasMenuItem": [{
      "@type": "MenuItem",
      "name": "Margherita",
      "description": "San Marzano, fior di latte, basil",
      "offers": { "@type": "Offer", "price": "16.00", "priceCurrency": "USD" }
    }]
  }]
}
```

Attach via the `hasMenu` property on the Restaurant node, or as a separate node on the
menu page. Only worth maintaining if the client will keep prices current — wrong schema
prices are worse than none.

## FAQ schema

If the page has a real FAQ section (parking, dietary, reservations policy), mirror it
with `FAQPage` schema. Content must exist visibly on the page.

## Technical checklist

- `<html lang>`, canonical URL, mobile viewport meta.
- Open Graph: `og:title`, `og:description`, `og:image` (1200×630, appetizing, real),
  `og:type=website`; Twitter `summary_large_image`.
- `sitemap.xml` + `robots.txt` for multi-page sites; favicon and apple-touch-icon.
- Image `alt` text names dishes and spaces (SEO + accessibility double duty).
- No render-blocking third-party widgets above the fold; reservation widgets load
  deferred or on interaction.

## Google Business Profile alignment

The site supports GBP, not the reverse:
- Link GBP → site (primary URL) and site → GBP map/directions.
- Categories, hours, menu URL, and reservation URL on GBP should point at the site's
  canonical equivalents.
- Encourage the client to keep photos and posts flowing on GBP; the site's FAQ answers
  should match what staff tell callers.
