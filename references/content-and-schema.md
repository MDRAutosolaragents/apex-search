# Answer Content, Information Gain, and Entity Graph Design

Use this reference to create or improve search-facing content, entity architecture, and JSON-LD. All facts, source URLs, claims, prices, locations, credentials, reviews, identities, and dates must be verified before publication.

## A. Citation-ready content brief

Build a brief before drafting:

| Field | Required decision |
|---|---|
| Page job | The business and user outcome this page supports |
| Audience and context | Who needs the answer and their market, stage, and constraints |
| Primary question | The exact customer question, not merely a keyword |
| Answer contract | Direct answer, conditions, proof, limitation, and next step |
| Primary entity | The thing/person/service/process the page is chiefly about |
| Source plan | First-party method/data, primary sources, expert review, and external corroboration as applicable |
| Conversion | The relevant action and the information required to take it safely |
| Internal links | Evidence/deeper reading in; next decision/action out |
| Risk review | Claims requiring legal, clinical, financial, or subject-matter review |

### Page pattern

Use the pattern that fits the query. Omit parts that do not add decision value.

```text
H1: specific page promise

Direct answer
  - 1–3 concise sentences that answer the heading.
  - Include the condition or scope that prevents a misleading answer.
  - Link or cite the evidence supporting material factual claims.

What this means / definition
  - Define the entity, service, standard, or decision term precisely.

How it works / parameters
  - Ordered steps or a parameter table, sourced where needed.

Comparison or decision matrix
  - Compare criteria that materially affect the visitor’s choice.

Evidence, method, and limitations
  - State author/expert, provenance, dates, exclusions, uncertainty, conflicts, and who the advice does not fit.

Related choices and next step
  - Contextual internal links and one appropriate CTA.
```

### Claim ledger

Create a claim ledger for material assertions before publishing:

| Claim | Claim type | Proof/source | Date/scope | Limitation | Page location | Review status |
|---|---|---|---|---|---|---|

Claim types include first-party observation, public statistic, expert opinion, policy/standard, customer outcome, comparison, and marketing statement. A source link alone does not cure a misleading comparison or unsupported causal claim.

### Retrieval-friendly semantic structure

- Use a heading that names the real question or entity.
- Put the most complete direct answer directly after the heading.
- Express key relationships with explicit nouns and verbs: provider → offers → service → for audience → in market → under conditions.
- Use `<table>` only for genuine tabular comparison, with column headers and a caption if helpful. Pair a dense table with explanatory prose for accessibility and nuance.
- Use `<ol>` for a real sequence and `<dl>` for definitions. Do not hide critical information in an accordion or image alone.
- Cite first-party method pages, primary sources, and reliable independent sources near the assertion they support. Do not create fake citation lists.
- Use publish/review dates only when the editorial process can substantiate them. Explain changes to material numbers or methodology.

## B. Information Gain Index

Use this index to decide whether a proposed section contributes source-worthy information beyond generic consensus. Score each dimension 0–3 using evidence in the reviewed corpus:

| Dimension | 0 | 1 | 2 | 3 |
|---|---|---|---|---|
| Originality | Rephrased common claim | Common synthesis | Specific experience/analysis | New, non-duplicative primary finding or method |
| Verifiability | Unsupported | Vague attribution | Traceable source/method | Reproducible source, methodology, scope, and limitations |
| Specificity | Broad claim | Some context | Defined audience/conditions | Precise variables, boundaries, and exceptions |
| Decision utility | No practical effect | General education | Helps compare or choose | Changes a consequential decision with appropriate caveats |
| Maintenance | Undated/volatile | Dated but unclear upkeep | Owner/review trigger stated | Update method and version/change context are available |

`Information Gain Index = sum of five dimensions / 15`

Interpret as an editorial triage signal:

- **0.00–0.33:** Remove, consolidate, or obtain evidence before publishing.
- **0.34–0.66:** Useful support content; improve provenance or specificity.
- **0.67–1.00:** Strong candidate for a source or citation asset, subject to independent review.

This does not measure quality universally, predict rankings, or estimate any model’s citation probability. A high score cannot compensate for poor crawlability, inaccurate facts, legal risk, or a weak customer need.

## C. Citation readiness coverage

Use a claim-level coverage review instead of an opaque “AI score.” For each priority question, count material answer claims and score whether each has all of the following:

- a clear statement;
- visible supporting evidence or a source;
- date/scope or qualifying condition where material;
- a resolved primary entity;
- a stable, publicly accessible canonical URL.

`Coverage = fully supported material claims / total material claims`

Report the numerator, denominator, scope, and unresolved claims. This indicates editorial completeness for the chosen sample only. It does not predict retrieval, citation, ranking, or model knowledge.

## D. Entity graph design

Start by drawing verified relationships. Example:

```text
WebSite ─publishes→ WebPage ─about→ Service
   │                         └─mainEntity→ Article / FAQ / Product
   └─publisher→ Organization ─offers→ Service
                            └─founder/member→ Person
Person ─worksFor→ Organization
Organization / Person ─sameAs→ verified official or authoritative identifiers
```

Use one stable absolute `@id` for each reusable entity. Prefer the entity’s canonical page fragment, such as `https://example.com/#organization` or `https://example.com/about/jordan-lee/#person`. `sameAs` is for identity equivalence, not a list of social networks to manufacture. Include only real profiles that the owner controls or a verified authoritative identifier that unequivocally names the entity.

### Production JSON-LD starting pattern

Replace placeholders only after verifying them. Remove optional fields that lack evidence. Match each page fragment to visible page content; this example is a design pattern, not a universal block to paste on every page.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Organization",
      "@id": "https://example.com/#organization",
      "name": "Verified Organization Name",
      "url": "https://example.com/",
      "logo": {
        "@type": "ImageObject",
        "@id": "https://example.com/#logo",
        "url": "https://example.com/assets/logo.png"
      },
      "founder": { "@id": "https://example.com/about/jordan-lee/#person" },
      "sameAs": [
        "https://www.linkedin.com/company/verified-organization",
        "https://www.wikidata.org/wiki/QVERIFIED"
      ]
    },
    {
      "@type": "Person",
      "@id": "https://example.com/about/jordan-lee/#person",
      "name": "Jordan Lee",
      "url": "https://example.com/about/jordan-lee/",
      "worksFor": { "@id": "https://example.com/#organization" },
      "sameAs": ["https://www.linkedin.com/in/verified-person"]
    },
    {
      "@type": "WebSite",
      "@id": "https://example.com/#website",
      "url": "https://example.com/",
      "name": "Verified Organization Name",
      "publisher": { "@id": "https://example.com/#organization" }
    },
    {
      "@type": "WebPage",
      "@id": "https://example.com/service/#webpage",
      "url": "https://example.com/service/",
      "name": "Visible page title",
      "isPartOf": { "@id": "https://example.com/#website" },
      "about": { "@id": "https://example.com/service/#service" },
      "publisher": { "@id": "https://example.com/#organization" }
    },
    {
      "@type": "Service",
      "@id": "https://example.com/service/#service",
      "name": "Visible service name",
      "provider": { "@id": "https://example.com/#organization" },
      "url": "https://example.com/service/"
    }
  ]
}
</script>
```

Validation checklist:

1. JSON parses and each absolute URL resolves to the intended canonical public page or asset.
2. Each `@type`, property, and relationship has the intended schema meaning.
3. Every claim, price, rating, location, offer, credential, and review is visible and verifiable on the page.
4. Reused entities have one consistent `@id`; page-specific entities do not overwrite them.
5. `FAQPage`, `Review`, `AggregateRating`, `Product`, `Course`, `LocalBusiness`, medical, and other specialised types match current eligibility and visible content. Omit any unsupported type.
6. Validate with an appropriate current validator, then inspect the rendered page and resulting graph. Validator success does not guarantee display or use by a search or answer engine.

## E. Content quality gate

Before handoff, check:

- direct answer is accurate, complete enough for the heading, and appropriately qualified;
- terminology resolves the primary entity and its relationships;
- each comparison dimension is fair, current, and relevant to the user’s decision;
- sources are real, accessible, accurate, and near the claims they support;
- original data says how it was collected and what it cannot show;
- medical, legal, financial, safety, and regulated claims have the required review and limitations;
- schema exactly represents visible page facts;
- copy is useful to a person first and does not make claims of guaranteed AI inclusion.
