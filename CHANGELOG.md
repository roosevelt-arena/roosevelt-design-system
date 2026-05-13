# Changelog

Volgens [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) · SemVer 2.0.

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
