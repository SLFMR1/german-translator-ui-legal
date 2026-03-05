# QA Validation Checklist

**First:** Determine text type (UI or LEGAL). Run only the sections that apply.

| Section | UI | LEGAL |
|---------|:--:|:-----:|
| Structural | yes | yes |
| Accuracy | yes | yes |
| Naturalness | yes | **skip** |
| Tone & Style (UI) | yes | **skip** |
| Tone & Style (Legal) | **skip** | yes |
| Linguistic (UI) | yes | **skip** |
| Linguistic (Legal) | **skip** | yes |
| Legal-Specific | **skip** | yes |
| Completeness | yes | yes |

---

## Structural Checks (CRITICAL if failing) — All text types

- [ ] **Key parity**: Every key in EN exists in DE, and vice versa
- [ ] **Nesting match**: JSON structure (depth, namespaces) is identical
- [ ] **Valid JSON**: DE file parses without errors
- [ ] **Placeholder preservation**: All `{variable}` placeholders in EN exist in DE with identical names
- [ ] **HTML tag preservation**: All HTML tags preserved exactly
- [ ] **No translated keys**: Only values are translated, never keys

## Accuracy Checks (CRITICAL if meaning changes) — All text types

- [ ] **Back-translation**: Mentally translate each DE value back to English. Match? If not → CRITICAL (meaning error) or WARNING (nuance drift)
- [ ] **No omissions**: No parts of a sentence dropped
- [ ] **No additions**: No meaning added that wasn't in the EN source. Exception for UI heroes/headlines: creative rewrites that preserve the intent are acceptable (see hero headline strategies in swiss-german-style.md) — but body text, descriptions, and legal text must not add meaning
- [ ] **Number preservation**: All numbers, amounts, percentages match
- [ ] **Brand name preservation**: All "Never Translate" glossary items unchanged

## Naturalness Checks (WARNING) — UI only

> **Skip entirely for LEGAL text.** Legal text has different standards — see Legal sections below.

- [ ] **Reads like written German**: Sounds like it was written in German, not translated. Check translationese traps in [swiss-german-style.md](swiss-german-style.md)
- [ ] **No nominalizations**: Verbs used where possible, not bureaucratic noun chains
- [ ] **No literal structure mapping**: German sentence structure follows German logic, not English word order
- [ ] **Natural vocabulary**: English loans where Swiss tech uses them, German where natural German exists

## Tone & Style — UI only

- [ ] **Address form consistency**: Chosen form (Sie or Du) used throughout — zero mixing of forms
- [ ] **Swiss conventions**: "ss" not "ß" throughout
- [ ] **No Denglisch hybrids**: No "gedownloaded", "upgedated" etc.
- [ ] **Register**: Professional but human — not bureaucratic, not casual
- [ ] **Glossary compliance**: "Keep in English" terms kept, "Always Translate" terms translated
- [ ] **No marketing hyperbole**: No "revolutionär", "einzigartig" unless EN source warrants it
- [ ] **Obvious Adams Test 4**: Does each headline/CTA click instantly?

## Tone & Style — LEGAL only

- [ ] **Sie-Form consistency**: Formal Sie throughout
- [ ] **Swiss conventions**: "ss" not "ß" throughout
- [ ] **No Denglisch hybrids**: No "gedownloaded", "upgedated" etc.
- [ ] **Formal register**: Consistently formal and precise — not marketing tone, not casual
- [ ] **Glossary compliance**: Brand names and "Never Translate" terms kept as-is
- [ ] **No inappropriate simplification**: Formal legal language maintained, not dumbed down

## Linguistic Checks — UI only

- [ ] **Grammar**: Correct cases, verb conjugation, article agreement
- [ ] **Spelling**: No typos, correct compound nouns (one word: "Rechnungsverarbeitung")
- [ ] **Sentence length**: Flag over 20 words — consider splitting
- [ ] **Consistency**: Same EN term → same DE term throughout

## Linguistic Checks — LEGAL only

- [ ] **Grammar**: Correct cases, verb conjugation, article agreement
- [ ] **Spelling**: No typos, correct compound nouns
- [ ] **Sentence length**: Long sentences are acceptable if they preserve legal precision. Only flag if length causes ambiguity
- [ ] **Consistency**: Same legal term must map to the same DE term throughout the entire document. Zero variation (e.g., always "Einwilligung" for "consent", never mixing with "Zustimmung")

## Legal-Specific Checks (CRITICAL/WARNING) — LEGAL only

- [ ] **Legal terminology**: Standard DSGVO/DSG terms used correctly (see legal term table in SKILL.md)
- [ ] **Qualifier preservation**: "may" → "kann", "shall" → "hat zu" (NOT "soll" — "soll" is weaker, closer to "should"), "unless" → "sofern nicht", "notwithstanding" → "ungeachtet". Not softened, not dropped
- [ ] **No simplification**: Complex legal sentences preserve all conditions and subclauses
- [ ] **Swiss law awareness**: Where EN references EU/GDPR, check if Swiss equivalents (DSG/nDSG, OR) are noted
- [ ] **Jurisdiction references**: Courts, regulators, applicable law mentions flagged in review notes
- [ ] **Source fidelity**: Translation matches the source term's formality level. "personal information" ≠ "personenbezogene Daten" (that's "personal data"). "opt out" ≠ "widersprechen" (that's formal DSGVO objection). Translate what the source says, not what it should say
- [ ] **Compound completeness**: All German compound truncations are grammatically complete. "Rechts- oder Behördenanfragen" (correct), not "Rechts- oder Behörden" (broken)
- [ ] **Review notes exist**: `_review_notes.md` accompanies the translation
- [ ] **"Personal data" consistency**: If EN uses "personal data" → DE must use "personenbezogene Daten" (DSGVO term). If EN uses "personal information" (informal) → DE uses "persönliche Informationen". Never mix them within one document
- [ ] **Consent term consistency**: "Einwilligung" (DSGVO) or "Zustimmung" (general) — pick one per document and stick to it. Prefer "Einwilligung" for DSGVO/DSG contexts
- [ ] **GDPR → DSGVO**: In German text, always use "DSGVO" (Datenschutz-Grundverordnung), never "GDPR". Similarly: FADP → DSG, FDPIC → EDÖB
- [ ] **Swiss DSG alongside DSGVO**: Where EN references EU data protection law, verify that Swiss equivalents (DSG/nDSG) are mentioned where applicable — they are separate legal frameworks
- [ ] **Data processing verbs**: "erheben/erfassen" (collect), "verarbeiten" (process), "weitergeben" (share) — consistent verb choices throughout. Don't mix "erheben" and "sammeln" in the same legal document
- [ ] **Cookie terminology**: "Cookies" stays English. "Cookie-Einstellungen" (settings), "Cookie-Richtlinie" (policy). "Similar technologies" → "ähnliche Technologien" or "vergleichbare Technologien" — pick one consistently

## Completeness Check — All text types

### Coverage (CRITICAL if failing)

- [ ] **Key parity (again)**: Diff EN keys vs DE keys. Every EN key must exist in DE. Every DE key must exist in EN. Zero orphans in either direction
- [ ] **All namespaces covered**: Every namespace/section in EN has corresponding translations in DE
- [ ] **Empty values**: No empty strings `""` where EN has content
- [ ] **Untrimmed whitespace**: No leading/trailing spaces that differ from EN
- [ ] **No EN leftovers in DE values**: Scan all DE values for full English sentences that were not translated. A DE value that is identical to its EN value is suspicious unless it's a keep-in-English term (see below)

### Keep-in-English Compliance (WARNING if failing)

Cross-reference every DE value against [glossary.md](glossary.md). These checks prevent two opposite errors:

**Error 1 — Accidentally translated a keep-in-English term:**
- [ ] **Brand/product names unchanged**: All items from "Never Translate" lists appear identically in DE
- [ ] **Tech terms preserved**: Terms from "Keep in English" list (Agent, AI, API, CRM, Dashboard, Support, Workflow, etc.) are not germanized when used as nouns
- [ ] **Product feature names preserved**: Slack Connect, Shop Pay, CloudTec®, MX Series etc. appear identically

**Error 2 — Left an English term that should be translated:**
- [ ] **Always-translate terms germanized**: Check every DE value against the "Always Translate" table. Flag if any of these appear in English: products→Produkte, solutions→Lösungen, pricing→Preise, features→Funktionen, careers→Karriere, privacy policy→Datenschutzerklärung, etc.
- [ ] **Navigation terms translated**: Products, Solutions, Pricing, Resources, Features, Careers, About us must be in German (per brand crawl: 100% of brands translate these)
- [ ] **CTA text translated**: Get started, Learn more, Sign in, Contact us, Shop now etc. must be in German (per brand crawl: 100% of brands translate these)
- [ ] **Common anglicisms caught**: No "Landing Page" (→ Startseite), "Use Case" (→ Anwendungsfall), "Feedback" in formal text (→ Rückmeldung), "Feature" as noun (→ Funktion)

### Split-Decision Audit (INFO)

For terms in the "Split Decisions" section of the glossary, verify the choice is consistent and fits the context:
- [ ] **Conversion**: Kept EN in analytics/marketing context, translated in general context
- [ ] **Templates**: Translated to "Vorlagen"
- [ ] **Stories**: "Storys" (German spelling) or "Geschichten" — not "Stories"

### Identical-Value Scan

Systematic check: for every key where `EN value === DE value`, classify as:

| Classification | Action | Example |
|---------------|--------|---------|
| Keep-in-English term | OK — no action | "Agent", "CRM", "API" |
| Brand/product name | OK — no action | "Slack Connect", "CloudTec®" |
| URL, email, number | OK — no action | "contact@example.ch", "0800 555 155" |
| Placeholder-only value | OK — no action | "{count}", "{name}" |
| Actual untranslated text | CRITICAL — must translate | Full English sentence left as-is |
| Single English word that should be German | WARNING — check glossary | "Pricing" should be "Preise" |

**Process:** Export all keys where EN === DE. For each, check if it falls into an "OK" category above. Anything remaining is a translation gap.

### Length Check (UI text only — WARNING if failing)

German expands ~20-30% vs English. UI strings must fit the same visual space as their English counterparts.

- [ ] **Buttons & CTAs**: DE character count ≤ 120% of EN. If longer, shorten. "Jetzt starten" not "Jetzt loslegen und starten"
- [ ] **Navigation items**: DE character count ≤ 120% of EN. Nav items have fixed-width containers
- [ ] **Labels & tooltips**: DE character count ≤ 120% of EN. Short labels break first when too long
- [ ] **Headings**: DE character count ≤ 130% of EN. Slightly more room, but still constrained
- [ ] **Body text & descriptions**: No strict limit, but avoid unnecessary padding. German verbosity is a sign of translationese

**Shortening strategies:**
- Drop filler words: "Sie können jetzt" → "Jetzt"
- Use shorter synonyms: "Benachrichtigungen" → "Hinweise", "Konfigurieren" → "Einrichten"
- Use imperative instead of polite form: "Bitte wählen Sie" → "Wählen" (Du) or "Wählen Sie" (Sie)
- Compound nouns can be shorter than phrases: "Kontoeinstellungen" vs "Einstellungen für Ihr Konto"

---

## Final Verdict

- **PASS**: Zero CRITICAL issues. Warnings acceptable if documented
- **FAIL**: Any CRITICAL issue → file needs fixes before use

Completeness failures are always CRITICAL — a missing or untranslated string means the user sees English in a German interface, or worse, a blank.
