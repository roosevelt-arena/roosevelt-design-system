# Iconography

**Status:** v0.1 · Ronde 5 · 14 mei 2026

Iconen en pictogrammen voor Roosevelt OPS — gebaseerd op Otl Aicher's grid-systematiek (HfG Ulm) en Bauhaus Vorkurs (Itten/Kandinsky) geometrie-semantiek. Lucide als basis-library, Roosevelt-gecustomized.

---

## 1. Principes

Iconen zijn geen decoratie maar **functionele tekens** (Aicher). Drie regels:

1. **Eén icoon = één betekenis.** Hergebruik nooit voor meerdere concepten.
2. **Geometrie volgt functie.** De vorm draagt de boodschap voordat de label dat doet.
3. **Configureerbaar via tokens.** Stroke-dikte, canvas-grootte en kleur worden via DTCG-tokens gestuurd, niet hardcoded.

## 2. Grid + Canvas

| Canvas | Token | Tailwind | Gebruik |
|---|---|---|---|
| 16×16 (micro) | `icon.canvas-sm` | `size-4` | Badge-cijfers · inline tekst · tabel-cellen |
| **24×24 (primair)** | `icon.canvas` | `size-6` | Navigatie · buttons · cards · agent-badges |
| 32×32 (feature) | `icon.canvas-lg` | `size-8` | Onboarding · lege staat · rapport-headers |

**Niet 20px:** Google-only standaard. **Niet regulier 32px:** geen UI-grid, alleen incidentele vergroting (IBM Carbon-logica).

## 3. Stroke

| Token | Waarde | Context |
|---|---|---|
| `icon.stroke.width-sm` | `1px` | Op 16px canvas |
| `icon.stroke.width` | **`1.5px`** | Standaard (op 24px) |
| `icon.stroke.width-lg` | `2px` | Op 32px canvas of emphasis |
| `icon.stroke.cap` | `square` | De Stijl-override |
| `icon.stroke.join` | `miter` | Scherpe verbindingen |

**Waarom 1.5px (niet Lucide's default 2px):** 8.3% gewicht-ratio voelt zwaar naast Inter Regular. Heroicons-precedent (6.25%) past beter bij Gugelot-stilte. Material Symbols `wght=300` equivalent.

## 4. Lucide customization

`globals.css`:

```css
@layer base {
  .lucide {
    stroke-width: 1.5;
    stroke-linecap: square;
    stroke-linejoin: miter;
  }
  .lucide * {
    vector-effect: non-scaling-stroke;
  }
}
```

`tailwind.config.ts`:

```ts
theme: {
  extend: {
    spacing: {
      'icon-sm': '16px',
      'icon-md': '24px',
      'icon-lg': '32px',
    },
  },
}
```

Gebruik:

```tsx
import { ChevronRight } from 'lucide-react';

<ChevronRight className="size-6" />                  // 24px, 1.5px (default)
<ChevronRight className="size-4 stroke-1" />         // 16px micro
<ChevronRight className="size-8 stroke-2" />         // 32px feature
```

## 5. Uitsluitingslijst (Lucide-subset)

Niet importeren — strijdig met canon §2:

- `sun-moon`, `sparkles`, `wand-*`, `wand-sparkles` — decoratief
- `heart`, `star`, `thumbs-up`, `thumbs-down` — consumer-app
- Alle `*-3d`-named iconen — Rams anti-pattern

Named imports (`import { X } from 'lucide-react'`) → tree-shaking elimineert ongebruikte iconen.

## 6. Pictogrammen — Agent-geometrie

Itten/Kandinsky Vorkurs-mapping voor Roosevelt's vier agent-rollen:

| Agent | Kleur | Vorm | Constructie | Itten/Kandinsky-anker |
|---|---|---|---|---|
| **Strategic** | `blue.500` | ○ Cirkel (open) | r=9px, 1.5px stroke | *"continually moving, eternally rotating"* — onbegrensd strategisch |
| **Risk** | `red.500` | ◪ Vierkant + diagonaal | 16×16px, diagonaal, 1.5px | *"intensive inner seething — a tension within it"* |
| **Advisory** | `yellow.500` | △ Driehoek (radius 2px) | equilatérale, 1.5px, hoek-radius | Driehoek = intellectuele energie; radius = Toni's human touch |
| **Technical** | `neutral.800` | ▬ Rechthoek | 18×12px, 1.5px, 0px radius | Aicher-grid = pure structuurlogica |

## 7. Pictogrammen — F0–F9 fase-emblem

**Container:** cirkel — beste leesbaarheid op 24px voor enkelvoudige cijfers, geen anti-aliasing-ruis (vs hexagoon), geen hoeken-focus-conflict (vs vierkant).

| Property | Waarde |
|---|---|
| `pipeline.emblem.diameter` | 20px (binnen 24px canvas) |
| `pipeline.emblem.cipher-size` | 11px |
| `pipeline.emblem.cipher-font` | Geist Mono (tabulaire cijfers) |
| `pipeline.emblem.cluster.diagnostic` (F0–F4) | `neutral.500` border |
| `pipeline.emblem.cluster.synthesis` (F5–F9) | `blue.500` border |

**16px micro-versie:** gevulde cirkel (solid) Ø9px, geen cijfer — puur kleur-code.

## 8. Duotone-principe (hybride)

Agent + fase tegelijk weergeven zonder apart pictogram per combinatie:

- Agent-vorm = outline (primaire agent-kleur)
- Fase-cluster = gevulde achtergrond (20% opacity)

Voorbeeld: Strategic Agent in F3 = blauwe cirkel-outline + grijs gevuld binnengebied (F0–F4 cluster). **Aicher's configureerbare syntaxis, digitaal vertaald.**

## 9. Do / Don't

| ✅ Do | ❌ Don't |
|---|---|
| Lucide met Roosevelt-override gebruiken | Lucide as-is met 2px round caps |
| 24px primair, 16px micro | 20px tussenmaat |
| 1.5px stroke via token | Hardcoded `strokeWidth={2}` per icoon |
| Square cap + miter join | Round cap (Lucide default) |
| Cirkel voor F-fase cijfer | Hexagoon (anti-aliasing-ruis op 24px) |
| Agent-geometrie consistent toepassen | Agent-rol via tekstlabel alleen |
| Tree-shaking via named imports | `import * from 'lucide-react'` |

## 10. Bronnen

- [Otl Aicher München 1972 — Eye Magazine analyse](https://www.eyemagazine.com/feature/article/otl-aicher-and-the-1972-munich-olympics-pictograms)
- [HfG-Archiv Ulm](https://hfg-archiv.museumulm.de/en/)
- [Lucide documentation](https://lucide.dev)
- [Heroicons](https://heroicons.com)
- [Bauhaus Vorkurs — Bauhaus-Archiv Berlin](https://www.bauhaus.de/en/)
- [Kandinsky, *Punkt und Linie zu Fläche* (1926)](https://www.guggenheim.org/artwork/artist/vasily-kandinsky)

## 11. Provenance

- Volledig onderzoeksrapport: [`canon/aicher-research-ronde5.md`](../../canon/aicher-research-ronde5.md)
- ADR-021 (volgt): canvas + stroke + Lucide-override beslissing
- Tokens: zie `tokens.json` v0.5+

---

*Onderdeel van Roosevelt Design System · ronde 5 · Sam Swaab.*
