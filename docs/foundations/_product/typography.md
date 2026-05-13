# Typography

> Pillar: Product
> Canon-anker: [bauhaus-canon.md](../../bauhaus-canon.md) §1.2 Dessau-typografie + §1.5 Gugelot/Rams-stilte
> Tokens: `tokens.json → semantic.typography.*`
> Stack-impact: `next/font` loader · Tailwind preset `packages/tailwind-config/typography.js` · CSS variables `:root`
> Status: v0.1 — 14 mei 2026

---

## 1. Filosofie

Typografie is in Roosevelt OPS een **functionele communicatiemachine**, geen expressie. De Bauhaus formuleerde in Dessau drie typografische principes (samenvatting Moholy-Nagy 1923): (1) typografie wordt gevormd door functionele eisen; (2) doel is communicatie in de kortste, eenvoudigste, meest penetrerende vorm; (3) ingrediënten hebben interne en externe organisatie.

Herbert Bayer's *Universal*-typografie (1925) was de radicale uitvoering: één lettercasus, geometrische constructie uit cirkel en lijn, uniforme stamdikte. We nemen niet Bayer's experiment letterlijk over (alleen-kleine-letters bleek niet praktisch in de Bauhaus zelf), maar wel zijn *principe*: typografie is mathematica, niet kalligrafie.

Daarmee staat Roosevelt-typografie in dezelfde lijn als de Ulm HfG (Aicher's Lufthansa-identiteit, Maldonado's systeem-typografie) en de Braun-as (Gugelot/Rams: typografie is functioneel, niet decoratief). Concreet: één hoofdfont (Bayer-erfgenaam), één mono-font voor pipeline-data, één modulaire schaal, geen display-experimenten.

---

## 2. Principes

1. **Eén hoofdfont.** Inter Variable als geometrische sans. Geen tweede display-typeface (anti-Wise-pattern: Wise Sans als expressief-display).
2. **Eén modulaire schaal.** Ratio 1.250 (major third) — Bauhaus-mathematiek boven arbitraire waarden. Base 16px = 1rem.
3. **Mono voor data, niet voor sfeer.** Geist Mono voor pipeline-status, tokens, F-codes, technische output. Nooit decoratief.
4. **Functionele hiërarchie.** Maximaal 4 heading-niveaus. Body is `base` (16px), niet 14px — Bauhaus-leesbaarheid boven densiteit.
5. **Geen kapitalen in body-tekst.** Bayer-erfgenaam. Uitzondering: acroniemen (AI, DSR, WCAG, F0–F9). Labels mogen kapitalen met `+0.05em` letterspacing.

---

## 3. Tokens

### Layer 1 — Font families

| Token | $value | $type | Usage |
|---|---|---|---|
| `typography.font.family.sans` | `Inter Variable, -apple-system, BlinkMacSystemFont, system-ui, sans-serif` | `fontFamily` | Default UI + body + headings |
| `typography.font.family.mono` | `Geist Mono Variable, ui-monospace, SFMono-Regular, monospace` | `fontFamily` | Pipeline-data, tokens, codes |

**Beslissing: Inter Variable als hoofdfont.**
- Ontwikkeld door [Rasmus Andersson sinds 2017](https://rsms.me/inter/) specifiek voor *text-heavy UIs* — exact Roosevelt's gebruik
- OFL-licentie, breed peer-getest in 9 jaar iteratie
- Variable-font axes: `wght` (100–900), `slnt` (0–10), optical-sizing
- Bayer-erfgenaam: geometrische constructie, uniforme stamdikte, rationale lettervormen

**Mono-keuze: Geist Mono.** Vercel-ecosysteem (consistent met AI SDK 6), OFL, expliciet voor developers/designers ontworpen.

### Layer 1 — Font weights

| Token | $value | Gebruiksregel |
|---|---|---|
| `typography.font.weight.regular` | `400` | Body-tekst standaard |
| `typography.font.weight.medium` | `500` | Labels, navigation |
| `typography.font.weight.semibold` | `600` | Headings, emphasis |
| `typography.font.weight.bold` | `700` | Display, data-emphasis — **beperkt gebruik** |

Geen `extra-light` of `black` — Rams "less but better".

### Layer 1 — Modulaire schaal (ratio 1.250)

| Token | font-size | line-height | letter-spacing | Berekening |
|---|---|---|---|---|
| `typography.scale.xs` | `12px` | `16px` | `+0.02em` | base / 1.25^1.25 ≈ 12 |
| `typography.scale.sm` | `14px` | `20px` | `+0.01em` | base / 1.143 |
| `typography.scale.base` | `16px` | `24px` | `0` | **anchor** |
| `typography.scale.lg` | `20px` | `28px` | `-0.01em` | base × 1.250 |
| `typography.scale.xl` | `25px` | `32px` | `-0.015em` | base × 1.250² |
| `typography.scale.2xl` | `31px` | `40px` | `-0.02em` | base × 1.250³ |
| `typography.scale.3xl` | `39px` | `48px` | `-0.025em` | base × 1.250⁴ |
| `typography.scale.4xl` | `49px` | `56px` | `-0.03em` | base × 1.250⁵ |

**Mathematiek:** Schaal is geometrische progressie met ratio φ = 1.250 (major third in muziektheorie). Letter-spacing is omgekeerd evenredig met font-size — kleine tekst krijgt meer spacing voor leesbaarheid (Inter-aanbeveling), grote tekst krijgt negatieve spacing voor compactheid (Bayer-strengheid).

### Layer 2 — Semantic typography (rollen)

| Token | Alias naar | Roosevelt-usage |
|---|---|---|
| `semantic.typography.role.display` | `scale.4xl`, weight `semibold` | Adviesrapport-cover, hero-headlines |
| `semantic.typography.role.heading-1` | `scale.3xl`, weight `semibold` | Pagina-titel |
| `semantic.typography.role.heading-2` | `scale.2xl`, weight `semibold` | Sectie-titel |
| `semantic.typography.role.heading-3` | `scale.xl`, weight `semibold` | Subsectie |
| `semantic.typography.role.heading-4` | `scale.lg`, weight `medium` | Card-titel |
| `semantic.typography.role.body` | `scale.base`, weight `regular` | Standaard body-tekst |
| `semantic.typography.role.body-small` | `scale.sm`, weight `regular` | Tabellen, secundaire info |
| `semantic.typography.role.caption` | `scale.xs`, weight `regular` | Annotaties, footnotes |
| `semantic.typography.role.label` | `scale.sm`, weight `medium`, `+0.05em` | Buttons, form-labels (kapitalen toegestaan) |
| `semantic.typography.role.code` | `scale.sm` mono, weight `regular` | Tokens, F-codes, technische output |
| `semantic.typography.role.data` | `scale.base` mono, weight `medium` | Pipeline-status, metrics in adviesrapport |

### Layer 4 — Pipeline-specifieke typografie

| Token | Alias | Usage |
|---|---|---|
| `pipeline.typography.fase-label` | `role.label` + uppercase | "F0 INTAKE", "F4 STRATEGIC" |
| `pipeline.typography.agent-name` | `role.heading-4` | Agent-card titel |
| `pipeline.typography.status` | `role.data` | Live status-output |

---

## 4. Accessibility

### WCAG 2.2 minimumeisen

| Tekst-type | Minimum contrast | Aanbeveling |
|---|---|---|
| Body (< 18px regular of < 14px bold) | WCAG AA 4.5 | AAA 7.0 |
| Large text (≥ 18px regular of ≥ 14px bold) | WCAG AA 3.0 | AA 4.5 |
| Non-text UI | WCAG AA 3.0 | — |

Zie [colour.md §4](colour.md#4-accessibility) voor gevalideerde combinaties.

### Leesbaarheidsregels

| Eis | Waarde | Bron |
|---|---|---|
| Body line-height | 1.5 (24/16) | WCAG SC 1.4.12 |
| Maximum regelbreedte | 65 karakters (66ch) | Bringhurst, *Elements of Typographic Style* |
| Minimum regelbreedte | 45 karakters | Bringhurst |
| Paragraph spacing | 1em (16px) onder body | WCAG SC 1.4.12 |
| Letter-spacing body | 0 (Inter is geoptimaliseerd) | Inter design-notes |
| Word-spacing | 0.16em | WCAG SC 1.4.12 |

### Internationalisatie

- **Nederlands + Engels** primaire talen. Inter heeft volledige Latin Extended + accents.
- **Geen RTL-support** vereist in MVP (Roosevelt-klanten: EU). RTL-readiness niet uitgesloten — Inter ondersteunt het.
- **Cijfers tabulair** (`font-variant-numeric: tabular-nums`) verplicht voor pipeline-data en metrics — voorkomt jumpy uitlijning.

### Reduced motion / preferences

- `prefers-reduced-motion`: geen invloed op typografie zelf
- `prefers-contrast: more`: switch naar `text-primary` (neutral-950) voor alle body, ongeacht hiërarchie

---

## 5. Do / Don't

| Situatie | Do | Don't |
|---|---|---|
| Body-tekst | `role.body` (16px regular, neutral-950) | Niet 14px als body — leesbaarheid > densiteit |
| Adviesrapport-cover | `role.display` (49px semibold) | Niet `bold` weight — Bauhaus-rust |
| Pipeline-status live | `role.data` (mono, 16px medium) | Niet sans-serif voor pipeline-data |
| Form-label | `role.label` met `text-uppercase` + `+0.05em` | Niet body-styling — verlies van scanbaarheid |
| Citaat in adviesrapport | `role.body` met `font-style: italic` | Geen serif-font als citaat — geen tweede typeface |
| Cijfers in tabel | `tabular-nums` | Proportional-nums in datakolommen — uitlijning faalt |
| Heading-emphasis | `font-weight: 600` (semibold) | Geen `bold 700` voor headings — gereserveerd voor display |
| Code in body | `role.code` (mono, 14px) | Geen `<code>` met sans-font |
| Acroniem | "AI" — kapitalen + body-styling | Niet "Ai" of "ai" — leesbaarheid |
| Long-form (adviesrapport) | `max-width: 66ch` op tekstkolommen | Geen full-width body — > 65 karakters faalt Bringhurst |
| Display-experiment | — | Geen tweede display-typeface, geen handgeschreven stijlen |
| Decoratieve italic | — | Italic alleen voor werk-/papertitels |

---

## 6. Implementatie

### `next/font` loader (Next.js 14 App Router)

```tsx
// apps/web/app/layout.tsx
import { Inter } from "next/font/google";
import localFont from "next/font/local";

const inter = Inter({
  subsets: ["latin", "latin-ext"],
  variable: "--font-sans",
  display: "swap",
  axes: ["slnt"], // optional slant axis
});

const geistMono = localFont({
  src: "../public/fonts/GeistMonoVF.woff2",
  variable: "--font-mono",
  display: "swap",
});

export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html lang="nl" className={`${inter.variable} ${geistMono.variable}`}>
      <body className="font-sans text-base text-neutral-950 antialiased">
        {children}
      </body>
    </html>
  );
}
```

### Tailwind preset

```js
// packages/tailwind-config/typography.js
// Gegenereerd door Style Dictionary v4 uit tokens.json.
module.exports = {
  fontFamily: {
    sans: ["var(--font-sans)", "-apple-system", "BlinkMacSystemFont", "system-ui", "sans-serif"],
    mono: ["var(--font-mono)", "ui-monospace", "SFMono-Regular", "monospace"],
  },
  fontSize: {
    xs:   ["12px", { lineHeight: "16px", letterSpacing: "0.02em" }],
    sm:   ["14px", { lineHeight: "20px", letterSpacing: "0.01em" }],
    base: ["16px", { lineHeight: "24px", letterSpacing: "0em" }],
    lg:   ["20px", { lineHeight: "28px", letterSpacing: "-0.01em" }],
    xl:   ["25px", { lineHeight: "32px", letterSpacing: "-0.015em" }],
    "2xl":["31px", { lineHeight: "40px", letterSpacing: "-0.02em" }],
    "3xl":["39px", { lineHeight: "48px", letterSpacing: "-0.025em" }],
    "4xl":["49px", { lineHeight: "56px", letterSpacing: "-0.03em" }],
  },
  fontWeight: {
    regular:  "400",
    medium:   "500",
    semibold: "600",
    bold:     "700",
  },
};
```

### CSS variables (semantic rollen)

```css
/* packages/design-tokens/dist/typography.css */
:root {
  --font-sans: "Inter Variable", -apple-system, BlinkMacSystemFont, system-ui, sans-serif;
  --font-mono: "Geist Mono Variable", ui-monospace, SFMono-Regular, monospace;

  --typo-display:    600 49px/56px var(--font-sans);
  --typo-heading-1:  600 39px/48px var(--font-sans);
  --typo-heading-2:  600 31px/40px var(--font-sans);
  --typo-heading-3:  600 25px/32px var(--font-sans);
  --typo-heading-4:  500 20px/28px var(--font-sans);
  --typo-body:       400 16px/24px var(--font-sans);
  --typo-body-small: 400 14px/20px var(--font-sans);
  --typo-caption:    400 12px/16px var(--font-sans);
  --typo-label:      500 14px/20px var(--font-sans);
  --typo-code:       400 14px/20px var(--font-mono);
  --typo-data:       500 16px/24px var(--font-mono);
}

/* Body-default — Bauhaus-leesbaarheid */
body {
  font: var(--typo-body);
  letter-spacing: 0;
  font-feature-settings: "cv02", "cv03", "cv04", "cv11"; /* Inter: stylistic alts voor leesbaarheid */
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* Tabulaire cijfers voor data */
.font-data, [data-tabular] {
  font: var(--typo-data);
  font-variant-numeric: tabular-nums;
}

/* Labels — Bayer-erfgenaam, kapitalen toegestaan */
.label-uppercase {
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

/* Bringhurst max-width voor long-form */
.prose {
  max-width: 66ch;
}
```

### shadcn override

```tsx
// packages/ui/src/heading.tsx
import { cva } from "class-variance-authority";

export const headingVariants = cva("font-sans text-neutral-950", {
  variants: {
    level: {
      display:  "text-4xl font-semibold tracking-tight",
      h1:       "text-3xl font-semibold tracking-tight",
      h2:       "text-2xl font-semibold tracking-tight",
      h3:       "text-xl  font-semibold",
      h4:       "text-lg  font-medium",
    },
  },
  defaultVariants: { level: "h2" },
});
```

---

## 7. Verwante foundations

- [Mission](mission.md) — Roosevelt-context, brand-DNA
- [Colour](colour.md) — kleur + typografie samen als hiërarchie
- [bauhaus-canon §1.2 Dessau](../../bauhaus-canon.md) — Bayer en typografische principes
- Grid (volgt) — typografie + grid als compositie
- Spacing (volgt) — line-height + paragraph spacing
- Markup (volgt) — HTML-semantiek + ARIA voor heading-niveaus

---

## 8. Provenance (DSR)

| Veld | Waarde |
|---|---|
| Bron-paper | Swaab, S. (2026). *Bauhaus-Geïnspireerd Headless Design System voor Roosevelt OPS*, v1.0 |
| RQ-koppeling | RQ4a (Token-Architectuur) + RQ4c (Bauhaus-Fideliteitsmetric — form follows function, modulariteit) |
| Hevner-guideline | 1 (Design as Artifact) + 3 (Design Evaluation — Bringhurst regelbreedte als metric) + 5 (Research Rigor — DTCG-conform) |
| Peffers-DSRM-activiteit | Activity 3 (Design and Development) |
| ADR | ADR-020 (kleur + typografie samen als systeem) |
| Externe bronnen | [Inter — Rasmus Andersson](https://rsms.me/inter/) · [The birth of Inter — Figma Blog](https://www.figma.com/blog/the-birth-of-inter/) · [Geist Font — Vercel](https://vercel.com/font) · [Herbert Bayer Universal Typeface — Encyclopedia of Design](https://encyclopedia.design/2023/01/10/herbert-bayer-universal-typeface/) · [Bauhaus Typography — Design History](http://www.designhistory.org/Avant_Garde_pages/BauhausType.html) · [Wise Foundations Typography](https://wise.design/foundations/typography) (geraamte-bron) |
| Vakliteratuur | Bringhurst, R. (2004). *The Elements of Typographic Style* (regelbreedte 45–75 karakters) · Moholy-Nagy, L. (1923). Bauhaus typografische principes |
| Versie | v0.1 — 14 mei 2026 |

---

*Einde Typography v0.1*
