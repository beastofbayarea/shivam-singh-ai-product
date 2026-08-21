# Removing merchant work with governed context

## The product I stopped

During my Rakuten internship, the initial merchant-AI concept was a common chatbot. Usage showed that it relocated work rather than removing it: open another interface, explain the store and product, refine a prompt, copy the output, and paste it into the operating tool.

I stopped treating conversation as the product.

The jobs were already clear—write a listing, prepare an image, understand reviews, answer a customer, interpret store performance. The system should arrive with the permitted store, catalog, policy, and workflow context, produce a reviewable draft where the work happened, and wait for the merchant to publish.

That reversal became my product mandate: define an architecture that could compound across an ecosystem of more than 70 Rakuten services and an eligible base above 50,000 merchants without confusing shared context with shared access.

## The build-versus-partner decision

I separated commodity model capability from differentiated product infrastructure.

**Partner:** general language generation and broad reasoning could be sourced and changed over time.

**Build:** merchant and product identity, source provenance, permissioned retrieval, business rules, evaluations, workflow placement, merchant approval, and feedback were specific to Rakuten.

Rakuten publicly [announced an exploratory OpenAI partnership in August 2023](https://global.rakuten.com/corp/news/press/2023/0802_01.html), during my internship. That supports the strategic context, not a claim that every internal component or metric used one provider.

I also delayed cross-service monetization. Near-term selling optionality was not worth an unexplainable permission path between services. That was a product sequencing decision: first prove identity, purpose, inference control, and merchant agency; only then widen the economic surface.

## Context became a control plane

The graph connected merchant, store, user, product, category, transaction, review, campaign, and policy entities. Every relationship required an identifier, source, effective time, owner, and permission.

[W3C RDF](https://www.w3.org/TR/2014/REC-rdf11-concepts-20140225/) informed the entity-and-statement model, while [W3C PROV-O](https://www.w3.org/TR/2013/REC-prov-o-20130430/) informed provenance. They are design references; the retained record does not prove a literal standards-compliant RDF implementation.

Retrieval deliberately combined two modes. Semantic search found related meaning where language varied. Exact search protected SKUs, merchant IDs, policy terms, prices, and other facts where “similar” could be dangerous. The graph narrowed the relevant neighborhood; the policy layer decided whether the current merchant, user, service, purpose, and action could retrieve it.

Sensitive fields were minimized or transformed under policy. “Redacted” data still required residual-disclosure testing. Drafts retained their sources and never published without merchant approval.

## Three embedded products proved the platform

### Listing creation

Current product facts, category rules, merchant tone, prohibited claims, and accepted examples were assembled automatically. The merchant saw a sourced draft inside listing creation and decided whether to edit or publish.

### Review intelligence and responses

The system selected eligible reviews and current store policy, distinguished customer statements from merchant facts, synthesized themes, and created a response draft. Evidence and agency stayed visible.

### Image preparation

Channel dimensions and presentation rules were applied inside the listing workflow rather than through a separate generic assistant.

These narrow products created a better platform test than chatbot engagement: could the same governed context remove steps from distinct jobs while each surface retained its own permissions and rules?

## What the internal evidence means

- **Listing time:** 45 minutes baseline → reduce task effort → 12 minutes. Method: event-defined start to completed eligible listing, segmented by SKU complexity and merchant cohort. Recorded change: 33 minutes and 73.3% lower.
- **Adoption:** zero for the new experience → sustained merchant activation → 40% at six months. Method: activated eligible exposed merchants / eligible exposed merchants. The source does not preserve the denominator, so I do not multiply 40% by the ecosystem total.
- **Weekly retention:** baseline absent → repeated workflow value → 78%. Method: week-N activated merchants completing a qualifying job / original cohort; logo-versus-user definition is not retained.
- **Commercial association:** conversion index 100 → positive purchase-quality signal → 115 among merchants using generated copy. Method: randomized or matched SKU/merchant comparison with consistent order window. The recorded 15% is observational, not proven incrementality.

A separate 25% mobile-network energy reduction appears in the source but belongs to a telecommunications product with different operators and controls. I exclude it.

Rakuten publicly launched [RMS AI Assistant (Beta) in March 2024](https://global.rakuten.com/corp/news/press/2024/0430_01.html), after my internship ended. Its description—product-copy generation, image processing, inquiry responses, sales analysis, and merchant support—validates the later company direction but is not a launch I claim.

Stopping the chat-first product and replacing it with job-level experiences was my call; I also set the build/partner boundary, graph and permission requirements, cross-service sequence, launch priorities, and measurement. Engineering implemented, Privacy/Legal controlled data use, commerce teams governed local workflows, and merchants controlled publication.

The strategic asset was not an assistant. It was a governed context layer that could create many task-specific products, make Rakuten’s proprietary data useful without making it universally accessible, and reduce merchant work where that work already happened.
