# Changelog

Volgens [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) · SemVer 2.0.

## [0.8.2] — 2026-05-14

### Removed
- **Ronde 6 (Logo) volledig uit prototype verwijderd** — sectie + sidebar-link. Logo-systeem blijft alleen als bron-documentatie in `docs/foundations/_product/logo.md` (indien aanwezig).
- SVG-monogram in manifest-header vervangen door pure typografische `manifest-wordmark` (Inter 800 clamp 32–56px + Geist Mono 500 clamp 14–18px).

### Changed
- Bauhaus-strict: nul logo-decoratie in het prototype zelf. Wordmark = typografie, niet illustratie.

## [0.8.1] — 2026-05-14

### Added
- **Ronde 8** — Responsive foundations (Apple HIG × Bauhaus). Conflict-policy tabel: principes + touch-targets + safe-areas overgenomen, visuele taal geweigerd.
- DTCG tokens: `--bp-compact` (640), `--bp-regular-sm` (1024), `--bp-regular-md` (1280), `--touch-min` (44px), `--touch-comfortable` (48px), `--safe-{top,bottom,left,right}` via `env(safe-area-inset-*)`.
- `viewport-fit=cover` voor notch-support op iPhone.
- Topbar `Responsive`-link en sidebar `Responsive (Apple HIG)`-link.

### Changed
- **Bauhaus-cleanup** — alle beschrijvende lede-paragrafen verwijderd uit R1–R7 (vorm volgt functie). Manifest-sub + meta-dots uit header. Footer leeggemaakt.
- **Logo eruit** — SVG-monogram in topbar vervangen door pure typografische wordmark (ROOSEVELT + OPS in Inter 800 / Geist Mono 500). Bauhaus-strict, geen monogram-decoratie in nav.

## [0.8.0] — 2026-05-13

### Added
- **Wise.design-stijl navigation** — sticky topbar (logo + 4 primary links + version chip) + left sidebar (240px, 11 foundations + Resources) + right rail (220px, scrollspy “Op deze pagina”).
- 3-koloms grid layout (`240px / 1fr / 220px`) op ≥1280px, 2-koloms 1024–1279, drawer-nav onder 1024px.
- Intersection Observer scrollspy voor sidebar en right-rail.
- Mobile drawer met hamburger toggle, ESC-close, click-outside-close, body-scroll-lock.
- Skip-link (WCAG 2.4.1), focus-states (#E8B306), aria-current/aria-expanded states.
- Section-IDs: `sec-r1` t/m `sec-r8`.

## [0.7.0] — 2026-05-13

### Added
- **Ronde 7** — Editorial foundations (lexicon Do/Don't, hype/corporate-koud verboden-lijst, grammar-regels, microcopy-voorbeelden, conflict-policy).
- `gap-analyse-en-roadmap.md` als kerndocument voor design system fase Concept & Design.

## [0.6.0] — 2026-05-13

### Added
- **Ronde 6** — Logo system (6 SVG-varianten: monogram, wordmark, lock-up, favicon, inverse, micro).
- 17 logo-tokens in `tokens.json`: `logo.{monogram,wordmark,lockup,favicon}.{viewbox,width,height,minSize,clearspace}`.
- WCAG contrast-tabel voor logo op alle background-surfaces.
- Do/Don't grid (8 voorbeelden).

## [0.5.0] — 2026-05-14

### Added
- **Ronde 5** — Iconography + Pictograms (Aicher-onderzoek + Vorkurs-geometrie).
- Iconenset: Lucide (Apache 2.0), 24px canvas, 1.5px stroke, square caps, miter joins.
- DTCG tokens: `dimension.icon.*` (canvas/stroke/padding), `icon.stroke.{cap,join}`, `semantic.color.icon.*`, `agent.{strategic,risk,advisory,technical}.{shape,color}`, `pipeline.emblem.*` (28 nieuwe leaf-tokens, totaal 214).
- Agent-pictogrammen: Kandinsky/Itten geometrie-mapping (○ Strategic, ◪ Risk, △ Advisory, ▬ Technical).
- F0-F9 pipeline-emblemen: hybride aanpak — cijfer + cluster-kleur (neutral.500 diagnostiek, blue.500 synthese).
- Foundation: `docs/foundations/_product/iconography.md`.
- Canon-onderzoek: `docs/canon/aicher-research-ronde5.md` (Aicher München '72, ISOTYPE, Vorkurs).

## [0.4.0] — 2026-05-14

### Added
- **Ronde 4** foundations: Grid (12-koloms asymmetrisch), Spacing (4pt+8pt-ankers), Radius (0/2/4), Border (1px+2px), Elevation (subtle/raised), Motion (5 durations + 3 easings), Focus (WCAG 2.4.13).
- DTCG tokens uitgebreid: `dimension.grid.*`, `dimension.spacing.0-20`, `dimension.radius.*`, `shadow.elevation-*`, `duration.*`, `cubicBezier.*`, `semantic.surface/border/motion/spacing.*`.
- Prototype-secties: Grid demo, Spacing schaal, Shape (radius/border/elevation), Motion + Focus indicator.

## [0.3.0] — 2026-05-13

### Added
- **Ronde 3** — HTML prototype (single-file, alle CSS inline) gedeployed.
- Visuele verificatie van Layer 1+2+4 tokens.

## [0.2.0] — 2026-05-13

### Added
- **Ronde 2** — Typography foundation. Inter Variable + Geist Mono. Schaal 1.250 (major third). 11 type-rollen.

## [0.1.0] — 2026-05-13

### Added
- **Ronde 1** — Mission + Colour foundations.
- Bauhaus-canon (5 stromingen) vastgelegd.
- Wise foundations IA-mapping (23→17).
- DTCG 2025.10 tokens.json (Layer 1+2+4).
- Foundations README + paginatemplate.
- WCAG/APCA contrast-validatie (alle kleurcombinaties).
