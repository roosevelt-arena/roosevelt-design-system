# Wise → Roosevelt Foundations — Mapping & IA

> Bron: [Wise Design Foundations](https://wise.design/foundations) (geanalyseerd 14 mei 2026)
> Doel: Wise IA + paginastructuur overnemen als geraamte voor Roosevelt OPS docs/design/foundations.
> Conflict-policy: **Roosevelt-Bauhaus canon wint altijd.**

---

## 1. Wise IA — wat we overnemen (geraamte)

Wise structureert Foundations in **twee pillars**: Product en Editorial. Subpagina's staan in één alfabetische lijst.

**Wise paginatemplate (per subpagina):**
1. Philosophy / Principles (waarom dit bestaat, brand-context)
2. Functional token-categorieën met naming + usage-descriptie
3. Accessibility-tabel (WCAG + APCA scores)
4. Do/Don't tabel
5. Cross-links naar verwante foundations

**Wise IA-besluiten die we overnemen:**
- ✓ Tweepillar-splitsing (Product + Editorial)
- ✓ Functional-naming (Content Primary, Background Neutral, etc. — niet `gray-500`)
- ✓ Per-token usage-descriptie als eerste-klas content
- ✓ Accessibility ingebakken op tokenpagina, niet aparte pagina
- ✓ Do/Don't als gestructureerde tabel
- ✓ Geen code-snippets op foundations-niveau — code hoort bij componenten
- ✓ Alfabetische ordening binnen pillar (Aicher-systematiek: voorspelbaarheid)

**Wat we expliciet NIET overnemen:**
- ✗ Wise's joviale tone-of-voice ("pinch of spice", "shout about something") — Roosevelt is academisch-pragmatisch
- ✗ "Bright Green als visual metaphor" — onze kleur is Weimar-semantisch, geen brand-metafoor
- ✗ Wise Sans display-font — wij gebruiken geen tweede display-typeface
- ✗ International glyphs / expressive headlines — anti-Bauhaus
- ✗ Tapestries als marketing-asset — niet relevant voor B2B-adviespipeline

---

## 2. Subpagina-mapping

| Wise foundation | Pillar | Roosevelt-equivalent | Status | Canon-toets |
|---|---|---|---|---|
| Mission | Product | **Mission** (Roosevelt OPS purpose, DSR-context) | Nieuw schrijven | Academisch fundament |
| Colour | Product | **Colour** (Weimar-semantiek, agent-rollen) | Geraamte overnemen, inhoud vervangen | Bauhaus §1.1 |
| Typography | Product | **Typography** (Bayer-erfgenaam, modulaire schaal 1.250) | Geraamte overnemen, inhoud vervangen | Bauhaus §1.2 |
| Grid | Product | **Grid** (asymmetrisch-orthogonaal, Mondriaan/Berlage) | Geraamte overnemen, inhoud vervangen | Bauhaus §1.3 |
| Spacing | Product | **Spacing** (8px Bauhaus-grid + 4px micro) | Geraamte overnemen, inhoud vervangen | Bauhaus §1.5 |
| Padding | Product | *Samenvoegen met Spacing* | Schrappen als losse pagina | Rams "less but better" |
| Size | Product | *Samenvoegen met Spacing* | Schrappen als losse pagina | Rams "less but better" |
| Radius | Product | **Radius** (0/2/4 max — De Stijl-orthogonaliteit) | Geraamte overnemen, scherper invullen | Bauhaus §1.3 |
| Icons | Product | **Iconography** (Aicher-grid, eigen pictogram-systeem) | Geraamte overnemen, eigen systeem | Bauhaus §1.4 |
| Focus states | Product | **Focus states** (functioneel, blauw-ring) | Geraamte overnemen | Bauhaus §1.5 |
| Motion System | Product | **Motion** (functioneel, 120/200/320ms) | Geraamte overnemen, beperkter | Bauhaus §1.5 |
| Transitions | Product | *Samenvoegen met Motion* | Schrappen als losse pagina | Rams "less but better" |
| Cards | Product | *Verschuiven naar Components* | Geen foundation | — |
| Flags | Product | **Pictograms** (F0–F9, agent-rollen, status) | Eigen Roosevelt-categorie, Aicher-systeem | Bauhaus §1.4 + paper Layer 4 |
| Illustration | Product | — | Schrappen | Anti-Bauhaus (decoratie) |
| Photography | Product | — | Schrappen | Anti-Bauhaus (geen photography in B2B-tool) |
| Logo | Product | **Logo** (Berlage-silhouet, bestaande `logo.size` + `logo.color` tokens) | Nieuw schrijven | Bauhaus §1.3 |
| Markup | Product | **Markup** (HTML-semantiek, ARIA, Next.js-context) | Geraamte overnemen | Operational excellence |
| Tone of voice | Editorial | **Tone of voice** (academisch-pragmatisch, AI Sales Labs human touch) | Geraamte overnemen, eigen invulling | Brand-DNA |
| Grammar and style | Editorial | **Grammar & style** (NL + EN, vaktermen-policy) | Geraamte overnemen | Brand-DNA |
| Vocabulary | Editorial | **Vocabulary** (pipeline-termen: F0–F9, agent-rollen, sales-DNA Toni van Dam) | Geraamte overnemen, Roosevelt-glossarium | Operational excellence |
| Tapestries | Editorial | — | Schrappen | Anti-Bauhaus (marketing-asset) |
| Promo assets | Editorial | — | Schrappen | Geen marketing-asset-niveau hier |
| — | Product | **Elevation** (geen — alleen functionele shadow op floating) | Nieuw, expliciet "niet gebruiken" als statement | Bauhaus §1.5 |
| — | Product | **Border** (Mondriaan-zwartlijn als structureel vlak) | Nieuw | Bauhaus §1.3 |

**Resultaat:** Wise heeft 23 subpagina's, Roosevelt foundations krijgt **17 subpagina's** — minder maar steviger (Rams "less but better").

---

## 3. Roosevelt Foundations — IA

```
docs/design/
├── bauhaus-canon.md                    [bestaand v0.1]
└── foundations/
    ├── README.md                       [index + IA-overzicht]
    │
    ├── _product/
    │   ├── mission.md                  [Roosevelt OPS purpose, DSR-context, ICIS 2026]
    │   ├── colour.md                   [Weimar-semantiek, agent-rollen, status, WCAG/APCA]
    │   ├── typography.md               [Inter/Geist, schaal 1.250, mono voor pipeline-data]
    │   ├── grid.md                     [asymmetrisch-orthogonaal, Mondriaan/Berlage]
    │   ├── spacing.md                  [8px base + 4px micro, M125-modulariteit]
    │   ├── radius.md                   [0/2/4 max — De Stijl-orthogonaliteit]
    │   ├── border.md                   [Mondriaan-zwartlijn als structureel vlak]
    │   ├── elevation.md                [statement: alleen floating, geen card-shadow]
    │   ├── iconography.md              [Aicher-grid, 24px canvas, 2px stroke]
    │   ├── pictograms.md               [F0–F9 + agent-rollen + status, Layer 4 token-koppeling]
    │   ├── motion.md                   [120/200/320ms, easing-out, functioneel]
    │   ├── focus-states.md             [blauw-ring 2px, accessibility-anker]
    │   ├── logo.md                     [Berlage-silhouet, tokens-koppeling]
    │   └── markup.md                   [HTML-semantiek, ARIA, Next.js App Router]
    │
    └── _editorial/
        ├── tone-of-voice.md            [academisch-pragmatisch + human touch]
        ├── grammar-and-style.md        [NL primair, EN vaktermen-policy]
        └── vocabulary.md               [F0–F9 glossarium, agent-rollen, Toni van Dam sales-DNA]
```

---

## 4. Roosevelt paginatemplate

Elke foundation-pagina volgt dit template (overgenomen van Wise, aangepast voor Roosevelt):

```markdown
# [Foundation naam]

> Pillar: Product | Editorial
> Canon-anker: bauhaus-canon.md §[paragraaf]
> Tokens: tokens.json → [pad]
> Stack-impact: [Tailwind preset / CSS var / TS type]

## 1. Filosofie
[Waarom dit bestaat. Verwijzing naar Bauhaus-canon-stroming. Roosevelt-toepassing.]

## 2. Principes
[3–5 bullets. Concreet, geen woollig taalgebruik.]

## 3. Tokens
[Tabel: token-naam | $value | usage-descriptie | DTCG-type]
[Aliassen Layer 1 → 2 → 4 expliciet.]

## 4. Accessibility
[WCAG 2.2 AA minimum + APCA waar relevant. Tabel met scores.]

## 5. Do / Don't
[Tabel met concrete voorbeelden.]

## 6. Implementatie
[Tailwind preset snippet / CSS variable / shadcn-override. Geen volledige component-code.]

## 7. Verwante foundations
[Cross-links binnen `foundations/*`.]

## 8. Provenance (DSR)
[Welke bron, welke paper-RQ, welke ADR. Voor ICIS 2026.]
```

**Verschil met Wise:**
- Sectie 6 (Implementatie) toegevoegd — Wise heeft geen code; wij wel, beperkt tot tokens-snippets (anti-duplicatie met component-docs)
- Sectie 8 (Provenance) toegevoegd — DSR-traceerbaarheid voor paper, niet bij Wise
- Sectie 1 (Filosofie) verplicht verwijzen naar bauhaus-canon — Wise heeft losse philosophy per pagina, wij centraliseren

---

## 5. Gap-analyse — wat moeten we nieuw bouwen

| Onderdeel | Status | Effort |
|---|---|---|
| `foundations/README.md` index | Nieuw | 1u |
| Paginatemplate als `_template.md` | Nieuw | 0.5u |
| `colour.md` (canon §1.1 + tokens al klaar) | Vullen | 2u |
| `typography.md` (canon §1.2 + tokens al klaar) | Vullen | 2u |
| `grid.md` (canon §1.3) | Vullen | 2u |
| `spacing.md` (canon §1.5 + tokens klaar) | Vullen | 1u |
| `radius.md` + `border.md` + `elevation.md` | Vullen | 2u totaal |
| `iconography.md` + `pictograms.md` | Onderzoek nodig (Aicher-grid eigen set) | 6u |
| `motion.md` + `focus-states.md` | Vullen | 2u |
| `mission.md` | Nieuw schrijven | 1u |
| `logo.md` | Bestaande tokens documenteren | 1u |
| `markup.md` | Next.js-specifiek schrijven | 2u |
| Editorial 3 pagina's | Nieuw, brand-DNA-werk | 4u |
| **Totaal** | | **~27u** |

Past binnen paper-roadmap P0–P1 (was ~15u, dit zit dichter bij P0–P2 incl. iconografie-onderzoek).

---

## 6. Iteratie-model (per nieuw onderdeel opnieuw analyseren)

Per nieuw Roosevelt-onderdeel doorlopen we:

1. **Wise-vergelijk:** is er een Wise-foundation die hier raakvlak mee heeft? Zo ja, paginatemplate + IA-keuze als startpunt.
2. **Canon-toets:** botst dit met bauhaus-canon? Canon wint.
3. **DSR-koppeling:** welke paper-RQ raakt dit, welke ADR moet geschreven.
4. **Token-impact:** welke laag (1/2/3/4) en hoe alias-keten.
5. **Documentatie:** vul paginatemplate, link in `foundations/README.md`.

Dit iteratie-model wordt opgenomen in `foundations/README.md` als governance-regel.

---

*Einde mapping v0.1*
