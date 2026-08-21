# Wealth Management Churn — Explainable Next-Best Actions

I completed this work during my [Microsoft experience from January 2020 to August 2022](https://github.com/beastofbayarea/shivam-singh-ai-product/blob/main/shivam-singh-ai-product.pdf).

## An accurate model nobody used

The churn model produced risk scores, but advisor usage remained below 5%. Advisors had to search five systems to interpret an alert, could not see why the client was flagged, and worried the model was designed to replace judgment.

I changed the product from a prediction surface into a next-best-action workflow. The job was not to tell an advisor that a client might leave; it was to help the advisor decide what to do, understand the evidence, and remain accountable.

## Designing the advisor action

Every alert included:

- a recommended next action;
- plain-language reasons;
- the source evidence behind the recommendation;
- uncertainty and relevant alternatives;
- an audit record;
- a structured way to accept, modify, or dismiss the action.

NIST’s explainability principles helped me separate explanation from confidence theater. An explanation needed to have a reason, be meaningful to the intended user, reflect the system’s process accurately, and acknowledge when the system lacked a justified answer.

Research on whether explanations improve human decisions reinforced a second point: an explanation is not useful merely because it increases trust. I evaluated whether it helped advisors identify problems, justify a decision, and act appropriately.

## Making disagreement useful

I converted dismissals into reason-coded feedback. Advisors could identify stale CRM data, missing mortality signals, a known life event, or a recommendation that did not fit the relationship.

That feedback improved both the model and the operating data. It reduced false positives 18% within three months and turned human override from an apparent product failure into a structured learning channel.

## Responding to drift

COVID-19 changed the meaning of previously predictive behavior. Cash accumulation, for example, could reflect market uncertainty rather than churn intent. I changed the action policy and retraining cadence instead of assuming that a historically accurate model remained useful.

I paired external data scientists with internal engineers so the organization could own the model, feedback, and monitoring after the initial build.

## What changed

| Outcome | Result |
|---|---:|
| Recommendations consumed | 11 million |
| Pilot churn | -12% |
| Client-preparation time | -50% |
| False positives | -18% in three months |
| Annual revenue protected in the pilot | Approximately £600K |

I connect the value claim to a controlled pilot rather than attributing every retained relationship to the model.

## The product principle

I optimized for appropriate advisor action and retained client relationships, not AUC alone. The model became valuable only when it fit the workflow, exposed evidence, accepted disagreement, and learned from the people accountable for the decision.

## Sources and external context

These sources informed the explanation, privacy, and human-decision design. The resume link establishes the work period.

| Source | How it informed my work | Timing |
|---|---|---|
| [NIST — Four Principles of Explainable Artificial Intelligence](https://doi.org/10.6028/NIST.IR.8312) | I used the principles of explanation, meaningfulness, explanation accuracy, and knowledge limits to design advisor-facing evidence. | 2021 |
| [NIST — Privacy Framework 1.0](https://www.nist.gov/privacy-framework/privacy-framework) | I used it to connect client data, purpose, governance, and privacy-risk management. | 2020 |
| [Lai and Tan — Does Explainable Artificial Intelligence Improve Human Decision-Making?](https://arxiv.org/abs/2006.11194) | I used it to test explanation quality through decision performance rather than trust alone. | 2020 |

