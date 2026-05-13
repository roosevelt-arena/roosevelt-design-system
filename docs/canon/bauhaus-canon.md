# Bauhaus-canon Roosevelt OPS
**Visuele filosofie voor het Headless Design System**

> Status: Draft v0.1 — Concept & Design fase
> Auteur: Sam Swaab
> Datum: mei 2026
> Locatie: `docs/design/bauhaus-canon.md`
> Bron-ADR: ADR-020 (te schrijven)
> Stack-context: Next.js 14 App Router · shadcn 4 · Tailwind 3 · Nx monorepo · Hetzner

---

## 0. Doel van dit document

Dit manifest legt de **visuele filosofie** vast die boven alle design tokens, componenten en pagina's van Roosevelt OPS hangt. Het is de bron-van-waarheid waaraan elk volgend artefact (kleurpalet, typografische schaal, grid, componenten) wordt getoetst.

Roosevelt OPS is een diagnostische F0–F9 adviespipeline voor B2B-salesorganisaties. Het design system moet:
- **Operational excellence** uitstralen (Vodafone, Signify, Allianz, Sarens als klanten)
- **Academisch fundament** tonen (DSR-methodologie, ICIS 2026 target)
- **AI Sales Labs human touch** dragen (Toni van Dams salesfilosofie, niet generiek-corporate)
- Zich onderscheiden van Concentrix Agentic AI Assessment en Hyperion AI Readiness Assessment

De canon is **geen stijlhandleiding** — die volgt uit deze canon. Dit document beantwoordt de waarom-vraag.

---

## 1. De vijf stromingen — canon

Vier Bauhaus-stromingen plus de Gugelot/Rams-as vormen de basis. Elk levert een specifiek principe.

### 1.1 Weimar (1919–1925) — *kleur als semantiek*

**Erfgoed:** Johannes Itten's *Vorkurs*, Wassily Kandinsky's *Punkt und Linie zu Fläche*, Paul Klee's pedagogische schetsboeken.

**Kernidee:** Kleur is geen decoratie maar psychologische en symbolische taal. Itten identificeerde zeven contrastsoorten (tint, licht-donker, koud-warm, complementair, simultaan, verzadiging, extensie). Kandinsky koppelde primaire kleuren aan elementaire vormen: geel-driehoek (scherp, agressief), rood-vierkant (statisch, materieel), blauw-cirkel (oneindig, geestelijk).

**Roosevelt-toepassing:**
- Primaire kleuren krijgen **semantische rol**, geen esthetische:
  - **Rood** = risk-signaal, urgentie, F-fase met escalatie
  - **Blauw** = strategic-agent, advies-fundament, rust
  - **Geel** = advisory-attention, review nodig, human-in-the-loop
- Grijsschaal = structuur en hiërarchie, niet decoratie
- Geen warme accentkleuren (oranje, paars, teal) — die voegen ruis toe aan semantiek

**Anti-pattern:** Tailwind-default `bg-red-500` als generieke "primary destructive". Kleur moet altijd terug te leiden zijn naar pipeline-betekenis.

### 1.2 Dessau (1925–1932) — *typografie als systeem*

**Erfgoed:** Herbert Bayer's *Universal*-typografie (1925, alleen kleine letters, geometrisch geconstrueerd uit cirkel en lijn), László Moholy-Nagy's typografische manifesten, Marcel Breuer's tubular-steel meubels.

**Kernidee:** Typografie is een functionele communicatiemachine, geen kalligrafische expressie. Bayer's *Universal* was een radicale poging: één lettercasus, mathematische constructie, uniforme stamdikte. De Bauhaus formuleerde drie typografische principes: (1) typografie wordt gevormd door functionele eisen, (2) doel is communicatie in kortste/eenvoudigste/meest penetrerende vorm, (3) ingrediënten hebben interne en externe organisatie.

**Roosevelt-toepassing:**
- Geometrisch sans als hoofdfont (Bayer-erfgenaam: **Inter** of **Geist Sans** — beide moderne implementaties van Bayer-principes)
- **Geen kapitalen in body-tekst** — Bayer-erfenis; uitzondering: acroniemen (AI, DSR, F0)
- **Hoofdletters wél in display/labels** als bewuste schakelaar (Bauhaus stond niet 100% achter Bayer's experiment; Dessau-typografie was praktisch)
- Body-tekst is altijd **functionele communicatie**: geen italics als decoratie, alleen voor titels van werken/papers
- Mono-font voor pipeline-status, code, token-namen: **JetBrains Mono** of **Geist Mono** — toont "eerlijk materiaal" (dit is data, geen proza)

**Anti-pattern:** Decoratieve display-fonts, handgeschreven stijlen, condensed-varianten zonder functie.

### 1.3 De Stijl (1917–1931) — *Nederlandse as: orthogonale strengheid*

**Erfgoed:** Piet Mondriaan's *Composition with Red, Blue, and Yellow* (1930), Gerrit Rietveld's rood-blauwe stoel (1918) en Schröderhuis, Theo van Doesburg's manifesten.

**Kernidee:** Reductie tot rechthoeken, primaire kleuren puur (rood/blauw/geel) plus zwart/wit/grijs, **asymmetrische balans** als compositieprincipe. Mondriaan zag zwarte lijnen niet als omtrekken maar als pigmentvlakken op zichzelf — horizontaal en verticaal zijn evenwaardig. De compositie is harmonie van contrasten, niet symmetrische rust.

**Roosevelt-toepassing:**
- Lay-out is **asymmetrisch-orthogonaal**, niet 12-koloms-center-default
- **Berlage-silhouet** (uit bestaande `tokens.json`, commit e80c405) als noordelijke variant: Amsterdamse School-strengheid, baksteen-orthogonaliteit, democratisch ("insignificant as individual, power as mass" — Berlage)
- Black-lines-as-planes: borders zijn nooit 0.5px-dun-decoratief, altijd 1px of 2px **structureel** (= ze dragen betekenis, scheiden vlakken)
- Witruimte is een **vlak**, geen leegte (Rietveld-principe)
- Cards hebben **scherpe hoeken** of maximaal 2px-radius — geen `rounded-2xl` shadcn-default

**Anti-pattern:** Symmetrische "hero-centered" landingspagina's, decoratieve borders, gradient-fills (vervangen orthogonale duidelijkheid door illusie).

### 1.4 Ulm HfG (1953–1968) — *systeemdenken*

**Erfgoed:** Max Bill (oprichter, Bauhaus-alumnus), Otl Aicher (München 1972-pictogrammen, Lufthansa-identiteit), Tomás Maldonado (design als wetenschappelijke discipline), Hans Gugelot (productdesign, doceerde vanaf 1954).

**Kernidee:** Design is een wetenschappelijke discipline. Aicher's München-pictogrammen zijn niet losse iconen maar een **systeem** — een grid van verticale, horizontale en 45°-diagonale lijnen genereert een hele pictogramfamilie. Maldonado verbond design aan systeemtheorie en cybernetica.

**Roosevelt-toepassing:**
- **Pictogram-systeem** voor F0–F9 fasen, agent-rollen (Strategic/Technical/Advisory/Risk), pipeline-status (running/approval/completed/error) — niet losse Lucide-icons
- **Grid voor iconografie:** 24px canvas, 2px stroke, opbouw uit cirkel + vierkant + 45°-diagonalen (Aicher-logica)
- DSR-methodologie en Ulm-rationalisme zijn natuurlijke verwanten — design system fungeert als **wetenschappelijk artefact** (Hevner 2004)
- Roosevelt's claim "academisch fundament" wordt zichtbaar via Ulm-discipline, niet via decoratieve "academische" stijl

**Anti-pattern:** Losse icon-libraries gebruiken zonder systeemcoherentie; Lucide-icons direct importeren zonder rationalisering.

### 1.5 Gugelot + Rams / Braun (1955–1965) — *productdiscipline, modulariteit, stilte*

**Erfgoed:** Hans Gugelot (Nederlands-Zwitsers, doceerde Ulm 1954–1965), samen met Dieter Rams ontwierp hij Braun *SK4 "Schneewittchensarg"* (1956), Phonosuper, Sixtant-scheerapparaat. Gugelot's *M125*-meubelsysteem was modulair als ethiek. Rams formuleerde later de tien principes ("less, but better").

**Kernidee:** Producten zijn neutraal en terughoudend — *unobtrusive* — om ruimte te laten voor de gebruiker. Modulariteit is geen technische keuze maar een **ethische**: één basis-eenheid, vele configuraties, geen waste. Rams' tien principes: innovatief, useful, aesthetisch, understandable, unobtrusive, honest, long-lasting, thorough, environmentally-friendly, *as little design as possible*.

**Roosevelt-toepassing:**
- **Componenten zijn "Braun-stil"** — niets schreeuwt, alles werkt
- **Modulariteit** verwerkt in token-architectuur (Layer 1 → 4 in paper) is een Gugelot-M125-principe: één basis-set tokens, vele samenstellingen
- **Eerlijk materiaal:** geen fake-elevation, geen neumorphism, geen glow-effects. Schaduw alleen waar het functioneel is (modal, dropdown)
- **Long-lasting design:** geen trend-volgen (geen Memphis-revival, geen Y2K-aesthetic, geen 3D-blob-decoratie)
- **As little design as possible:** elke pixel verantwoorden — als hij weg kan, gaat hij weg

**Cross-pollinatie:** Gugelot → doceerde aan Ulm → Aicher als opvolger → systeemdesign-lijn loopt ononderbroken van Weimar 1919 naar Braun 1965 naar Roosevelt 2026. Deze ononderbroken lijn is de **historische legitimiteit** van de canon.

**Anti-pattern:** "Bold" UI met grote shadows, gradient-cards, oversized-illustraties, "vibrant" gradients als section-dividers.

---

## 2. DNA-formule Roosevelt OPS

```
  Weimar-semantiek      (kleur = pipeline-betekenis)
+ Dessau-typografie     (Bayer-strengheid, geometrisch sans)
+ De Stijl-grid         (asymmetrische orthogonaliteit, Berlage-anker)
+ Ulm-systeem           (pictogrammen als taal, niet ornament)
+ Gugelot/Rams-stilte   (modulair, eerlijk, terughoudend)
─────────────────────────────────────────────────────
= Roosevelt-Bauhaus
```

Dit is geen mood maar een **operatieve constraint**. Elk token, elk component, elke pagina wordt erop getoetst.

---

## 3. Toetsing aan Roosevelt OPS-concept

Elke designkeuze beantwoordt drie vragen:

1. **Dient dit de F0–F9 pipeline-leesbaarheid?**
2. **Versterkt dit de positionering (academisch fundament + human touch) tegenover Concentrix/Hyperion?**
3. **Is dit consistent met de stack (Next.js 14 + shadcn 4 + Tailwind 3 + Nx)?**

| Designvraag | Roosevelt-toets | Beslissing |
|---|---|---|
| Welke huistypografie? | Bayer-erfgenaam, modern, vrij beschikbaar, variable-font support, leesbaar in dashboard én adviesrapport | **Inter** (Rasmus Andersson) of **Geist Sans** (Vercel) — beide pass |
| Welk kleurpalet voor agent-rollen? | Weimar-semantiek: rood/blauw/geel als rolmarkering | Strategic=blauw, Risk=rood, Advisory=geel, Technical=zwart/grijs |
| Wat doen we met shadcn-default `rounded-md`? | De Stijl-orthogonaliteit eist scherpte | Override naar 0px voor cards, 2px voor buttons (Tailwind preset) |
| Hoe ziet F0–F9 status-indicator eruit? | Ulm-pictogram-systeem: één grid, vele varianten | 24px canvas, 2px stroke, cirkel+vierkant+diagonaal construeerbaar |
| Wat is het basale spacing-ritme? | Bauhaus 8px-grid + Gugelot-M125-modulariteit | 4px micro, 8px base, 16/24/32/48/64/96 schaal |
| Welke iconen-library? | Geen library-as-is; Ulm eist systeem | Eigen pictogram-set bouwen, geïnspireerd door Aicher; tijdelijk Lucide met strikte subset |
| Border-radius cards? | Mondriaan/Berlage = rechthoekige vlakken | `--radius-card: 0` |
| Schaduwen? | Rams "eerlijk" = alleen functionele depth | Alleen op `floating` (modal/dropdown), geen `elevation` op cards |

---

## 4. In en uit — wat de canon binnenhaalt en uitsluit

### Binnen ✓

- Inter / Geist Sans als body
- JetBrains Mono / Geist Mono voor pipeline-data
- Rood/blauw/geel als **semantische** accenten (3 kleuren, niet meer)
- Grijsschaal van 50→950 als structuurpalet
- 8px-grid spacing-systeem
- Asymmetrische lay-outs
- Scherpe of bijna-scherpe hoeken
- Witruimte als compositie-element
- Aicher-geïnspireerde pictogrammen, eigen set
- Functionele schaduwen (alleen op overlay-elementen)
- 1px en 2px borders als structurele scheiders
- Variable fonts voor performance + flexibiliteit

### Buiten ✗

- Material-Design-shadow-elevations
- Tailwind-default kleurenpaletten als-is
- Gradient-fills (paars→blauw, oranje→roze)
- `rounded-2xl` shadcn-default op cards
- Lucide-icons zonder rationalisering en subset
- Decoratieve illustraties (3D-blobs, isometric-people)
- Memphis-revival, Y2K-aesthetic, brutalist-randomness
- Neumorphism, glassmorphism, glow-effects
- Animaties als decoratie (alleen functioneel: state-change, focus, loading)
- Italics buiten werktitels
- Body-tekst in kapitalen
- "Vibrant" als productadjectief

---

## 5. Verbinding met de paper (RQ4 + Bauhaus-fideliteit)

De paper benoemt vijf Bauhaus-principes als meetbare fideliteits-metrics. Deze canon **operationaliseert** ze als designkeuzes vóór de metrics worden geëvalueerd:

| Paper-principe | Meting (uit paper) | Hoe canon dit borgt |
|---|---|---|
| Form follows function | >85% token coverage | Elke token heeft semantische rol (§1.1, §3) |
| Less is more | <50 custom rules | Tailwind preset overschrijft shadcn waar canon dat eist; geen ad-hoc CSS (§1.5) |
| Ehrliche Materialien | 100% DTCG-conform | Tokens tonen wat ze zijn, geen magic values (§1.5) |
| Modulariteit | 0 circular deps | Atomic design + Gugelot-M125 (§1.5, four-layer token-architectuur) |
| Gesamtkunstwerk | <5% visuele diff | Canon is de eenheid die deze coherentie waarborgt over F0–F9 + adviesrapport + intake |

---

## 6. Referenties (voor moodboard / DSR-paper)

**Visueel:**
- Herbert Bayer, *Universal*-typografie (1925)
- László Moholy-Nagy, Bauhaus-catalogus Dessau (ca. 1929)
- Piet Mondriaan, *Composition with Red, Blue, and Yellow* (1930)
- Gerrit Rietveld, Rood-blauwe stoel (1918), Schröderhuis (1924)
- H.P. Berlage, Beurs van Berlage (1898–1903), Amsterdam
- Otl Aicher, München 1972 Olympische pictogrammen
- Hans Gugelot + Dieter Rams, Braun SK4 "Schneewittchensarg" (1956)
- Hans Gugelot, M125 modulair meubelsysteem (1956)

**Literatuur:**
- Itten, J. (1961). *Kunst der Farbe*.
- Kandinsky, W. (1926). *Punkt und Linie zu Fläche*.
- Rams, D. *Ten Principles for Good Design* (Braun, 1976–1985).
- Hevner, A. (2004). *Design Science in Information Systems Research*. — paper-anker.
- Peffers, K. et al. (2007). *Design Science Research Methodology*.

**Online bronnen (gebruikt voor dit document):**
- [Bayer Universal Typeface — Encyclopedia of Design](https://encyclopedia.design/2023/01/10/herbert-bayer-universal-typeface/)
- [Bauhaus Color Theory — Getty](https://www.getty.edu/research/exhibitions_events/exhibitions/bauhaus/new_artist/form_color/color/)
- [Mondrian Composition — Smarthistory](https://smarthistory.org/mondrian-composition-ii-in-red-blue-and-yellow/)
- [Hans Gugelot: The Architecture of Design — HfG-Archiv Ulm](https://hfg-archiv.museumulm.de/en/exhibition/hans-gugelot-100-en/)
- [Aicher's Munich pictograms — Eye Magazine](https://eyemagazine.com/blog/post/this-sporting-myth)
- [Dieter Rams 10 Principles — Braun](https://www.braun-audio.com/en-FR/10principles)
- [Berlage Beurs — Arch Journey](https://archjourney.org/projects/beurs-van-berlage/)

---

## 7. Status & volgende stappen

Dit canon-document is **laag 1: visuele filosofie**. Volgende lagen worden hier rechtstreeks aan getoetst:

- **Laag 2 — Tokens** (deel A: kleur, deel B: typografie, deel C: spacing/grid). Volgt direct uit §3 en §4.
- **Laag 3 — Atomen** (button, input, badge, icon-base). Concrete shadcn-overrides op basis van canon.
- **Laag 4 — Moleculen** (status-badge F0–F9, agent-card, pipeline-step-indicator). Combinaties van atomen.
- **Laag 5 — Governance** (ADR-020, review-cadence, DTCG-build-pipeline).

ADR-020 zal naar dit document verwijzen als **bron-van-waarheid** voor alle designbeslissingen.

---

*Einde document v0.1*
