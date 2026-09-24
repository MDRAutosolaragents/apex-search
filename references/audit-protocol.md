# Full Generative Search Audit Protocol

Use this protocol for an unrestricted website audit, ranking diagnosis, or strategic roadmap. A focused request may use the relevant sections only. Preserve observed evidence alongside the final report.

## 0. Establish scope and an evidence register

Record the target domains/hosts, markets, languages, devices, date/timezone, permitted page and query limits, desired conversion, supplied data, and limitations. Keep a capture log that connects each material conclusion to its source.

Classify each item as:

| State | Meaning |
|---|---|
| Confirmed | Directly observed in a dated source or supplied first-party export |
| Directional | Partial capture or a source whose method/coverage limits a firm conclusion |
| Estimated | Transparent calculation from stated inputs |
| Unverified | A lead, assumption, snippet, or uninspected claim |

Do not turn a failed request, empty render, blocked URL, snippet, or missing export into proof that content, schema, visibility, or demand is absent.

## 1. Review the business and page system

1. Inspect the homepage, navigation, core commercial pages, About/contact pages, proof/case/review pages, blog/resources, and key conversion steps.
2. Build a page inventory: URL, page class, offer/topic, audience, market, conversion, indexability observation, internal links in/out, source of proof, and page owner where known.
3. Create a business model: offers, customer segments, decision criteria, market/geography, differentiators that can be proved, purchase friction, and priority conversion events.
4. Draft customer queries and questions in natural buyer language. Keep hypotheses distinct from observed query data.
5. Assign each important query/question to a page, proof asset, local/reputation action, or intentionally deprioritised gap.

## 2. Technical and rendering diagnostic

Sample representative templates, priority pages, and a bounded crawl where permitted. For each observation retain URL, final URL, status, canonical, robots directives, capture time, and raw/rendered representation.

| Area | Inspect | Useful decision |
|---|---|---|
| Access | DNS/TLS, response status, redirects, rate limits, WAF/challenge behavior | Fix delivery/access faults; do not bypass controls |
| Crawl and index controls | `robots.txt`, sitemap(s), meta/X-Robots directives, canonicals, pagination/facets | Identify intended indexable canonical URLs and contradictions |
| Rendering | Raw HTML vs rendered DOM, hydration errors, late content, asset failures, blocked scripts | Determine whether primary content/links exist in accessible HTML or depend on successful rendering |
| Architecture | Navigation, links, depth, duplicate paths, orphan candidates, language/region alternates | Improve discoverability and consolidate duplication |
| Page quality | Title, heading hierarchy, main content, canonical, images, structured data, accessibility landmarks | Recommend specific page/template changes |
| Experience | CWV field data when available, lab observations, payload/critical path, mobile interaction friction | Separate measured user data from a lab hypothesis |
| Measurement | Analytics/Search Console/CRM events, consent/tracking paths | Confirm whether outcomes can be tied to visibility and conversion |

Do not call a page “indexed” merely because it returned `200`, and do not call a page “not indexed” merely because it is absent from a limited search sample. Use a first-party index report when available and label lesser evidence accurately.

### AI retrieval access diagnostic

1. Capture `robots.txt`, relevant response headers, and any access challenge on the scoped host.
2. Identify the present retrieval/training/user-initiated bot policy from primary documentation. User-agent strings are examples, not stable categories.
3. Map every observed directive to its documented bot and purpose. Note conflicting routes, subdomain rules, sitemap references, and default behavior.
4. Assess whether key pages are public, crawlable, renderable, and supported by stable canonical URLs. This is readiness, not evidence that any model has retrieved them.
5. Report blocks and options in the owner’s terms. Never suggest circumvention.

## 3. On-page, answer, and content diagnostic

For each priority page, answer these questions:

1. Which user need and conversion does the page serve?
2. Does the title/H1/main body make the offer, audience, and context unambiguous?
3. Does the page directly answer the primary and natural follow-up questions?
4. Are definitions, process, scope, price/range, comparison, risks, eligibility, and next step present when relevant?
5. What first-party expertise, source, method, citation, expert identity, date, or limitation makes the assertions reliable?
6. Which supporting and commercial pages does it link to, and why?
7. What duplicated, obsolete, unsupported, or generic material should be repaired, consolidated, or removed through the authorised CMS/process?

Capture page-specific recommendations: title/H1 change, missing answer, required proof, internal source/target link, schema opportunity, CTA, and acceptance check. A generic instruction to “add FAQs” is incomplete.

## 4. Entity and citation-readiness diagnostic

Create an entity inventory before adding structured data:

| Entity | Canonical name/ID | Official URL | Facts to prove | Official profiles/identifiers | Conflicts or unknowns |
|---|---|---|---|---|---|

Then examine:

- identity: name variants, logo, owner/author/expert, address/service area, official profiles, and contact paths;
- relationship clarity: organisation-person, organisation-service/product, local organisation-location, author-work, product-offer, and page-main entity;
- source-worthiness: original findings, methodology, data collection, qualified experience, precise scope, external sources, and limitations;
- consistency: visible pages, metadata, schema, business profiles, social pages, review platforms, and independent mentions;
- answer coverage: a documented prompt/query, direct response, proof/citation, next question, and source page;
- citation gaps: exact facts, independent sources, clear author ownership, page sections, and retrieval access that are missing from a viable answer.

Do not claim a page is excluded from a named answer engine without a dated, reproducible observation. If an engine exposes cited sources, record the prompt, locale/context, date, complete answer state, observed citations, and caveats such as personalisation or feature rollout.

## 5. Local, reputation, and authority diagnostic

Use this section only where local discovery or third-party proof is relevant.

### Local

Inspect the official business profile where accessible, categories, services, contact/address consistency, service area, appointment links, photos/posts where relevant, review volume and themes, location/service landing pages, and dated local/map results. Distinguish a user-supplied profile from an independently verified one. Never recommend fake locations or city pages that add no local value.

### Reputation and links

For each sampled source, record source URL, capture date, type (editorial, directory, partner, sponsored, owned, review), target URL/mention, context, topical and market relevance, disclosure/relationship, link attribute if observed, and verification state.

Separate:

- verified links;
- verified mentions without a link;
- owned, partner, employee, or otherwise affiliated sources;
- unverified prospects or search leads;
- paid/sponsored placements;
- reviews/testimonials supported by a real platform and policy-compliant evidence.

Use comparable discovery/query/verification budgets for competitors. A sample can support a practical prospect plan but rarely a complete account of a site’s link graph or reputation.

## 6. Competitor and SERP comparison

Build a small eligible cohort. For each candidate, inspect relevant pages and record: business fit, shared audience/market, specific comparable offer, source page, capture date, and reason for inclusion or rejection.

Compare the client and each competitor through a shared matrix:

| Dimension | Client evidence | Competitor evidence | Gap/advantage | Recommended response | Confidence |
|---|---|---|---|---|---|
| Offer/page fit |  |  |  |  |  |
| Answer coverage |  |  |  |  |  |
| Original proof |  |  |  |  |  |
| Entity clarity |  |  |  |  |  |
| Reputation/local proof |  |  |  |  |  |
| Conversion path |  |  |  |  |  |

Do not copy competitor text or assume that a visible feature caused a ranking/mention. Explain how the observed difference may better answer a customer need, then propose a source-backed improvement.

## 7. Action register and roadmap

Create an action record for every selected item:

| Priority band | Owner | URL/template | Customer need | Action | Evidence/mechanism | Dependency | Acceptance check | Measurement window |
|---|---|---|---|---|---|---|---|---|

Use a relative priority calculation based on business impact, confidence, reach, effort, and risk. Explain a priority change when a baseline, measurement scope, data source, or scoring model changes.

For a 30/60/90-day roadmap, sequence work rather than promise outcomes:

- **Days 0–30:** access/indexation/measurement blockers, conversion-critical commercial pages, canonical/entity fact cleanup, and baseline evidence.
- **Days 31–60:** priority answer blocks, proof assets, page-to-page architecture, schema implementation/validation, and local/reputation foundations.
- **Days 61–90:** source-worthy content, appropriate third-party authority work, competitor gap execution, first comparative measurement, and plan adjustment.

Adapt the sequence to resource constraints and dependencies. New pages, publishing, hosting edits, outreach, paid placements, and account changes remain proposals until the owner authorises them.

## Suggested report structure

1. Goal, scope, capture dates, data sources, and limitations
2. Executive assessment and three highest-value actions
3. Technical and rendering readiness
4. Search, content, answer, and entity/citation readiness
5. Local/reputation/authority and competitor evidence, where applicable
6. Query/question-to-page and conversion map
7. Prioritised action register and roadmap
8. Measurement plan, assumptions, and missing data
