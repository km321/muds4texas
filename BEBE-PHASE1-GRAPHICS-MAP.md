# Bebe Phase 1 Graphics Map — muds4texas.org

**Author:** Bebe (Designer / UX)  
**For:** Timmy (implement)  
**Date:** 2026-09-22 (ET)  
**Ask:** Supporting graphics / HTML SVGs so concepts read faster — engaging, not stock-heavy.  
**Constraint:** Design locked from engage+mobile pass. Graphics support layout; **no redesign**.  
**Preview:** https://km321.github.io/muds4texas/ (noindex)

---

## Dials (locked)

| Dial | Value | Graphics implication |
|------|------:|----------------------|
| **VARIANCE** | **6** | Distinct civic diagrams OK; not experimental illustration worlds |
| **MOTION** | **2** | Hover/focus opacity or 1px stroke only; respect `prefers-reduced-motion`; no scroll theatre |
| **DENSITY** | **5** | One clear diagram per concept; don’t stack three SVGs in one fold |

**Palette (capitol-stone — use CSS tokens / current hex):**

| Token | Hex | Diagram role |
|-------|-----|--------------|
| ground | `#E6E9E4` | Soft fills behind schematic |
| paper / surface | `#F7F8F6` / `#FCFDFB` | Panel fills |
| ink | `#0B1726` | Primary stroke + labels |
| muted | `#4A5560` | Secondary labels |
| line | `#C5CBC4` | Hairlines, dividers |
| civic | `#1B4F72` | Structure / authority nodes |
| civic-dark | `#143A55` | Emphasis nodes on light |
| clay | `#C45C26` | Accent / “attention” node only (1–2 per diagram) |
| mesquite | `#2F4F44` | Optional nature/utility secondary |
| caution | `#7A5B12` | Disclaimer / “not advice” cue only |

**Type in diagrams:** Source Sans 3 for labels (11–13px); Newsreader only if a diagram title sits outside the SVG in HTML.

---

## Craft rules (Timmy implement checklist)

1. **Inline SVG** (or small partials in `website/assets/diagrams/*.svg` inlined at build) — themeable, crisp at 320, no PNG diagram replacements unless noted.
2. **Education-only** — no urgency badges, no lead magnets, no fake “savings” charts, no invented stats. Cite or omit numbers.
3. **Lucide** = UI chrome only (nav, external-link, chevrons). **Concept diagrams = custom SVG**, not Lucide-in-a-circle card OS.
4. **No eyebrow kickers** labeling diagrams; caption below or `figcaption` in plain sentence.
5. **A11y:** `<figure>` + `<figcaption>`; decorative `aria-hidden="true"` only when adjacent text fully explains; otherwise title + text alternative in caption.
6. **Mobile:** max-width 100%; prefer vertical stack of nodes under 480px; stroke ≥1.5 at 320; tap targets not inside tiny SVG hotspots (links stay in HTML).
7. **Anti-clone:** not Air amber rings, not Hufflin forest leaves, not Melton soft SaaS blobs.
8. **Reuse assets first:** keep `homepage-numbers-banner.png`, `factsheet-infographic.png` / `graphic-what-is-a-mud-infographic.png`, playground photos where already placed — SVG **adds** clarity beside them, doesn’t silently delete campaign art without Kenny note.
9. **Mud-vs embed:** layout fix already pushed — do **not** restyle the comparison animation; optional thin frame chrome already in mockups.

---

## Shared diagram system (build once)

Name files under `website/assets/diagrams/` (suggested):

| ID | File | Purpose | Reuse |
|----|------|---------|-------|
| `sys-services` | `mud-services-cluster.svg` | Water / sewer / drainage / roads-drainage cluster | What is, Home (optional teaser) |
| `sys-streams` | `three-money-streams.svg` | Tax vs utility bill vs HOA/PID | Taxes, Buying cost model |
| `sys-entities` | `mud-pid-hoa-entities.svg` | Three entity types + overlap note | Compare |
| `sys-lookup` | `find-steps-path.svg` | 3–4 step path (not a map) | Find, Taxes lookup |
| `sys-who-call` | `who-to-call-routes.svg` | Route homeowner questions | Living |
| `sys-cost-stack` | `ownership-cost-stack.svg` | Layered cost mental model | Buying |
| `sys-governance` | `board-bonds-services.svg` | Board → bonds → services (high level) | What is |

**Stroke language:** 1.5–2px ink/civic; corner radius 4–6px on panels (match site cards); clay reserved for the single “watch this” node.

**Do not ship:** isometric cities, cartoon mascots, stock “handshake” vectors, gradient-mesh blobs, emoji.

---

## Per-page map

### 1. Home (`index.html`)

| Placement | Graphic | Type | Notes |
|-----------|---------|------|-------|
| Hero | Optional soft district-grid wash (very low opacity ink on ground) | Inline SVG background | Max ~8% opacity; must not fight H1. Skip if noisy on 320. |
| Start where you are | None new | — | Asymmetric panels already carry hierarchy; Lucide optional at link row only |
| Proof band | **Keep** `homepage-numbers-banner.png` | Raster (existing) | Don’t replace with fake SVG metrics |
| `#mud-vs-compare` | **Keep** iframe embed | Existing animation | Frame/caption only; no second diagram beside it |
| Guides | Tiny **distinct** monoline marks (one per row, 24px) — not identical icon cards | Inline SVG or Lucide sparingly | Marks must differ by shape language (definition / coin / key / home / scales / pin) |
| Official tools | Small “external registry” mark beside CTA | Lucide `external-link` OK | No big illustration |
| Video slot | Placeholder frame only | Existing | Outside party video |

**Priority for Timmy:** Guides row marks + (optional) hero wash. Skip hero wash if timeboxed.

---

### 2. What is a MUD? (`what-is-a-mud.html`)

| Placement | Graphic | Type | Notes |
|-----------|---------|------|-------|
| Campaign overview | **Keep** factsheet / what-is infographic PNG | Raster | Primary campaign asset |
| After “plain language” / services | `sys-services` cluster | HTML SVG | Label typical services; caption: “Typical — districts vary” |
| Who governs | `sys-governance` simple flow | HTML SVG | Board → bonds (high level) → services; no legal advice framing |
| Texas framing | Optional thin “ETJ / city / district” adjacency sketch | HTML SVG | Abstract boxes only; no fake map of Texas counties |
| Video / FAQ | None | — | Text wins |

**Priority:** `sys-services` then `sys-governance`.

---

### 3. Living (`living-in-a-mud.html`)

| Placement | Graphic | Type | Notes |
|-----------|---------|------|-------|
| Hero | Keep playground photo treatment | Raster | Already photo-supported |
| Who to call | `sys-who-call` routing diagram | HTML SVG | Branches: tax bill → appraisal/district; water bill → operator; amenities/CCRs → HOA if any; meetings → district site. Clay on “start here” node only |
| Water vs tax | Mini split from `sys-streams` (two of three nodes) | HTML SVG partial | Reinforce separation |
| Board / transparency | None or calendar-line mark | Lucide | Don’t decorate FAQ |

**Priority:** `sys-who-call` (highest education value on this page).

---

### 4. Buying (`buying-in-a-mud.html`)

| Placement | Graphic | Type | Notes |
|-----------|---------|------|-------|
| Context photo | Keep | Raster | |
| Diligence checklist | Optional vertical progress rail (1–n) | CSS + SVG ticks | Don’t turn checklist into icon cards |
| Notice to Purchaser | Document silhouette + 2–3 callout lines | HTML SVG | “What it is” — cite TREC Form 59-0 in caption/HTML, not inside SVG as legal text wall |
| Cost mental model | `sys-cost-stack` | HTML SVG | Layers: county/city tax · MUD tax · utility · HOA/PID if present. Neutral, not “deal” framing |
| Video / FAQ | None | — | |

**Priority:** `sys-cost-stack` + Notice silhouette.

---

### 5. Taxes (`mud-taxes.html`)

| Placement | Graphic | Type | Notes |
|-----------|---------|------|-------|
| Atmospheric strip | Keep hero-muds-background if present | Raster | |
| Three money streams | `sys-streams` **full** | HTML SVG | Hero diagram for this page — three equal columns on desktop, stack on mobile |
| Does tax go away? | Bond / tax-base **mental model** timeline | HTML SVG | Careful copy: “often declines as bonds are paid / base grows — not a promise.” Caution color only on disclaimer caption |
| Lookup steps | `sys-lookup` | HTML SVG | Align with numbered HTML steps; links stay in HTML |
| Video | Placeholder | — | |

**Priority:** `sys-streams` first (this is the money-confusion page).

---

### 6. Compare (`mud-vs-pid-vs-hoa.html`)

| Placement | Graphic | Type | Notes |
|-----------|---------|------|-------|
| Navy brand strip | Keep wordmark treatment | Existing | |
| Above or beside comparison table | `sys-entities` | HTML SVG | Three labeled entities + soft overlap note (“a home can sit in more than one”). Table remains source of truth — SVG is orientation only |
| Under-table nuance | None extra | — | Avoid second competing diagram |
| FAQ | None | — | |

**Priority:** `sys-entities` once; do not icon-decorate every table cell.

---

### 7. Find your MUD (`find-your-mud.html`)

| Placement | Graphic | Type | Notes |
|-----------|---------|------|-------|
| How to find steps | `sys-lookup` (same system as Taxes) | HTML SVG | Path metaphor, **not** interactive map / not fake GIS |
| Official tools | Tool-type marks (search / building / file) | Lucide or tiny SVG | Beside existing CTAs |
| Curated list | None until names/links leave TBD | — | Hold remains TBD |

**Priority:** `sys-lookup` reuse; no invented district map.

---

### 8. About (`about.html`)

| Placement | Graphic | Type | Notes |
|-----------|---------|------|-------|
| Hero | Keep photo/ink treatment | Raster | |
| Mission / what we are | Optional “sources → plain language → reader” chain | HTML SVG | Trust diagram; 3 nodes max |
| Contact / disclaimer | None | — | Holds: CONFIRM WITH CLIENT MANAGER |

**Priority:** Low — ship mission chain only if other pages done; About stays copy-led.

---

## Suggested build order (Timmy)

1. `three-money-streams.svg` → Taxes + Buying partial  
2. `who-to-call-routes.svg` → Living  
3. `mud-services-cluster.svg` + `board-bonds-services.svg` → What is  
4. `ownership-cost-stack.svg` + Notice silhouette → Buying  
5. `mud-pid-hoa-entities.svg` → Compare  
6. `find-steps-path.svg` → Find + Taxes lookup  
7. Home Guides row marks + optional hero wash  
8. About sources chain (nice-to-have)

---

## QA before merge

- [ ] 320px: no horizontal scroll; diagrams stack; labels readable  
- [ ] Contrast ≥ 4.5:1 for text in SVG  
- [ ] `prefers-reduced-motion`: no mandatory animation  
- [ ] No new marketing claims or stats in SVG text  
- [ ] Campaign PNGs still present where mapped  
- [ ] Melton chrome still OFF  

---

## Out of scope

- Redesigning engage+mobile layout, type, or palette  
- Replacing mud-vs animation concept  
- Stock Unsplash packs / Lottie sales kits  
- Filling TBD curated districts or client-manager CONFIRM fields  
- Dark-ink wordmark asset (still missing — Option A lockups remain)

Questions on craft (stroke, which node gets clay, caption wording): ping Bebe. No redesign unless Kyle/Kenny reopen.
