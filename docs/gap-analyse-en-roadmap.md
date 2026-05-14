# Roosevelt OPS — Gap-analyse & 12-maanden Roadmap

**Versie** v1.0 · **Datum** 14 mei 2026 · **Auteur** Sam Swaab
**Scope** Concept & Design fase, Headless Design System
**Methodologie** Design Science Research (Hevner 2004, Peffers 2007)

---

## 0. Doel van dit document

Dit document beantwoordt drie vragen:

1. **Waar staat het Roosevelt-prototype v0.6.0** ten opzichte van de eigen canon (Bauhaus + Toni van Dam human touch) en ten opzichte van de top-15 design systems uit het Reddit-onderzoek?
2. **Welke gaten** moeten gedicht worden voordat Roosevelt OPS DSR-volwassen is voor ICIS 2026?
3. **Welke roadmap** brengt het systeem van v0.6.0 naar productie-rijp in 12 maanden, opgedeeld in drie horizons?

Conflict-policy: bij twijfel wint `bauhaus-canon.md`. Bij copy-twijfel wint `tone-of-voice.md`. Bij terminologie-twijfel wint `vocabulary.md`. Bij grammar-twijfel wint `grammar.md`.

---

## 1. Huidige staat — prototype v0.6.0

### 1.1 Wat zit er in

| Laag | Status v0.6.0 | Bron |
| --- | --- | --- |
| **Bauhaus-fundament** (5 stromingen) | Aanwezig in canon-doc, deels visueel in prototype | `bauhaus-canon.md`, `index.html` Ronde 1-2 |
| **Tokens** (kleur, type, spacing, motion, radius) | DTCG-conform, Style Dictionary output | `tokens.json` |
| **Typografie** (Inter Variable + Geist Mono) | Volledig gedocumenteerd, in prototype zichtbaar | `typography.md`, Ronde 3 |
| **WCAG 2.2 AA contrast** | Gevalideerd, AAA op primaire combinaties | Ronde 4 audit |
| **Pipeline-visualisatie F0-F9** | Canon-aligned labels (Core-map, Triangulatie, Multi-Judge, Render) | Ronde 5 |
| **Logo-systeem (Ronde 6)** | 6 SVG-varianten, 17 tokens, Do/Don't | `roosevelt-logo-assets.md`, `logo.md` |
| **Tone of voice** | Geschreven, niet visueel in prototype | `tone-of-voice.md` |
| **Editorial foundations** (grammar + vocabulary) | **Geschreven, niet in prototype** | `grammar.md`, `vocabulary.md` |
| **Copy-audit fixes** | Pipeline-labels canon-aligned, u-form F9, versie-stamps | v0.5.2-laag |

### 1.2 Wat zit er nog niet in

| Laag | Status | Vereist voor |
| --- | --- | --- |
| **Editorial Foundations in prototype** | Geschreven (28 KB) maar onzichtbaar | v0.7.0 prototype-update |
| **Component-library (moleculen + organismen)** | Concept-mapping aanwezig, geen render | H2 (0-3 mnd) |
| **Governance-flow** (ADR-template, review cadence) | Niet vastgelegd | H3 (3-12 mnd) |
| **Multi-brand theming** (AI Sales Labs + Roosevelt + toekomstige spin-offs) | Niet uitgewerkt | H3 (3-12 mnd) |
| **Style Dictionary output naar Tailwind 3** | DTCG-bron aanwezig, geen build | H2 (0-3 mnd) |
| **Figma Variables sync** | Geen Figma-bestand actief | H2 (0-3 mnd) |
| **DSR-evaluatie-protocol** (N=3 experts) | Skill aanwezig, geen uitvoering | H3 (3-12 mnd) — ICIS 2026 |
| **F9-rapportcomponenten** (adviesrapport-templates) | Geen sales-asset-templates | H3 (3-12 mnd) |

---

## 2. Gap-analyse — prototype vs canon

### 2.1 Bauhaus-canon dekking

| Bauhaus-principe | Vereist door canon | Aanwezig in v0.6.0 | Gap |
| --- | --- | --- | --- |
| **1.1 Weimar-geometrie** (cirkel/vierkant/driehoek per agent-rol) | Strategic=cirkel, Risk=vierkant diagonaal, Advisory=driehoek, Technical=rechthoek | Pipeline-vis Ronde 5 toont geometrie | Geen — gedekt |
| **1.2 Dessau-typografie** (zinscase, geen titlecase) | grammar.md sectie 2 | Logo + headers in zinscase | Geen — gedekt |
| **1.3 Ehrliche Materialien** (geen verbergen, agent benoemen) | vocabulary.md sectie 6.2 | Pipeline-labels expliciet, geen "AI magic" | Geen — gedekt |
| **1.4 Gesamtkunstwerk** (één stem over alle artefacten) | tone-of-voice.md | Logo + UI + tokens consistent, **editorial niet in prototype** | **Gap A** — editorial-laag mist visueel |
| **1.5 Funktionalismus** (vorm volgt functie) | Alle componenten | Tokens functioneel benoemd | Geen — gedekt |

### 2.2 Toni van Dam human-touch dekking

| Human-touch element | Vereist | Aanwezig | Gap |
| --- | --- | --- | --- |
| **U-form in F9-rapport** | mission.md | v0.5.2 gefixed: "Uw salesorganisatie heeft 67%..." | Geen — gedekt |
| **Je-form in UI F0-F8** | grammar.md 1.2 | Niet expliciet in prototype getoond | **Gap B** — UI-microcopy demo mist |
| **Salesfilosofie als context** | mission.md | Geen quote-sectie in prototype | **Gap C** — Toni-quote-laag mist |
| **AI Sales Labs koppeling** | mission.md | Geen verwijzing in prototype | **Gap D** — herkomst-laag mist |

### 2.3 DSR-rigor dekking

| Hevner-guideline | Vereist | Aanwezig | Gap |
| --- | --- | --- | --- |
| **G1 Design as artefact** | Tokens + prototype | Aanwezig | Geen |
| **G2 Problem relevance** | mission.md | Aanwezig | Geen |
| **G3 Design evaluation** | N=3 expert review | **Niet uitgevoerd** | **Gap E** — kritiek voor ICIS 2026 |
| **G4 Research contributions** | Theorie + artefact | Theorie in bauhaus-canon | **Gap F** — bijdrage niet geformaliseerd |
| **G5 Research rigor** | Traceability tokens → canon | DTCG met canon-anker | Geen |
| **G6 Design as search** | Iteratieprotocol | Ronde 1-6 logs aanwezig | Geen |
| **G7 Communication** | Wetenschappelijk + management | **A3 poster + paper-skeleton ontbreken** | **Gap G** — ICIS-paper niet gestart |

---

## 3. Gap-analyse — prototype vs top-15 Reddit-DS

Op basis van `reddit-sentiment-synthese.md` en `reddit-sentiment-15-design-systems.csv`.

### 3.1 Wat Reddit prijst (top-3 patterns)

| Pattern | Bron-DS | Roosevelt-status v0.6.0 |
| --- | --- | --- |
| **Copy-paste-bare componenten met inline code-voorbeelden** | shadcn/ui | **Gap H** — geen code-snippet-sectie in prototype |
| **Mailchimp-style structuur voor voice-guide** (audience-aware, context-aware) | Mailchimp | Tone-of-voice.md volgt deze structuur — **Gap I** in prototype-zichtbaarheid |
| **Adobe Spectrum gestructureerde content-guidance** (button labels, titles) | Spectrum | Vocabulary.md volgt — **Gap I** in prototype-zichtbaarheid |

### 3.2 Wat Reddit haat (top-3 patterns) — vermijdingsvalidatie

| Pattern | Bron-DS | Roosevelt-vermijding |
| --- | --- | --- |
| **Onvolledige docs, missende voorbeelden** | Carbon, Fluent 2, Primer, Lightning | **Risico H** — momenteel weinig componenten gerendered |
| **Slechte vertalingen, on-Engelse zinnen** | Ant Design | Gedekt via vocabulary.md sectie 5 |
| **Whimsy UX-copy overal** | Mailchimp-imitators | Gedekt via tone-of-voice.md academisch-pragmatisch register |

### 3.3 Niet-toepasbaar voor Roosevelt

- **Polaris merchant-voice** — te warm voor B2B C-level
- **shadcn copy-pasteable docs** — DX-helderheid past wel voor foundations, niet voor F9
- **Ant Design vertaalbenadering** — Roosevelt is NL-eerst, Engels selectief

### 3.4 Positioneringsruimte

> Voice-strength gemiddeld over de 15 systemen: 1.7/5. De community klaagt vaker dan ze prijst. **Er is ruimte voor een kalm-stellig-academische voice — juist omdat de grote systemen daar niet voor staan.** ([reddit-sentiment-synthese.md](file://reddit-sentiment-synthese.md))

---

## 4. Geconsolideerde gap-lijst (A-I)

| ID | Gap | Severity | Horizon |
| --- | --- | --- | --- |
| **A** | Editorial-laag (grammar + vocabulary) niet visueel in prototype | P0 | H1 (0-2 wkn) |
| **B** | UI-microcopy demo (je-form F0-F8) mist | P1 | H1 |
| **C** | Toni-quote/human-touch sectie mist | P2 | H2 |
| **D** | AI Sales Labs herkomst-koppeling mist | P2 | H2 |
| **E** | DSR-evaluatie N=3 expert review niet uitgevoerd | P0 — ICIS-blokker | H3 |
| **F** | Research contribution niet geformaliseerd | P1 | H3 |
| **G** | ICIS 2026 paper-skeleton + A3 poster niet af | P0 — ICIS-blokker | H3 |
| **H** | Component-library docs (copy-paste-bare) mist | P1 | H2 |
| **I** | Voice-guide structuur niet zichtbaar in prototype | P1 | H1 |

---

## 5. 12-maanden Roadmap

### Horizon 1 — Stabilisatie (0-2 weken, mei 2026)

**Doel** Editorial-laag visueel maken, gaps A/B/I dichten.

| Sprint | Deliverable | Skill | Status |
| --- | --- | --- | --- |
| W1 | Prototype v0.7.0 met Editorial Foundations sectie (lexicon-tabel + grammatica + do/don't-zinnen) | content-creative + dev-engineering | **Deze sessie** |
| W1 | UI-microcopy demo-sectie (je-form vs u-form) | content-creative | v0.7.0 |
| W2 | CHANGELOG v0.7.0 entry, ADR-021 Copy Voice Governance vaststellen | operations-cx | v0.7.0 |
| W2 | Style Dictionary build-pipeline opzetten (tokens.json → Tailwind 3) | dev-engineering | v0.7.1 |

**Exit-criterium H1** Alle P0/P1 gaps uit H1 gedicht. Editorial-laag is in prototype zichtbaar en met canon-bronnen aangehaakt.

### Horizon 2 — Component-library (0-3 maanden, mei-augustus 2026)

**Doel** Atomen → moleculen → organismen renderen, gaps C/D/H dichten.

| Maand | Deliverable | Skill |
| --- | --- | --- |
| Mei-juni | Atomen: Button, Input, Badge, Card, Divider, Icon — als shadcn 4 componenten met DTCG-tokens | dev-engineering + visual-design |
| Juni | Moleculen: FormField, AgentCard, PhaseStep, DimensionBar, ConfidenceScore | dev-engineering |
| Juli | Organismen: PipelineVisualizer, AdvisoryReportSection, IntakeForm, F9-RapportTemplate | dev-engineering + sales |
| Juli-aug | Figma Variables sync (één bron per token via DTCG) | content-creative |
| Aug | Toni van Dam quote-sectie + AI Sales Labs herkomst-laag in prototype | marketing + content-creative |

**Exit-criterium H2** Componentbibliotheek is bruikbaar in Next.js 14 + shadcn 4 stack. Figma en code zijn in sync via DTCG. Roosevelt is visueel niet meer hetzelfde als generieke Concentrix/Hyperion-templates.

### Horizon 3 — DSR-validatie + ICIS 2026 (3-12 maanden, augustus 2026-mei 2027)

**Doel** Gaps E/F/G dichten, ICIS 2026 Lissabon submission.

| Kwartaal | Deliverable | Skill | ICIS-koppeling |
| --- | --- | --- | --- |
| Q3 2026 (aug-okt) | A3 poster afronden (roosevelt-design-concept-a3 skill) | content-creative | Visual abstract |
| Q3 2026 | Expert-review pakket N=3 voorbereiden (roosevelt-dsr-design-evaluation) | research-knowledge | Empirische evaluatie G3 |
| Q4 2026 (nov-dec) | Expert-reviews uitvoeren, rubric-template invullen | operations-cx | Data-collectie |
| Q4 2026 | ICIS 2026 Research-in-Progress paper-skeleton invullen | research-knowledge | G4 + G7 |
| Q1 2027 (jan-feb) | Paper-finale + submission ICIS 2026 deadline | research-knowledge | Submission |
| Q1 2027 | Multi-brand theming opzetten (Roosevelt + AI Sales Labs split) | dev-engineering + marketing | n.v.t. |
| Q2 2027 (mrt-mei) | F9-rapport sales-asset-templates productie-rijp | sales + dev-engineering | n.v.t. |
| Q2 2027 | Governance: ADR-cadence, peer-review template, versioning policy | operations-cx + pm | DSR rigor G5 |

**Exit-criterium H3** ICIS 2026 paper submitted. DSR-evaluatie compleet met N=3 experts. Roosevelt OPS is productie-rijp voor AI Sales Labs pilot-klanten. Roadmap voor multi-brand spin-offs ligt vast.

---

## 6. ICIS 2026 Alignment

| Hevner-guideline | Deliverable | Horizon |
| --- | --- | --- |
| G1 Design as artefact | Prototype v1.0.0 + token-library | H1 + H2 |
| G2 Problem relevance | mission.md + AI Sales Labs pilot-data | H3 Q4 |
| G3 Design evaluation | N=3 expert review + rubric | H3 Q4 |
| G4 Research contributions | Bauhaus-canon-toepassing op B2B-DS | H3 Q1 paper |
| G5 Research rigor | DTCG-traceability + ADR-trail | H1-H3 |
| G6 Design as search | Ronde 1-6+ iteratielogs | doorlopend |
| G7 Communication | A3 poster + RiP paper | H3 Q3-Q1 |

**Target submission** ICIS 2026 Lissabon — Research-in-Progress track.

---

## 7. Risico's en mitigatie

| Risico | Severity | Mitigatie |
| --- | --- | --- |
| Component-library scope-creep | Hoog | Strikt atomic-design fasering, geen organismen voor moleculen af zijn |
| ICIS-deadline slippage | Hoog | H3 Q3 buffer-maand inbouwen voor expert-rekrutering |
| Multi-brand theming te vroeg | Middel | Pas vanaf Q1 2027, na pilot-evaluatie |
| Reddit "voice-guide-fatigue" overslaan op Roosevelt | Laag | Vermijd Mailchimp-imitatie, hou academisch-pragmatisch register |
| Editorial-laag rot in foundations-docs | Middel | v0.7.0 maakt het zichtbaar, ADR-021 codificeert governance |

---

## 8. Referenties

- `bauhaus-canon.md` — 5-stromingen fundament
- `mission.md` — Roosevelt OPS positionering
- `tone-of-voice.md` — Voice principes
- `grammar.md` — Redactionele conventies v1.0
- `vocabulary.md` — Lexicon Roosevelt OPS v1.0
- `tokens.json` — DTCG token-library
- `reddit-sentiment-15-design-systems.csv` — 15-DS evidence base
- `reddit-sentiment-synthese.md` — Top-3 prijs/haat patterns
- `logo.md` + `roosevelt-logo-assets.md` — Ronde 6 logo-systeem
- Hevner, A.R. (2004) — Design Science in Information Systems Research
- Peffers, K. (2007) — Design Science Research Methodology
- W3C Design Tokens Community Group — DTCG 2025.10

---

*Einde gap-analyse en roadmap v1.0 — 14 mei 2026*
