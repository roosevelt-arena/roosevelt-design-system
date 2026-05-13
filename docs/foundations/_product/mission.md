# Mission

> Pillar: Product
> Canon-anker: [bauhaus-canon.md](../../bauhaus-canon.md) — DNA-formule §2
> Tokens: n.v.t. (deze pagina definieert geen tokens)
> Stack-impact: n.v.t.
> Status: v0.1 — Concept & Design fase

---

## 1. Filosofie

Roosevelt OPS is een diagnostische F0–F9 adviespipeline voor B2B-salesorganisaties. Het Headless Design System is geen visuele schil rond een product — het is een **wetenschappelijk artefact** in de zin van Hevner (2004): een ontworpen object dat zowel praktisch nut levert (operational excellence in de pipeline) als kennisbijdrage (Bauhaus-fideliteit als meetbare designstandaard binnen Design Science Research).

Daarmee staat dit design system in twee tradities tegelijk:

- **De Bauhaus-canon** (Weimar → Dessau → De Stijl → Ulm → Gugelot/Rams) als historische en visuele legitimering. Een ononderbroken Europese lijn van 1919 tot 1965, doorlopend naar Roosevelt OPS in 2026.
- **De Design Science Research-methodologie** (Hevner 2004, Peffers 2007) als wetenschappelijke legitimering, met doelpublicatie ICIS 2026 Lissabon.

Het systeem is geen schil. Het is een **bouwwerk** — net als Berlage's Beurs aan het Damrak: "insignificant as an individual, but a power as a mass."

---

## 2. Principes

1. **Operational excellence boven esthetiek.** Elke designkeuze dient de F0–F9 pipeline-leesbaarheid en de adviesrapport-helderheid voor klanten zoals Vodafone, Signify, Allianz en Sarens.
2. **Academisch fundament zichtbaar maken.** DSR-methodologie en Ulm-rationalisme zijn natuurlijke verwanten — discipline, niet decoratieve "academische" stijl.
3. **AI Sales Labs human touch borgen.** Toni van Dams salesfilosofie is niet generiek-corporate en niet hype-AI; het design system draagt deze toon door terughoudendheid (Gugelot/Rams-stilte), niet door warmte-decoratie.
4. **Bauhaus-canon wint altijd.** Bij conflict tussen externe benchmarks (Wise, Carbon, Polaris) en de canon, wint de canon. Elke afwijking krijgt een eigen ADR.
5. **Less but better.** Geen foundation die niet werkt, geen token zonder semantische rol, geen component zonder paper-traceerbaarheid.

---

## 3. Positionering

Roosevelt onderscheidt zich expliciet van twee concurrenten in het AI-readiness-segment:

| Dimensie | Concentrix Agentic AI Assessment | Hyperion AI Readiness Assessment | **Roosevelt OPS** |
|---|---|---|---|
| Methodologie | Bedrijfsraamwerk, niet gepubliceerd | Consultancy-rubric | DSR (Hevner 2004), peer-reviewed, ICIS 2026-target |
| Visuele identiteit | Corporate, generiek SaaS | Hyperion-blauw, generiek | Bauhaus-canon, getoetst aan 5 fideliteits-metrics |
| Human-in-the-loop | Toolingvragen | Workshops | Toni van Dam-salesfilosofie expliciet ingebakken |
| Klant-output | Powerpoint-rapport | Spreadsheet-scorecard | Adviesrapport + educatieplan, gegenereerd via het design system zelf |

Het design system is daarmee **zelf onderscheidend vermogen** — niet een afgeleide ervan.

---

## 4. DSR-koppeling (Hevner-guidelines)

| Hevner-guideline | Roosevelt-toepassing |
|---|---|
| 1. Design as Artifact | Het Headless Design System ís het artefact. Tokens, componenten, foundations-docs vormen samen het design-object. |
| 2. Problem Relevance | B2B-salesorganisaties missen een wetenschappelijk gefundeerd AI-readiness-instrument. Roosevelt vult dat gat. |
| 3. Design Evaluation | Bauhaus-fideliteit als meetbare metric (>85% token coverage, <50 custom rules, 100% DTCG-conform, 0 circular deps, <5% visuele diff). |
| 4. Research Contributions | Bauhaus-canon-operationalisering + Roosevelt-canon-formule als nieuwe DSR-bijdrage. |
| 5. Research Rigor | DTCG 2025.10-conformiteit, WCAG 2.2 AA-validatie, peer-review-pakket (N=3). |
| 6. Design as Search Process | Iteratie-model (5-stappen-loop) per nieuw onderdeel. |
| 7. Communication | Deze foundations-docs + ICIS 2026 Research-in-Progress paper. |

---

## 5. Scope (wat het systeem wél en niet doet)

**Wel:**
- Headless tokens (DTCG 2025.10) als bron-van-waarheid
- Foundations-documentatie voor Product (14) en Editorial (3) categorieën
- Atomic component-library in `packages/ui` (Nx) bovenop shadcn 4
- Pipeline-specifieke Layer 4 tokens (F0–F9, agent-rollen, status)
- Adviesrapport-template F9 die op het system draait
- ADR-traceability voor elke designbeslissing
- Bauhaus-fideliteits-evaluatie als CI-check

**Niet:**
- Marketing-assets (tapestries, illustraties, photography) — buiten scope
- Multi-brand white-label support — Roosevelt-only
- Native-app design tokens — webfirst, Next.js 14
- Decoratieve micro-interacties — alleen functionele motion

---

## 6. Stakeholders

| Stakeholder | Belang |
|---|---|
| Sam Swaab | Hoofdauteur, Design Science Research-onderzoeker, ICIS 2026-target |
| Toni van Dam (AI Sales Labs) | Brand-DNA-eigenaar, sales-methodologie-bron |
| Klanten Roosevelt | Vodafone, Signify, Allianz, Sarens — ontvangen adviesrapport F9 |
| Peer-reviewers ICIS 2026 | Wetenschappelijke validatie van de bijdrage |
| Solo-developer-feasibility | Het system moet door één ontwikkelaar onderhoudbaar zijn (paper RQ4d) |

---

## 7. Stack-context

Roosevelt-stack is een harde randvoorwaarde:

- **Frontend:** Next.js 14 App Router, shadcn 4, Tailwind 3, Radix UI
- **Backend:** Fastify, Inngest 3, Supabase Postgres + pgvector
- **AI:** Vercel AI SDK 6, Claude Sonnet + GPT-4o-mini
- **Auth:** Clerk JWT
- **Hosting:** Hetzner + Docker + Caddy (ADR-013)
- **Observability:** Sentry + OpenTelemetry (ADR-018)
- **Monorepo:** Nx met `packages/design-tokens`, `packages/ui` (P1)
- **CI:** 25 checks, lineaire git history

Geen designkeuze mag deze stack schenden. Geen voorstel voor CSS-in-JS bibliotheek X als die conflicteert met Tailwind-preset. Geen design token-pipeline die Style Dictionary v4 omzeilt.

---

## 8. Verwante foundations

- [bauhaus-canon.md](../../bauhaus-canon.md) — visuele filosofie
- [README.md](../README.md) — IA-overzicht foundations
- `_template.md` — paginatemplate voor alle foundation-pagina's
- ADR-020 (te schrijven) — formele design-system-architectuur-beslissing

---

## 9. Provenance (DSR)

| Veld | Waarde |
|---|---|
| Bron-paper | Swaab, S. (2026). *Bauhaus-Geïnspireerd Headless Design System voor Roosevelt OPS*, v1.0 Pre-registration Draft |
| RQ-koppeling | RQ4 (geheel) — minimale headless design system-architectuur Bauhaus-inspired |
| Hevner-guidelines | 1, 2, 4 primair; 7 secundair |
| Peffers-DSRM-activiteit | Activity 2 (Define objectives of a solution) |
| ADR | ADR-020 (te schrijven, verwijst naar dit document als objectives-bron) |
| Versie | v0.1 — 14 mei 2026 |

---

*Einde Mission v0.1*
