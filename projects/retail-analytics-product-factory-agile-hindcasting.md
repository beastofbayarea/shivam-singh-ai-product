# Building a retail-pricing system merchants could challenge

I led product strategy for a national retailer’s pricing transformation at McKinsey. I saw that one seasonal, cost-plus process was overpricing visible essentials and leaving margin unused on less sensitive products. I worked with customers and merchants, category and marketing leaders, store and digital-channel teams, data scientists, engineers, finance, operations, and client executives.

## Historical sales could not answer the pricing question

Two years of sales records appeared rich, but prices had barely moved. A model trained on that history could mistake “we did not vary price” for “demand does not respond to price.” Competitor changes, promotions, stockouts, seasonality, store mix, and cross-shopping further confounded the relationship.

I would not optimize prices from that correlation. I introduced controlled store- and geography-level tests to create learnable variation. The design stratified locations by format and baseline sales, used A/A checks to detect pre-existing imbalance, set sample size and duration before reading the result, staggered windows around seasonal events, and excluded stockout periods where observed sales were supply-constrained.

The analysis compared treatment and control changes, then challenged the estimate for competitor movement, promotion overlap, spillover to substitute products, basket effects, and placebo periods. This produced a causal elasticity estimate only within the tested price range and population; it was not a permanent property of a SKU.

## Every product needed an economic job

I built a Python log-log regression layer above the legacy ERP because the coefficient had a meaning merchants could interrogate: the expected percentage change in unit demand for a percentage change in price, conditional on the model and test population.

I owned the end-to-end decision factory behind the model: experimental evidence, product-role taxonomy, recommendation design, merchant authority, 500-item customer guardrails, cross-channel publication, a permanent learning sample, and the executive bridge to a $50 million opportunity. The product succeeded only if it could move from test to reconciled store and digital execution in under a week without turning forecast confidence into unilateral pricing authority.

I then made the recommendation portfolio-aware:

- **Key value items:** visible, price-sensitive products that shaped customer value perception; keep competitive.
- **Basket builders:** products whose direct margin understated profitable attachments; optimize the basket.
- **Core category items:** balance volume, substitution, and category margin.
- **Long-tail items:** lower visibility and sensitivity; capture defensible margin.
- **Heritage or brand items:** reputationally sensitive; require stronger evidence and review.

That segmentation prevented the optimizer from maximizing every SKU independently. A low price on an essential could earn traffic and attachments; a selective long-tail increase could fund the proposition. Finance evaluated net category and basket economics rather than summing isolated model recommendations.

## The guardrails were part of the product strategy

The engine protected brand and customer commitments before it optimized:

- the top 500 high-visibility items were locked during sensitive periods;
- weekly movement was capped at plus or minus 5%;
- private-label and national-brand ladders had to preserve the approved tier relationship;
- stockouts, promotions, competitor shocks, or channel conflicts could block release; and
- point-of-sale, web, and app publication had to reconcile before a price became active.

The system recommended a price corridor, expected volume and basket effect, confidence, and relevant constraints. It did not personalize price to an individual customer or present a mathematically optimal price as a business obligation.

## The heritage-product objection changed the interface

The pilot nearly stopped after the engine recommended increasing the price of a beloved product. The chief merchant’s resistance was rational: the screen supplied a new price but no evidence, customer implication, or constraint.

I rebuilt the recommendation as a glass-box decision card. It showed current and proposed price, estimated elasticity and uncertainty, experiment and recent history, the trigger for change, expected volume/basket/margin effect, competitor context, brand and ladder constraints, and an accountable override with a required reason.

Reason review distinguished four conditions: the model was wrong, the data was stale, a business constraint was missing, or the merchant had information not yet captured. Casual overrides fell 50% after review began, and the source reports total overrides below 5% by month two. Those are different measures and should not be described as a 50%-to-5% funnel without the original override rate and denominators.

## The product factory changed the speed of action

The former workflow passed work sequentially among data, merchant, marketing, and channel teams. I formed a weekly pod around one pricing decision. The merchant set category intent; the data scientist defended the estimate; marketing reconciled promotions and customer message; operations checked inventory and channel readiness; engineering published only after automated gates passed.

Each increment had a named decision, eligible SKU population, treatment plan or evidence, guardrail, acceptance rule, publish path, and post-change measure. Rolling historical tests—hindcasts—checked stability across earlier periods and segments, but they did not replace live experiments where historical price variation was absent.

The local approval-to-publication cycle fell from six weeks to under one week: at least five weeks faster and more than an 83.3% reduction. A separate program measure reports 30% faster speed to market. The scopes clearly differ; I retain the local workflow result and broader program result separately rather than pretending they are the same calculation.

## Continuous learning after launch

Daily sales, inventory, competitor, and promotion data refreshed recommendations. A rotating 1% SKU sample maintained exploration so the model did not become another static seasonal table. Forecast versus actual was monitored by category; error above 5% for two weeks triggered review and potential retraining.

That 5% control threshold should not be confused with causal certainty. Forecast accuracy asks how close predicted demand was to observed demand. Elasticity confidence asks how precisely an incremental price effect was estimated. A model can forecast well while being wrong about what a price change caused.

## The financial and operating account

| Claim | Starting point | Recorded result | What I would show to substantiate it |
|---|---:|---:|---|
| Revenue opportunity | existing price architecture | estimated $50M | eligible volume, counterfactual prices, demand response, basket margin, cannibalization, and realization bridge; this is opportunity, not booked incremental revenue |
| Local price-change cycle | 6 weeks | <1 week | approval timestamp to reconciled channel publication; >83.3% reduction |
| Broader speed to market | index 100 | index 70 | source-reported 30% improvement on the broader program denominator |
| Forecast accuracy | not retained | 95% | metric must be named—such as one minus weighted MAPE—with forecast horizon, SKU weighting, and stockout treatment |
| Overrides | not retained | <5% by month 2 | overridden eligible recommendations / recommendations reviewed, split by reason and economic effect |
| Exploration | no permanent test cell | 1% rotating sample | eligible SKUs randomly assigned with exposure, power, stop, and guardrail rules |
| Weekly price movement | unconstrained process | ±5% cap | policy control, not a business outcome |

## My role in the decision system

I owned the problem framing, experimentation standard, product-role taxonomy, recommendation interface, guardrails, pod operating model, learning loop, merchant adoption, and executive value account. Data scientists owned estimation. Merchants retained category judgement. Marketing owned promotion coherence. Operations and technology owned publication integrity. Finance owned realized economics.

The strategic result was not “an algorithm set prices.” It was a transparent loop that created causal evidence, translated it into portfolio strategy, allowed accountable challenge, protected customer value perception, and learned after every decision. That is why the product could move faster without equating speed with unreviewed automation.

## Research context

- The retained project record supplies the experiment design, portfolio roles, guardrails, override behavior, operating changes, and economic figures.
- [Tashman: Out-of-sample tests of forecasting accuracy](https://doi.org/10.1016/S0169-2070(00)00065-0) — methodological basis for rolling-origin historical evaluation rather than one in-sample fit.
- [McKinsey Global Institute: Big data—the next frontier for innovation, competition, and productivity](https://www.mckinsey.com/capabilities/tech-and-ai/our-insights/big-data-the-next-frontier-for-innovation) — contemporaneous industry context for analytics-led retail value and operating-model change.
