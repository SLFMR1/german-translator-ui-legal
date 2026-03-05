# Swiss-German Style Guide

## Register

Formal Swiss Hochdeutsch. Standard written German as used in Swiss business — not dialect (Mundart), not Bundesdeutsch (Germany), not Austrian German.

## The Obvious Adams Test (UI text only — skip for legal)

Before finalizing any UI/marketing translation, apply the five tests:
1. **Is it simple?** If it needs explanation, it's not right yet
2. **Does it match how people actually talk?** Not how documents sound
3. **Can you express it in short words?** Prefer "einfach" over "unkompliziert", "schnell" over "zeitoptimiert"
4. **Does it click instantly?** If a reader has to re-read it, rewrite it
5. **Read it out loud.** Would a product manager in Zug say this over coffee?

## Core Rules

### Address Form
- **Sie** (formal): Capitalized — Sie, Ihnen, Ihr, Ihre. Use for B2B, corporate, legal, professional contexts
- **Du** (informal): Lowercase — du, dir, dein, deine. Use for B2C apps, casual products, startups
- Ask the user which form to use. Default to Sie if unclear. Legal text always uses Sie
- Whichever form is chosen, apply it **100% consistently** — zero mixing

### Locale Conventions

The user chooses **Swiss (CH)** or **German (DE)** locale. Apply the matching conventions:

| Convention | Swiss (CH) | German (DE) |
|-----------|-----------|------------|
| Eszett | No ß — always "ss": Strasse, dass, grosse | Standard ß: Straße, dass, große |
| Thousands separator | Apostrophe: 1'000'000 | Dot: 1.000.000 |
| Decimal separator | Point: 99.90 | Comma: 99,90 |
| Currency | CHF before amount: CHF 100 | € after amount: 100 € |
| Date format | TT.MM.JJJJ (31.12.2025) | TT.MM.JJJJ (31.12.2025) |

Default to **Swiss (CH)** if unclear.

**Both locales:**
- "E-Mail" (hyphenated) when used as a German noun

### Tone
- Professional but human — not stiff, not casual
- Direct and confident — Swiss business communication is precise
- Short sentences. If over 20 words, consider splitting
- Active voice over passive
- Verbs over nominalizations ("prüfen" not "Prüfung durchführen")
- "einfach" is the most important word in Swiss SaaS copy — use it naturally

### Word Choice: The Key Decision

**Use English where Swiss tech actually uses English:**
Agent, AI, API, Business, Compliance, CRM, Dashboard, Deals, Inbox, Integration, Meeting, Onboarding, Support, Tools, Workflow

Note: "E-Mail" (hyphenated) is the standard German spelling, not an English loanword. Always write "E-Mail", never "Email" or "email".

**Germanize where it sounds more natural:**
Aufgabe (not Task), Rechnung (not Invoice), Anhang (not Attachment), Antwort (not Reply), Funktion (not Feature), Aktualisierung (not Update)

**Avoid Denglisch hybrids** — verbs that bolt German grammar onto English roots:
Not "gedownloaded" → "heruntergeladen". Not "upgedated" → "aktualisiert". Not "gecancelled" → "abgesagt"

**Avoid bureaucratic German** — forms that sound like government documents:
Not "Mitarbeitende" in marketing copy (HR-speak) → "Kollegen" or "Mitarbeiter". But "Mitarbeitende" is acceptable in formal corporate/B2B contexts (UBS uses it). Not "Nutzende" → "Nutzer". Not "Durchführung der Optimierung" → "optimieren"

### Translationese Traps

These patterns reveal translated (not written) German. Avoid all of them:

| English pattern | Translationese (avoid) | Natural German |
|---|---|---|
| We help you... | Wir helfen Ihnen... | State what happens directly |
| Powered by AI | Angetrieben von KI | Mit AI / KI-gestützt |
| Seamless integration | Nahtlose Integration | Verbindet sich direkt mit Ihren Systemen |
| Transform your workflow | Transformieren Sie Ihren Workflow | Name the concrete benefit |
| Unlock the power of... | Entfesseln Sie die Kraft von... | Nutzen Sie... / just name the benefit |
| Get started today | Starten Sie noch heute | Jetzt starten |
| Building the future of X | Die Zukunft von X bauen | No German equivalent. Use noun phrase or imperative |

### Restructuring Patterns

German sentence logic differs from English. Key rules:

- **Drop the subject when it's obvious.** EN: "We build custom agents." DE: "Massgeschneiderte AI-Agents für Ihr Unternehmen." — the "we" is implied
- **Object before verb for emphasis.** EN: "We'll handle the rest." DE: "Den Rest übernehmen wir." — puts the benefit first
- **Verb chains create energy.** EN: "Review it, reply to refine, or move on." DE: "Prüfen, antworten, anpassen — oder einfach weiterarbeiten."
- **Don't translate hedging.** EN: "We believe that..." — drop it in German. Direct claim is stronger

### Compound Noun Truncation

German allows shortening compound nouns when two share a base word: "Ein- und Ausgabe" (Eingabe + Ausgabe). Rules:

- The base word must appear in full at least once: "Rechts- oder Behördenanfragen" (correct)
- Never truncate leaving a dangling prefix: "Rechts- oder Behörden" (broken — "Behörden" is not the base word)
- When in doubt, write both words in full: "Rechtsanfragen oder Behördenanfragen"

### Gender-Inclusive Language
- Use gender-neutral forms where natural and not bureaucratic
- "Kollegen" in casual/marketing context, "Kolleginnen und Kollegen" in formal context where space permits
- Avoid Genderstern (*), Doppelpunkt (:), or Unterstrich (_) in B2B website copy

### Common Translation Patterns

**Sie-form defaults** (for Du-form, see CTA Button Conventions in the brand crawl section below):

| English | Swiss-German (Sie) | Swiss-German (Du) | Avoid |
|---------|-------------------|-------------------|-------|
| Send an email | Eine E-Mail senden | Eine E-Mail senden | Ein Email schicken |
| Get started | Jetzt starten | Jetzt starten / Jetzt loslegen | — |
| Learn more | Mehr erfahren | Mehr erfahren | — |
| Your inbox | Ihre Inbox | Deine Inbox | "Posteingang" (sounds dated in tech) |
| Contact us | Schreiben Sie uns | Schreib uns | "Kontaktieren" (too formal for Du, too generic for Sie) |
| AI Agent | AI-Agent | AI-Agent | KI-Agent (acceptable but less common in Swiss tech) |
| How it works | So funktioniert es | So funktioniert es | Wie es funktioniert (acceptable alternative) |

---

## Real-World Patterns from Top Brands (Crawl Data, March 2025)

Based on analysis of 12+ major brands with EN+DE websites: Swisscom, UBS, On Running, Logitech, IKEA CH, Stripe, Notion, Slack, Apple, Shopify, BMW, Vercel.

### Hero Headline Strategies

Top brands use **five distinct strategies** for hero translations — not just word-for-word:

**1. Shorten and punch** (Apple's approach)
- EN: "Amazing Mac. Surprising price." → DE: "Starker Mac. Smarter Preis."
- EN: "Feature stacked. Value packed." → DE: "Kann viel. Guter Deal."
- Pattern: Fewer words, stronger rhythm. German can be more compact.

**2. Complete rewrite** (Notion's approach)
- EN: "One workspace. Zero busywork." → DE: "Arbeite mit deinem KI-Team noch schneller."
- Pattern: Different message entirely, optimized for what resonates in DE market.

**3. Add engagement** (Shopify's approach)
- EN: "Be the next big thing." → DE: "Was steckt in dir? Der nächste grosse Renner."
- Pattern: Add a question to create dialogue. German audiences respond to directness.

**4. Restructure for German logic** (Stripe's approach)
- EN: "Financial infrastructure to grow your revenue." → DE: "Die Finanzinfrastruktur für mehr Umsatz."
- Pattern: Simplify the verb phrase. "grow your revenue" → "für mehr Umsatz" (noun phrase).

**5. Stay close** (Swisscom's approach — when structure already works)
- EN: "Unlimited on Switzerland's best network" → DE: "Unlimitiert im besten Netz der Schweiz"
- Pattern: When the English structure is already Germanic, keep it. Don't change for the sake of changing.

### CTA Button Conventions (Industry Standard)

From analyzing 50+ CTAs across brands, these are the established patterns:

| Pattern | Sie-form | Du-form | Used by |
|---------|----------|---------|---------|
| Get started | Jetzt starten | Jetzt starten | Stripe, Shopify |
| Start for free | Kostenlos starten | Kostenlos starten | Shopify |
| Learn more | Mehr erfahren | Mehr erfahren | Common |
| Learn more (alt) | Weitere Infos | Weitere Infos | Apple |
| Contact sales | Sales-Team kontaktieren | — | Stripe |
| Request a demo | Demo anfordern | Demo anfordern | Notion, Slack |
| Shop now | Jetzt kaufen | Jetzt kaufen | Logitech |
| Pre-order | Vorbestellen | Vorbestellen | Apple |
| Sign in | Anmelden | Anmelden | Stripe, Slack |
| Log in | Einloggen | Einloggen | Shopify |
| View offer | Angebot ansehen | Angebot ansehen | Swisscom |
| Add to cart | In den Warenkorb | In den Warenkorb | IKEA |
| Find your X | Finden Sie Ihren X | Finde deinen X | BMW, Slack |

### Du vs Sie — The Industry Split

Clear pattern across 12+ brands:

**Du-form brands** (B2C, consumer, prosumer):
Swisscom (private), On Running, IKEA, Notion, Slack, Shopify, Apple DE

**Sie-form brands** (B2B, finance, enterprise, premium):
UBS, Logitech, Stripe, Swisscom (business)

**Decision rule:** If individuals buy the product → Du. If companies buy → Sie. Swisscom even splits: Du for private customers, formal for business.

### Number & Currency Formatting (Swiss Conventions Confirmed)

| Convention | Example | Confirmed by |
|-----------|---------|-------------|
| Apostrophe thousands | 1'000, 2'499.– | Swisscom, UBS |
| CHF before amount | CHF 100 | Swiss standard |
| Millions abbreviated | 150Mio.+ | Shopify DE |
| Billions | 1,4 Bio. $ | Stripe DE |
| Price format | 49.90/Mt. | Swisscom |
| Dash for .00 | 99.– | Swisscom |

### Gender-Inclusive Language in Practice

Brands handle this differently:

| Brand | Approach | Example |
|-------|----------|---------|
| Stripe | Slash form | Entwickler/innen |
| Slack | Colon form | Kolleg:innen |
| UBS | Full form | Mitarbeitenden |
| Logitech | Neutral | (avoids gendered terms) |
| On Running | Asterisk | Athlet*innen |
| Swisscom | (varies) | — |

**Recommendation for Swiss B2B:** Avoid Genderstern (*) and colon (:) in website copy. Use neutral forms or slash (/) if needed. Full form ("Kolleginnen und Kollegen") for formal contexts.

### Navigation Taxonomy (What Gets Translated)

Across all crawled brands, navigation follows consistent rules:

**Always translate:**
Products → Produkte, Solutions → Lösungen, Pricing → Preise/Preisgestaltung/Tarife, Resources → Ressourcen, Features → Funktionen, Careers → Karriere, About us → Über uns

**Never translate:**
Enterprise, Support, Shop, Blog, Community, FAQ

**Product names stay English:** Slack Connect, Shop Pay, Shopify Flow, CloudTec®, MX Series

### Legal Register Patterns from Top Brands (Crawl Data, March 2025)

Based on privacy policies, terms of service, and legal pages from Apple, Stripe, UBS, Logitech, Shopify, Slack, IKEA CH.

**1. Formal legal register — how brands maintain it**

Legal text uses a distinctly different register from UI/marketing. Key patterns:
- **Nominalizations are acceptable** in legal text (unlike UI). "Erhebung, Nutzung und Weitergabe" (Stripe) instead of verb chains
- **Longer sentences are acceptable** if they preserve legal precision. Apple and Stripe routinely use 30+ word sentences in legal text
- **Passive voice is standard.** "Daten werden erhoben" is normal legal German — don't rewrite to active voice as you would for UI
- **Genitive constructions are preferred.** "Weitergabe personenbezogener Daten durch Apple" — formal genitive, not "Apple gibt Ihre Daten weiter"

**2. Sie-form in legal text**

5 of 7 crawled brands use **Sie** in legal text, even if they use Du elsewhere:
- Apple (Du in store → Sie in privacy policy)
- Stripe, UBS, Logitech, Shopify: Sie throughout legal text

Exceptions: Slack and IKEA CH maintain **Du** in privacy policies — consistent with their overall brand voice. This is unusual but deliberate.

**Recommendation:** Default to **Sie** for legal text. Only use Du if the brand explicitly maintains Du across all content including legal.

**3. Swiss ss convention in legal context**

Swiss ss applies in legal text just as in UI — confirmed by all brands:
- "Datenschutz" (not "Datenschütz") — all brands
- "Verstoss" / "Verstösse" — implied in violation contexts
- "Massnahmen" — all brands (not "Maßnahmen")
- "gemäss" — IKEA, Apple (not "gemäß")
- "grosser" / "grosse" — all Swiss brands (not "großer")

No brand uses ß in any context. The ss convention is universal in Swiss legal text.

**4. Jurisdiction clauses for Swiss law**

How brands reference Swiss law:
- Stripe: "Bundesgesetz über den Datenschutz (DSG)" for Swiss FADP
- IKEA CH: "Eidgenössischer Datenschutz- und Öffentlichkeitsbeauftragter (EDÖB)" for the Swiss DPA
- Stripe: "Datenschutzrahmen Schweiz–USA" for Swiss-U.S. DPF
- All brands: "DSGVO" (not "GDPR") when referencing EU regulation in German text
- Stripe SSA: Switzerland falls under UK/England governing law with ICC arbitration in London

**Pattern:** Brands with Swiss operations reference both DSGVO and DSG. The DSG (Swiss data protection act) is always mentioned separately — it's never assumed to be covered by DSGVO.

**5. "Einwilligung" vs "Zustimmung"**

Both translate "consent" but have different weight:
- **Einwilligung**: Formal DSGVO legal term, used by Apple, Stripe, IKEA in data protection contexts
- **Zustimmung**: Slightly less formal, used by Shopify, Logitech for general agreement

**Rule:** In DSGVO/DSG-specific contexts (data processing consent, cookie consent), always use "Einwilligung". For general agreement language ("by using this service, you agree"), "Zustimmung" or "Einverständnis" (UBS) is acceptable.

**6. Data processing verb preferences**

| Formality | "collect" | "process" | "share" |
|-----------|-----------|-----------|---------|
| Formal (Sie) | erheben / erfassen | verarbeiten | weitergeben |
| Standard | erfassen | verarbeiten | weitergeben |
| Casual (Du) | sammeln | verarbeiten | weitergeben / teilen |

"verarbeiten" and "weitergeben" are universal across all formality levels. Only "collect" varies: "erheben" (most formal, Stripe/Apple) → "erfassen" (neutral) → "sammeln" (casual, IKEA/Slack).
