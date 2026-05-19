# Editorial — Tone · Grammar · Vocabulary

**Status:** v0.1 · Ronde 7 · 13 mei 2026

Verbale identiteit van Roosevelt OPS. Drie lagen — tone-of-voice (register), grammar (regels), vocabulary (lexicon) — plus conflict-policy bij twijfel. Bron: prototype-sectie R7 (v0.7.0).

---

## 1. Roosevelt-lexicon (Do/Don't, 15 sleuteltermen)

| Wel gebruiken | Niet gebruiken | Reden |
|---|---|---|
| `diagnose` | analyse | Medisch-technisch framing — analyse is generiek |
| `raamwerk` | framework (klant-copy) | Academisch register — framework alleen in developer-docs |
| `fase` | stap, step | Sluit aan op F0–F9 pipeline-taal |
| `readiness` | gereedheid, volwassenheid | Ingeburgerd vakterm (MITRE AI MM, CMMI) |
| `menselijk oordeel` | human-in-the-loop (klant-copy) | NL-term met menselijke connotatie in UI/rapport |
| `advies` | suggestie, tip | Roosevelt levert substantieel advies, geen tips |
| `inzicht` | insight | NL en zwaarder qua register |
| `salesteam` | sales team, verkoopteam | Aaneengesloten compound — verkoopteam te formeel |
| `intake` | vragenlijst, assessment | Roosevelts eigen term — assessment is Concentrix-taal |
| `pipeline` | pijplijn, workflow | Technische én klant-gebruikte term |
| `clustering` | groepering, categorisering | Technisch correct voor F3 |
| `dimensie` | categorie, as, domein | Modelmatig begrip — academisch register |
| `Strategic Agent` | strategische agent, hoofd-agent | Eigennaam — NL-variant verlaagt register |
| `AI-readiness` | AI-maturiteit, AI-volwassenheid | Roosevelts eigen positioneringsterm |
| `operationeel` | actief, live, draaiend | Juiste zakelijke register |

## 2. Verboden termen — absoluut

**Hype-AI** (verboden in alle klant-facing teksten):

- revolutionair, game-changer
- AI-powered, next-generation
- cutting-edge, state-of-the-art
- transformeer, unlock the power of
- leverage, synergy, disruptief
- holistic, magic, seamless
- empowering, future-proof
- end-to-end (vaag), real-time (zonder spec)
- insights als standalone buzzword

**Corporate-koud** (verboden in klant-copy):

| ❌ | ✅ |
|---|---|
| the organization | uw salesteam |
| your enterprise | uw salesorganisatie |
| our solution | Roosevelt OPS |
| stakeholders | uw salesleiding |
| deliverables | het adviesrapport |
| action items | de volgende stap |
| value-added | welke waarde concreet |

**Visuele tekst-regels:** geen emoji's, geen uitroeptekens — overal.

## 3. Grammar-conventies

Bron: `grammar.md` v1.0 · ANS (Algemene Nederlandse Spraakkunst) + Nederlandse Taalunie als basis.

| Conventie | Regel | Voorbeeld |
|---|---|---|
| Aanspreking UI (F0–F8) | `je` / `jouw` — werkplaats-register | «Start je intake» |
| Aanspreking rapport (F9) | `u` / `uw` — C-level, formeel | «Uw salesorganisatie heeft 67%…» |
| Hoofdletters | Zinscase — geen titlecase | «Start uw intake», niet «Start Uw Intake» |
| Uitroeptekens | Absoluut verboden | «Uw rapport is gereed.» nooit «Klaar!» |
| Streepjes | Em-dash — terzijde, en-dash – bereik (F0–F9) | «Roosevelt OPS — een pipeline — analyseert…» |
| Komma | Geen Oxford-komma in NL | «F3, F4 en F5» |
| Getallen | 1–12 uitschrijven, vanaf 13 cijfers, in data altijd cijfers | «zeven fasen» · «14 dimensies» |
| Decimaal | Komma (NL), punt voor duizendtal | 73,4 · 1.250 klanten |
| Datum klant-facing | DD maand JJJJ uitgeschreven | 14 mei 2026 |
| F-prefix | Hoofdletter F + getal, geen spatie | F0, F3, F9 · nooit `f3`, `F-3`, `fase-3` |
| Zinslengte UI-microcopy | ≤ 5 woorden labels/buttons | «Start intake» |
| Zinslengte UI-body | ≤ 22 woorden helper-text | Less-is-more (Bauhaus 1.5) |
| Zinslengte rapport | ≤ 30 woorden per zin | C-level leest scannerend |
| Stem | Actief voorkeur — passief OK als agent irrelevant | «F3 clustert uw intakegegevens» |
| Zin-opening | Niet beginnen met «Wij», «Er», «Gewoon», «Eigenlijk» | «Roosevelt identificeert drie aanbevelingen» |

## 4. UI-microcopy — voorbeelden

| Context | ✅ Canon-correct | ❌ Canon-overtreding |
|---|---|---|
| UI button | «Start intake» | «Start Uw Intake!» (titlecase + `!`) |
| Helper text | «Je voortgang is bewaard.» | «Je bent er bijna!» (consumer-gamification) |
| Lege staat | «Nog geen diagnose. Start je intake.» | «Oeps! Er ging iets mis» (neerbuigend + Er-opening) |
| F-status | «F4 Strategic-kern — 67% verwerkt» | «Step 4 — analyzing your data» (Engels + step) |
| Foutmelding | «De pipeline kon F3 niet voltooien. Probeer opnieuw.» | «Onze AI-powered solution…» (hype) |
| F9-rapport | «Uw salesorganisatie scoort 34 op Dimensie 3 Proces-automatisering — het laagste van vier dimensies.» | «Your enterprise heeft 3 action items» (Concentrix + `3` < 13) |
| Bevestiging | «Intake verwijderen?» | «Gefeliciteerd! Uw rapport is klaar!» (`!` × 2) |

## 5. Conflict-policy bij twijfel

| Twijfel-domein | Winnaar | Bestand |
|---|---|---|
| Register (formeel vs werkplaats) | Tone of voice | `tone-of-voice.md` |
| Specifieke woordkeuze | Vocabulary | `vocabulary.md` |
| Leestekens, zinsbouw, getallen | Grammar | `grammar.md` |
| Spelling | Nederlandse Taalunie | Woordenlijst NL Taal |
| Grammatica-edge-case | ANS | Algemene Nederlandse Spraakkunst |
| Visuele canon-overtreding | Bauhaus-canon | `bauhaus-canon.md` |

## 6. Do / Don't

| ✅ Do | ❌ Don't |
|---|---|
| `je`/`jouw` in F0–F8 UI | `u`/`uw` in UI (te formeel voor werkplaats) |
| `u`/`uw` in F9 rapport | `je`/`jouw` in rapport (verlaagt register naar C-level) |
| Roosevelt's eigen lexicon (intake, fase, dimensie) | Concentrix-taal (assessment, stakeholders, deliverables) |
| Concrete getallen (14 dimensies, F0–F9) | Vage hype-termen (next-generation, holistic) |
| Em-dash voor terzijde, en-dash voor bereik | Hyphen voor alles (`F0-F9` zonder en-dash) |
| Zinscase overal | Title Case Op Knoppen |
| Statements zonder `!` | Uitroeptekens om enthousiasme |

## 7. Provenance

- Prototype-sectie: [R7 in `docs/index.html`](../../index.html#sec-r7) (7.1–7.5)
- Beoogde split-files (nog niet aanwezig in repo, alleen in prototype-referenties): `vocabulary.md`, `grammar.md`, `tone-of-voice.md`. Deze foundation consolideert die drie.
- Externe bronnen: [Nederlandse Taalunie — Woordenlijst](https://woordenlijst.org/), [ANS Elektronische versie](https://e-ans.ivdnt.org/), MITRE AI Maturity Model, CMMI
- Bron: ronde 7 implementatie v0.7.0 (CHANGELOG 2026-05-13)

---

*Onderdeel van Roosevelt Design System · ronde 7 · Sam Swaab.*
