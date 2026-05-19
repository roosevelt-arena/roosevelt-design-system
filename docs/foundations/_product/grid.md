# Grid · Spacing · Radius · Border · Elevation · Motion · Focus

**Status:** v0.1 · Ronde 4 · 14 mei 2026

Layout-fundamenten voor Roosevelt OPS. Twaalfkoloms-grid (Aicher/De Stijl-erfenis), 4pt+8pt-spacingsysteem, scherpe radius-keuze, en kalme motion. Niet decoratief — strikt functioneel.

---

## 1. Grid — 12 kolommen, asymmetrisch

12 kolommen geven zowel symmetrische (12/12) als asymmetrische (3/9, 2/7/3) verdelingen ruimte. Asymmetrie is canon: De Stijl + Bauhaus-erfenis wijst symmetrische saaiheid af.

**Standaard-verdelingen:**

| Verdeling | Gebruik |
|---|---|
| `3 / 9` | Sidebar + content (Wise.design-shell, prototype-pattern) |
| `2 / 7 / 3` | Rapport-pagina's met meta-kolom |
| `12 × 1` | Data-tabellen of overzichts-grids |

## 2. Spacing — schaal 0 → 96

4pt-anker (kleine details) + 8pt-anker (layout-modules). Twaalf stappen totaal.

| Token | Waarde | Typische toepassing |
|---|---|---|
| `space.0` | 0 | Reset |
| `space.px` | 1px | Hairline |
| `space.0-5` | 2px | Icon-padding |
| `space.1` | 4px | Inline gap |
| `space.2` | 8px | Form-gap |
| `space.3` | 12px | Card-interne |
| `space.4` | 16px | Sectie-spacing-sm |
| `space.6` | 24px | Sectie-spacing-md |
| `space.8` | 32px | Sectie-spacing-lg |
| `space.12` | 48px | Block-marge |
| `space.16` | 64px | Sectie-scheider |
| `space.20` | 96px | Header-block |

## 3. Radius — drie waarden

| Token | Waarde | Toepassing |
|---|---|---|
| `radius.none` | 0px | Cards, panels, sectie-blokken (Bauhaus-default) |
| `radius.sm` | 2px | Buttons, inputs, badges |
| `radius.md` | 4px | Dropdowns, tooltips, popovers |

**Geen `radius.lg` / `radius.full`** — past niet bij De Stijl-canon (geen pillen, geen ronde avatars).

## 4. Border

| Token | Waarde | Toepassing |
|---|---|---|
| `border.subtle` | `1px solid neutral.200` | Tabelrijen, divider |
| `border.default` | `1px solid neutral.300` | Card-omtrek, input-rust |
| `border.emphasis` | `2px solid neutral.950` | Mondriaan-scheider, focus-state |

## 5. Elevation — minimaal

Bauhaus + Gugelot wijzen overmatige schaduwen af. Drie niveaus volstaan.

| Token | Waarde | Toepassing |
|---|---|---|
| `elevation.none` | geen schaduw | Default rust |
| `elevation.subtle` | `0 1px 2px rgba(0,0,0,0.04)` | Sticky topbar, hover |
| `elevation.raised` | `0 4px 12px rgba(0,0,0,0.08)` | Modal, dropdown |

## 6. Motion

| Token | Duur | Toepassing |
|---|---|---|
| `duration.instant` | 0ms | Reduce-motion override |
| `duration.fast` | 120ms | Hover, focus |
| `duration.normal` | 200ms | State-change |
| `duration.slow` | 320ms | Panel slide |
| `duration.deliberate` | 480ms | Modal entry |

**Easings:** `linear`, `ease-out` (`cubic-bezier(0, 0, 0.2, 1)`), `deliberate` (`cubic-bezier(0.2, 0, 0, 1)`). Geen bouncing/elastic — Bauhaus wijst speelse motion af.

```css
.dropdown {
  transition: opacity var(--duration-normal) var(--ease-out);
}

@media (prefers-reduced-motion: reduce) {
  * { transition-duration: var(--duration-instant) !important; }
}
```

## 7. Focus — WCAG 2.4.13

| Property | Waarde |
|---|---|
| Indicator | 2px solid `blue.500` |
| Offset | 2px |
| Trigger | `:focus-visible` (niet `:focus`) |
| Contrast | ≥ 3:1 op alle backgrounds (WCAG 2.4.13 niveau AA) |

```css
:focus-visible {
  outline: 2px solid var(--focus-ring);
  outline-offset: 2px;
}
```

## 8. Do / Don't

| ✅ Do | ❌ Don't |
|---|---|
| 12-kolom raster bewust verdelen (3/9, 2/7/3) | 8-kolom of 16-kolom raster |
| Spacing via tokens (`space.4`) | Hardcoded `padding: 17px` |
| `radius.none` voor cards | Tablet-app rounded corners |
| `elevation.subtle` of `none` | Drop shadows als decoratie |
| `:focus-visible` voor toetsenbord-focus | `:focus` (ook bij muis-click zichtbaar) |

## 9. Provenance

- Prototype-secties: [R4 in `docs/index.html`](../../index.html#sec-r4)
- Tokens: `dimension.grid.*`, `dimension.spacing.*`, `dimension.radius.*`, `shadow.elevation-*`, `duration.*`, `cubicBezier.*`, `semantic.surface/border/motion/spacing.*`
- Bron: ronde 4 implementatie v0.4.0 (CHANGELOG 2026-05-14)

---

*Onderdeel van Roosevelt Design System · ronde 4 · Sam Swaab.*
