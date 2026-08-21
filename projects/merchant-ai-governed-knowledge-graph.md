# Merchant AI Platform — Governed Knowledge Graph at Scale

I completed this work during my [Rakuten experience from June to December 2023](https://github.com/beastofbayarea/shivam-singh-ai-product/blob/main/shivam-singh-ai-product.pdf).

## Why the chatbot failed

More than 70 businesses had fragmented data and duplicated AI work. The first common experience was a generic chatbot, but merchants had to explain the listing, product, campaign, or review context before the system could help. Usage evidence showed that the interface did not remove a meaningful job.

I stopped the chatbot and changed the product thesis: the platform needed to know the merchant’s authorized context and appear inside the workflow where that context mattered.

## The build-versus-buy choice

I partnered for foundation-model intelligence and invested internally in the differentiated layers:

- a governed merchant, product, transaction, and operating knowledge graph;
- hybrid semantic and exact retrieval;
- permission-aware context assembly;
- business-specific policy;
- task-level workflow integrations;
- merchant review and correction.

Buying the model avoided recreating commodity reasoning capability. Building the context and workflow layer protected the knowledge, permissions, and operating behavior that distinguished the product.

## Designing the shared context

I used a common entity-and-relationship model to connect merchant, product, transaction, and operational data. W3C RDF informed the graph representation, while W3C PROV influenced how the platform recorded source and derivation.

The graph did not grant broad access by default. Every retrieval respected the merchant, business, user, and purpose boundary. Privacy redaction, authorized grounding, local policy, and merchant approval formed a three-layer safety model.

I delayed cross-service selling until those controls were strong enough. The commercial upside did not justify creating an inference path across businesses before the platform could explain and enforce permission.

## Replacing chat with jobs

I embedded task buttons into listing, review, and image workflows. A merchant could improve a listing, draft a response, or prepare an image without reconstructing the context in a prompt.

That design reduced listing time from 45 minutes to 12. AI-generated copy increased merchant conversion 15%. The result confirmed that workflow placement mattered as much as model quality.

## Adoption and retention

| Outcome | Result |
|---|---:|
| Merchant population | More than 50,000 |
| Adoption | 40% in six months |
| Weekly retention | 78% |
| Listing time | 45 minutes to 12 |
| Merchant conversion | +15% |

The shared context layer also supported a 25% reduction in mobile-network energy use. I treat that as evidence of platform reuse, not as a direct result of the listing experience.

## How I governed a horizontal platform

I aligned more than 70 businesses around shared identity, context, retrieval, and safety standards without forcing identical interfaces. Local product teams retained responsibility for their user journeys and policy detail. The platform team owned the reusable context and control contract.

## Sources and external context

These sources informed the graph, provenance, and governance design. The resume link establishes the employment timeline.

| Source | How it informed my work | Timing |
|---|---|---|
| [W3C — RDF 1.1 Concepts and Abstract Syntax](https://www.w3.org/TR/2014/REC-rdf11-concepts-20140225/) | I used it to structure graph statements, resources, identifiers, and interchange. | 2014 |
| [W3C — PROV-O](https://www.w3.org/TR/2013/REC-prov-o-20130430/) | I used it to represent the source and derivation of context returned to an AI workflow. | 2013 |
| [NIST — AI Risk Management Framework 1.0](https://doi.org/10.6028/NIST.AI.100-1) | I used it to connect permissions, evaluation, monitoring, and accountability across the AI lifecycle. | 2023 |

