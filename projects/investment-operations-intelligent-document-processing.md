# Turning financial documents into decision-grade data

A page of recognized characters was not a product.

Across 15 investment and operations teams at D. E. Shaw, statements, notices, filings, and deal documents were moving through local tools and incompatible taxonomies. Basic OCR was near 80% on complex material, particularly nested tables, footnotes, and fields whose meaning depended on headings. Operations staff retyped information, while investors could not reliably trace a figure back to its source.

I led the product definition and operating model for a document platform that treated every output as a typed, validated, attributable fact.

## A number had to carry its meaning

“12.4” became decision-grade only when the system knew the entity, field, unit, currency, period, table relationship, source page and region, document version, extraction version, review state, and downstream use.

I defined the lifecycle as:

**received → classified → located → extracted → normalized → validated → published or reviewed → consumed → corrected or superseded**

The source document remained immutable. Every transformation emitted provenance, and every downstream write was reversible. That made auditability a working product feature rather than a report produced after an incident.

[W3C PROV-O](https://www.w3.org/TR/2013/REC-prov-o-20130430/) informed the source–activity–agent model. In practical terms, a user could answer: Which document produced this field? Which system or person changed it? What rules ran? Was it auto-published or approved? Which report or investment process consumed it? Can the value be reproduced?

## I set the boundary between automation and judgment

The retained record cites a 0.98 confidence threshold. I did not treat that as 98% accuracy. Model confidence can be miscalibrated, and portfolio averages can conceal failure on consequential fields.

An auto-publish route required five independent proofs:

1. representative held-out documents and field-level precision at the proposed threshold;
2. calibration by document class and model version;
3. deterministic validation for type, range, totals, currency, period, and cross-field consistency;
4. stable source and schema with monitored drift; and
5. a permissioned, traceable, reversible downstream write.

High-consequence legal or investment terms could require a person regardless of confidence. Anything outside the validated envelope entered an authorized review queue. The objective was not maximum straight-through processing; it was minimum total decision cost subject to an agreed silent-error rate.

## One reviewer screen connected the system

The extraction pipeline combined character recognition, layout, table structure, entity context, and business validation. Document classification selected the schema; layout analysis recovered blocks and relationships; table logic preserved row/column meaning; entity resolution linked names to governed identifiers; rules detected impossible values.

[LayoutLM](https://arxiv.org/abs/1912.13318), first posted in December 2019, later formalized joint text-and-layout representation. It is relevant research context, not a claim that this platform used that exact model.

Reviewers saw the source region beside the proposed value, nearby context, confidence, failed checks, prior comparable decisions, and downstream consequence. They could accept, correct, abstain, or escalate with a reason.

Corrections entered a versioned labeled-data pool, not a blind production retraining stream. Representative sampling, quality review, entitlement checks, offline evaluation, and controlled promotion separated human feedback from model change. Operations therefore moved from transcription toward exception judgment and data stewardship without pretending manual responsibility disappeared.

## Platform scale without one universal risk model

I separated reusable infrastructure—ingestion, classification, extraction, confidence, review, provenance, audit, and publishing—from document-specific schemas and thresholds. That let 15 teams share a platform while fund notices, financial statements, contracts, and deal materials retained distinct risk rules.

The product account had to show quality and coverage together. High precision achieved by reviewing everything is not automation; high automation achieved by accepting silent error is not quality. I required field precision/recall, auto-publish coverage, review volume and time, correction rate, silent-error escapes, cost, and downstream reproducibility to be read as one system.

## The retained operating result

| Mechanism | Baseline → target → recorded result | Measurement method |
|---|---|---|
| Complex-document recognition | ~80% OCR performance → semantic, field-level understanding → final quality rate not retained | Field-level exact/normalized match by document class; do not convert architecture into an unrecorded accuracy result |
| Eligible ingestion speed | hours → near-real-time structured record → seconds | Source receipt to structured output; report median, tail, and review time separately |
| Processing economics | cost index 100 → reduce total eligible-document cost → ~30 | Infrastructure plus reviewer labor for comparable mix and volume; roughly 70% lower |
| Operating effort | baseline not retained → reduce repetitive work → ~15 person-weeks annually | Time study or task logs; an estimate, not 15 FTEs |
| Automation policy | manual/low-trust flow → evidence-gated routing → 0.98 threshold | Field precision and coverage at threshold, by consequence and document class |

The retained narrative also claims that the platform shortened a QC Ware deal process from 48 hours to six and supported a $25 million Series B. Public records date that [Series B to September 2021](https://www.qcware.com/news), after my D. E. Shaw tenure ended in December 2019. I exclude that result. QC Ware’s [$6.5 million Series A in July 2018](https://www.prnewswire.com/news-releases/qc-ware-raises-6-5-million-series-a-financing-for-its-cloud-quantum-computing-software-service-300678415.html) confirms a contemporaneous firm relationship, not this platform’s contribution.

I owned the product boundary, user workflow, taxonomy strategy, automation policy, review experience, feedback governance, cross-team adoption, and trade-offs among speed, cost, and silent-error risk. ML and data specialists owned implementation; operations retained exception judgment; legal and compliance owned controls; investment teams owned decisions.

The strategic asset was a governed supply chain for financial facts: fast where evidence justified automation, human where uncertainty or consequence demanded it, and traceable from immutable source to every material use.
