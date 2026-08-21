# Removing merchant work with governed context

I led product work on a merchant AI platform during my Rakuten internship. I saw that merchants did not want to explain their store and products to a generic assistant before it could help. I worked with merchants, commerce product teams, data and AI engineers, designers, privacy and legal partners, marketplace operations, support, business leaders, and an external model partner.

## I stopped the first product

The initial common experience was a chatbot. Usage showed that it merely moved work: a merchant opened another interface, described the product and desired task, refined a prompt, copied the result, and pasted it back into the operating tool.

I stopped treating conversation as the product. The user jobs were concrete: create a product description, prepare an image, understand reviews, answer a customer, or interpret store performance. The platform should already know the permitted store, catalogue, policy, and workflow context, then let the merchant review the result where the work was performed.

I set the product architecture that could make those jobs reusable across an ecosystem of more than 70 services and an eligible population above 50,000 merchants without pretending that shared context meant shared access. The strategic decision was to build the identity, provenance, permission, retrieval, and workflow layer Rakuten could differentiate; partner for commodity model capability; and delay cross-service monetization until the control model could defend it.

That reversal separated two product layers:

- **Partner for general model capability:** language generation and broad reasoning could be sourced and changed over time.
- **Build the differentiated system:** entity resolution, source provenance, retrieval, permissions, business rules, evaluation, workflow placement, merchant approval, and feedback were specific to Rakuten’s ecosystem.

Rakuten and OpenAI publicly [announced an exploratory partnership in August 2023](https://global.rakuten.com/corp/news/press/2023/0802_01.html), during my internship. That is contemporaneous company context for the partner decision; it is not proof that every internal component or metric in this project used one named provider.

## The knowledge graph was a control surface

The source described more than 70 “businesses,” but Rakuten’s contemporaneous public language was [more than 70 services](https://global.rakuten.com/corp/news/press/2023/1114_02.html). I use the company’s term. A service count is not a claim that my product integrated all of them.

The context layer connected merchant, store, user, product, category, transaction, review, campaign, and policy entities. Each relationship needed an identifier, source, effective time, owner, and permission. [W3C RDF](https://www.w3.org/TR/2014/REC-rdf11-concepts-20140225/) offered the entity-and-statement model; [W3C PROV-O](https://www.w3.org/TR/2013/REC-prov-o-20130430/) offered a vocabulary for which source, transformation, and accountable actor produced a fact. I use those standards as design references, not evidence that the internal store was a literal standards-compliant RDF implementation.

Hybrid retrieval solved two different problems. Semantic search could find related meaning when wording differed; exact search protected SKUs, merchant IDs, policy terms, prices, and other values where similarity was dangerous. The graph narrowed the relevant neighborhood, while the policy layer decided whether the current user and task could retrieve it.

“Shared context” never meant shared access. The request carried merchant, user, service, purpose, and action attributes. Retrieval enforced those boundaries before generation. Sensitive fields were minimized or transformed according to policy; calling something “redacted” did not remove the need to test residual disclosure. Generated content retained its supporting sources and was a draft until the merchant approved publication.

I delayed cross-service selling because the permission and inference controls could not yet justify it. That decision gave up near-term commercial optionality to avoid creating an unexplainable path between service contexts.

## Three jobs replaced one assistant

**Listing copy.** The system assembled current product facts, category rules, merchant tone, prohibited claims, and examples; generated a draft; showed the merchant the evidence; and published only after approval.

**Review synthesis and responses.** Retrieval selected eligible reviews and current store policy, separated customer statements from merchant facts, and presented a draft that could be edited or rejected.

**Image preparation.** A task control applied channel dimensions and presentation rules inside listing creation rather than sending the merchant to a separate tool.

This is why workflow placement mattered as much as model quality. The model disappeared behind a task the merchant already intended to complete.

## The internal product account

The retained record reports an eligible merchant population above 50,000. It also reports 40% adoption in six months, 78% weekly retention, listing time falling from 45 to 12 minutes, and a 15% conversion lift for merchants using generated copy.

I would present those figures as follows:

| Measure | Baseline | Recorded result | Calculation | Evidence still required |
|---|---:|---:|---:|---|
| Listing completion time | 45 min | 12 min | 33 min and 73.3% lower | task start/end events, SKU complexity, merchant cohort, median and tail |
| Adoption | 0 for new experience | 40% at 6 months | source-reported rate | eligible denominator, activation event, exposure, and cohort; do not infer 20,000 users from the total merchant context |
| Weekly retention | not retained | 78% | source-reported rate | whether this is logo or user retention, cohort definition, week number, and qualifying action |
| Merchant conversion | baseline index 100 | index 115 | 15% increase | whether relative or points, selection controls, time window, and order definition |

The source says merchants “using generated copy” saw the conversion change. Without random assignment or a credible matched design, more capable merchants may be more likely both to use the tool and to convert. I therefore describe the 15% as an observed association, not proven incremental lift.

The source also attaches a 25% reduction in mobile-network energy use to reuse of the context layer. That is a separate telecommunications product with different operators, controls, and outcomes. No evidence ties it to my merchant-product ownership, so I exclude it from my results.

## Chronology matters

Rakuten publicly launched [RMS AI Assistant (Beta) on March 28, 2024](https://global.rakuten.com/corp/news/press/2024/0430_01.html), after my internship ended in December 2023. The announcement describes product-description generation, image processing, inquiry-response text, sales analysis, and a merchant-support chatbot for a base of 57,000 merchants. It is strong evidence that Rakuten later shipped a similar merchant problem set; it is not a launch or adoption outcome I claim personally.

The defensible story is product discovery, reversal of the chat-first thesis, governed-context design, workflow prototypes or internal release, and the internally retained measurements within my tenure. Later public availability is follow-on company context.

## My product ownership

I owned the user-job reframing, build-versus-partner boundary, embedded experience, context and permission requirements, cross-service trade-off, measurement plan, and launch prioritization. Data and engineering leaders owned implementation. Privacy and legal retained approval authority. Commerce teams owned local workflow and policy. Merchants retained control of published content.

The strategic asset was not a single assistant. It was a governed way to turn Rakuten’s proprietary context into many narrow, useful experiences without granting every product access to every fact. That system could compound across jobs while each interface, permission, and business rule remained purpose-specific.
