# Responsive — Adaptive layout (Apple HIG × Bauhaus)

**Status:** v0.1 · Ronde 8 · 14 mei 2026

Adaptive layout-fundamenten voor Roosevelt OPS. Apple HIG levert principes + meet-tokens (size classes, touch-targets, safe-areas); Bauhaus-canon wint op visuele taal (geen SF, geen blur, geen rounded corners). Bron: prototype-sectie R8 (v0.8.1).

---

## 1. Conflict-policy

| Apple HIG levert | Roosevelt-canon wint bij | Beslissing |
|---|---|---|
| Compact / Regular size classes | — | Overgenomen als `--bp-compact` / `--bp-regular-*` |
| 44pt minimum touch target | — | Overgenomen: `--touch-min: 44px` |
| Safe area insets | — | Overgenomen via `env(safe-area-inset-*)` |
| Dynamic Type (system font scaling) | Inter Variable + modular scale | Bauhaus wint — geen system font, wel `clamp()` |
| SF Pro / Apple kleuren / rounded corners | Bauhaus-canon | Bauhaus wint — niet overgenomen |
| iOS Liquid Glass / blur / vibrancy | Bauhaus "form follows function" | Bauhaus wint — geen materials/blur |

## 2. Breakpoint-tokens (DTCG)

| Token | Waarde | HIG-equivalent | Roosevelt-gebruik |
|---|---|---|---|
| `--bp-compact` | 0–639px | Compact width (iPhone portrait) | Single-column, drawer-nav, body uit grid |
| `--bp-regular-sm` | 640–1023px | Regular width compact (iPad portrait, iPhone landscape Plus) | 2-koloms content, sidebar nog drawer |
| `--bp-regular-md` | 1024–1279px | Regular (iPad landscape) | Sidebar zichtbaar, right-rail verborgen |
| `--bp-regular-lg` | 1280px+ | Regular extended (iPad Pro, desktop) | 3-koloms: sidebar + main + right-rail |

```css
@media (max-width: 639px)  { /* compact */ }
@media (min-width: 640px) and (max-width: 1023px)  { /* regular-sm */ }
@media (min-width: 1024px) and (max-width: 1279px) { /* regular-md */ }
@media (min-width: 1280px) { /* regular-lg */ }
```

## 3. Touch-target & safe-area tokens

| Token | Waarde | Bron | Toepassing |
|---|---|---|---|
| `--touch-min` | 44px | Apple HIG (iOS) — minimum tap-zone | Knoppen, links, form-controls op < 1024px |
| `--touch-comfortable` | 48px | Material 3 — convergerend met HIG | Primaire CTA, mobile drawer-items |
| `--safe-top` | `env(safe-area-inset-top)` | Apple HIG safe area | Sticky topbar, fixed dialogs |
| `--safe-bottom` | `env(safe-area-inset-bottom)` | Apple HIG safe area | Sticky CTA-bar, footer-fix |
| `--safe-left` / `--safe-right` | `env(safe-area-inset-{left,right})` | Apple HIG (notch + landscape) | Edge-content op landscape iPhones |

**HTML viewport:**

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover" />
```

`viewport-fit=cover` is verplicht voor notch-support op iPhone.

## 4. Adaptive principes — HIG → Roosevelt

| HIG-principe | Roosevelt-interpretatie | Bewijs in prototype |
|---|---|---|
| Prioritization — essentials prominent | F0–F9 pipeline + adviesrapport eerst; foundations als ondersteuning | Topbar-volgorde: Foundations → Components → Editorial → Responsive |
| Content extension — edge-to-edge | Sectie-backgrounds tot rand, content respecteert safe-area | Section padding met `max()` + safe-area |
| Visual hierarchy — top + leading | Eyebrow → H2 → demo, geen lede-paragrafen (Bauhaus: vorm volgt functie) | v0.8.1 cleanup: alle leeg-prikkende paragrafen verwijderd |
| Adaptability traits | 3 → 2 → 1-koloms met drawer-transitie | 1280 / 1024 / 640 breakpoints |
| Defer compact switch (iPad resize) | Sidebar blijft zichtbaar tot < 1024px — pas dan drawer | `@media (max-width: 1023px)` regel |
| Dynamic Type respect | Geen system-font; `clamp()` + relatieve units zodat user-zoom werkt | Type-scale tokens in `tokens.json` v0.3+ |
| Control spacing | 44px tap-zones op mobile, 32px op desktop hover | Topbar-toggle, sidebar-link, drawer-items |

## 5. Layout-shifts per breakpoint

| Breakpoint | Layout |
|---|---|
| Compact (`< 640`) | 1 koloms. Topbar collapsed → hamburger. Sidebar → drawer. Right-rail verborgen. Body-padding 16px. Touch ≥ 44px. |
| Regular-sm (`640–1023`) | 1 koloms content, tabellen breder. Sidebar nog drawer. Right-rail nog verborgen. Body-padding 24px. |
| Regular-md (`1024–1279`) | 2-koloms: sidebar 240px + main. Right-rail nog verborgen. Topbar volledig zichtbaar. |
| Regular-lg (`1280+`) | 3-koloms: sidebar 240px + main + right-rail 220px. Scrollspy actief. Volledige Wise.design-shell. |

## 6. Wat we niet overnemen van Apple HIG

| HIG-pattern | Reden om niet over te nemen |
|---|---|
| SF Pro / SF Rounded fonts | Inter Variable is Bauhaus-erfgenaam — canon-verankerd |
| iOS rounded corners (16pt default) | Bauhaus = scherpe hoeken, rechthoek + cirkel als primitieven |
| Liquid Glass / vibrancy / blur | "Form follows function" — decoratie zonder functie |
| Apple system kleuren (Blue, Indigo, Pink) | Goud (#E8B306) is canon, accent-palet is vastgesteld |
| Tab-bar onderaan | Roosevelt is desktop-first B2B; sidebar + topbar wint |
| Haptic feedback patterns | Web-context, niet native |

## 7. Do / Don't

| ✅ Do | ❌ Don't |
|---|---|
| Breakpoint-tokens (`--bp-compact`, etc.) | Hardcoded `@media (max-width: 768px)` |
| `--touch-min: 44px` op mobile-controls | 32px buttons op touch-screens |
| `viewport-fit=cover` + safe-area-insets | Vaste padding zonder safe-area |
| `clamp()` voor type-scale | Vaste px font-sizes (breekt user-zoom) |
| Sidebar zichtbaar ≥ 1024px | Drawer-pattern op desktop |
| Roosevelt-kleuren + Inter | SF Pro of Apple system kleuren als shortcut |

## 8. Provenance

- Prototype-sectie: [R8 in `docs/index.html`](../../index.html#sec-r8) (8.1–8.6)
- Tokens: `breakpoint.*`, `touch.*`, `safe-area.*` in `tokens.json` v0.8.1
- Externe bron: [Apple Human Interface Guidelines — Layout](https://developer.apple.com/design/human-interface-guidelines/layout)
- Bron: ronde 8 implementatie v0.8.1 (CHANGELOG 2026-05-14)

---

*Onderdeel van Roosevelt Design System · ronde 8 · Sam Swaab.*
