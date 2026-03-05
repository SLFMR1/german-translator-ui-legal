# Legal Translation — Subagent Workflow

Multi-agent workflow for legal text (privacy, terms, imprint). Based on ISO 17100 TEP standard adapted for AI translation.

## Why Legal Needs More Passes

Legal text fails differently than UI text:
- A wrong word can change legal liability ("kann" vs "hat zu" for "shall")
- Bilingual reviewers unconsciously read the correct meaning into ambiguous translations — they don't catch what the German text *actually says* in isolation
- Legal terminology must be 100% consistent (always "Einwilligung", never mixing with "Zustimmung")
- Swiss law references (DSG/nDSG, OR) must be flagged where EN only mentions GDPR

## Recommended 4-Agent Pipeline

```
Agent 1: TRANSLATOR     → EN legal JSON → DE legal JSON + _review_notes.md
Agent 2: BACK-TRANSLATOR → DE legal JSON → EN (without seeing original)
Agent 3: VALIDATOR       → Compares all three: original EN, DE translation, back-translated EN
Agent 4: REFINER         → Applies fixes from validator findings
```

### Agent 1: Translator

**Skill mode:** TRANSLATE + LEGAL

**Prompt pattern:**
```
Use the german-translation-qa skill in TRANSLATE + LEGAL mode.
Translate this legal JSON file from English to Swiss-formal German.

Source file: [path to EN JSON]
Output: DE JSON + _review_notes.md

Pay special attention to:
- Legal term table in the skill (DSGVO standard terms)
- Swiss law references (DSG/nDSG, OR) wherever GDPR is mentioned
- Qualifier precision (may/shall/unless/notwithstanding)
```

**Output:** `messages/de/[page].json` + `messages/de/[page]_review_notes.md`

### Agent 2: Back-Translator

**Purpose:** Translate the German back to English WITHOUT seeing the original. Divergences between back-translation and original reveal meaning errors.

**Critical: This agent must NOT have access to the original English file.**

**Prompt pattern:**
```
You are a professional translator. Translate this German legal text
to English. Translate precisely — preserve the exact legal meaning,
all qualifiers, and all conditions.

Do NOT simplify. Do NOT improve. Translate exactly what the German says.

Source file: [path to DE JSON]
Output: back-translated EN JSON
```

**Output:** `messages/de/[page]_backtranslation.json`

**Why this works:** If the original says "The company shall notify the user within 30 days" and the back-translation says "The company may inform the user within 30 days" — that's a critical error (shall→may changed an obligation to a permission). A bilingual reviewer might miss this because they'd read the German and unconsciously import the correct English meaning.

### Agent 3: Validator

**Skill mode:** VALIDATE + LEGAL

**Prompt pattern:**
```
Use the german-translation-qa skill in VALIDATE + LEGAL mode.

You have three files:
1. Original English: [path to EN JSON]
2. German translation: [path to DE JSON]
3. Back-translation: [path to backtranslation JSON]

Run the full LEGAL validation checklist. Additionally:

BACK-TRANSLATION DIFF:
For each key, compare original EN (file 1) with back-translated EN (file 3).
- If meaning matches: OK
- If meaning differs slightly: WARNING with explanation
- If meaning changes materially (e.g., obligation→permission,
  condition dropped, scope changed): CRITICAL

BLIND READ:
Read ONLY the German text (file 2) without looking at the English.
Flag anything that sounds unnatural, unclear, or ambiguous as a
standalone German legal document.

Output a validation report per the skill's format.
```

**Output:** Validation report with CRITICAL/WARNING/INFO issues

### Agent 4: Refiner

**Purpose:** Apply fixes from the validator's findings.

**Prompt pattern:**
```
Use the german-translation-qa skill in TRANSLATE + LEGAL mode.

Here is the German legal translation and the validation report:
- Current DE translation: [path to DE JSON]
- Original EN source: [path to EN JSON]
- Validation report: [paste or path to report]

Fix all CRITICAL issues. Address WARNING issues where the suggestion
improves accuracy. Preserve everything that passed validation.

Output: corrected DE JSON + updated _review_notes.md
```

**Output:** Corrected `messages/de/[page].json` + updated `_review_notes.md`

## After the Pipeline

Run Agent 3 (Validator) one more time on the corrected output. If PASS → done. If FAIL → one more refine cycle. Stop after 2 refine cycles maximum (diminishing returns).

## Cross-File Consistency Check

After all legal pages are translated, run a final consistency pass:

**Prompt pattern:**
```
Read all German legal translation files:
- messages/de/privacy.json
- messages/de/terms.json
- messages/de/imprint.json

Check that the same English legal term is translated identically
across all files. Flag any inconsistencies.

Key terms to check (from SKILL.md legal term table):
personal data, data processing, data controller, data processor,
consent, legitimate interest, data subject, right to erasure,
terms of service, liability, indemnification, governing law,
severability, intellectual property

Output a consistency report listing any term translated differently
across files.
```

## Summary

| Agent | Task | Catches |
|-------|------|---------|
| 1. Translator | EN→DE with legal precision | — |
| 2. Back-Translator | DE→EN blind (no original) | Meaning errors invisible to bilingual review |
| 3. Validator | Compare all three + blind read + checklist | Everything: structure, accuracy, naturalness, legal precision |
| 4. Refiner | Fix flagged issues | — |
| Final | Cross-file consistency | Same term translated differently across files |
