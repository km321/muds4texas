# MUDs 4 Texas Phase 1 — Production BUILD NOTES

Generated: 2026-09-22 (America/New_York, ET)
Source: `/workspace/melton-launch/muds4texas/website/`
Output: `/workspace/melton-launch/muds4texas/production/`

## Page list (copied)

- `index.html`
- `what-is-a-mud.html`
- `living-in-a-mud.html`
- `buying-in-a-mud.html`
- `mud-taxes.html`
- `mud-vs-pid-vs-hoa.html`
- `find-your-mud.html`
- `about.html`
- `privacy.html`
- `terms.html`
- `style-guide.html` (noindex)
- `animations/` (full folder)
- `assets/` (full folder)
- `robots.txt`, `sitemap.xml`, `.nojekyll`

### Excluded (not copied)
- `logo-options.html`
- `_shot-mud-vs.html`
- `preview-polish/`
- Exclusion check: **PASS**

## Em dash counts (U+2014 / &mdash; / numeric entities)

| Page | Em dashes |
| --- | ---: |
| `index.html` | 0 |
| `what-is-a-mud.html` | 0 |
| `living-in-a-mud.html` | 0 |
| `buying-in-a-mud.html` | 0 |
| `mud-taxes.html` | 0 |
| `mud-vs-pid-vs-hoa.html` | 0 |
| `find-your-mud.html` | 0 |
| `about.html` | 0 |
| `privacy.html` | 0 |
| `terms.html` | 0 |
| `style-guide.html` | 3 |

- Public pages total: **0** (must be 0) — **PASS**
- `style-guide.html` may retain em dashes (count=3)

## Index embed

- `index.html` embeds `animations/mud-vs-no-mud-embed.html`: **PASS**

## `.cta-row` presence

| Page | CSS defined | Markup instances |
| --- | --- | ---: |
| `index.html` | yes | 3 |
| `what-is-a-mud.html` | yes | 0 |
| `living-in-a-mud.html` | yes | 1 |
| `buying-in-a-mud.html` | yes | 1 |
| `mud-taxes.html` | yes | 1 |
| `mud-vs-pid-vs-hoa.html` | yes | 0 |
| `find-your-mud.html` | yes | 0 |
| `about.html` | yes | 0 |
| `privacy.html` | yes | 0 |
| `terms.html` | yes | 0 |

- Home (`index.html`): markup present (3 instances) — **PASS**
- Interiors with `.cta-row` CSS shared chrome: all public pages define the class.
- Interiors with markup instances: `living-in-a-mud` (1), `buying-in-a-mud` (1), `mud-taxes` (1).
- Other interiors define `.cta-row` in CSS but do not currently use a `.cta-row` wrapper in body markup (buttons use other patterns). Logged as observation, not a copy redesign.

## HOLDS still present

- **About contact CONFIRM**: PRESENT
- **Find districts TBD (pending client manager)**: PRESENT
- **Harris-only tax URLs (hctax.net)**: PRESENT
- **[VIDEO:] placeholders**: PRESENT
- **Dark wordmark Option A (LOCKED in style-guide)**: PRESENT

### Detail — `[VIDEO:]` placeholders
- `index.html: [VIDEO: home / overview]`
- `what-is-a-mud.html: [VIDEO: what-is-a-mud / explainer]`
- `living-in-a-mud.html: [VIDEO: living-in-a-mud / homeowner]`
- `buying-in-a-mud.html: [VIDEO: buying-in-a-mud / guide]`
- `mud-taxes.html: [VIDEO: mud-taxes / explainer]`

### Detail — Harris-only tax URLs
- Canonical example link: `https://www.hctax.net/Property/ViewStatementReceipts`
- Appears in: `index.html`, `what-is-a-mud.html`, `living-in-a-mud.html`, `buying-in-a-mud.html`, `mud-taxes.html`, `mud-vs-pid-vs-hoa.html`, `find-your-mud.html`, `about.html`, `privacy.html`, `terms.html`, `style-guide.html`

### Detail — Find districts TBD
- Callout: “District names pending client manager” / curated rows hidden until names supplied.

### Detail — About contact CONFIRM
- Two `CONFIRM WITH CLIENT MANAGER` callouts (mission purpose + contact policy).
- Contact details still placeholder: “Contact details coming from the client manager.”

### Detail — Dark wordmark Option A
- Style guide locks Option A wordmark; footer/chrome use `assets/logo-muds4texas-on-dark.svg`.
- Style guide note: missing dark-ink horizontal wordmark for light headers (text wordmark + logo on ink chip in use).

## Melton brand scrub (public copy)

- `about.html` Melton Studios naming removed: **PASS** (web strategy/design/education copy; client manager owns contact).
- Extra public Melton chrome also removed for production consistency:
  - `living-in-a-mud.html`: “not a Melton database” → “not a third-party proprietary database”
  - `privacy.html`: stub + inbox lines de-branded (vendor/production-team wording)
- Public HTML pages now contain **0** Melton brand strings (style-guide may still mention internal process if any).

## Crawl / deploy helpers

- `robots.txt`: Allow `/`; Disallow `/style-guide.html`; Sitemap absolute URL.
- `style-guide.html`: `<meta name="robots" content="noindex, nofollow" />`
- `sitemap.xml`: 8 content pages + privacy + terms at `https://muds4texas.org/...`
- `.nojekyll`: present (empty)

## Production file tree

```
production/
├── animations/
│   ├── mud-vs-no-mud-embed.html
│   └── mud-vs-no-mud.html
├── assets/
│   ├── factsheet-infographic.png
│   ├── graphic-numbers-banner.png
│   ├── graphic-what-is-a-mud-infographic.png
│   ├── hero-muds-background.png
│   ├── homepage-numbers-banner-2500.png
│   ├── homepage-numbers-banner.png
│   ├── kids-on-playground.png
│   ├── kids-playground-2500.png
│   ├── kids-playground.png
│   ├── logo-muds4texas-on-dark.svg
│   ├── logo-muds4texas-stacked.svg
│   ├── logo-muds4texas.svg
│   ├── logo-option-a-horizontal.png
│   ├── logo-option-b-stacked.png
│   ├── logo-option-c-badge.png
│   ├── logo-white-type-1500.png
│   ├── logo-white-type-2500.png
│   ├── logo-white-type-alt.png
│   ├── logo-white-type.png
│   ├── logo.png
│   ├── muds-background-2500.png
│   ├── muds-background.png
│   ├── photo-background.png
│   ├── photo-kids-playground.png
│   └── what-is-a-mud-infographic.png
├── .nojekyll
├── about.html
├── buying-in-a-mud.html
├── find-your-mud.html
├── index.html
├── living-in-a-mud.html
├── mud-taxes.html
├── mud-vs-pid-vs-hoa.html
├── privacy.html
├── robots.txt
├── sitemap.xml
├── style-guide.html
├── terms.html
└── what-is-a-mud.html
```

## Issues / notes

- No git push performed (per brief; parent owns push).
- Em dashes: public = 0; style-guide retains some (allowed).
- Several interiors define `.cta-row` but only home + living/buying/taxes use markup wrappers; other CTAs are single buttons without the row wrapper. No redesign applied.
- HOLDS intentionally left in place for client manager follow-up.
- Residual Melton mentions found on living-in-a-mud + privacy beyond the about.html brief; scrubbed for public production consistency.
