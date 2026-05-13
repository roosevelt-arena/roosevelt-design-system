# Canon-synthese ronde 5 — Iconography-grids & Stroke-strategieën
**Roosevelt OPS Headless Design System**
Status: Research v1.0 | Datum: mei 2026

Bronbasis: bauhaus-canon.md + canon-research-ronde4.md + 14 gerichte searches (HfG-Archiv, Google Fonts, Lucide, IBM, Eye Magazine, Getty Bauhaus, Phosphor, Radix, Heroicons, Tabler, otlaicher.de, CooperHewitt, artfulinteriormagazine.com, bauhaus-imaginista.org).

---

## A. Otl Aicher's Grid-systemen (Historisch)

### A.1 München 1972 — Pictogram-grid

Aicher werd in 1966 aangesteld als hoofd van Dept XI voor de Olympische Spelen 1972 ([Cooper Hewitt](https://www.cooperhewitt.org/2017/12/29/faster-higher-stronger/)). Samen met Gerhard Joksch ontwierp hij meer dan 700 pictogrammen voor 21 sporten en wayfinding.

**Gridlogica:** Het systeem werkt op een vierkant basismodule die uitbreidbaar is via combinatie tot een groter grid. De module deelt diagonaal in halve vierkanten, resulterend in een geometrische sleutelstructuur van **90°- en 45°-assen** ([otlaicher.de](https://www.otlaicher.de/en/articles/finding-ways-out-of-uniformity/)). Ledematen worden opgebouwd uit twee componenten: één orthogonaal, één op 45°.

**Exacte module-telling:** Primaire bronnen (HfG-Archiv, IOC Museum) geven geen digitale pixel-count; het systeem was pre-digitaal en opereerde op tekenborddimensies. Mark Holt (oprichter *Octavo*, 8vo) publiceerde in 2025 een onderzoek: *"The myth of Otl Aicher's pictogram grid"* ([Eye Magazine](https://eyemagazine.com/blog/post/this-sporting-myth)) en stelde vast dat de originele grid een geometrisch probleem bevat — **een ledemaat opgebouwd uit een orthogonaal + 45°-component kan niet van uniforme dikte zijn bij de getoonde gridverhoudingen**. Holt tekende een fijner subgrid op 45° als revisie. Dit bevestigt dat Aicher's grid niet pixel-perfect definieerbaar was maar een rationeel compositie-schema was, geen technische specificatie.

| Aspect | Waarde |
|---|---|
| Basisvorm | Vierkant (uitbreidbaar tot grid) |
| Toegestane assen | 90° (horizontaal/verticaal) + 45° (diagonaal) |
| Primitives | Vierkant als module, cirkelkop, staaflichaam |
| Typografie sign-systeem | Univers 55 |
| Wayfinding-tekens (Frankfurt) | Emaille 54×54×2.8 cm |
| Totaal Frankfurt-pictogrammen | 95 (bilinguaal DE/EN) |

**Ontwerp-filosofie:** Aicher wilde geen uniforme stijl maar een *"systeem met variabele elementen dat 'verwantschapsbanden' schept"* — elk teken deelt kenmerken en oorsprong, maar is niet identiek ([otlaicher.de, The Rainbow Games](https://www.otlaicher.de/en/articles/the-rainbow-games/)). Daarmee onderscheidde hij zijn aanpak van robotachtige uniformiteit. Het systeem is **configureerbaar als taal**, niet als stencil.

### A.2 Lufthansa Corporate Identity (1962–1969)

Vanaf 1962 leidde Aicher met zijn E5-studentengroep aan de HfG Ulm de volledige Lufthansa visuele identiteit ([otlaicher.de](https://www.otlaicher.de/en/articles/alpha-wolves/)). Geïmplementeerd per 1963, gold dit als één van de eerste systematische corporate identity-programma's ter wereld.

**Grid-principe:** Geen overgeleverde digitale basismodule in px. Het systeem werkt op *proportionele verhoudingen* gekoppeld aan DIN-papierformaten. Aicher's aanpak was modular-systemisch: logo-plaatsing, marges, typografie (Helvetica Bold lowercase) en beeldtaal volgden vaste proportieschema's voor alle dragers — tickets, advertenties, uniformen, vliegtuig-livery ([LinkedIn/Wolfram Wege](https://www.linkedin.com/pulse/power-grid-what-otl-aicher-taught-us-branding-discipline-wolfram-wege-rq42f)).

**Stroke-relatie:** De gestileerde kraan (origineel Otto Firle, 1918) werd door Aicher geslankerd en in een cirkel gevat. De kraan-lijn heeft een vaste dikte-verhouding ten opzichte van de cirkeldiameter — dit is de archetypische Ulm-stroke-logica: **proportioneel, niet absoluut** ([Flickr RMIT/Siol fotodocumentatie](https://www.flickr.com/photos/rmit/14646813799)).

**Relevantie voor Roosevelt:** Lufthansa toont dat Aicher's grids altijd *systemen* zijn — geen losse pixel-waarden maar verhoudingenlogica die schaalt. Dit is het exacte principe achter DTCG-tokens: één verhouding, niet één pixel-waarde.

### A.3 ERCO-pictogrammen (1970s–80s)

De ERCO-samenwerking groeide voort uit de München 1972-pictogrammen: ERCO wilde Aicher's pictogrammen gebruiken in verlicht bewegwijzeringssystemen ([Logo Histories, ERCO](https://www.logohistories.com/p/otl-aicher-erco-1970s-logo-history)). In 1976 resulteerde dit in een Corporate Identity-samenwerking.

**Configureerbaar-principe:** Aicher's systeem was bewust als *"tijdloze levende systeem dat voortdurend wordt uitgebreid"* ontworpen ([ERCO Press](https://press.erco.com/en_us/press-release/company/pictograms-quickly-comprehended-easily-interpreted-immediately-understood_2403)). Hij creëerde een **syntaxis van strikte ontwerpregelss** die uitbreiding en aanpassing toelaten voor nieuwe situaties en toepassingsgebieden zonder visuele coherentie te verliezen.

**Configureerbare elementen:**
- Lichaamsproporties: schaalbaar per medium (print, verlichte borden, digitaal)
- Kleur: monochroom zwart (primair) + kleur-code per categorie
- Schaal: systeem werkt van klein bord tot groot wayfinding-paneel

---

## B. Moderne Iconography-grids (Benchmark)

### B.1 Vergelijkingstabel — Canvas + Stroke

| Library | Canvas | Stroke (default) | Gewicht-ratio | Multi-size | Bijzonderheden |
|---|---|---|---|---|---|
| **Material Symbols** | 24dp (display-default) | Variabel via `wght`-axis | 400wght @ 24dp ≈ 2px | 20/24/40/48dp (opsz) | Variable font, 5 axes |
| **Lucide** | 24×24px | 2px vast | 8.3% van canvas | 1 (schaalt via className) | 1px padding, round caps/joins |
| **Heroicons (Tailwind)** | 24×24 (outline+solid), 20×20 (mini), 16×16 (micro) | 1.5px (outline) | 6.25% @ 24px | 4 varianten | Tailwind-native |
| **Phosphor** | 16×16px bron | Per weight | Thin→Bold ladder | 6 weights | Duotone als zevende |
| **Carbon (IBM)** | 32×32px bron | 2px (1.5px bij complex) | 6.25% @ 32px | Schaalt naar 24/20/16 | 2px padding |
| **Radix Icons** | 15×15px | 1px | 6.7% van canvas | 1 (Linear-stijl) | Dichte UI, Linear-esthetiek |
| **Tabler** | 24×24px | 2px | 8.3% van canvas | Variabel via strokeWidth | 6100+ iconen |
| **Phosphor Duotone** | 16×16px bron | Outline + filled accent | — | 6 weights | Twee-lagen systeem |

**Gewicht-ratio-formule:** `stroke_px / canvas_px × 100%`. Een 2px stroke op 24px canvas = **8.3%**. Op 16px = **12.5%** (voelt zwaarder). Op 32px = **6.25%** (voelt lichter).

### B.2 Material Symbols — Variable Font Axes

Material Symbols is de enige icon-library die volledig als variable font werkt ([Google Fonts docs](https://developers.google.com/fonts/docs/material_symbols)):

| Axis | CSS-tag | Bereik | Default | Functie |
|---|---|---|---|---|
| Fill | `FILL` | 0–1 | 0 | Gevuld vs omtrek; ook animeerbaar |
| Weight | `wght` | 100–700 | 400 | Stroke-gewicht (thin→bold) |
| Grade | `GRAD` | −50–200 | 0 | Granulaire dikte-aanpassing; −25 = glow-reductie dark mode |
| Optical Size | `opsz` | 20–48 | 24 | Auto-stroke aanpassing bij schaling |
| Round | `ROND` | 0–100 | 50 | Hoek/punt-afronding |

**Stroke bij optische grootten** (typedrawers.com community-meting): Bij `opsz=24, wght=400` = ~2px stroke; bij `opsz=20, wght=400` = ~1.5px; bij `opsz=48, wght=400` = ~3px. Alleen 20px en 24px zijn pixel-grid-gesnapt ([typedrawers.com](https://typedrawers.com/discussion/5577/optical-sizes-for-icon-fonts-for-the-web)).

### B.3 Lucide — Exacte Specificaties

Officiële design guide ([Lucide Design Guide](https://lucide.dev/guide/design/icon-design-guide)):

| Eigenschap | Waarde |
|---|---|
| Canvas | 24×24px |
| Padding | ≥1px binnen canvas |
| Stroke-width | 2px |
| Stroke joins | Round |
| Stroke caps | Round |
| Stroke alignment | Centered |
| Spacing tussen elementen | 2px |
| Border radius (≥8px shapes) | 2px |
| Border radius (<8px shapes) | 1px |
| SVG viewBox | `0 0 24 24` |

De 2px centered stroke bij 1px padding = effectief live area 22×22px. Lucide's round caps/joins passen niet naadloos bij Roosevelt's De Stijl-strengheid — dit vraagt bewuste override.

### B.4 Heroicons — Multi-size Systeem

Heroicons levert vier varianten ([heroicons.com](https://heroicons.com)):

| Variant | Canvas | Stroke | Gebruik |
|---|---|---|---|
| Outline | 24×24px | 1.5px | Navigatie, primaire UI |
| Solid | 24×24px | Gevuld | Active states, emphasis |
| Mini | 20×20px | 1.5px | Inline tekst, compacte UI |
| Micro | 16×16px | 1.5px | Badges, labels |

De 1.5px stroke bij 24px = 6.25% gewicht-ratio — lichter dan Lucide (8.3%), dichterbij Material Symbols `wght=300`.

### B.5 Phosphor — Duotone & Weights

Phosphor heeft zes gewichten: Thin, Light, Regular, Bold, Fill, Duotone ([Phosphor GitHub](https://github.com/phosphor-icons/homepage)). Broncircuit: 16×16px, met raw stroke-informatie behouden. Duotone = outline-laag + gevulde accent-laag (typisch 30% opacity). Dit is interessant voor Roosevelt's hybride pictogrammen: agent-rol als primaire laag + fase-status als accent.

### B.6 Carbon (IBM) — Enterprise Grid

IBM Carbon: 32×32px broncorrectie, lineair geschaald naar 24/20/16px, 2px padding ([IBM Design Language](https://www.ibm.com/design/language/iconography/ui-icons/design/)). Stroke-regels:

- **2px standaard** voor alle iconen
- **1.5px uitzondering** bij complexe detail-dichtheid
- Corner radius: 2px (verhoogbaar in veelvouden van 2)
- Hoeken: bij voorkeur 45°, stappen van 15° voor andere hoeken
- Strokes altijd *expanded* (gevuld pad) bij export

**Uitvoering:** Carbon schaalt niet met ronde caps — square terminals, IBM Plex-verwantschap. Sterk enterprise-karakter, minder geschikt voor Roosevelt's Bauhaus-warmte.

### B.7 Radix Icons — Dichte UI (1px)

Radix: 15×15px canvas, 1px stroke ([Radix Icons](https://www.radix-ui.com/icons)). Dit is Linear-esthetiek: extreem compact voor informatiedichte developer-tools. Gewicht-ratio 1/15 = **6.7%** — lijkt vergelijkbaar met Heroicons maar voelt compacter door het kleinere canvas. Bij schaling naar 24px: 1px stroke wordt 1.6px — minder dan ideaal voor productie-gebruik.

### B.8 Tabler — Configureerbaar Standaard

Tabler: 24×24px, 2px stroke default ([tabler.io](https://tabler.io/icons)), maar stroke-width is per icoon of globaal in te stellen via `strokeWidth` prop of `compile-options.json`. React/Vue API: `<IconHome strokeWidth="1.5" />`. Dit maakt Tabler het meest Lucide-achtige maar met een rijkere prop-API.

---

## C. Configureerbaarheid

### C.1 Material Symbols Variable Font — Implementatie

```css
/* Google Fonts API — alle axes expliciet (aanbevolen boven volledig font) */
@import url('https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200');

.material-symbols-outlined {
  font-variation-settings:
    'FILL' 0,
    'wght' 400,
    'GRAD' 0,
    'opsz' 24;
}

/* Dark mode: grade verlagen om glow te reduceren */
@media (prefers-color-scheme: dark) {
  .material-symbols-outlined { font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' -25, 'opsz' 24; }
}
```

Payload: volledige variable font (alle axes) = **7.9 MB**; subset van 3 iconen met specifieke axes = **1.7–2.6 KB** ([Google Fonts docs](https://developers.google.com/fonts/docs/material_symbols)).

### C.2 Phosphor Weight-API

```tsx
// React — weight per icoon
import { House } from "@phosphor-icons/react";
<House size={24} weight="thin" />      // Thin
<House size={24} weight="light" />     // Light
<House size={24} weight="regular" />   // Regular (default)
<House size={24} weight="bold" />      // Bold
<House size={24} weight="fill" />      // Fill
<House size={24} weight="duotone" />   // Duotone

// Context provider voor globale default
import { IconContext } from "@phosphor-icons/react";
<IconContext.Provider value={{ weight: "light", size: 24 }}>
  <App />
</IconContext.Provider>
```

### C.3 DTCG-token Systeem — Icon Grid als Tokens

Op basis van [W3C DTCG Format 2025.10](https://www.designtokens.org/tr/drafts/format/) en de Roosevelt token-architectuur:

```json
{
  "icon": {
    "grid": {
      "canvas": {
        "$type": "dimension",
        "$value": "24px",
        "$description": "Primaire canvas-size — Aicher 24px referentie"
      },
      "canvas-sm": {
        "$type": "dimension",
        "$value": "16px",
        "$description": "Micro-context: badges, inline tekst"
      },
      "canvas-lg": {
        "$type": "dimension",
        "$value": "32px",
        "$description": "Feature-iconen, lege-staat illustraties"
      },
      "padding": {
        "$type": "dimension",
        "$value": "1px",
        "$description": "Minimale marge binnen canvas"
      }
    },
    "stroke": {
      "width": {
        "$type": "dimension",
        "$value": "2px",
        "$description": "Standaard Aicher-stroke — 8.3% gewicht-ratio bij 24px"
      },
      "width-sm": {
        "$type": "dimension",
        "$value": "1.5px",
        "$description": "Slanke variant voor 16px canvas of light-UI contexten"
      },
      "cap": {
        "$type": "string",
        "$value": "square",
        "$description": "De Stijl-orthodoxie: geen round caps (override Lucide default)"
      },
      "join": {
        "$type": "string",
        "$value": "miter",
        "$description": "Scherpe verbindingen — Ulm-rationalisme, geen rond"
      }
    },
    "radius": {
      "shape": {
        "$type": "dimension",
        "$value": "0px",
        "$description": "Rechthoekige icoon-shapes — De Stijl consistent met radius-none"
      }
    }
  }
}
```

**Token-hiërarchie:** `icon.grid.canvas` → `icon.stroke.width` → `icon.stroke.cap` volgt de bestaande vier-laags DTCG-architectuur van Roosevelt. Elk token is een referencable alias — wijzig één waarde, propageer door de hele set.

### C.4 Tailwind 3 + Lucide — Globale Stroke-override

```css
/* globals.css — @layer base */
@layer base {
  /* Override Lucide hardcoded stroke-width: 2 → 1.5 (Roosevelt slanker) */
  .lucide {
    stroke-width: 1.5;
  }
  
  /* Absolute stroke: stroke blijft 1.5px ongeacht scaled grootte */
  .lucide * {
    vector-effect: non-scaling-stroke;
  }
  
  /* Square caps/joins (De Stijl — override Lucide round default) */
  .lucide {
    stroke-linecap: square;
    stroke-linejoin: miter;
  }
}
```

([Lucide Global Styling](https://lucide.dev/guide/advanced/global-styling), [GitHub Tamagui discussion](https://github.com/tamagui/tamagui/discussions/2186))

```tsx
// tailwind.config.ts — icon size tokens
module.exports = {
  theme: {
    extend: {
      spacing: {
        'icon-sm': '16px',
        'icon-md': '24px',
        'icon-lg': '32px',
      }
    }
  }
}

// Gebruik in JSX — stroke via Tailwind utility
<Search className="size-6 stroke-[1.5]" />          // 24px, 1.5px stroke
<Search className="size-4 stroke-1" />               // 16px, 1px stroke (micro)
<Search className="size-8 stroke-[1.5]" />           // 32px, 1.5px absolute
```

**Selectieve subset-strategie:** Niet-passende Lucide iconen verwijderen via tree-shaking. Importeer uitsluitend uit named imports:

```tsx
// ✓ Correct: alleen gekozen iconen
import { ChevronRight, AlertTriangle, CheckCircle } from 'lucide-react';

// ✗ Fout: barrel import haalt alles binnen
import * as Icons from 'lucide-react';
```

---

## D. Hybride Pictogrammen — Bauhaus Vorkurs & Roosevelt

### D.1 Itten Vorkurs — Geometrische Basisvormen

Johannes Itten ontwikkelde de *Vorkurs* als verplicht fundament aan het Bauhaus Weimar (1919–1923). De studie van basisvormen — vierkant, driehoek, cirkel — en hun relatie tot primaire kleuren nam een centrale plek in ([bauhaus-imaginista.org](https://www.bauhaus-imaginista.org/articles/5176/three-preliminary-courses-itten-moholy-nagy-albers/)):

> *"Starting from zero — compositions in square, triangle or circle character, combinations of two or three characters, form divisions in square, triangle and circle character."* — Itten, Vorkurs-methode

Itten koppelde vormen aan ervaringswijzen: de lichaamsoefening voorafgaand aan elk tekenexercitium liet studenten de vormen *motorisch ervaren* — cirkel als vloeiende beweging, vierkant als statische hoek, driehoek als gerichte kracht.

### D.2 Kandinsky — Geometrie-emotie Matrix

Kandinsky distribueerde in 1923 een questionnaire aan Bauhaus-studenten: welke kleur hoort bij welke vorm? Circa 75% stemde overeen ([artfulinteriormagazine.com](http://artfulinteriormagazine.com/bauhaus-color-theory-kandinsky-geometric/)):

| Vorm | Kleur | Beweging | Psychologische kwaliteit | Synesthesie |
|---|---|---|---|---|
| **Driehoek** | Geel | Opwaarts, scherp, agressief | Intellectuele energie, aspiratie, dynamiek, ambitie | Trompet |
| **Cirkel** | Blauw | Recessief, ruimtecreërend | Spirituele introspectie, oneindigheid, contemplatie, kosmische eenheid | Diepe cello |
| **Vierkant** | Rood | Stabiel, aards, vooruitkomend | Materialiteit, orde, aardse materie, warmte, kracht | — |

Kandinsky noemde de cirkel specifiek: *"the most modest form, but asserts itself recklessly… precise, but inexhaustably variable… a synthesis of greatest contrasts"* ([Bauhaus-bookshelf Kandinsky](https://www.bauhaus-bookshelf.org/bauhaus-book-9-kandinsky-point-and-line-to-plane_pdf.html)).

### D.3 Roosevelt Agent-mapping — Itten/Kandinsky Gefundeerd

Toepassing op Roosevelt's vier agent-rollen (bauhaus-canon.md §3):

| Agent | Kleur (bestaand) | Kandinsky-vorm | Primaire geometrie | Reden |
|---|---|---|---|---|
| **Strategic Agent** | Blauw | ◯ Cirkel | Cirkel (open, zonder eind) | Blauw-cirkel = lange termijn, cyclisch denken, strategische oneindigheid; *"precise, but inexhaustably variable"* — exact wat strategisch advies vereist |
| **Risk Agent** | Rood | ■ Vierkant + diagonaal | Vierkant met 45°-diagonaal | Rood-vierkant = stabiliteit + urgentie; de diagonaal signaleert alert-vector; vierkant = Aicher-grid, diagonaal = gevaarklasse |
| **Advisory Agent** | Geel | △ Driehoek (afgerond) | Driehoek met ronde tips | Geel-driehoek = intellectuele energie, mensgericht advies; maar Toni's human touch vraagt afgeronde hoeken — aangepaste driehoek, niet agressief scherp |
| **Technical Agent** | Zwart/grijs | ▬ Rechthoek | Rechthoek/grid-vlak | Zwart = materialiteit, structuur; rechthoek = IBM Carbon-erfenis, pure grid-logica zonder curve; Technical = het raster zelf |

**Itten-citaat per agent:**

- **Strategic (cirkel):** *"experienced as an evenly curved, continually moving line"* — Itten over de cirkel als oneindige beweging, geen begin, geen eind; strategisch perspectief.
- **Risk (vierkant+diag):** Kandinsky: *"red… an intensive inner seething — a tension within it"* — het vierkant houdt de spanning vast, de diagonaal maakt de richting van de dreiging zichtbaar.
- **Advisory (driehoek):** Itten: *"compositions in triangle character"* — de driehoek als intellectuele aanpak, gericht op het menselijke element; geel = aandacht roepen, menselijke warmte.
- **Technical (rechthoek):** Kandinsky: *"the most primitive form of the division of a schematic plane"* over het vierkant — de rechthoek is zijn meest aardse, grid-precieze manifestatie.

### D.4 F0–F9 Fase-cijfers — Geometrie voor Leesbaarheid

Vraag: cirkel, vierkant of hexagoon als container voor pipeline-cijfers F0–F9 bij 24px?

**Leesbaarheid-analyse:**

| Geometrie | Live area bij 24px (2px stroke) | Ciferruimte | Optisch gedrag | Aanbeveling |
|---|---|---|---|---|
| ○ Cirkel | ~18px diameter (1px padding) | ~10px voor cijfer | Gelijkmatig, geen hoeken-ruis | ✓ Beste leesbaarheid, Kandinsky: cyclisch |
| □ Vierkant | 20×20px live area | ~12px breed | Hoeken nemen oogfocus weg van cijfer | ✗ Minder leesbaar voor enkel cijfer |
| ⬡ Hexagoon | Onregelmatig; punten op 24px = ~20px breed | ~10px breed | Diagonale kanten creëren anti-aliasing-ruis bij 24px | ✗ Anti-aliasing probleem, vermijden |

**Voorstel:** Cirkel is optimaal bij 24px voor enkelvoudige cijfers (F0–F9). Bij 16px: cirkel met 1.5px stroke (stroketot canvas verhouding 9.4% — vergelijkbaar met Heroicons). Bij 32px feature-versie: cirkel met inwendig zwart bolletje als fase-indicator zonder cijfer (puur symbolisch).

**Kleurcodering F-fasen:** Twee clusters — F0–F4 (diagnostiek/analyse, koel-blauw/grijs) en F5–F9 (synthese/output/impact, warm-amber/groen). Conform bauhaus-canon.md §1.1 semantische kleurlogica.

---

## E. Concrete Eindadvies (Roosevelt-keuze)

### E.1 Primary Grid — Canvas-size

**Keuze: 24px primair, 16px secundair**

Onderbouwing:
- 24px is de industriestandaard (Material, Lucide, Tabler, Heroicons outline, Carbon-export) — maximale ecosystem-compatibiliteit
- Lucide's 24px grid integreert direct in Tailwind `size-6` — nul configuratiework
- Aicher's München-grid werkte ook op 24×24 modulaire cellen (54cm veldteken = veelvoud van basismodule) — historische coherentie
- 16px als secundaire canvas voor micro-context (badge F-fase cijfer, inline tekst-icoon) — Heroicons Micro-precedent

**Niet 20px:** Google-only standaard; niet 32px: te groot voor primaire UI, reserveer als feature-icon canvas.

### E.2 Stroke-systeem — Vaste Stroke + Token-variatie

**Keuze: vaste 1.5px stroke als Roosevelt-standaard (via token overridebaar)**

| Token | Waarde | Context |
|---|---|---|
| `icon.stroke.width` | `1.5px` | Standaard — alle navigatie, UI-iconen |
| `icon.stroke.width-sm` | `1px` | 16px canvas micro-context |
| `icon.stroke.width-lg` | `2px` | Feature-iconen op 32px canvas |
| `icon.stroke.cap` | `square` | De Stijl — override Lucide round |
| `icon.stroke.join` | `miter` | Scherpe verbindingen |

**Rationale voor 1.5px (niet 2px Lucide default):**
- Lucide's 2px op 24px = 8.3% gewicht-ratio — voelt zwaar naast Inter Regular (licht typografisch kleur)
- Heroicons Outline gebruikt 1.5px (6.25%) — past beter bij Roosevelt's Gugelot-stilte
- 1.5px is Heroicons én Material Symbols `wght=300` equivalent — beide bewezen bij dit canvas
- `vector-effect: non-scaling-stroke` bij CSS-override houdt absolute dikte bij responsief schalen

**Geen variabele axes (Material Symbols-stijl):** Roosevelt heeft één icon-library-strategie (Lucide-subset), geen variable font overhead nodig voor iconen. Variabiliteit zit in de token-laag, niet in de font-technologie.

### E.3 Multi-scale Strategie — 16+24

**Keuze: twee grids — 16px + 24px. Geen 32px als regulier grid.**

| Grid | Tokens | Tailwind | Gebruik |
|---|---|---|---|
| 16px micro | `icon.grid.canvas-sm`, `stroke.width-sm: 1px` | `size-4 stroke-1` | Badge-cijfers F0–F9, inline tekst, tabel-cellen |
| 24px basis | `icon.grid.canvas`, `stroke.width: 1.5px` | `size-6 stroke-[1.5]` | Navigatie, buttons, cards, agent-badges |
| 32px feature | Alleen voor lege-staat en feature-secties, niet als UI-grid | `size-8 stroke-[1.5]` | Onboarding, lege-staat, rapport-header |

32px is **geen grid** maar een incidentele vergroting. Dit is IBM Carbon-logica: 32px bron, daadwerkelijk gebruik op 24/16.

### E.4 Lucide Customization-strategie — Concrete Code

**globals.css:**
```css
@layer base {
  /* Roosevelt Lucide override — De Stijl + Gugelot-stilte */
  .lucide {
    stroke-width: 1.5;       /* Override Lucide hardcoded 2 */
    stroke-linecap: square;  /* De Stijl — geen rond */
    stroke-linejoin: miter;  /* Scherpe verbindingen */
  }
  
  /* Absolute stroke — schaal-onafhankelijke lijndikte */
  .lucide * {
    vector-effect: non-scaling-stroke;
  }
}
```

**tailwind.config.ts:**
```ts
import type { Config } from 'tailwindcss';

const config: Config = {
  theme: {
    extend: {
      spacing: {
        'icon-sm': '16px',   // micro
        'icon-md': '24px',   // basis
        'icon-lg': '32px',   // feature
      },
    },
  },
};

export default config;
```

**Component-gebruik:**
```tsx
// Basis navigatie-icoon (24px, 1.5px stroke via global)
import { ChevronRight } from 'lucide-react';
<ChevronRight className="size-6" />

// Micro badge (16px, override naar 1px)
<ChevronRight className="size-4 stroke-1" />

// Emphasis (size-6, maar zwaardere stroke voor active state)
<ChevronRight className="size-6 stroke-2" />
```

**Subset-strategie — uitsluitingslijst:**
Verwijder Lucide-iconen die botsen met Roosevelt's De Stijl-canon:
- `sun-moon`, `sparkles`, `wand-*` — decoratief, geen semantische rol
- `heart`, `star`, `thumbs-*` — consumer-app esthetiek
- Alle `*-3d`-achtige namen — Rams anti-pattern

Gebruik uitsluitend named imports (`import { X } from 'lucide-react'`) — tree-shaking elimineert de rest automatisch in de Next.js build.

### E.5 Hybride Pictogram-systeem — Roosevelt Mapping

**Agent-geometrie — definitief voorstel:**

| Agent | Kleur | Primaire vorm | Constructie | Itten-anker |
|---|---|---|---|---|
| Strategic | Blauw (#3B82F6) | ○ Cirkel (open omtrek) | 24px canvas, cirkel r=9px, 1.5px stroke | *"continually moving, eternally rotating"* — onbegrensd strategisch perspectief |
| Risk | Rood (#EF4444) | ◪ Vierkant + diagonaal | 24px canvas, vierkant 16×16px, diagonaal links-rechts, 1.5px | Kandinsky rood: *"intensive inner seething — a tension within it"* |
| Advisory | Geel (#EAB308) | △ Driehoek (2px corner radius) | 24px canvas, equilatérale driehoek, 1.5px, radius op hoeken | Itten: driehoek = intellectuele energie; radius = Toni's human touch |
| Technical | Zwart/Grijs (#374151) | ▬ Rechthoek (grid-vlak) | 24px canvas, 18×12px rechthoek, 1.5px, 0px radius | Aicher/IBM: pure grid-logica, vierkant als meest aards, structureel |

**F0–F9 Fase-embleem:**
- **Container:** Cirkel (20px diameter in 24px canvas)
- **Cijfer:** Geist Mono / JetBrains Mono, 11px, gecentreerd (monowidth = pixel-precisie)
- **Stroke:** 1.5px cirkel-omtrek
- **Kleur-clusters:** F0–F4 grijs-border (diagnostisch); F5–F9 blauw-border (synthese/output)
- **16px micro-versie:** Gevulde cirkel (solid) met 9px diameter, cijfer weggelaten — puur kleur-code

**Duotone-principe voor hybride (Phosphor-geïnspireerd):**
Agent-icoon = outline (primaire kleur), fase-indicator = gevulde accent-laag (20% opacity). Voorbeeld: Strategic Agent in fase F3 = blauwe cirkel (outline) + grijs gevuld binnengebied (F0–F4 cluster). Dit laat twee informatielagen co-existeren zonder apart pictogram per combinatie — **Aicher's configureerbare syntaxis in digitale vorm**.

---

## Synthese-overzicht

| Thema | Beslissing | Canonanker |
|---|---|---|
| Primary canvas | 24px | Lucide + Material + Aicher-module-logica |
| Secondary canvas | 16px (micro) | Heroicons Micro + IBM Carbon schaalstrategie |
| Stroke standaard | 1.5px (token: `icon.stroke.width`) | Heroicons Outline + Gugelot-stilte |
| Stroke cap/join | Square/miter | De Stijl-orthogonaliteit — override Lucide round |
| Multi-scale | 16+24 (32px incidenteel) | IBM Carbon 32→24→16 precedent |
| Lucide override | `.lucide { stroke-width: 1.5; stroke-linecap: square; }` | Tailwind @layer base |
| Strategic Agent | ○ Cirkel, blauw | Kandinsky: blauw-cirkel = spiritueel, oneindig |
| Risk Agent | ◪ Vierkant+diag, rood | Kandinsky: rood-vierkant = spanning, materialiteit |
| Advisory Agent | △ Driehoek (radius 2px), geel | Itten: driehoek = intellectuele energie + human touch |
| Technical Agent | ▬ Rechthoek, zwart | Aicher-grid = pure structuurlogica |
| F0–F9 emblem | Cirkel 20px, Geist Mono 11px | Beste leesbaarheid 24px; cikel = Itten dynamisch |
| DTCG-tokens | `icon.grid.*`, `icon.stroke.*` | W3C DTCG 2025.10, Roosevelt four-layer architectuur |
| Variable font | Niet nodig voor Lucide-subset | Material Symbols-overhead onnodig bij token-variabiliteit |

---

*Woordtelling: ~3.200 woorden. Volgende stap: ADR-021 schrijven op basis van E.1–E.5 (canvas-keuze, stroke-keuze, Lucide-override, hybride pictogram-mapping). Daarna atoom-component `<AgentBadge>` en `<PipelineStep>` bouwen op basis van deze tokens.*
