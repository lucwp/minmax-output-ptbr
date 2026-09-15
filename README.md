# MinMax PT-BR Output

**Production-grade PT-BR output for AI agents: natural Brazilian Portuguese, semantic fidelity, register control, and resistance to mechanical AI prose.**

MinMax PT-BR Output is an editorial standard for agents that need to write, rewrite, translate, edit, or review text in Brazilian Portuguese without sacrificing meaning for polish.

It is deliberately stricter than a generic "write better Portuguese" prompt. The skill protects facts, agency, modality, attribution, chronology, scope, commitments, ambiguity, and exact spans before optimizing style. It also distinguishes naturalness from informality: the target is prose that fits the artifact, audience, channel, and register rather than one universal conversational voice.

## What it does

- Produces contemporary, idiomatic Brazilian Portuguese from meaning instead of translating an English sentence mold.
- Preserves semantic relations before stylistic elegance.
- Protects quotations, legal clauses, formulas, code, commands, identifiers, paths, environment variables, product display names marked as exact, and literal error messages.
- Preserves authorial voice and useful irregularity instead of flattening every text into the same polished cadence.
- Integrates established technical jargon into Portuguese syntax without unnecessary linguistic purism.
- Detects mechanical structures such as canned antithesis, manufactured anticipation, empty metadiscourse, forced synonym cycling, generic product-copy molds, rhythmic groups of three, and English calques when they are actually defects in context.
- Uses progressive loading so deeper grammar, punctuation, naturalness, and editorial references are consulted only when the task needs them.
- Includes a regression suite for maintaining semantic fidelity and preventing over-editing as the skill evolves.

## What it is not

MinMax PT-BR Output is not a persona, a blanket grammar checker, a slang injector, or an AI-detector-evasion tool. It does not use word blacklists, punctuation quotas, sentence-length targets, or a score for how "human" a text appears.

It also does not normalize other Portuguese varieties toward Brazilian Portuguese and should not be invoked merely because a conversation happens to be in Portuguese.

## Core design

The runtime follows five hard priorities:

1. Preserve facts, thesis, intention, certainty, uncertainty, attribution, chronology, commitments, scope, agency, modality, and causal or logical relations.
2. Preserve protected exact spans character for character unless transformation is explicitly requested.
3. Never resolve material ambiguity by guessing.
4. Never invent facts, causal links, deadlines, commitments, emotions, relationships, examples, metrics, urgency, testimonials, guarantees, or recovery steps.
5. Treat semantic preservation as more important than elegance.

After those gates, the skill calibrates syntax, cadence, register, technical language, punctuation, and artifact-specific structure.

## Progressive references

The core `SKILL.md` is sufficient for routine work. Additional references are loaded only when a failure mode is present:

- `references/naturalness-and-register.md` — voice-sensitive work, register calibration, cadence, and over-editing.
- `references/grammar-and-style.md` — ambiguity, agreement, `se`, gerunds, participles, modifier scope, and complex syntax.
- `references/punctuation.md` — punctuation-specific questions and cases where punctuation changes interpretation.
- `references/editorial-standard.md` — structural rewrites, complex commercial/product prose, long-form work, and stubborn translation calques.
- `references/regression-suite.md` — maintenance, benchmarking, and stress testing only.

## Repository structure

```text
.
├── SKILL.md
├── README.md
├── CREDITS.md
├── agents/
│   └── openai.yaml
├── assets/
│   └── icon.svg
└── references/
    ├── editorial-standard.md
    ├── grammar-and-style.md
    ├── naturalness-and-register.md
    ├── punctuation.md
    └── regression-suite.md
```

## Installation

With the Skills CLI:

```bash
npx skills@latest add https://github.com/lucwp/minmax-output-ptbr
```

The runtime skill name is `minmax-ptbr-output`.

## Attribution and provenance

MinMax PT-BR Output was built from and materially adapts **[Better Portuguese](https://github.com/rafaelquintanilha/skills/tree/master/skills/better-portuguese)** by **[Rafael Quintanilha](https://github.com/rafaelquintanilha)**.

The upstream is visible in the current runtime itself: the grammar, punctuation, and editorial references retain Better Portuguese provenance. This repository makes that relationship explicit rather than presenting the work as greenfield.

The MinMax version extends and reorganizes that foundation around a stricter semantic-preservation contract, selective progressive loading, artifact calibration, a dedicated naturalness/register layer, and a maintenance regression suite.

The grammar and punctuation references also rely on research from **Napoleão Mendes de Almeida, _Gramática metódica da língua portuguesa_**. Almeida is a bibliographic source for the linguistic rules, not an upstream software/skill author.

See [`CREDITS.md`](CREDITS.md) for a more explicit provenance record.

## Licensing note

At the time this repository was prepared, the upstream `rafaelquintanilha/skills` repository did not expose a root license file. For that reason, this repository does **not** add an open-source license that could imply rights over upstream-derived material that were not granted by the upstream author.

Attribution documents provenance; it does not by itself create or replace a license.
