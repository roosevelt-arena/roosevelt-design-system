# Colour

> Pillar: Product
> Canon-anker: [bauhaus-canon.md](../../bauhaus-canon.md) §1.1 Weimar-semantiek + §1.3 De Stijl-primairen
> Tokens: `tokens.json → color.*` (Layer 1), `semantic.color.*` (Layer 2), `pipeline.phase.*` (Layer 4)
> Stack-impact: Tailwind preset `packages/tailwind-config/colors.js` + CSS variables `:root`
> Status: v0.1 — 14 mei 2026

---

## 1. Filosofie

Kleur is in Roosevelt OPS geen decoratie maar **semantiek**. Itten leerde in zijn *Vorkurs* dat elke kleur een psychologische rol heeft; Kandinsky koppelde primaire kleuren aan elementaire vormen (geel-driehoek scherp, rood-vierkant statisch, blauw-cirkel oneindig). Mondriaan en De Stijl reduceerden de gehele compositie tot primairen plus zwart-wit-grijs als structuur.

Voor Roosevelt betekent dit: drie primaire kleuren (rood, blauw, geel) krijgen een vaste rol in de F0–F9 pipeline en mogen niet decoratief worden ingezet. De grijsschaal levert structuur — niet warmte, niet sfeer. Witruimte is een vlak, geen leegte (Rietveld-principe).

Daarmee staat Roosevelt-kleur expliciet **niet** in de traditie van moderne UI-kleurenpaletten zoals Tailwind-default, Material-Design of Wise's "Bright Green als visual metaphor". Geen branding-metafoor, geen warme-kleurenpalet, geen accent-kleur per categorie. Drie kleuren, drie rollen, vastgepind.

---

## 2. Principes

1. **Kleur = semantiek.** Elke primaire kleur heeft één vaste rol: blauw = strategic-agent, rood = risk, geel = advisory. Hergebruik buiten die rol is verboden.
2. **Grijsschaal = structuur.** Grijs draagt hiërarchie, niet sfeer. Geen warm-grijs, geen cool-grijs — neutraal.
3. **Drie primairen, niet meer.** Geen oranje, paars, teal of magenta als accent. Less but better.
4. **Mondriaan-vlak, geen gradient.** Kleurvlakken zijn vlak. Geen gradient-fills, geen overlay-blends.
5. **Toegankelijkheid is hard, niet wenselijk.** WCAG 2.2 AA is minimum; AAA waar tekst-op-achtergrond. APCA aanvullend voor WCAG 3-readiness.

---

## 3. Tokens

### Layer 1 — Global (grondstof)

#### Neutraal — structuurpalet

| Token | $value | Usage |
|---|---|---|
| `color.neutral.0` | `#FFFFFF` | Pure wit — base background |
| `color.neutral.50` | `#FAFAFA` | Surface — subtiele scheiding van base |
| `color.neutral.100` | `#F2F2F2` | Tertiary background |
| `color.neutral.200` | `#E5E5E5` | Border-subtle |
| `color.neutral.300` | `#D1D1D1` | Border-default |
| `color.neutral.400` | `#A3A3A3` | Non-text decoratief (icons-disabled) |
| `color.neutral.500` | `#737373` | Mid-tier text op donkere achtergrond |
| `color.neutral.600` | `#525252` | Text-secondary |
| `color.neutral.700` | `#404040` | Borders op surface |
| `color.neutral.800` | `#262626` | Technical agent (kleur-rol) |
| `color.neutral.900` | `#171717` | Inverse-base |
| `color.neutral.950` | `#0A0A0A` | Text-primary (Mondriaan-zwart) |
| `color.neutral.1000` | `#000000` | Reserveerd — niet standaard |

#### Primair — Weimar-semantiek

| Token | $value | Kandinsky-vorm | Roosevelt-rol |
|---|---|---|---|
| `color.primary.blue.500` | `#1E4D8C` | Cirkel (oneindig, geestelijk) | Strategic-agent, advies-fundament |
| `color.primary.red.500` | `#C8332B` | Vierkant (statisch, materieel) | Risk-signaal, escalatie |
| `color.primary.yellow.500` | `#E8B306` | Driehoek (scherp, agressief) | Advisory-attention, review nodig |

Plus tints (300) en shades (600, 700, 900) per kleur — zie `tokens.json`.

#### Supportief

| Token | $value | Usage |
|---|---|---|
| `color.supportive.green.500` | `#1F7A3A` | Completed-state (alleen) |
| `color.supportive.green.600` | `#176030` | Completed-strong |

Groen is bewust **niet** primair (geen Bauhaus-primaire) en bewust gedempt — geen succes-vlag-groen.

### Layer 2 — Semantic (ambacht)

| Token | Alias naar | Usage |
|---|---|---|
| `semantic.color.background.base` | `color.neutral.0` | Default page-background |
| `semantic.color.background.surface` | `color.neutral.50` | Cards, sections |
| `semantic.color.background.inverse` | `color.neutral.950` | Dark-mode base |
| `semantic.color.text.primary` | `color.neutral.950` | Body-tekst hoofdrol |
| `semantic.color.text.secondary` | `color.neutral.600` | Body-tekst secundair |
| `semantic.color.text.tertiary` | `color.neutral.400` | **Alleen non-text** — placeholders met grote font-size |
| `semantic.color.text.accent` | `color.primary.blue.500` | Links, accenten |
| `semantic.color.border.subtle` | `color.neutral.200` | Default cards |
| `semantic.color.border.default` | `color.neutral.300` | Inputs, dividers |
| `semantic.color.border.strong` | `color.neutral.950` | Mondriaan-zwartlijn (structureel) |
| `semantic.color.agent.strategic` | `color.primary.blue.500` | Strategic-agent rol-marker |
| `semantic.color.agent.risk` | `color.primary.red.500` | Risk-agent rol-marker |
| `semantic.color.agent.advisory` | `color.primary.yellow.500` | Advisory-agent rol-marker |
| `semantic.color.agent.technical` | `color.neutral.800` | Technical-agent rol-marker |
| `semantic.color.status.idle` | `color.neutral.400` | Pipeline-step idle |
| `semantic.color.status.running` | `color.primary.blue.500` | Pipeline-step running |
| `semantic.color.status.approval` | `color.primary.yellow.500` | Wacht op human-in-the-loop |
| `semantic.color.status.completed` | `color.supportive.green.500` | Pipeline-step done |
| `semantic.color.status.error` | `color.primary.red.500` | Pipeline-step error |

### Layer 4 — Pipeline (F0–F9 gradiënt)

Pipeline-fasen volgen een visueel verloop van neutraal naar agent-rol-kleur. Géén decoratie — een volgordesignaal.

| Token | Alias | Fase-betekenis |
|---|---|---|
| `pipeline.phase.F0` | `color.neutral.300` | Intake — neutraal start |
| `pipeline.phase.F1` | `color.neutral.400` | Data-collectie |
| `pipeline.phase.F2` | `color.neutral.500` | Pre-analyse |
| `pipeline.phase.F3` | `color.primary.blue.300` | Strategic-fase begint |
| `pipeline.phase.F4` | `color.primary.blue.500` | Strategic-kern |
| `pipeline.phase.F5` | `color.primary.blue.700` | Strategic-diepteanalyse |
| `pipeline.phase.F6` | `color.primary.yellow.500` | Advisory review |
| `pipeline.phase.F7` | `color.primary.yellow.700` | Advisory finalisatie |
| `pipeline.phase.F8` | `color.supportive.green.500` | Adviesrapport-finalisatie |
| `pipeline.phase.F9` | `color.supportive.green.600` | Impactmeting |

---

## 4. Accessibility

Validatie uitgevoerd via `wcag_check.py` op 14 mei 2026.

### Tekst op witte achtergrond (`#FFFFFF`)

| Voorgrond | WCAG-ratio | Niveau | APCA Lc | Verdict |
|---|---|---|---|---|
| `neutral-950` (text-primary) | 19.80 | AAA | 105.8 | ✓ Volledig vrij gebruik |
| `neutral-600` (text-secondary) | 7.81 | AAA | 87.2 | ✓ Volledig vrij gebruik |
| `neutral-400` (text-tertiary) | 2.52 | **Fail** | 49.5 | ✗ Niet voor tekst |
| `blue-500` (text-accent) | 8.42 | AAA | 88.6 | ✓ Tekst + links |
| `red-500` (risk) | 5.30 | AA | 74.9 | ✓ Tekst (niet AAA) |
| `red-700` (risk-strong) | 9.58 | AAA | 90.8 | ✓ Volledig vrij gebruik |
| `yellow-500` (advisory) | 1.93 | **Fail** | 36.7 | ✗ Niet als tekst |
| `yellow-700` (advisory-strong) | 5.17 | AA | 75.4 | ✓ Tekst (niet AAA) |
| `green-500` (completed) | 5.38 | AA | 76.4 | ✓ Tekst (niet AAA) |

### Tekst op donkere achtergrond (`neutral-950 #0A0A0A`)

| Voorgrond | WCAG-ratio | Niveau | APCA Lc | Verdict |
|---|---|---|---|---|
| `neutral-0` (white) | 19.80 | AAA | −107.7 | ✓ |
| `neutral-200` | 15.72 | AAA | −90.9 | ✓ |
| `blue-300` | 7.67 | AAA | −51.4 | ✓ |
| `red-300` | 10.43 | AAA | −66.4 | ✓ |
| `yellow-300` | 13.73 | AAA | −82.2 | ✓ |

### Knoppen en componenten

| Combinatie | WCAG | Niveau | Verdict |
|---|---|---|---|
| Witte tekst op `blue-500` (primary button) | 8.42 | AAA | ✓ |
| Witte tekst op `blue-600` | 10.97 | AAA | ✓ |
| Witte tekst op `red-500` (destructive) | 5.30 | AA | ✓ |
| Witte tekst op `red-600` | 7.15 | AAA | ✓ |
| Witte tekst op `yellow-500` | 1.93 | **Fail** | ✗ Gebruik zwarte tekst |
| **Zwart op `yellow-500`** | 10.26 | AAA | ✓ Verplichte combinatie |
| Witte tekst op `yellow-700` | 5.17 | AA | ✓ Alternatief |
| Witte tekst op `green-500` | 5.38 | AA | ✓ |
| Witte tekst op `neutral-800` (technical) | 15.13 | AAA | ✓ |

### Regels

- **Geel als achtergrond → altijd zwarte tekst** (`neutral-950`). Witte tekst op geel is verboden.
- **`neutral-400` is geen tekst-kleur** op lichte achtergronden. Alleen voor disabled-iconen of decoratieve dividers.
- **`yellow-500` is geen tekst-kleur** op lichte achtergronden. Voor advisory-tekst gebruik `yellow-700`.
- Body-tekst onder 18px: WCAG 4.5 minimum, streef 7.0+ (AAA).
- Tekst 18px+ of 14px+ bold: WCAG 3.0 minimum (AA-large) toegestaan, streef 4.5+.

---

## 5. Do / Don't

| Situatie | Do | Don't |
|---|---|---|
| Strategic-agent badge | `bg: blue-500`, `text: white` | Niet rood of geel — verbreekt semantiek |
| Risk-alert | `bg: red-50`, `text: red-700`, `border: red-500` | Niet `red-500` background met tekst — pas met witte tekst werkt |
| Advisory-banner (human-in-the-loop) | `bg: yellow-500`, `text: neutral-950` | Geen witte tekst op geel (faalt WCAG) |
| Pipeline-step "running" | `bg: blue-500` of `border: blue-500` | Geen pulsing-glow — anti-Bauhaus |
| Body-tekst | `neutral-950` op `neutral-0` | Niet `neutral-400` of `neutral-500` — onleesbaar |
| Link in body | `blue-500` met underline | Geen oranje, paars of teal links |
| Disabled state | `neutral-400` op `neutral-100` | Niet transparantie — eerlijk materiaal (Rams) |
| Success-toast | `bg: green-500`, `text: white` | Geen confetti-illustraties of emoji |
| F0–F9 fase-indicator | Layer 4 pipeline.phase token | Geen rainbow-volgorde of regenboog-gradient |
| Adviesrapport-cover | Wit met `neutral-950` typografie | Geen gradient-cover, geen stock-photo |

---

## 6. Implementatie

### Tailwind preset

```js
// packages/tailwind-config/colors.js
// Gegenereerd door Style Dictionary v4 uit tokens.json — niet handmatig bewerken.
module.exports = {
  neutral: {
    0:    '#FFFFFF', 50:   '#FAFAFA', 100:  '#F2F2F2',
    200:  '#E5E5E5', 300:  '#D1D1D1', 400:  '#A3A3A3',
    500:  '#737373', 600:  '#525252', 700:  '#404040',
    800:  '#262626', 900:  '#171717', 950:  '#0A0A0A',
  },
  blue:   { 50: '#EFF4FB', 300: '#7CA4D6', 500: '#1E4D8C', 600: '#163C70', 700: '#102C54' },
  red:    { 50: '#FEF2F2', 300: '#FCA5A5', 500: '#C8332B', 600: '#A82420', 700: '#871A18' },
  yellow: { 50: '#FFFBEB', 300: '#FCD34D', 500: '#E8B306', 600: '#B88A04', 700: '#8A6803' },
  green:  { 500: '#1F7A3A', 600: '#176030' },
};
```

### CSS variables (semantic + pipeline)

```css
/* packages/design-tokens/dist/semantic.css */
:root {
  --color-bg-base: #FFFFFF;
  --color-bg-surface: #FAFAFA;
  --color-bg-inverse: #0A0A0A;

  --color-text-primary: #0A0A0A;
  --color-text-secondary: #525252;
  --color-text-accent: #1E4D8C;

  --color-border-subtle: #E5E5E5;
  --color-border-default: #D1D1D1;
  --color-border-strong: #0A0A0A;

  --color-agent-strategic: #1E4D8C;
  --color-agent-risk:      #C8332B;
  --color-agent-advisory:  #E8B306;
  --color-agent-technical: #262626;

  --color-status-idle:      #A3A3A3;
  --color-status-running:   #1E4D8C;
  --color-status-approval:  #E8B306;
  --color-status-completed: #1F7A3A;
  --color-status-error:     #C8332B;
}
```

### shadcn override

```tsx
// packages/ui/src/badge.tsx — voorbeeld agent-rol-badge
import { cva } from "class-variance-authority";

export const badgeVariants = cva(
  "inline-flex items-center px-2 py-0.5 text-xs font-medium",
  {
    variants: {
      agent: {
        strategic: "bg-blue-500 text-white",
        risk:      "bg-red-500 text-white",
        advisory:  "bg-yellow-500 text-neutral-950", // ← verplichte zwarte tekst
        technical: "bg-neutral-800 text-white",
      },
    },
  }
);
```

---

## 7. Verwante foundations

- [Mission](mission.md) — Roosevelt-context en positionering
- [bauhaus-canon §1.1](../../bauhaus-canon.md) — Weimar kleur-semantiek
- [bauhaus-canon §1.3](../../bauhaus-canon.md) — De Stijl primairen
- Typography (volgt) — kleur + typografie als geheel
- Border (volgt) — Mondriaan-zwartlijn-toepassing
- Pictograms (volgt) — agent-rol kleur-koppeling

---

## 8. Provenance (DSR)

| Veld | Waarde |
|---|---|
| Bron-paper | Swaab, S. (2026). *Bauhaus-Geïnspireerd Headless Design System voor Roosevelt OPS*, v1.0 |
| RQ-koppeling | RQ4a (Token-Architectuur) |
| Hevner-guideline | 3 (Design Evaluation — WCAG/APCA als evaluatiemetric) + 5 (Research Rigor — DTCG 2025.10 + meetbare contrast-ratios) |
| Peffers-DSRM-activiteit | Activity 3 (Design and Development) |
| ADR | ADR-020 (te schrijven, verwijst naar deze pagina als kleur-bron) |
| Externe bronnen | [Bauhaus Color Theory — Getty](https://www.getty.edu/research/exhibitions_events/exhibitions/bauhaus/new_artist/form_color/color/) · [Mondrian Composition — Smarthistory](https://smarthistory.org/mondrian-composition-ii-in-red-blue-and-yellow/) · [Wise Foundations Colour](https://wise.design/foundations/colour) (geraamte-bron) |
| Validatie | `wcag_check.py` — 14 mei 2026, alle ratio's WCAG 2.2 + APCA-Lc berekend |
| Versie | v0.1 — 14 mei 2026 |

---

*Einde Colour v0.1*
