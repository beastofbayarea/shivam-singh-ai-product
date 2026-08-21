# Investment Operations — Intelligent Document Processing

I completed this work during my [D. E. Shaw experience from July 2016 to December 2019](https://github.com/beastofbayarea/shivam-singh-ai-product/blob/main/shivam-singh-ai-product.pdf).

## The workflow I replaced

Thousands of financial documents were manually retyped into inconsistent tools. Basic OCR operated near 80% accuracy and broke on nested tables, footnotes, and context-dependent fields. The cost was not only data entry: fragmented taxonomies slowed investment decisions and made it difficult to trace a value back to the source document.

I defined the product as structured, auditable data—not extracted text.

## The automation boundary

I set a 98% confidence threshold for automated passage into downstream systems. Lower-confidence fields and higher-risk values went to authorized reviewers. That decision deliberately limited straight-through automation, but it prevented silent errors from entering investment and reporting workflows.

Operations staff were not a fallback queue. I made their review decisions part of the product: every correction captured the source, extracted value, confidence, reviewer action, reason, and resulting model feedback.

## Moving beyond character recognition

I designed semantic table and entity extraction that used layout and document context rather than relying on character recognition alone. LayoutLM research, published at the end of the work period, later formalized the same technical direction by jointly modeling text and layout for document understanding.

I separated reusable capabilities from deal-specific logic:

- ingestion and document classification;
- semantic extraction and confidence scoring;
- source lineage and review records;
- correction and feedback capture;
- audit and downstream publishing;
- deal-specific taxonomies, thresholds, and exception rules.

That separation allowed 15 global teams to use one platform without pretending that every document or decision carried the same risk.

## Provenance as a product feature

I treated source lineage as first-class data. W3C PROV provided a useful model for representing the entities, activities, and agents behind a derived value. In practice, that meant a user could see where a field came from, how it changed, who reviewed it, and which version entered a downstream decision.

NIST SP 800-53 and COSO informed the control model around access, integrity, audit, contingency, reliable information, and monitoring.

## Reuse under deal pressure

The platform architecture became valuable beyond routine ingestion. I reused it to consolidate live deal data, reducing turnaround from 48 hours to six. The faster, traceable view helped close a $25M Series B one week ahead of competitors.

I did not create a separate emergency pipeline. Reuse was possible because the core platform separated stable ingestion and audit capabilities from the schema and thresholds of a particular deal.

## What changed

| Outcome | Result |
|---|---:|
| Document ingestion | Hours to seconds |
| Processing cost | Approximately -70% |
| Live deal consolidation | 48 hours to six |
| Annual operating effort | Approximately 15 person-weeks saved |
| Transaction supported | $25M Series B closed one week ahead of competitors |

## What I protected

I automated only the work the system could perform with sufficient confidence. I kept human accountability for uncertainty, preserved a trace from source to decision, and avoided one global taxonomy that would have hidden meaningful differences in document and deal risk.

## Sources and external context

These sources informed the document, provenance, and control architecture. The resume link establishes the work period.

| Source | How it informed my work | Timing |
|---|---|---|
| [Xu et al. — LayoutLM](https://arxiv.org/abs/1912.13318) | I used it as contemporaneous evidence for combining text and layout in document understanding rather than relying on OCR alone. | December 2019 |
| [W3C — PROV-O](https://www.w3.org/TR/2013/REC-prov-o-20130430/) | I used it to structure provenance across source entities, transformation activity, and accountable agents. | 2013 |
| [NIST — SP 800-53 Revision 4](https://csrc.nist.gov/pubs/sp/800/53/r4/upd1/final) | I used it to define security, integrity, audit, access, and contingency controls. | 2015 |
| [COSO — Internal Control Integrated Framework](https://www.coso.org/guidance-on-ic/pages/default.aspx) | I used it to connect reliable information, control activities, ownership, and monitoring. | 2013 |

