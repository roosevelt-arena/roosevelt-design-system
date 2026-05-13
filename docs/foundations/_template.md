# [Foundation naam]

> Pillar: Product | Editorial
> Canon-anker: [bauhaus-canon.md](../../bauhaus-canon.md) §[paragraafnummer]
> Tokens: `tokens.json → [DTCG-pad]`
> Stack-impact: [Tailwind preset / CSS variable / TypeScript type / shadcn override]
> Status: v[major.minor] — [datum]

---

## 1. Filosofie

[Waarom dit bestaat. 2–4 alinea's. Verwijzing naar specifieke Bauhaus-canon-stroming (Weimar / Dessau / De Stijl / Ulm / Gugelot-Rams). Wat Roosevelt-toepassing onderscheidt van generieke implementatie. Concreet, geen woollig taalgebruik.]

---

## 2. Principes

1. **[Principe in fat]** — [1-zin onderbouwing]
2. **[Principe in fat]** — [1-zin onderbouwing]
3. **[Principe in fat]** — [1-zin onderbouwing]
4. **[Principe in fat]** — [1-zin onderbouwing]
5. **[Principe in fat]** — [1-zin onderbouwing]

[Optioneel: 5e principe. Niet meer dan 5 — Rams "less but better".]

---

## 3. Tokens

### Layer 1 — Global (grondstof)

| Token | $value | $type | Usage |
|---|---|---|---|
| `[pad.naam]` | `[waarde]` | `[type]` | [korte usage] |

### Layer 2 — Semantic (ambacht)

| Token | Alias naar | Usage |
|---|---|---|
| `[semantic.pad.naam]` | `[layer-1-pad]` | [Roosevelt-semantiek] |

### Layer 4 — Pipeline (indien van toepassing)

| Token | Alias naar | F-fase / agent / status |
|---|---|---|
| `[pipeline.pad.naam]` | `[semantic-pad]` | [koppeling] |

---

## 4. Accessibility

**Minimumeisen:** WCAG 2.2 AA. APCA-scores aanvullend voor preview van WCAG 3.

| Combinatie | WCAG-ratio | WCAG-niveau | APCA-score | Verdict |
|---|---|---|---|---|
| [voorgrond op achtergrond] | [getal] | AA / AAA / Fail | [getal] | ✓ / ✗ |

**Aanvullende notities:**
- [Specifieke uitsluitingen of beperkingen]
- [Reduced motion / high contrast / dark mode]

---

## 5. Do / Don't

| Situatie | Do | Don't |
|---|---|---|
| [context 1] | [aanbeveling] | [anti-pattern] |
| [context 2] | [aanbeveling] | [anti-pattern] |

---

## 6. Implementatie

### Tailwind preset

```js
// packages/tailwind-config/[bestand].js
module.exports = {
  // [snippet]
}
```

### CSS variables

```css
:root {
  /* [snippet] */
}
```

### shadcn override (indien van toepassing)

```tsx
// packages/ui/src/[component].tsx
// [snippet]
```

---

## 7. Verwante foundations

- [Foundation X](../_product/x.md) — [korte relatie]
- [Foundation Y](../_editorial/y.md) — [korte relatie]
- [bauhaus-canon §X](../../bauhaus-canon.md) — [canon-paragraaf]

---

## 8. Provenance (DSR)

| Veld | Waarde |
|---|---|
| Bron-paper | Swaab, S. (2026). *Bauhaus-Geïnspireerd Headless Design System voor Roosevelt OPS*, v1.0 |
| RQ-koppeling | RQ[4a / 4b / 4c / 4d] |
| Hevner-guideline | [1–7] |
| Peffers-DSRM-activiteit | Activity [2 / 3 / 4 / 5] |
| ADR | ADR-[nummer] |
| Externe bron(nen) | [URL + datum geraadpleegd] |
| Versie | v[major.minor] — [datum] |

---

*Einde [Foundation naam] v[major.minor]*
