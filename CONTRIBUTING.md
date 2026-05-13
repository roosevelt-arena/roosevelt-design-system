# Contributing

## Review-cadence

Iteratieve 5-stappen-loop per foundation (zie `docs/foundations/README.md`):

1. **Verkennen** — research, benchmarks, brand-DNA-checks
2. **Concept** — keuze + canon-conflictbeoordeling (Roosevelt-Bauhaus wint)
3. **Specificatie** — md-bestand + token-update + ADR indien systeem-impact
4. **Prototype** — visualisatie in `docs/index.html`
5. **Review** — peer-review (N=3 voor ICIS-paper rigor)

## ADR-proces

Elke beslissing die de canon raakt, de stack beperkt, of conflict-resolutie vereist krijgt een Architecture Decision Record in `docs/adr/`.

Template: `docs/adr/_template.md` (volgt Michael Nygard format).

## Conflict-policy

**Roosevelt-Bauhaus canon wint altijd** bij conflict met:
- Wise foundations IA
- Tailwind/shadcn defaults
- Material/Apple HIG patterns
- Generieke design-system best practices

Documenteer de conflict-resolutie in de relevante foundation-md onder "Trade-offs".

## Commit conventies

Conventional Commits ([conventionalcommits.org](https://www.conventionalcommits.org/)):

```
feat(typography): Inter Variable als primaire sans
fix(colour): yellow-500 contrast op wit → forceer black text
docs(foundations): mission.md v0.1
chore(tokens): bump tokens.json naar v0.4
```

Scope = foundation-naam of subsysteem.

## DSR-rigor

Voor ICIS 2026 paper-traceability:
- Elke beslissing terug naar Toni's brand-DNA OF empirische bron
- Peer-review log per ronde (N=3 reviewers minimum bij major versions)
- WCAG 2.2 AA validatie verplicht bij kleur/contrast/focus-wijzigingen
- Changelog per release

## Maintainer

[Sam Swaab](mailto:swaabsam@gmail.com) — Amsterdam, NL.
