# Launch checklist

Run top to bottom before calling a restaurant site done. Verify with `webapp-testing`
(Playwright) rather than by eyeball where possible.

## Conversion
- [ ] Primary CTA visible above the fold at 390px width and clicks through to the live
      reservation/ordering system (or `tel:` link).
- [ ] Sticky mobile bar present; all targets ≥ 44px; works with iOS safe area.
- [ ] Phone is a `tel:` link; address opens maps with correct pin.
- [ ] Today's hours are correct and prominent; full weekly hours present.
- [ ] Menu reachable in one tap from landing; renders as HTML text.
- [ ] All prices, dishes, and dietary marks confirmed against the client's real menu.
- [ ] No fabricated reviews, ratings, awards, or photos anywhere.

## Design
- [ ] Aesthetic thesis sentence exists and the page still defends it.
- [ ] Exactly one accent color for CTAs; ≤ 2 typefaces; menu body text effortlessly
      legible at 16px+.
- [ ] Screenshots taken at 390px and 1440px; no horizontal scroll, no broken layouts.
- [ ] Ran `design-critique` and addressed or consciously declined each note.

## SEO
- [ ] Title, meta description, single `h1`, semantic heading order.
- [ ] Restaurant JSON-LD present, valid, and consistent with rendered NAP + hours.
- [ ] NAP character-identical: footer, visit block, schema, GBP.
- [ ] OG/Twitter tags with real 1200×630 image; share preview checked.
- [ ] Canonical URL, `lang` attribute, favicon; sitemap/robots for multi-page sites.

## Performance & accessibility
- [ ] Hero image compressed (AVIF/WebP + fallback), dimensions set, below-fold lazy.
- [ ] No console errors; no blocking third-party scripts above the fold.
- [ ] Contrast passes WCAG AA — especially text over photography.
- [ ] Every image has meaningful alt text; keyboard can reach every action.
- [ ] Ran `accessibility-review` and fixed AA-level findings.

## Handoff
- [ ] Client confirmed: menu, prices, hours, NAP, reservation link.
- [ ] Told the client which things go stale (menu, hours, seasonal photos) and where to
      update them.
