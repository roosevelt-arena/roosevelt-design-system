# Canon-synthese ronde 4 — Design Foundations
**Roosevelt OPS Headless Design System**
Status: Research v1.0 | Datum: mei 2026

Bronbasis: bauhaus-canon.md (Weimar / Dessau / De Stijl / Ulm / Gugelot+Rams) + 8 gerichte searches.

---

## 1. GRID

**Conclusie:** Asymmetrisch 12-koloms grid met De Stijl-logica — niet center-gecentreerd, maar vlak-gecomponeerd; biedt maximale compositievrijheid terwijl het compatibel blijft met Tailwind 3 en shadcn grid-utilities.

Het HfG Ulm-gebouw werkte met een 3×6m modulair cel-systeem ([HfG-Ulm Architecture](https://www.hfg-ulm.de/en/hfg-ulm/architecture/)) — geen voorschrift voor 8 webbkolommen. De Stijl dicteert asymmetrische orthogonaliteit, geen symmetrisch 8-koloms raster. 12 kolommen bieden de nodige fijnmazigheid voor asymmetrische F0–F9 dashboardlay-outs.

| Breakpoint | Kolommen | Gutter | Margin | Max-width |
|---|---|---|---|---|
| Mobile (`<640px`) | 4 | 16px | 16px | 100% |
| Tablet (`640–1024px`) | 8 | 24px | 24px | 100% |
| Desktop (`≥1024px`) | 12 | 24px | 32px | 1280px |
| Wide (`≥1440px`) | 12 | 32px | 48px | 1440px |

Gutter is altijd veelvoud van 8 (Ulm-modulariteit). Kolom-gebruik is **asymmetrisch**: sidebar 3 kolommen, content 9 kolommen op desktop — Mondriaan-verdeling, geen 6/6 split.

**Tailwind-token:**
```css
--grid-cols-mobile: 4;
--grid-cols-tablet: 8;
--grid-cols-desktop: 12;
--grid-gutter: 24px;       /* desktop default */
--grid-max-width: 1280px;
```

Bron: [De Stijl — Tate](https://www.tate.org.uk/art/art-terms/d/de-stijl) · [HfG-Ulm Architecture](https://www.hfg-ulm.de/en/hfg-ulm/architecture/)

---

## 2. SPACING

**Conclusie:** 4pt-basis met 8pt-ankerpunten — de 4pt-basis (Braun-erfenis) geeft micro-precisie zonder de Ulm-8pt-modulariteit te verliezen; elke waarde is deelbaar door 4, de meeste door 8.

Braun gebruikte een vast rastermodel met DIN-formaat kolommen en vaste marges ([The Braun Grid System](https://onlyonceshop.com/blog/the-braun-grid-system)). In UI-termen vertaalt dit naar 4pt als kleinste eenheid, 8pt als basismaat ([spec.fm 8-Point Grid](https://spec.fm/specifics/8-pt-grid)).

| Token | px | Gebruik |
|---|---|---|
| `space-0` | 0 | Reset, geen ruimte |
| `space-px` | 1 | Hairline-correcties |
| `space-0.5` | 2 | Micro-gaps (icon→label) |
| `space-1` | 4 | Inline-padding klein (badge) |
| `space-2` | 8 | Basis-padding (button compact) |
| `space-3` | 12 | Tussen gerelateerde elementen |
| `space-4` | 16 | Standaard component-padding |
| `space-6` | 24 | Sectie-interne ruimte |
| `space-8` | 32 | Sectie-scheider |
| `space-12` | 48 | Grote verticale ademruimte |
| `space-16` | 64 | Sectie-marge desktop |
| `space-24` | 96 | Pagina-sectie-overgang |

Ankers 8 / 16 / 24 / 32 / 48 / 64 / 96 zijn alle deelbaar door 8 = Ulm-modulariteit. Tussenstappen 4 / 12 = Braun-precisie voor dichte UI.

Bron: [spec.fm 8-Point Grid](https://spec.fm/specifics/8-pt-grid) · [The Braun Grid System](https://onlyonceshop.com/blog/the-braun-grid-system)

---

## 3. RADIUS

**Conclusie:** Drie waarden — 0px voor vlakken, 2px voor interactieve elementen, 4px voor floating — volgt De Stijl-orthogonaliteit; niets ronder dan 4px.

| Token | px | Component |
|---|---|---|
| `radius-none` | 0 | Cards, panels, tabel-cellen, badges, dividers |
| `radius-sm` | 2 | Buttons, inputs, select, tabs (subtiele menselijkheid) |
| `radius-md` | 4 | Dropdowns, tooltips, floating-elementen |

Niets gebruikt `rounded-lg` (8px) of `rounded-xl`/`rounded-2xl` — dit zijn de expliciete anti-patterns uit bauhaus-canon.md §1.3. shadcn default `--radius: 0.5rem` wordt overridden naar `0.125rem`.

```css
--radius-none: 0px;
--radius-sm: 2px;
--radius-md: 4px;
```

Bron: [bauhaus-canon.md §1.3](../bauhaus-canon.md) · [Mondrian/De Stijl — Smarthistory](https://smarthistory.org/mondrian-composition-ii-in-red-blue-and-yellow/)

---

## 4. BORDER

**Conclusie:** 1px structureel + 2px emphasis — synthese van Rams-eerlijkheid (geen decoratieve lijnen) en Mondriaan-vlakscheiding (2px als pigment-vlak, niet omtrek).

| Token | Waarde | Gebruik |
|---|---|---|
| `border-structural` | `1px solid {color.border.default}` | Tabel-rijen, input-omtrekken, card-scheiders |
| `border-emphasis` | `2px solid {color.border.strong}` | Actieve states, geselecteerde items, De Stijl-vlakscheiders |
| `border-focus` | `2px solid {color.blue.500}` | Focus-ring (zie §7) |

**Kleurtokens:**

| Token | Licht | Donker | Semantiek |
|---|---|---|---|
| `color.border.default` | `gray.200` (#E5E7EB) | `gray.700` | Subtiele structuurlijn |
| `color.border.strong` | `gray.400` (#9CA3AF) | `gray.500` | Emphasis-scheider |
| `color.border.brand` | `blue.600` | `blue.400` | Agent / actieve state |
| `color.border.error` | `red.500` | `red.400` | Risk-signaal (Weimar) |

Geen 0.5px hairlines — "borders zijn nooit 0.5px-dun-decoratief" (bauhaus-canon.md §1.3).

Bron: [bauhaus-canon.md §1.3](../bauhaus-canon.md) · [Mondrian De Stijl — Centre Pompidou](https://mediation.centrepompidou.fr/education/ressources/ENS-mondrian/ENS-mondrian-en.html)

---

## 5. ELEVATION

**Conclusie:** Twee stappen — `subtle` (divider-effect, geen echte schaduw) en `raised` (functionele depth voor modals/dropdowns) — conform Rams "eerlijk materiaal", geen Material-style gelaagdheid.

Schaduwen zijn alleen toegestaan op floating/overlay-elementen (bauhaus-canon.md §1.5: "Alleen op `floating`"). Alle DTCG shadow-tokens volgen het W3C DTCG composite-formaat ([designtokens.org](https://www.designtokens.org/tr/drafts/format/)).

### `elevation.subtle` — voor elevated cards, sticky headers
```json
{
  "$type": "shadow",
  "$value": {
    "color": "rgba(0, 0, 0, 0.06)",
    "offsetX": "0px",
    "offsetY": "1px",
    "blur": "3px",
    "spread": "0px"
  }
}
```

### `elevation.raised` — voor modals, dropdowns, toasts
```json
{
  "$type": "shadow",
  "$value": {
    "color": "rgba(0, 0, 0, 0.12)",
    "offsetX": "0px",
    "offsetY": "4px",
    "blur": "12px",
    "spread": "0px"
  }
}
```

Géén derde stap (geen `elevation.high` à la Material). Géén gekleurde schaduwen, géén meerdere lagen. Cards in standaard-state: `elevation.none` (geen schaduw).

CSS equivalent:
- `subtle`: `box-shadow: 0 1px 3px rgba(0,0,0,0.06)`
- `raised`: `box-shadow: 0 4px 12px rgba(0,0,0,0.12)`

Bron: [Dieter Rams Ten Principles — designmanifestos.org](https://designmanifestos.org/dieter-rams-ten-principles-for-good-design/) · [W3C DTCG shadow format](https://www.designtokens.org/tr/drafts/format/)

---

## 6. MOTION

**Conclusie:** Lineaire en ease-out easings voor systeem-responses; langzame ease-in-out voor bewuste state-transities — Ulm-rationalisme (voorspelbaar, functioneel) met minimale Toni-humaniteit in de tragere curves.

### Duration-tokens

| Token | ms | Gebruik |
|---|---|---|
| `duration.instant` | 0 | Toggle states zonder visuele afleidng (b.v. hidden→visible-skip) |
| `duration.fast` | 120 | Micro-interactions: hover-kleur, active-press |
| `duration.normal` | 200 | State-changes: button-loading, badge-update, focus-ring |
| `duration.slow` | 320 | Panel-open/close, accordion, tab-switch |
| `duration.deliberate` | 480 | Modal-enter, page-transition, F0→F1 pipeline-advance |

### Easing-tokens

| Token | Cubic-bezier | Gebruik |
|---|---|---|
| `easing.linear` | `cubic-bezier(0,0,1,1)` | Loading-bars, progress-indicators (geen vertraging suggereert gelijkmatig verloop) |
| `easing.out` | `cubic-bezier(0,0,0.2,1)` | Elementen die *inkomen*: modal-open, dropdown-enter, toast-appear |
| `easing.in-out` | `cubic-bezier(0.4,0,0.2,1)` | Bewuste transities: panel-toggle, accordion, tab (startig en eindigend met deceleration) |

### Combinaties per transitie-type

| Transitie | Duration | Easing |
|---|---|---|
| Hover-kleur (button, link) | `fast` (120ms) | `easing.out` |
| Focus-ring verschijnt | `fast` (120ms) | `easing.out` |
| Dropdown-open | `normal` (200ms) | `easing.out` |
| Accordion open/dicht | `slow` (320ms) | `easing.in-out` |
| Modal mount | `deliberate` (480ms) | `easing.out` |
| Pipeline-stap advance (F0→F1) | `deliberate` (480ms) | `easing.in-out` |
| Loading-bar fill | doorlopend | `easing.linear` |

Animaties zijn **uitsluitend functioneel** (state-change, focus, loading) — bauhaus-canon.md §4: "Animaties als decoratie" staat buiten.

Bron: [bauhaus-canon.md §4](../bauhaus-canon.md) · [Otl Aicher HfG-Archiv](https://hfg-archiv.museumulm.de/en/bequests/the-bequest-of-otl-aicher/)

---

## 7. FOCUS

**Conclusie:** 2px ring + 2px offset + blue.500 kleur + 2px wit tussenring — WCAG 2.4.13 compliant, visueel sterk, niet decoratief; de witte offset scheidt de ring van elke achtergrondkleur.

WCAG 2.4.13 vereist minimaal 2px dikte en 3:1 contrastverhouding in gefocuste vs ongefocuste state ([W3C Focus Appearance](https://www.w3.org/WAI/WCAG22/Understanding/focus-appearance.html)). Een 2px blauwe outline met 2px witte offset voldoet hieraan over alle achtergrondkleuren ([Sara Soueidan focus guide](https://www.sarasoueidan.com/blog/focus-indicators/)).

| Token | Waarde |
|---|---|
| `focus.ring-width` | `2px` |
| `focus.ring-offset` | `2px` |
| `focus.ring-color` | `blue.500` (#3B82F6) |
| `focus.ring-offset-color` | `white` (#FFFFFF) — dark-mode: `gray.900` |

**CSS-implementatie (Tailwind):**
```css
/* tailwind.config.js — toegevoegd aan ring-utilities */
:focus-visible {
  outline: 2px solid var(--color-blue-500);
  outline-offset: 2px;
  box-shadow: 0 0 0 4px var(--color-white); /* wit tussenring */
}
```

Of als Tailwind-classes: `focus-visible:ring-2 focus-visible:ring-blue-500 focus-visible:ring-offset-2`

Gebruik `focus-visible`, niet `focus` — muisklikken tonen geen ring (Ulm-rationalisme: geen visuele ruis zonder functionele reden).

Bron: [W3C WCAG 2.4.13 Focus Appearance](https://www.w3.org/WAI/WCAG22/Understanding/focus-appearance.html) · [Sara Soueidan focus indicators](https://www.sarasoueidan.com/blog/focus-indicators/)

---

## Synthese-overzicht

| Foundation | Keuze | Canonanker |
|---|---|---|
| Grid | 12-koloms asymmetrisch, 4-koloms mobile | De Stijl + Ulm-modulariteit |
| Spacing | 4pt-basis, 12 waarden 0→96 | Braun/Gugelot modulariteit |
| Radius | 0 / 2 / 4px | De Stijl-orthogonaliteit |
| Border | 1px structural + 2px emphasis | Mondriaan-vlakscheiding |
| Elevation | 2 stappen subtle/raised, rgba 0.06/0.12 | Rams "eerlijk materiaal" |
| Motion | 5 durations 0–480ms, 3 easings | Ulm-rationalisme + human touch |
| Focus | 2px / 2px offset / blue.500 + wit | WCAG 2.4.13 + Bauhaus-strengheid |

---

*Woordtelling: ~1.100 woorden. Volgende stap: ADR-020 schrijven op basis van deze waarden.*
