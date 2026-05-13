# Roosevelt Design System

Headless design system voor **Roosevelt OPS** — een autonome F0–F9 AI-readiness diagnose-pipeline voor B2B-salesorganisaties (AI Sales Labs ecosystem, Haarlem).

**Status:** Concept & Design fase · v0.4 · ronde 1–4 ✓

[**→ Live prototype (GitHub Pages)**](https://hansbeeksma.github.io/roosevelt-design-system/)

---

## Wat is dit

Een **Bauhaus-geïnspireerd** headless design system: design tokens, atomic components, en een schaalbare visuele taal die losstaat van implementatie. Compatibel met Next.js 14 + shadcn 4 + Tailwind 3.

Brand-DNA: academisch fundament + AI Sales Labs human touch (Toni van Dam). Niet generiek, niet corporate-koud, niet hype-AI.

## Methodologie

Design Science Research (Hevner 2004, Peffers 2007). Target publicatie: **ICIS 2026 Lissabon**.

## Structuur

```
docs/
├── index.html              ← Live prototype (GitHub Pages root)
├── tokens.json             ← DTCG 2025.10 design tokens
├── foundations/            ← Per-foundation specificaties (.md)
│   ├── README.md           ← IA + iteratie-model
│   ├── _template.md        ← Paginatemplate
│   ├── _product/           ← Mission, Colour, Typography, ...
│   └── _editorial/         ← Tone, Grammar, Vocabulary (later)
├── canon/                  ← Bauhaus-onderzoek + research-md's
└── adr/                    ← Architecture Decision Records
```

## Foundations status

| # | Foundation | Status |
|---|---|---|
| 1 | Mission | ✓ v0.1 |
| 2 | Colour | ✓ v0.1 |
| 3 | Typography | ✓ v0.1 |
| 4 | Grid · Spacing · Radius · Border · Elevation · Motion · Focus | ✓ v0.1 |
| 5 | Iconography · Pictograms | ⏳ in progress |
| 6 | Logo · Markup · Tone · Grammar · Vocabulary | pending |

## Bauhaus-canon

Vijf stromingen synthetisch toegepast:
- **Weimar** (1919–1925) — kleur-semantiek
- **Dessau** (1925–1932) — typografie (Bayer-erfgenaam: Inter)
- **De Stijl** (1917–1931) — raster + orthogonaliteit
- **Ulm/HfG** (1953–1968) — systematiek + Aicher
- **Gugelot/Rams** — stilte + functionele eerlijkheid

Volledige canon: [`docs/canon/bauhaus-canon.md`](docs/canon/bauhaus-canon.md).

## Stack

Next.js 14.2.35 · shadcn 4.1.0 · Tailwind 3.4.1 · Nx · Supabase · Fastify · Inngest · Vercel AI SDK 6 · Clerk · Hetzner · Sentry.

## Maintainer

[Sam Swaab](mailto:swaabsam@gmail.com) — Amsterdam, NL.

---

*Geen license-bestand — alle rechten voorbehouden © Sam Swaab 2026.*
