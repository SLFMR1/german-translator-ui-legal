# Translation Examples

Real EN→DE examples. These are the quality benchmark.

**Core principle: Restructure, don't translate.** Write the German thought fresh. If it reads like someone ran it through a translator, rewrite it.

**Self-check before finalizing:** Read the German out loud. Would a Swiss product manager at a Zug tech company write it this way? If it sounds like a document, rewrite it until it sounds like a person.

## UI Strings (Short)

```json
// EN
{
  "Agents": {
    "heading": "Agents",
    "subheading": "Agentic coworkers, ready to work.",
    "description": "Some are available instantly. Others are custom-built for your company — with deep integrations into SAP, Microsoft 365, Slack, and your existing tools.",
    "hireInstantly": "Hire instantly",
    "customDeployment": "Custom deployment",
    "getStarted": "Get started",
    "requestAgent": "Request this agent",
    "showLess": "Show less",
    "showAll": "Show all {count}"
  }
}

// DE
{
  "Agents": {
    "heading": "Agents",
    "subheading": "Wie Kollegen. Nur schneller.",
    "description": "Einige Agents stehen sofort bereit. Andere entwickeln wir speziell für Ihr Unternehmen — mit direkter Integration in SAP, Microsoft 365, Slack und Ihre bestehenden Tools.",
    "hireInstantly": "Sofort einsetzen",
    "customDeployment": "Individuelle Entwicklung",
    "getStarted": "Jetzt starten",
    "requestAgent": "Agent anfragen",
    "showLess": "Weniger anzeigen",
    "showAll": "Alle {count} anzeigen"
  }
}
```

Why this works:
- "Wie Kollegen. Nur schneller." — doesn't literally translate "agentic coworkers." Captures the concept in natural German with rhythm. Two short sentences that click instantly (Obvious Adams Test 4)
- "Integration" kept — standard Swiss tech vocabulary, no need to germanize
- "Tools" kept — natural in Swiss tech context
- `{count}` placeholder preserved exactly

## Descriptive Strings (Medium)

```json
// EN
{
  "HowItWorks": {
    "heading": "How It Works",
    "subheading": "Three steps. No onboarding.",
    "step1Title": "Send an email",
    "step1Description": "Write to the agent like you'd write to a colleague. Plain language, attachments, whatever you need.",
    "step2Title": "The agent does the work",
    "step2Description": "It reads your request, connects to your systems — CRM, databases, APIs — and executes the task.",
    "step3Title": "You get the result",
    "step3Description": "A reply lands in your inbox with the completed work. Review it, reply to refine, or move on."
  }
}

// DE
{
  "HowItWorks": {
    "heading": "So funktioniert es",
    "subheading": "Drei Schritte. Kein Onboarding.",
    "step1Title": "E-Mail schreiben",
    "step1Description": "Schreiben Sie dem Agent wie einem Kollegen. Klartext, Anhänge — was immer Sie brauchen.",
    "step2Title": "Der Agent erledigt die Arbeit",
    "step2Description": "Er liest Ihre Anfrage, verbindet sich mit Ihren Systemen — CRM, Datenbanken, APIs — und erledigt die Aufgabe.",
    "step3Title": "Ergebnis in der Inbox",
    "step3Description": "Die fertige Arbeit landet direkt in Ihrer Inbox. Prüfen, antworten, anpassen — oder einfach weiterarbeiten."
  }
}
```

Why this works:
- "Klartext" — one punchy word instead of "einfache Sprache"
- "Ergebnis in der Inbox" — noun phrase, not "Sie erhalten das Ergebnis" (translationese)
- "Prüfen, antworten, anpassen" — verb chain creates energy, matches English rhythm
- "einfach weiterarbeiten" — "einfach" is the #1 word in Swiss SaaS copy per research

## Marketing / Hero Strings

```json
// EN
{
  "Hero": {
    "tagline": "We build AI agents you hire by email.",
    "description": "We build custom AI agents for your company — deeply integrated with SAP, Outlook, Teams, Slack, and more. Want your own? Get in touch.",
    "email": "contact@example.ch"
  },
  "CTABar": {
    "heading": "Want your own AI agent?",
    "description": "Tell us what you need. We'll take it from there."
  }
}

// DE
{
  "Hero": {
    "tagline": "AI-Agents, die Sie per E-Mail beauftragen.",
    "description": "Wir entwickeln massgeschneiderte AI-Agents für Ihr Unternehmen — tief integriert in SAP, Outlook, Teams, Slack und mehr. Interesse? Schreiben Sie uns.",
    "email": "contact@example.ch"
  },
  "CTABar": {
    "heading": "Ihr eigener AI-Agent?",
    "description": "Sagen Sie uns, was Sie brauchen. Den Rest übernehmen wir."
  }
}
```

Why this works:
- Tagline drops "We build" — stronger without subject. Starts with the product
- "Schreiben Sie uns" not "Kontaktieren Sie uns" — matches the email-first brand, more human
- "Den Rest übernehmen wir." — natural German word order (object first), confident and direct
- "massgeschneiderte" — Swiss ss, not ß

## Quote / Testimonial

```json
// EN
{
  "Founder": {
    "quote": "We believe the best AI tools disappear into workflows you already use. No dashboards to learn, no apps to install — just email. That's how work should be.",
    "name": "Jane Smith",
    "title": "Founder & CEO · Speaker at Web Summit & World Economic Forum"
  }
}

// DE
{
  "Founder": {
    "quote": "Die besten AI-Tools verschwinden in Workflows, die Sie schon nutzen. Keine Dashboards, keine neuen Apps — nur E-Mail. So soll Arbeit sein.",
    "name": "Jane Smith",
    "title": "Gründerin & CEO · Speaker am Web Summit & World Economic Forum"
  }
}
```

Why this works:
- Drops "We believe" — in German it hedges ("Wir glauben"). Direct claim is stronger
- "Workflows" kept — standard Swiss tech vocabulary, more natural than "Arbeitsabläufe"
- "So soll Arbeit sein." — four words. Declarative. Punchy. Doesn't over-explain

## Agent Descriptions

```json
// EN
{
  "invoiceProcessing": {
    "name": "Invoice Processing Agent",
    "description": "Send invoices as attachments. Gets them categorized, validated, and ready for approval."
  },
  "complianceMonitor": {
    "name": "Compliance Monitor Agent",
    "description": "Continuously checks processes against regulatory requirements and flags violations."
  },
  "crmCoworker": {
    "name": "CRM Coworker Agent",
    "description": "Reads inbound emails, updates CRM records, drafts replies, flags deals."
  }
}

// DE
{
  "invoiceProcessing": {
    "name": "Invoice Processing Agent",
    "description": "Rechnungen als Anhang senden. Werden automatisch kategorisiert, geprüft und zur Freigabe vorbereitet."
  },
  "complianceMonitor": {
    "name": "Compliance Monitor Agent",
    "description": "Prüft Prozesse laufend gegen regulatorische Vorgaben und meldet Verstösse."
  },
  "crmCoworker": {
    "name": "CRM Coworker Agent",
    "description": "Liest eingehende E-Mails, aktualisiert CRM-Einträge, entwirft Antworten, markiert Deals."
  }
}
```

Why this works:
- Agent names stay English — these are product identifiers
- "Werden automatisch kategorisiert, geprüft und..." — verbs, not nominalizations. "Kategorisierung, Prüfung und Freigabevorbereitung" would be bureaucratic
- "Verstösse" — Swiss ss convention
- "markiert Deals" — "Deals" is standard Swiss business vocabulary
- Short parallel structure — mirrors the punchy English rhythm without literal translation

## Legal Strings (Privacy / Terms)

```json
// EN
{
  "privacy": {
    "dataCollection": "We collect personal information you provide directly, such as your name, email address, and company details.",
    "cookies": "You may opt out of non-essential cookies at any time through your browser settings.",
    "thirdParty": "We may share your information with trusted service providers who assist us in operating our platform.",
    "rights": "You have the right to access, correct, or delete your personal information at any time.",
    "jurisdiction": "These terms are governed by the laws of the Canton of Zug, Switzerland."
  }
}

// DE
{
  "privacy": {
    "dataCollection": "Wir erfassen persönliche Informationen, die Sie uns direkt mitteilen, wie Ihren Namen, Ihre E-Mail-Adresse und Firmenangaben.",
    "cookies": "Sie können nicht-essenzielle Cookies jederzeit über Ihre Browser-Einstellungen deaktivieren.",
    "thirdParty": "Wir können Ihre Informationen an vertrauenswürdige Dienstleister weitergeben, die uns beim Betrieb unserer Plattform unterstützen.",
    "rights": "Sie haben jederzeit das Recht, Ihre persönlichen Informationen einzusehen, zu berichtigen oder löschen zu lassen.",
    "jurisdiction": "Diese Bedingungen unterliegen dem Recht des Kantons Zug, Schweiz."
  }
}
```

Why this works:
- "personal information" → "persönliche Informationen" — NOT "personenbezogene Daten" (which is the DSGVO term for "personal data"). Translate what the source says, not what it should say
- "opt out" → "deaktivieren" — NOT "widersprechen" (formal DSGVO Art. 21 right of objection). Match the weight of the source term
- "may share" → "können ... weitergeben" — preserves the "may" as permission, not obligation
- "trusted service providers" → "vertrauenswürdige Dienstleister" — NOT "Auftragsverarbeiter" (which would be "data processors" — a different legal concept)
- "Canton of Zug" → "Kanton Zug" — Swiss jurisdiction reference preserved

## Legal Pitfalls (What NOT to Write)

| English source | Wrong German | Why wrong | Correct German |
|---|---|---|---|
| personal information | personenbezogene Daten | Upgrades informal term to DSGVO term — changes legal meaning | persönliche Informationen |
| opt out | widersprechen | Escalates to formal DSGVO Art. 21 right — source is informal | deaktivieren / abmelden |
| service providers | Auftragsverarbeiter | "Data processors" is a different legal concept | Dienstleister |
| legal or regulatory requests | Rechts- oder Behörden | Incomplete compound — grammatically broken | Rechts- oder Behördenanfragen |
| we may share | wir geben weiter | Drops "may" — changes permission to statement of fact | wir können ... weitergeben |
| shall notify | soll benachrichtigen | "soll" is weaker than "shall" — use "hat zu benachrichtigen" | hat ... zu benachrichtigen |

## Common Traps (What NOT to Write)

For the full translationese traps table, see [swiss-german-style.md](swiss-german-style.md#translationese-traps). Key traps specific to UI translation:

| English | Translationese (avoid) | Natural German (use) |
|---------|----------------------|---------------------|
| Digital employees | Digitale Mitarbeitende | Sounds like HR policy. Use: Digitale Kollegen, AI-Agents, or rephrase entirely |
| Get started today | Starten Sie noch heute | Jetzt starten / Kostenlos testen |
| Unlock the power of... | Entfesseln Sie die Kraft von... | Nutzen Sie... or just name the benefit |

---

## Real Brand Translation Pairs (Crawled from Top 100 Brands)

The examples below are real EN→DE pairs observed on live brand websites (March 2025). They show how leading companies actually localize — not textbook theory.

### Hero Headlines

| Brand | EN | DE | Pattern |
|-------|----|----|---------|
| Apple | Amazing Mac. Surprising price. | Starker Mac. Smarter Preis. | Short rhythmic pairs, adjective swap for punchiness |
| Apple | Feature stacked. Value packed. | Kann viel. Guter Deal. | Even shorter in DE — 4 words instead of 4 |
| Stripe | Financial infrastructure to grow your revenue. | Die Finanzinfrastruktur für mehr Umsatz. | Simplified: "grow your revenue" → "für mehr Umsatz" |
| Notion | One workspace. Zero busywork. | Arbeite mit deinem KI-Team noch schneller. | Completely rewritten for DE market — different message |
| Slack | Slack is your team's collective brain. | Slack ist das gesammelte Wissen deines Teams. | Natural restructuring, Du-form |
| Shopify | Be the next big thing. | Was steckt in dir? Der nächste grosse Renner. | Added question opener — more engaging in DE |
| Swisscom | Unlimited on Switzerland's best network | Unlimitiert im besten Netz der Schweiz | Nearly literal — works because structure matches |
| BMW | Sheer Driving Pleasure | Freude am Fahren | Iconic rewrite — completely different structure |
| Logitech | Feel the difference | Spüren Sie den Unterschied | Direct translation — works for imperatives |
| On Running | (product hero) | Der Trainingslaufschuh mit dreifacher CloudTec® Dämpfung | Descriptive, compound noun, product-focused |

**Key insight:** Top brands don't translate heroes literally. Apple shortens, Notion rewrites entirely, Shopify adds a question. Only Swisscom/Logitech stay close to the original — and those are already structured similarly in both languages.

### CTA Buttons

| EN | DE | Brand(s) | Notes |
|----|----|----------|-------|
| Get started | Jetzt starten | Stripe | Most common pattern |
| Get started | Erste Schritte | Slack | Alternative — more literal |
| Start for free | Kostenlos starten | Shopify | Price-first in DE too |
| Get Notion free | Nutze Notion kostenlos | Notion | Du-form imperative + brand name |
| Learn more | Weitere Infos | Apple | Noun phrase instead of imperative |
| Learn more | Mehr erfahren | Common | Standard |
| Shop now | Jetzt kaufen | Logitech | Standard e-commerce |
| Shop deals | Jetzt kaufen | Logitech | "Deals" → "kaufen" (simplified) |
| Pre-order | Vorbestellen | Apple | Direct translation |
| View offer | Angebot ansehen | Swisscom | |
| Watch the film | Film ansehen | Apple | Object-first |
| Contact sales | Sales-Team kontaktieren | Stripe | "Sales" kept — hybrid term |
| Request a demo | Demo anfordern | Notion, Slack | "Demo" kept in EN |
| Find your plan | Deinen Plan finden | Slack | Du-form |
| Sign in | Anmelden | Stripe, Slack | Universal |
| Sign in with Google | Bei Google anmelden | Stripe | |
| Log in | Einloggen | Shopify | Casual alternative |
| Add to cart | In den Warenkorb | IKEA | Standard e-commerce |
| View developer docs | Entwicklerdokumentationen ansehen | Stripe | Full germanization |
| Start deploying | (kept EN) | Vercel | Dev-facing → stays English |

### Navigation Items

| EN | DE | Brand(s) |
|----|----|----------|
| Products | Produkte | Stripe, IKEA, Logitech |
| Solutions | Lösungen | Stripe, Slack, Shopify, Notion |
| Pricing | Preisgestaltung | Stripe |
| Pricing | Preise | Slack |
| Pricing | Tarife | Notion |
| Resources | Ressourcen | Stripe, Slack, Shopify, Notion |
| Features | Funktionen | Slack |
| Developers | Entwickler/innen | Stripe |
| Enterprise | Enterprise | Notion, Slack, Vercel (kept EN) |
| What's new | Was ist neu? | Shopify |
| Careers | Karriere | Logitech, Notion |
| Careers | Stellenangebote | Apple |
| Support | Support | Swisscom, Logitech (kept EN) |
| About us | Wir über uns | UBS |
| About us | Über uns | Notion |
| Accessories | Zubehör | Apple |
| Shop | Shop | IKEA, Logitech (kept EN) |

### Section Headings

| Brand | EN | DE |
|-------|----|----|
| Logitech | Discover our most popular product categories | Entdecken Sie unsere beliebtesten Produktkategorien |
| Logitech | Reasons to buy from Logitech.com | Gründe für einen Kauf auf Logitech.com |
| Logitech | Design for sustainability | Nachhaltiges Design |
| IKEA | Current IKEA Family offers | Aktuelle IKEA Family Angebote |
| IKEA | Shop by categories | Einkaufen nach Kategorien |
| IKEA | Inspiration for every room | Inspiration für jeden Raum |
| IKEA | What's new at IKEA? | Was gibt es Neues bei IKEA? |
| Swisscom | Current offers and tips | Aktuelle Angebote und Tipps |
| Swisscom | Counselling and support | Beratung und Support |
| Swisscom | Stay connected at all times | Bleib jederzeit verbunden |
| Swisscom | Feel secure | Fühl dich sicher |
| Swisscom | Get support | Erhalte Unterstützung |
| Swisscom | Awarded for service and network | Ausgezeichnet für Service und Netz |
| UBS | Our capabilities | Globale Kompetenzen |
| Stripe | Flexible solutions for every business model | Flexible Lösungen für jedes Geschäftsmodell |
| Stripe | Reliable, extensible infrastructure for every stack | Zuverlässige, erweiterbare Infrastruktur für jeden Stack |
| On Running | Stories that move | Storys, die bewegen |

### Benefit Statements & Feature Descriptions

| Brand | EN | DE |
|-------|----|----|
| Logitech | Buy now, pay later | Jetzt kaufen, später bezahlen |
| Logitech | Free shipping | Kostenloser Versand |
| Logitech | Money-back guarantee | Geld-zurück-Garantie |
| Logitech | 24/7 customer service | Kundenservice rund um die Uhr |
| Logitech | Exclusive offers | Exklusive Angebote |
| Swisscom | Online only: Free activation | Nur online: Aktivierung geschenkt |
| Swisscom | Best internet and most popular TV subscription | Bestes Internet & beliebtestes TV-Abo |
| Shopify | Higher conversions: 15% | Höhere Conversion: 15% |
| Shopify | High-intent shoppers: 150M+ | Interessierte mit hoher Kaufabsicht: 150Mio.+ |
| Slack | Move faster and work smarter, with people, apps, and AI at your side. | Arbeite schneller und intelligenter — mit Kolleg:innen, Apps und KI an deiner Seite. |
| Notion | Now a team of 7 feels like 70. | (rewritten entirely for DE) |
| UBS | We offer private clients a complete range of financial services... | UBS bietet vermögenden Privatpersonen weltweit eine umfassende Palette von massgeschneiderten Beratungs- und Anlagedienstleistungen. |

### Footer & Legal Labels

| EN | DE | Brand(s) |
|----|----|----------|
| Privacy Policy | Datenschutzrichtlinie | Apple, Logitech |
| Privacy Policy | Datenschutzerklärung | UBS |
| Terms of Use | Nutzungsbedingungen | Apple, UBS |
| Cookie Settings | Cookie-Einstellungen | Logitech |
| Sitemap | Sitemap | Apple, Logitech (kept EN) |
| Customer Service | Kundenservice | IKEA, Logitech |
| Help Center | Hilfe-Center | Notion |
| Returns & Claims | Rückgabe & Reklamation | IKEA |
| Delivery | Lieferung | IKEA |
| Assembly | Montage | IKEA |
| Contact us | Schreiben Sie uns / Kontaktiere uns | varies by Sie/Du |
| Report Misconduct | Fehlverhalten melden | UBS |
| Fraud Alert | Betrugswarnung | UBS |

### Du vs Sie — Brand Decisions

| Brand | Form | Context | Example |
|-------|------|---------|---------|
| Swisscom | Du | B2C residential | "Entdecke, was du kannst" / "Erzähl, was dich bewegt" |
| On Running | Du | B2C sport/lifestyle | "Finde deinen On" / "Zum Hauptinhalt springen" |
| IKEA | Du | B2C home/retail | "Hej! Logge dich ein" / "Lass dich inspirieren" |
| Notion | Du | B2C/prosumer SaaS | "Nutze Notion kostenlos" / "Arbeite mit deinem KI-Team" |
| Slack | Du | B2C/prosumer SaaS | "Deine Möglichkeiten" / "Deinen Plan finden" |
| Shopify | Du | B2C/SMB commerce | "Kostenlos starten" / "Was steckt in dir?" |
| Apple | Du | B2C consumer tech | "Gib dein iPhone in Zahlung" / "Weitere Infos" |
| UBS | Sie | B2B/wealth management | "Wir beraten Sie gerne" / formal throughout |
| Logitech | Sie | B2B/professional | "Spüren Sie den Unterschied" / "Entdecken Sie" |
| Stripe | Sie | B2B fintech | "Akzeptieren Sie Zahlungen" / "Jetzt starten" |

**Pattern:** B2C brands overwhelmingly use Du. B2B/enterprise/finance uses Sie. The dividing line is clear — if individuals buy the product, Du. If companies buy, Sie.

---

## Real Brand Legal Translation Pairs (Crawled from Top Brands)

Real EN→DE pairs from live privacy policies, terms of service, and legal pages (March 2025). Crawled from: Apple, Stripe, UBS, Logitech, Shopify, Slack, IKEA CH.

### Privacy Policy Section Headings

| Brand | EN | DE |
|-------|----|----|
| Apple | What Is Personal Data at Apple? | Was sind personenbezogene Daten bei Apple? |
| Apple | Personal Data Apple Collects from You | Personenbezogene Daten, die Apple von Ihnen erfasst |
| Apple | Apple's Use of Personal Data | Verwendung personenbezogener Daten durch Apple |
| Apple | Apple's Sharing of Personal Data | Weitergabe personenbezogener Daten durch Apple |
| Apple | Your Privacy Rights at Apple | Ihre Datenschutzrechte bei Apple |
| Apple | Cookies and Other Technologies | Cookies und andere Technologien |
| Apple | Transfer of Personal Data Between Countries | Übermittlung personenbezogener Daten zwischen Ländern |
| Stripe | Personal Data that we collect and how we use and share it | Erhebung, Nutzung und Weitergabe personenbezogener Daten |
| Stripe | Legal bases for processing data | Rechtsgrundlagen für die Verarbeitung personenbezogener Daten |
| Stripe | Your rights and choices | Ihre Rechte und Wahlmöglichkeiten |
| Stripe | Security and retention | Sicherheit und Speicherung |
| Stripe | International data transfers | Internationale Datenübermittlung |
| Logitech | Information We Collect | Informationen, die wir sammeln |
| Logitech | How We Use Information | Wie wir Informationen verwenden |
| Logitech | Sharing and Disclosing Information | Informationen teilen und offenlegen |
| Logitech | Your Rights and Choices | Ihre Rechte und Entscheidungen |
| Logitech | Special Information for EEA/UK/CH Users | Spezielle Informationen für Nutzer im EWR/UK/CH |
| Shopify | Why we process your information | Warum wir Ihre Daten verarbeiten |
| Shopify | Your rights over your information | Ihre Rechte an Ihren Daten |
| Shopify | Where we send your information | Wohin wir Ihre Daten senden |
| Shopify | How long do we retain your information | Wie lange bewahren wir Ihre Daten auf? |
| Slack | Information We Collect and Receive | Welche Daten erheben und empfangen wir |
| Slack | How We Process Your Information and Our Legal Bases | Verarbeitung deiner Daten und unsere Rechtsgrundlagen |
| Slack | How We Share and Disclose Information | Wie werden Daten von uns weitergegeben und offengelegt |
| IKEA CH | Responsibility for your personal data | Verantwortlichkeit für deine personenbezogenen Daten |
| IKEA CH | Types of personal data we collect | Arten von personenbezogenen Daten, die wir sammeln |
| IKEA CH | Cookies and similar technologies | Cookies und ähnliche Technologien |
| IKEA CH | Access to your information; correction and deletion | Zugang zu deinen personenbezogenen Daten, Korrektur oder Löschung |
| UBS | Privacy Notice for Clients | Datenschutzhinweis für Kunden |
| UBS | UBS Website, Social Media and Cookie Notice | UBS Website, Social-Media und Cookie-Mitteilung |

**Key patterns:**
- Stripe restructures freely: "collect and how we use and share it" → "Erhebung, Nutzung und Weitergabe" (noun chain)
- Apple uses genitive: "Apple's Sharing of..." → "Weitergabe ... durch Apple"
- Shopify simplifies: "your information" → "Ihre Daten" (not "Ihre Informationen")
- IKEA/Slack maintain Du-form even in privacy policies — consistent with B2C brand voice
- UBS uses "Datenschutzhinweis" (not "Datenschutzerklärung" or "Datenschutzrichtlinie")

### "Personal Data" — Universal Legal Translation

| Brand | EN Term | DE Term |
|-------|---------|---------|
| Apple | personal data | personenbezogene Daten |
| Stripe | Personal Data | personenbezogene Daten |
| Logitech | personal data / personal information | personenbezogene Daten |
| Shopify | Personal Data | personenbezogene Daten |
| Slack | Personal Data | personenbezogene Daten |
| IKEA CH | personal data | personenbezogene Daten |
| UBS | personal data | personenbezogene Daten |

**Universal rule:** Every brand uses "personenbezogene Daten" in legal context — never "persönliche Daten". This is the DSGVO standard. But remember: if the EN source uses the informal "personal information" (not "personal data"), translate as "persönliche Informationen" — don't upgrade (see Legal Pitfalls above).

### Data Collection & Processing Verbs

| EN | DE | Used by |
|----|----|---------|
| we collect | wir erheben / wir erfassen | Apple, Stripe, Shopify (formal) |
| we collect | wir sammeln | IKEA, Slack (slightly more casual) |
| we process | wir verarbeiten | Stripe, Shopify, Slack |
| we use | wir verwenden / wir nutzen | Apple, Logitech, Shopify |
| we share | wir geben ... weiter | All brands |
| we disclose | wir legen ... offen | Slack, Logitech |
| we store | wir speichern | Logitech, Shopify |
| we retain | wir bewahren ... auf | Shopify |
| we transfer | wir übermitteln | Apple |
| we delete | wir löschen | Shopify, IKEA |

**Guidance:** For formal legal text, prefer "erheben" or "erfassen" over "sammeln". "sammeln" is acceptable for B2C brands using Du-form.

### Consent & Rights Language

| Brand | EN | DE |
|-------|----|----|
| Apple | you have the right to withdraw your consent at any time | Sie haben das Recht, Ihre Einwilligung jederzeit zu widerrufen |
| Stripe | you may withdraw your consent at any time | Sie haben das Recht, Ihre Einwilligung jederzeit zu widerrufen |
| Apple | respect your ability to know, access, correct, transfer, restrict the processing of, and delete your personal data | Auskunft zu erhalten, auf sie zuzugreifen, sie zu korrigieren, zu übertragen, ihre Verarbeitung einzuschränken und sie zu löschen |
| Logitech | You can ask for a copy of the data we have about you | Sie können um eine Erklärung dazu bitten, welche Daten wir von Ihnen haben |
| Shopify | with your explicit consent | mit Ihrer ausdrücklicher Zustimmung |
| IKEA CH | Subject to your consent in the app settings | Vorbehaltlich deiner Einwilligung in den App-Einstellungen |
| UBS | By accessing UBS Websites, you accept our Notice | Mit dem Zugriff auf UBS-Websites erklären Sie Ihr Einverständnis |

**Pattern:** "consent" → "Einwilligung" (formal DSGVO term, used by Apple, Stripe, IKEA) or "Zustimmung" (slightly less formal, used by Shopify, Logitech). In strict DSGVO context, always use "Einwilligung".

### Cookie Language

| Brand | EN | DE |
|-------|----|----|
| Stripe | We use cookies and similar technologies | Verwendung von Cookies und vergleichbaren Technologien |
| Slack | Slack uses a variety of cookies and similar technologies | Slack verwendet zahlreiche verschiedene Cookies und ähnliche Technologien |
| Logitech | withdraw your consent or modify your choices at any time by clicking on 'Cookie Settings' | Logitech verwendet Cookies und ähnliche Technologien |
| IKEA CH | Cookies and similar technologies | Cookies sind kleine Dateien, die das Gerät generiert |
| Apple | (cookie categories) | Kommunikations-Cookies, Absolut notwendige Cookies, Sonstige Cookies |

**Pattern:** "Cookies" stays English everywhere. "similar technologies" → "ähnliche Technologien" (Slack, IKEA) or "vergleichbare Technologien" (Stripe). "Cookie-Einstellungen" for "Cookie Settings".

### Qualifier Words in Legal Context

| EN | DE | Brand Evidence |
|----|----|---------------|
| may | kann / dürfen | Stripe: "wir können ... weitergeben"; Logitech: "Wir dürfen Daten ... erfassen" |
| subject to | vorbehaltlich | IKEA: "Vorbehaltlich deiner Einwilligung"; Slack: "vorbehaltlich" |
| to the extent | soweit / im Umfang | Slack: "soweit"; Shopify: "im gesetzlich zulässigen Umfang" |
| where applicable | sofern zutreffend / gegebenenfalls | Apple, Logitech |
| provided that | sofern / vorausgesetzt dass | Slack: "sofern" |
| in accordance with | gemäss / in Übereinstimmung mit | IKEA, Apple |

**Note on "shall":** Stripe SSA uses "shall remain liable" → "bleibt haftbar" (present tense, not "hat zu" or "soll"). In practice, many brands avoid "shall" entirely and use present tense for obligations. Our rule: "shall" → "hat zu" for strong obligation — but verify the brand's actual pattern.

### Terms of Service — Liability & Indemnification

| Concept | EN (Shopify) | DE (Shopify) |
|---------|-------------|-------------|
| Liability cap | to the extent permitted by applicable laws, not liable for any direct, indirect, incidental, special, consequential or exemplary damages | im gesetzlich zulässigen Umfang nicht für direkte, indirekte, zufällige oder besondere Schäden |
| As-is disclaimer | Services are provided on an 'as is' and 'as available' basis | wie besehen und wie verfügbar |
| Indemnification | indemnify and hold us harmless from any claim or demand | erklären sich damit einverstanden, uns von allen Ansprüchen oder Forderungen freizustellen |

### Swiss-Specific Legal References

| Brand | EN | DE |
|-------|----|----|
| Stripe | Swiss Federal Act on Data Protection (FADP), as revised | Bundesgesetz über den Datenschutz (DSG) |
| Stripe | Swiss-U.S. Data Privacy Framework | Datenschutzrahmen Schweiz–USA |
| IKEA CH | Federal Data Protection and Information Commissioner (FDPIC) | Eidgenössischer Datenschutz- und Öffentlichkeitsbeauftragter (EDÖB) |
| Apple | Standard Contractual Clauses | Standardvertragsklauseln |
| Stripe | General Data Protection Regulation (GDPR) | Datenschutz-Grundverordnung (DSGVO) |
| Logitech | Swiss-U.S. Data Privacy Framework | Datenschutzrahmen Schweiz–USA |
| Apple | Data Protection Officer | Datenschutzbeauftragter |
| Apple | supervisory authority | Aufsichtsbehörde |

### Du vs Sie in Legal Text

| Brand | Form | Notes |
|-------|------|-------|
| Apple | Sie | "Ihre Datenschutzrechte", "von Ihnen erfasst" |
| Stripe | Sie | "Ihre Rechte und Wahlmöglichkeiten" |
| UBS | Sie | Formal throughout |
| Logitech | Sie | "Ihre Rechte und Entscheidungen" |
| Shopify | Sie | "Ihre Daten", "Ihre Rechte" |
| Slack | Du | "deiner Daten", "deine Rechte" — unusual for legal |
| IKEA CH | Du | "deine personenbezogenen Daten" — consistent with B2C voice |

**Pattern:** 5 of 7 brands use Sie in legal text. Slack and IKEA are exceptions — they keep Du-form consistent across all content. For Swiss B2B/SaaS legal text, Sie is the safe default.
