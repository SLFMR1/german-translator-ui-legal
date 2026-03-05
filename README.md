# German Translator Pro — Brand & Legal

An agent skill for translating English to Swiss-formal German (Hochdeutsch CH). Handles brand copy, UI strings, and legal text. Works with next-intl JSON, any key-value i18n format, or plain text.

## Why This Exists

LLMs can translate German. But they produce **translationese** — text that's grammatically correct but sounds translated, not written. "Entfesseln Sie die Kraft von..." instead of what a Swiss product manager would actually say.

This skill fixes that by giving the agent **curated translation knowledge** extracted from how top brands actually translate.

## How We Built It

We crawled the English and German websites of 12+ major brands operating in Switzerland and internationally:

**Swisscom, UBS, On Running, Logitech, IKEA CH, Stripe, Notion, Slack, Apple, Shopify, BMW, Vercel**

From their UI, marketing pages, privacy policies, and terms of service, we extracted:

- **100+ real EN→DE translation pairs** — hero headlines, CTAs, navigation, section headings, benefit statements, footer labels, legal headings, consent language, rights descriptions
- **Word-level decisions** — which English terms Swiss brands keep (Agent, API, Dashboard, Support) and which they always translate (Products→Produkte, Pricing→Preise, Features→Funktionen)
- **5 hero headline strategies** — how Apple shortens, Notion rewrites completely, Shopify adds engagement, Stripe restructures for German logic, Swisscom stays close when it already works
- **CTA conventions** — 15+ button patterns with Sie and Du variants, confirmed across brands
- **Du vs Sie split** — which industries use which form (B2C→Du, B2B→Sie, Swisscom splits by audience)
- **Legal register patterns** — how brands switch from casual UI tone to formal legal German, DSGVO/DSG terminology, consent language (Einwilligung vs Zustimmung), data processing verbs
- **29 legal term translations** — brand-confirmed DSGVO/DSG standard terms with evidence from Apple, Stripe, UBS, Logitech, Shopify, Slack, IKEA CH
- **Translationese traps** — 7+ patterns that reveal translated (not written) German, with natural alternatives

All of this is distilled into reference files that the agent reads before every translation, so it produces output that matches how these brands actually write German — not how a generic translator would.

## Install

```bash
npx skills add SLFMR1/german-translator-pro-brand-legal
```

Or install globally to use across all projects:

```bash
npx skills add SLFMR1/german-translator-pro-brand-legal -g
```

## How to Use

Once installed, just ask your agent to translate or validate German:

```
Translate messages/en.json to German
```

```
Validate the German translation in messages/de.json against the English source
```

```
Translate the privacy policy page to German
```

The skill asks four things before starting:

1. **Text type** — Brand/UI (marketing, buttons, headings) or Legal (privacy, terms, imprint)
2. **Action** — Translate (EN → DE) or Validate (QA-check existing DE)
3. **Address form** — Sie (formal, B2B) or Du (informal, B2C). Legal always uses Sie
4. **Locale** — Swiss (CH): `ss`, CHF, 1'000 or German (DE): `ß`, EUR, 1.000

## What It Does

|  | Brand / UI | Legal |
|---|---|---|
| **Translate** | Natural, punchy Swiss-German that sounds written, not translated | Precise, formal German with DSGVO/DSG legal terminology |
| **Validate** | QA-check for naturalness, accuracy, Swiss conventions | QA-check for legal precision, qualifier preservation, terminology |

### Key capabilities

- **Anti-translationese** — Restructures German thoughts fresh instead of mapping English sentence structures. Trained on how top brands actually write, not translate
- **Swiss (CH) or German (DE) locale** — Swiss: `ss`, 1'000, CHF. German: `ß`, 1.000, EUR. User chooses at the start
- **Back-translation QA** — Verifies meaning preservation by translating DE back to EN
- **Completeness checks** — Identical-value scan catches untranslated strings AND accidentally germanized brand terms. Cross-references glossary in both directions
- **Legal term precision** — 25+ standard DSGVO/DSG terms with brand-confirmed translations. Source fidelity rules prevent over-formalizing informal source text
- **4-agent legal pipeline** — Translator → Back-Translator → Validator → Refiner for legal documents
- **Configurable glossary** — Keep-in-English terms, always-translate terms, and split decisions — all backed by brand evidence

### Reference files

| File | What it contains |
|------|-----------------|
| **glossary.md** | 40+ keep-in-English terms, 25+ always-translate terms, split decisions, 29 legal terms — all with brand evidence |
| **swiss-german-style.md** | Swiss conventions, translationese traps, 5 hero headline strategies, CTA patterns, Du/Sie industry split, legal register patterns |
| **examples.md** | 100+ real EN→DE translation pairs (UI + legal) from top brands |
| **qa-checklist.md** | Structured QA with separate UI and legal sections, full completeness routine |
| **legal-workflow.md** | 4-agent pipeline for legal translation with role definitions |

## Customization

Edit the glossary to add your project-specific terms:

```bash
npx skills ls  # find your installed skill location
```

The glossary has a **Project-Specific Terms** template section ready to fill in with your brand names, product names, and domain vocabulary.

## Compatibility

Works with any agent that supports the [skills ecosystem](https://skills.sh):

- Claude Code
- Cursor
- VS Code Copilot
- Other compatible agents

## Links

- [Skills.sh page](https://skills.sh/SLFMR1/german-translator-pro-brand-legal)
- [Report issues](https://github.com/SLFMR1/german-translator-pro-brand-legal/issues)
