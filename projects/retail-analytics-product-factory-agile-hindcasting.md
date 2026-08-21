# Building a retail-pricing system merchants could challenge

The retailer did not have a prediction shortage. It had a decision-production problem.

A seasonal, cost-plus process was overpricing visible essentials, leaving margin unused on less sensitive products, and taking six weeks to move an approved change consistently across stores and digital channels. Two years of historical data looked abundant, but price had barely varied; correlation could not reveal how demand would respond to a decision the business had rarely made.

At McKinsey, I was responsible for making the pricing factory work end to end: experimental evidence, product roles, explainable recommendations, merchant authority, customer guardrails, cross-channel execution, continuous learning, and the bridge to a modeled $50 million opportunity.

## First, manufacture evidence

I would not optimize from static history. The team introduced store- and geography-level tests that stratified location by format and baseline sales, used A/A checks for imbalance, fixed sample and duration before reading results, staggered windows around seasonal events, and excluded stockout periods.

Treatment/control change was then challenged for competitor movement, promotion overlap, substitution, basket effects, geographic spillover, and placebo periods. The result was a causal elasticity estimate inside the tested price range and population—not an eternal SKU attribute.

I selected a Python log-log regression layer above the legacy ERP because its coefficient had an interpretation merchants could interrogate: expected percentage unit-demand change for a percentage price change, conditional on the design and population. Rolling historical hindcasts tested stability across earlier windows, but could not replace live experiments where history contained no useful variation.

## Then, give each SKU a job

The optimizer became portfolio-aware:

- **Key value items** protected customer price perception and traffic.
- **Basket builders** were evaluated through attachment economics.
- **Core category items** balanced unit volume, substitution, and category margin.
- **Long-tail items** captured measured headroom.
- **Heritage items** required stronger customer and brand evidence.

This prevented independent SKU maximization. A lower price on an essential could attract a profitable basket; selective long-tail movement could fund the promise. Finance evaluated net category economics rather than summing isolated recommendations.

## Product policy executed before optimization

The top 500 visible items could be locked during sensitive periods. Weekly movement was capped at ±5%. Approved private-label/national-brand ladders, stockout state, promotion, competitor shock, or channel conflict could block release. Store, web, and app prices had to reconcile before activation.

The system recommended a corridor with expected unit, basket, and margin effects; confidence and constraints remained visible. It never personalized price to an individual customer or presented mathematical optimality as an obligation.

## One objection redesigned the interface

When the engine proposed increasing the price of a beloved product, the chief merchant nearly stopped the pilot. The resistance was rational: a number had arrived without the experiment, customer implication, or policy context needed to judge it.

I rebuilt the output as a decision card:

**current/proposed price + elasticity interval + experimental evidence + trigger + unit/basket/margin effect + competitor context + brand/ladder controls + accountable override**

Override reasons distinguished model error, stale data, missing constraints, and legitimate new merchant information. Casual overrides fell 50%; overall overrides were below 5% by month two. They have different baselines and are not a 50%-to-5% funnel.

This interaction defined the product philosophy: the merchant did not “trust the model.” The merchant could challenge a legible recommendation, and disagreement became governed learning.

## The weekly decision factory

I replaced sequential handoffs with a pod. The merchant set category intent; the data scientist defended evidence; marketing reconciled promotion and customer message; operations checked inventory and readiness; engineering published only after automated gates.

Every increment had a named decision, eligible population, treatment or evidence source, acceptance rule, guardrail, publish route, and post-change measure. Approval-to-publication fell from six weeks to under one—at least five weeks faster and more than an 83.3% reduction. A separate broader program measure recorded 30% faster speed to market; I keep the perimeters distinct.

Daily sales, inventory, competitor, and promotion data refreshed recommendations. A rotating 1% SKU sample preserved exploration. Forecast error above 5% for two weeks triggered review. The 1% sample, 5% error trigger, and ±5% movement corridor are three controls with different denominators.

## Executive product account

| Product outcome | Baseline → target → recorded result | Measurement |
|---|---|---|
| Modeled value | existing architecture → opportunity inside constraints → $50M estimated | Eligible volume, counterfactual price, causal response, basket margin, cannibalization, realization bridge |
| Decision cycle | 6 weeks → <1 week → <1 week | Approval to reconciled omnichannel publication |
| Broader delivery speed | index 100 → accelerate → 70 | Original broader-program denominator; 30% faster |
| Forecast performance | baseline absent → useful operating accuracy → 95% | Named error metric, horizon, weighting, stockout treatment; not causal confidence |
| Adoption | override baseline absent → sustained use → <5% by month 2 | Overridden / eligible recommendations by reason and economic consequence |
| Learning coverage | no permanent test cell → ongoing exploration → 1% rotating sample | Random assignment, power, harm, and stop rules |
| Customer protection | unconstrained movement → explicit policy → top 500 locks and ±5% cap | Policy adherence, exceptions, and price-perception outcome |

Product-level responsibility for framing, experimentation, SKU roles, interface, guardrails, the pod, learning loop, merchant adoption, and value account stayed with me. Data Science estimated; merchants judged; Marketing protected promotion coherence; Operations/Technology protected publication; Finance calculated realized economics.

The result was not an algorithm that set prices. It was an operating system that created evidence, converted it into a constrained portfolio decision, exposed its reasoning, allowed accountable dissent, executed consistently, and learned from the market.
