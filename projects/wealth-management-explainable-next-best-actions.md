# Giving wealth advisers a decision, not a churn score

I led the redesign of a churn product for a large UK wealth manager during my Microsoft role. I saw that advisers could not act on a risk score they could not explain and did not want a model to replace their judgement. I worked with advisers, client-service leaders, compliance and privacy teams, data scientists, engineers, external specialists, operations, and executive sponsors.

## The model was accurate enough; the product was unusable

Adviser use remained below 5%. A risk alert did not say what to do, exposed no client-level evidence, and forced an adviser to search at least five systems before deciding whether the signal mattered. The product added interpretation work to a time-constrained relationship role.

I changed the product objective from “predict churn” to “help an adviser choose an appropriate next action.” Predictive performance remained necessary, but the operating outcome became an informed, timely adviser decision followed by a recorded client response.

The redesign also changed who had authority. The model could prioritize and recommend. The adviser remained accountable for contact. Compliance could reconstruct the evidence and decision. The client was not subjected to an automated relationship action merely because a score crossed a threshold.

## Anatomy of one recommendation

Each card combined six elements:

1. **Action:** a bounded suggestion such as call, review liquidity, discuss a life event, or offer service—not a vague “high risk” label.
2. **Client-specific reasons:** which current signals changed the recommendation and in what direction.
3. **Source evidence:** the underlying portfolio, service, digital, and CRM events with their dates and system of record.
4. **Limits:** uncertainty, unavailable evidence, data freshness, and alternative explanations.
5. **Human choice:** accept, change, defer, or dismiss.
6. **Audit and outcome:** who saw the card, what they did, which reason they supplied, whether contact occurred, and what followed.

[NIST’s Four Principles of Explainable AI](https://www.nist.gov/publications/four-principles-explainable-artificial-intelligence), published during the project period, sharpened the requirement. An explanation must provide reasons, be meaningful to its intended user, accurately reflect the system’s process, and respect knowledge limits. An attractive narrative that makes an adviser overconfident would fail that standard.

The UK Information Commissioner’s Office and Alan Turing Institute also published [guidance on explaining AI-assisted decisions](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/explaining-decisions-made-with-artificial-intelligence/) in 2020. It treats explanation as a lifecycle concern: select appropriate explanation types, build the system to extract relevant information, translate rationale for the affected audience, and prepare implementers. I used it as a contemporaneous product benchmark, not as a statement of the client’s legal conclusion.

## The dismiss button became the best sensor

I required reason-coded disagreement rather than a silent override. The retained three-month sample attributed:

- 35% of dismissals to clients already contacted, revealing a weekly CRM synchronization that was too stale;
- 22% to relationship or life-event context missing from financial data; and
- 8% to deceased clients, revealing a missing mortality signal.

Those categories explain 65% of dismissals; the source does not account for the other 35%, so I do not imply a complete taxonomy.

The product response depended on the cause. Stale state led to daily synchronization. Missing operating facts led to new inputs or prompts. A legitimate adviser disagreement became a labelled example for review. A data defect was not carelessly fed back as if it were model error.

False positives fell 18% within three months. To defend that result, the numerator must be recommendations later judged inapplicable, the denominator all adjudicated positive alerts, and the comparison made on equivalent cohorts. The retained source gives the change and window but not the counts or confidence interval.

## COVID changed the action policy before it changed the algorithm

Historical cash accumulation had indicated possible asset movement. During the pandemic it could instead mean fear, liquidity preference, or a request for reassurance. The same feature no longer justified the same intervention.

I moved the team to weekly monitoring and retraining during the shift, but more importantly changed the action policy from a sales-oriented response to an empathy-led check-in. Drift review looked at input distributions, outcome rate, calibration, reason patterns, segment performance, and adviser feedback. We did not assume that a stable headline AUC meant stable product usefulness.

This aligns with the Bank of England and FCA’s [2022 AI Public-Private Forum report](https://www.bankofengland.co.uk/research/fintech/ai-public-private-forum%C2%A0), which organized financial-services AI challenges around data, model risk, and governance and emphasized safe adoption rather than accuracy alone.

## How I measured whether the intervention worked

Eligible clients were assigned through pilot and control regions. I preserved the sequence from recommendation to adviser use, outreach, client response, churn, and retained economics. That prevented the team from calling an output valuable merely because it was generated.

| Measure | Baseline | Recorded result | Interpretation and measurement |
|---|---:|---:|---|
| Adviser usage | <5% | final rate not retained | baseline exposed product failure; 11M consumed recommendations is a volume, not a rate |
| Churn | control-region rate | 12% lower in pilot | source does not state relative versus percentage-point change; report as source-stated pilot difference pending cohort counts and pre-trend checks |
| Client preparation time | baseline index 100 | index 50 | 50% reduction; minutes, task boundary, and distribution not retained |
| False positives | baseline index 100 | index 82 after 3 months | 18% reduction; adjudication counts and interval absent |
| Recommendations consumed | none stated | 11M | needs definition of “consumed,” unique advisers/clients, period, and repeat frequency |
| Annual revenue protected | counterfactual pilot churn economics | about £600K | modeled annualized value tied to pilot; not identical to booked incremental revenue |

One case in the source describes an adviser contacting a client about falling liquidity and mortgage-page activity, uncovering refinancing plans, and retaining roughly £2 million in assets. I treat that as an illustrative intervention, not proof the model caused the retention or an amount to add directly to the £600,000 annual revenue model. Assets under management and revenue are different measures.

## Operating ownership after the build

I paired each external data scientist with an internal engineer so feature logic, monitoring, deployment, and feedback did not leave with the consulting team. Advisers co-designed explanations and actions. Compliance defined evidence and review needs. Data owners fixed source quality. Product owned the decision journey and outcome account.

I owned that product transformation: user research, action policy, recommendation card, feedback taxonomy, pilot design, drift response, cross-functional decisions, and handover model. I did not own the adviser’s client judgement or convert every retained relationship into a model win.

The strategic outcome was an evidence-bearing next-best-action system that learned from accountable human disagreement. It made the prediction useful without disguising the model’s limits or surrendering the relationship decision to it.
