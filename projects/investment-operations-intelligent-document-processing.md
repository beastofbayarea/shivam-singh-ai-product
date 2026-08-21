# Turning financial documents into decision-grade data

I led product development for an investment-operations document platform at D. E. Shaw. I saw that investment teams could not trace important figures while operations staff spent their time retyping difficult documents. I worked with investors, quantitative teams, operations reviewers, data and machine-learning engineers, legal and compliance partners, control owners, and technology leaders.

## Text extraction was the smallest part of the job

Thousands of statements, notices, filings, and deal documents flowed through 15 global teams using local tools and inconsistent taxonomies. The retained record puts basic OCR performance near 80% on complex material, especially nested tables, footnotes, and fields whose meaning depended on headings or surrounding text.

I defined the product output as a typed, validated, attributable fact—not a page of recognized characters. A number such as “12.4” had no decision value until the system knew its entity, unit, period, table relationship, source location, document version, and review state.

I owned the platform boundary across 15 investment and operations teams: which document classes shared infrastructure, which fields required human judgment, what a confidence score could authorize, how every extracted fact remained traceable, and when lower processing cost was worth the risk of a silent error. That changed automation from faster transcription into a governed information supply chain for investment decisions.

That led to a field lifecycle:

`received → classified → located → extracted → normalized → validated → auto-published or reviewed → consumed → corrected/superseded`

Each transition produced evidence. The source document remained immutable; derived values carried the page and region, extraction version, confidence, rules applied, reviewer, and downstream publication event.

## How I drew the automation boundary

The project record describes a 98% confidence threshold. A model confidence of 0.98 is not the same as 98% accuracy. Confidence can be miscalibrated, and aggregate performance can hide weak fields. I treated the number as a routing policy that had to be justified separately by document class, field risk, and downstream use.

For an auto-publish lane I required:

- representative held-out documents and field-level precision at the chosen threshold;
- calibration analysis so a score meant approximately the same thing across versions;
- deterministic checks for type, range, totals, currency, period, and cross-field consistency;
- a stable source and schema with no unresolved quality drift; and
- a reversible downstream write with lineage.

Anything outside the proven envelope entered an authorized review queue. High-consequence legal or investment terms could require a person regardless of confidence. The cost objective was not maximum straight-through processing; it was minimum total decision cost subject to an acceptable silent-error rate.

## The extraction and review product

The pipeline combined character recognition with layout, table structure, entity context, and business validation. Document classification chose the schema; layout analysis recovered blocks and relationships; table logic preserved row and column meaning; entity resolution linked names to governed identifiers; and rules caught impossible or inconsistent values.

[LayoutLM](https://arxiv.org/abs/1912.13318), first posted in December 2019 at the end of my tenure, later formalized the joint use of text and layout for document understanding. I cite it as contemporaneous research supporting the technical direction, not evidence that the project used that exact model.

Reviewers saw the original region beside the proposed value, relevant context, confidence, failed checks, prior similar decisions, and downstream consequence. They could accept, correct, abstain, or escalate with a reason. A correction entered a versioned labelled-data pool; it did not blindly retrain production on every click. Quality review, privacy and entitlement checks, representative sampling, offline evaluation, and controlled model promotion separated human feedback from automated learning.

That design changed the operations role from transcription to exception judgement and data stewardship without pretending all manual work disappeared.

## Provenance was part of the interface

[W3C PROV-O](https://www.w3.org/TR/2013/REC-prov-o-20130430/) provided a useful model for the source entity, transformation activity, and accountable human or system agent behind a value. In product terms, a user could answer:

- Which document and exact location produced this field?
- Which model, rule, or reviewer changed it?
- Was the value auto-published, approved, corrected, or superseded?
- Which downstream report, model, or investment decision consumed it?
- Can we reproduce the value from the retained source and versioned transformation?

I separated reusable platform capabilities—ingestion, classification, extraction, confidence, review, provenance, audit, and publishing—from deal- or document-specific schemas and thresholds. That let 15 teams share infrastructure without forcing fund notices, financial statements, contracts, and transaction work into one risk model.

## Operating evidence I can defend

The source supports the following portfolio-level account:

| Measure | Starting point | Recorded result | Measurement boundary |
|---|---:|---:|---|
| Complex-document OCR performance | about 80% | semantic pipeline introduced | accuracy definition, field mix, and final quality rate not retained; do not claim a percentage-point result |
| Document ingestion | hours | seconds | source-to-structured-record processing for eligible documents; median, tail, and review time absent |
| Processing cost | baseline index 100 | about 30 | roughly 70% lower; volume, infrastructure, reviewer labor, and period must be held constant |
| Annual operating effort | baseline not retained | about 15 person-weeks saved | estimate; small relative to 15 teams and not equivalent to 15 full-time roles |
| Auto-routing policy | manual or low-trust flow | 0.98 confidence gate | threshold, not accuracy; must be accompanied by field-level precision and coverage |

This scorecard deliberately reports both quality coverage and automation. A system could reach high precision by sending nearly everything to review; it could reach high automation by accepting dangerous error. The product had to show precision, recall, auto-publish rate, review volume, review time, correction rate, silent-error escapes, and cost together.

## The deal claim that does not survive chronology

The retained narrative says the architecture reduced live-deal consolidation from 48 hours to six and helped close a $25 million QC Ware Series B one week ahead of competitors. Public evidence places that [Series B on September 29, 2021](https://www.qcware.com/news), after my D. E. Shaw tenure ended in December 2019. I therefore exclude the $25 million round, the one-week claim, and the attached 48-to-six-hour result from my personal outcomes.

The contemporaneous public event was QC Ware’s [$6.5 million Series A on July 10, 2018](https://www.prnewswire.com/news-releases/qc-ware-raises-6-5-million-series-a-financing-for-its-cloud-quantum-computing-software-service-300678415.html), in which D. E. Shaw Ventures participated. That confirms a firm relationship during my tenure, but it does not prove that this document platform supported the round or justify transferring the later transaction claim backward. Contemporaneous internal evidence would be required.

## Product ownership and strategic value

I owned the product definition, user workflow, automation policy, taxonomy boundary, review experience, feedback governance, adoption across teams, metric account, and trade-offs between speed, cost, and silent-error risk. Specialists owned model and platform implementation. Operations retained judgement on exceptions. Legal and compliance owned applicable controls. Investment teams owned decisions made from the data.

The durable product was a factory for decision-grade facts: fast where the evidence supported automation, human where consequence or uncertainty required it, and traceable from source to every downstream use. Removing the anachronistic deal outcome makes the story smaller in headline transaction value and much stronger in technical and evidentiary credibility.

## Technical and control references

- The retained project record provides the 15-team scope, document types, OCR baseline, routing threshold, speed, cost, and operating-effort figures.
- [Xu et al.: LayoutLM](https://arxiv.org/abs/1912.13318) — late-2019 research context for joint text-and-layout representation.
- [W3C PROV-O](https://www.w3.org/TR/2013/REC-prov-o-20130430/) — provenance design reference.
- [NIST SP 800-53 Revision 4](https://csrc.nist.gov/pubs/sp/800/53/r4/upd1/final) — contemporaneous reference for access, integrity, audit, and contingency controls.
