# Shivam Singh — AI & Data Product Management

I build AI products as decision systems: not isolated models, but combinations of trusted context, bounded authority, reliable execution, human judgment, and measurable economic outcomes.

[Resume](./shivam-singh-ai-product.pdf) · [LinkedIn](https://www.linkedin.com/in/beastofbayarea) · [shiv-ai-product@umich.edu](mailto:shiv-ai-product@umich.edu)

## A model becomes a product only when the whole chain works

~~~text
real user decision
      ↓
trusted data and context
      ↓
permissioned action
      ↓
reliable workflow
      ↓
human feedback and recovery
      ↓
measured customer and business value
~~~

Each project in this portfolio owns a different failure point in that chain. Together they describe how I decide what to build, what not to automate, and what evidence a system needs before it receives more authority.

## Reliability changes the roadmap

[Resetting an enterprise GenAI roadmap around production use](./projects/enterprise-genai-production-reliability-turnaround.md) began when 90% of deployments remained in test and 70% of closed-lost deals cited reliability rather than missing features. I paused lower-priority expansion, made production promotion the unit of strategy, and introduced a four-stage maturity system spanning workflow ownership, quality, connectors, identity, observability, recovery, and cost. Interactive performance moved from three-to-five seconds to under 800 milliseconds, training cost fell 22%, and sustained-use engagement rose 25%; the final production-conversion rate is deliberately not invented.

That case establishes the first rule of this portfolio: a demo is an experiment, a feature is a dependency, and only an operable workflow is a product.

## Context must be governed before it can compound

At Rakuten, I [stopped a generic merchant chatbot and built around governed context](./projects/merchant-ai-governed-knowledge-graph.md). Listing, review, and image workflows shared merchant, catalog, policy, and performance knowledge without pretending one universal answer or risk threshold fit every job. The build-versus-partner decision and knowledge graph mattered because context became a reusable control plane, not merely prompt input.

In investment operations, [intelligent document processing](./projects/investment-operations-intelligent-document-processing.md) made each extracted field a typed, validated, attributable fact. The product distinguished routing confidence from field accuracy, tied reviewer corrections to governed training data, reduced comparable processing cost by roughly 70%, moved eligible ingestion from hours to seconds, and saved an estimated 15 person-weeks annually. Automation expanded only where evidence supported it.

## Authority should scale with consequence

[The regulated enterprise-agent platform](./projects/regulated-enterprise-agents-secure-deployment-platform.md) made the approved route easier than shadow deployment. Enterprise identity, private connectivity, persistent task state, permissioned tools, policy and human checkpoints, isolated execution, and customer-owned traces became one golden path. It grew from zero to more than 5,000 tenants and supported $20 million in commercial scope, while workflow-level time savings remained bounded to the deployments that measured them.

The product decision was not whether an agent could call a tool. It was who could grant authority, what could be done, when a person had to intervene, and how the customer could reconstruct the act.

## Explanations must change the user's next action

[Wealth-management next-best actions](./projects/wealth-management-explainable-next-best-actions.md) replaced an accurate but scarcely used churn score with one adviser card: recommended action, client-specific reasons, source evidence, limits, and a recorded human choice. Preparation effort fell 50%, false positives fell 18%, and a controlled regional pilot recorded 12% lower churn. Dismissal reasons became roadmap input, and the action policy changed when COVID made the old intervention unsafe even though the prediction still worked.

[The retail analytics product factory](./projects/retail-analytics-product-factory-agile-hindcasting.md) solved the opposite problem: historical prices could not reveal demand response. Controlled store tests manufactured evidence; SKU economic roles and customer guardrails constrained optimization; merchant evidence cards and overrides preserved accountable judgment. The publish cycle fell from six weeks to under one, overrides were below 5% by month two, and a rotating 1% sample kept the system learning.

## Ownership story — regulated enterprise agents

**Q: Tell me about a product you owned end to end.**

**A:** I owned the product strategy and operating contract for a regulated enterprise-agent platform that grew from no tenants on the new path to more than 5,000 and supported $20 million in commercial scope.

In discovery, customers were not asking for a more capable model. Their job was to deploy a stateful, tool-using agent inside existing identity, network, data, approval, and audit boundaries. Interviews and blocked deployments exposed six recurring limitations: private connectivity took weeks, task state was fragmented, tools lacked consistent permissioning, human review was bolted on, execution was insufficiently isolated, and traces mixed sensitive reasoning with operational evidence. Our advantage was the ability to turn those controls into one managed cloud path rather than asking every customer to assemble them.

I used a Double Diamond process. In **discover**, I combined customer blockers, security reviews, architecture patterns, support cases, and shadow-deployment behavior. In **define**, I wrote the deployable-agent contract: enterprise identity, private runtime, persistent task state, permissioned tool, policy or person, and customer-owned trace. I also made two deliberate roadmap vetoes—no blanket autonomy and no observability model that exposed sensitive reasoning by default.

In **develop**, Engineering evaluated runtime, networking, state, sandbox, and tracing options through RFCs. I used the PRD as a living product contract, captured hard-to-reverse permission and trace choices as ADRs, and made workflow risk determine approval depth. In **deliver**, the launch-readiness checklist required identity tests, private-path evidence, tool scopes, human checkpoints, rollback, incident ownership, cost limits, support readiness, and customer acceptance before promotion.

I measured the product across the whole funnel rather than counting created agents. Acquisition was qualified regulated demand; activation was a first grounded, permissioned workflow; retention was repeated successful operation with bounded incidents and cost; expansion was additional tools or business workflows; revenue was supported contract scope. Private-system connection moved from weeks to minutes. One bank audit workflow moved from weeks to days and recorded 60% more output; one clinical deployment saved roughly two hours per clinician per day. I kept those workflow results scoped rather than extrapolating them across all tenants.

The central trade-off with Engineering was immediate customer need versus scalable architecture. We used temporary enablement for one-off blockers, but built reusable identity, state, permission, isolation, and trace primitives for repeated needs. I owned the customer problem, product boundary, priorities, launch gates, adoption model, and outcome account; Engineering owned implementation, Risk retained approval, and customers retained workflow authority. End to end meant carrying the product from an unsafe shadow alternative to a repeatable production and commercial system.

## My product standard

Across AWS, Rakuten, Microsoft, D. E. Shaw, and McKinsey, I have owned product definitions, roadmap trade-offs, launch and promotion gates, evaluation systems, data and permission contracts, adoption loops, and executive outcome accounts. Engineering, Risk, Sales, Operations, and customers retain their own authority; good product leadership makes those boundaries executable.

The product is complete when a customer can use it repeatedly, understand its limits, recover from failure, govern its actions, and show that it improves a decision worth making.
