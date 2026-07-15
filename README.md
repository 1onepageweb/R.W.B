# R.W.B — Restaurant Website Builder Skills

This repository is equipped with a curated set of Claude skills (in `.claude/skills/`)
for building high-converting, uniquely designed, SEO-optimized restaurant websites.

All skills were downloaded from Anthropic's public GitHub repositories:

- [anthropics/skills](https://github.com/anthropics/skills)
- [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins)

## Installed skills

### Restaurant niche (custom)

| Skill | Purpose |
|---|---|
| `restaurant-website` | Custom end-to-end playbook for restaurant sites: five-phase workflow (brief → design → conversion copy → build → SEO → verify) with reference files for cuisine-driven design direction, conversion patterns (CTA hierarchy, menu presentation, sticky mobile bar), local SEO with ready-to-adapt Restaurant/Menu/FAQ JSON-LD, and a launch checklist. Orchestrates all the skills below. |

### Design & aesthetics

| Skill | Purpose |
|---|---|
| `frontend-design` | Distinctive, non-templated visual design direction — palette, typography, layout. The antidote to the "generic AI website" look. |
| `theme-factory` | 10 professional color/font themes, plus on-the-fly theme generation, for styling landing pages and other artifacts. |
| `canvas-design` | Original static visual art (PNG/PDF) — hero graphics, posters, menu art, social/OG images. |
| `design-critique` | Structured design feedback on usability, hierarchy, and consistency before shipping. |

### Build & test

| Skill | Purpose |
|---|---|
| `web-artifacts-builder` | Scaffolds and bundles complex multi-component sites with React, Tailwind CSS, and shadcn/ui. |
| `webapp-testing` | Playwright-based testing of local sites — verify functionality, capture screenshots, read browser logs. |

### SEO, copy & conversion

| Skill | Purpose |
|---|---|
| `seo-audit` | Keyword research, on-page analysis, content gaps, technical checks, competitor comparison, prioritized action plan. |
| `content-creation` | Channel-specific marketing copy — landing pages, SEO-optimized text, headline options, calls to action. |
| `accessibility-review` | WCAG 2.1 AA audit — contrast, keyboard navigation, touch targets, screen-reader behavior. |

## Typical restaurant-site workflow

1. **Design direction** — `frontend-design` + `theme-factory` to establish a unique visual identity for the restaurant's cuisine and vibe.
2. **Copy** — `content-creation` for hero copy, menu descriptions, CTAs (reserve, order, call).
3. **Build** — `web-artifacts-builder` for the site itself; `canvas-design` for custom imagery.
4. **Optimize** — `seo-audit` for local-search keywords, structured data, and content gaps.
5. **Verify** — `webapp-testing` for functional checks; `accessibility-review` and `design-critique` for final polish.

Licenses: see `.claude/skills/THIRD_PARTY_NOTICES.md`, per-skill `LICENSE.txt` files,
and `.claude/skills/LICENSE-knowledge-work-plugins`.
