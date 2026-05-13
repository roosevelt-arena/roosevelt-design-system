# Roosevelt OPS — Foundations

> Headless Design System — Concept & Design fase
> Auteur: Sam Swaab · mei 2026 · v0.1
> Locatie: `docs/design/foundations/`

---

## Overzicht

Foundations zijn de **bron-van-waarheid** voor het Roosevelt Headless Design System. Elke component, elk pattern, elk adviesrapport-element verwijst naar foundations. Niets daarbuiten.

De structuur volgt het Wise Design-geraamte (IA + paginatemplate), maar elke inhoudelijke keuze is getoetst aan de **[Bauhaus-canon](../bauhaus-canon.md)**. Bij conflict wint de canon.

---

## Twee pillars

Wise-conventie overgenomen: foundations zijn gesplitst in **Product** (visueel/technisch) en **Editorial** (taal/toon).

### Product (14 foundations)

| # | Foundation | Canon-anker | Status |
|---|---|---|---|
| 1 | [Mission](_product/mission.md) | DNA-formule §2 | ✓ v0.1 |
| 2 | [Colour](_product/colour.md) | §1.1 Weimar-semantiek | ✓ v0.1 |
| 3 | [Typography](_product/typography.md) | §1.2 Dessau | ✓ v0.1 |
| 4 | Grid | §1.3 De Stijl | ⏳ |
| 5 | Spacing | §1.5 Gugelot-M125 | ⏳ |
| 6 | Radius | §1.3 De Stijl | ⏳ |
| 7 | Border | §1.3 Mondriaan-zwartlijn | ⏳ |
| 8 | Elevation | §1.5 Rams-ehrlich | ⏳ |
| 9 | Iconography | §1.4 Aicher-grid | ⏳ |
| 10 | Pictograms | §1.4 + paper Layer 4 | ⏳ |
| 11 | Motion | §1.5 functioneel | ⏳ |
| 12 | Focus states | §1.5 functioneel | ⏳ |
| 13 | Logo | §1.3 Berlage | ⏳ |
| 14 | Markup | Operational excellence | ⏳ |

### Editorial (3 foundations)

| # | Foundation | Canon-anker | Status |
|---|---|---|---|
| 1 | Tone of voice | Brand-DNA | ⏳ |
| 2 | Grammar & style | Brand-DNA | ⏳ |
| 3 | Vocabulary | Operational excellence | ⏳ |

---

## Paginatemplate

Elke foundation volgt `_template.md` met 8 verplichte secties:

1. **Filosofie** — Waarom dit bestaat, verwijzing naar canon-paragraaf
2. **Principes** — 3–5 bullets, concreet
3. **Tokens** — DTCG-tabel met aliassen Layer 1 → 2 → 4
4. **Accessibility** — WCAG 2.2 AA minimum, APCA waar relevant
5. **Do / Don't** — Tabel met concrete voorbeelden
6. **Implementatie** — Tailwind preset / CSS variable / shadcn-override snippet
7. **Verwante foundations** — Cross-links
8. **Provenance (DSR)** — Paper-RQ, Hevner-guideline, ADR

Verschil met Wise: secties 6 (Implementatie) en 8 (Provenance) zijn Roosevelt-specifiek.

---

## Governance — iteratie-model

Elk nieuw onderdeel (foundation, token, component) doorloopt deze 5-stappen-loop:

```
┌─────────────────────────────────────────────────────────────────┐
│ 1. Wise-vergelijk    Bestaat er een Wise-foundation met overlap?│
│                      Zo ja → paginatemplate + IA als startpunt. │
│                                                                 │
│ 2. Canon-toets       Botst dit met bauhaus-canon.md?            │
│                      Canon wint. Afwijking → ADR.               │
│                                                                 │
│ 3. DSR-koppeling     Welke paper-RQ raakt dit?                  │
│                      Welke Hevner-guideline?                    │
│                      Welke ADR moet geschreven?                 │
│                                                                 │
│ 4. Token-impact      Welke laag (1/2/3/4)?                      │
│                      Hoe loopt de alias-keten?                  │
│                                                                 │
│ 5. Documentatie      Vul paginatemplate.                        │
│                      Link in deze README.                       │
│                      Update tokens.json indien nodig.           │
└─────────────────────────────────────────────────────────────────┘
```

---

## Review-cadence

| Frequentie | Wie | Wat |
|---|---|---|
| Per pagina toegevoegd | Sam (self-review) | Template-compleetheid, canon-toets, DSR-koppeling |
| Per token-wijziging | Sam + CI | DTCG-validatie, WCAG-contrast-test, circular-deps-check |
| Per maand | Sam | Audit: 5 Bauhaus-fideliteits-metrics op het hele system |
| Per kwartaal | Peer-reviewer (N=3) | DSR-rigor-review voor ICIS 2026 |

---

## Versioning

Semver op het design system als geheel, vastgelegd in `packages/design-tokens/package.json`:

- **MAJOR** — Breaking change in token-namen of Layer 1-waarden
- **MINOR** — Nieuwe foundation, nieuwe token, nieuwe component
- **PATCH** — Documentatie-update, accessibility-correctie, non-breaking token-aanpassing

Elke release: changelog in `CHANGELOG.md`, gekoppeld aan ADR-nummers.

---

## Conventies

- Bestandsnamen: `kebab-case.md`
- Sectie-koppen: H1 = paginatitel, H2 = template-secties, H3+ = inhoudelijke onderverdeling
- Tokens in tekst: `code-formaat` met DTCG-pad (bijv. `color.primary.blue.500`)
- Aliassen tonen met pijl: `semantic.color.agent.strategic → color.primary.blue.500`
- Geen kapitalen in body-tekst (Bayer-erfgenaam), uitzondering: acroniemen (AI, DSR, WCAG, F0)
- Engels toegestaan voor vaktermen (design tokens, atomic design, etc.), rest in Nederlands

---

## Externe referenties

- [Bauhaus-canon](../bauhaus-canon.md) — visuele filosofie (bron-document)
- [tokens.json](../../packages/design-tokens/tokens.json) — DTCG token-bron
- ADR-020 — design system architectuur-besluit (te schrijven)
- Paper: *Bauhaus-Geïnspireerd Headless Design System voor Roosevelt OPS* (Swaab 2026)
- Geraamte-bron: [Wise Design Foundations](https://wise.design/foundations)

---

*v0.1 — 14 mei 2026*
