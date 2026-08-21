# Giving wealth advisers a decision, not a churn score

Adviser usage was below 5%. The churn model might have been statistically useful, but its product was a score with no action, no client-level evidence, and no explanation. An adviser still had to search at least five systems before deciding whether the alert mattered.

For a large UK wealth manager during my Microsoft role, I reframed and directed the redesign from **predict churn** to **help an adviser choose an appropriate next action**. The model prioritized; the adviser controlled contact; Compliance reconstructed evidence; no relationship action followed automatically from a threshold.

## One card replaced five searches

Each recommendation carried:

1. a bounded action—call, review liquidity, discuss a life event, or offer service;
2. the client-specific signals that moved the recommendation;
3. dated source evidence from portfolio, service, digital, and CRM systems;
4. uncertainty, stale or unavailable evidence, and alternative explanations;
5. accept, change, defer, or dismiss controls; and
6. a trace from display through adviser choice, contact, client response, and outcome.

[NIST’s Four Principles of Explainable AI](https://www.nist.gov/publications/four-principles-explainable-artificial-intelligence) sharpened the design: explanations must provide reasons, mean something to the user, reflect the actual system, and acknowledge limits. The UK ICO and Alan Turing Institute’s [guidance on explaining AI-assisted decisions](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/explaining-decisions-made-with-artificial-intelligence/) also treated explanation as a lifecycle capability. These were external benchmarks, not claims about the client’s legal determination.

## The dismiss button found the roadmap

I required advisers to give a reason when they disagreed. A three-month sample showed:

- 35% of dismissals involved clients already contacted, revealing weekly CRM synchronization was too stale;
- 22% reflected relationship or life-event context absent from financial data;
- 8% involved deceased clients, exposing a missing mortality signal.

The retained categories explain 65% of dismissals; I do not invent the remaining 35%.

Each reason produced a different product response. Stale state led to daily synchronization. Missing operating facts created new data or workflow requirements. Legitimate adviser disagreement became a reviewed example. A source defect did not become mislabeled model error.

False positives fell 18% in three months. The defensible measure is inapplicable recommendations / adjudicated positive recommendations for equivalent cohorts; the record does not retain counts or confidence intervals.

## COVID changed the action before the prediction

Before the pandemic, unusual cash accumulation could indicate impending asset movement. During the shock, it could instead mean fear, liquidity preference, or a need for reassurance. The same input no longer justified the same intervention.

I changed the action policy from a sales response to an empathy-led check-in and moved monitoring and retraining to a weekly cadence. Drift review covered input distributions, outcome rates, calibration, dismissal reasons, segment performance, and adviser feedback. Stable AUC would not have proved stable usefulness.

The Bank of England and FCA’s [AI Public-Private Forum report](https://www.bankofengland.co.uk/research/fintech/ai-public-private-forum%C2%A0) later organized financial-services AI risk around data, models, and governance; I use it as an external benchmark for the operating logic.

## The pilot followed the whole causal chain

Eligible clients were assigned through pilot and control regions. Measurement connected recommendation, adviser consumption, adviser decision, outreach, client response, churn, and retained economics. That stopped the team from treating generated or viewed recommendations as impact.

| Outcome | Baseline → target → recorded result | Measurement method |
|---|---|---|
| Adviser adoption | <5% use → make recommendations operationally useful → final rate not retained | Eligible active advisers completing a meaningful card action / exposed advisers |
| Client churn | control-region rate → lower in pilot → 12% lower | Pilot/control cohort outcome with pre-trend and mix checks; source does not retain relative-versus-point definition |
| Preparation effort | time index 100 → halve multi-system work → 50 | Same client-review task boundary; recorded 50% reduction |
| False positives | index 100 → reduce through feedback and fresher data → 82 after 3 months | Adjudicated inapplicable recommendations / positive recommendations |
| Product volume | none stated → sustained workflow use → 11M recommendations consumed | Define consumed event, unique advisers/clients, period, and repeat frequency; volume is not adoption |
| Protected value | counterfactual churn economics → positive annualized value → ~£600K | Incremental retained accounts × fee economics under pilot/control assumptions; modeled, not booked revenue |

One case describes an adviser noticing falling liquidity and mortgage-page behavior, discovering refinancing plans, and retaining roughly £2 million in assets. I use it as an illustrative workflow, not causal proof or an amount to add to the £600,000 annualized model. AUM and revenue are different units.

## Ownership that survived the build

External data scientists were paired with internal engineers so feature logic, monitoring, deployment, and feedback did not leave with the project. Advisers co-designed explanations and actions. Compliance defined the evidence and reconstruction need. Data owners fixed sources. Operations managed the new cadence.

User research, action policy, the recommendation interface, feedback taxonomy, pilot, COVID response, cross-functional choices, measurement chain, and handover sat inside my product scope. Adviser judgment remained outside it, and no retained relationship was automatically labeled a model success.

The product’s durable advantage was accountable disagreement. A useful next-best-action system did not hide uncertainty or replace the relationship; it gave the adviser enough evidence to act, enough control to refuse, and enough structure for every refusal to improve the system.
