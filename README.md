# Shivam Singh — AI & Data Product Management

## Profile

**Tell me about yourself.**

I am an AI and data product leader who turns complex analytical systems into products people can trust and operate. I began at McKinsey in digital, analytics, and FinTech strategy, moved into intelligent document and data workflows at D. E. Shaw, and led cloud-data and lifecycle-intelligence products at Microsoft. During my MBA role at Rakuten, I redirected a generic merchant chatbot toward embedded merchant jobs backed by a governed knowledge graph. At AWS, I have focused on enterprise GenAI readiness and secure agent platforms: reliability, identity, permissions, private connectivity, evaluation, observability, and cost.

My progression has been from analytical strategy to workflow products to enterprise AI platforms. I define the product boundary, make roadmap trade-offs, align Engineering, Risk, Sales, and Operations, and build the promotion and measurement system that lets an AI product earn production authority.

I build AI products as decision systems: trusted context, bounded authority, reliable execution, human judgment, and measurable economic outcomes.

[Resume](./shivam-singh-ai-product.pdf) · [LinkedIn](https://www.linkedin.com/in/beastofbayarea) · [shiv-ai-product@umich.edu](mailto:shiv-ai-product@umich.edu)

## Product thesis

An AI model becomes a product only when the whole chain works:

```text
real user decision → trusted context → permissioned action
→ reliable workflow → human feedback and recovery
→ measured customer and business value
```

Each project below owns a different failure point in that chain. Together, they show how I decide what to build, what not to automate, and what evidence a system needs before it receives more authority.

## Selected evidence

### Reliability changes the roadmap

[Resetting an enterprise GenAI roadmap around production use](./projects/enterprise-genai-production-reliability-turnaround.md) started with 90% of deployments still in test and 70% of closed-lost deals citing reliability over missing features. I shifted the strategy to production promotion and introduced a four-stage maturity system spanning workflow ownership, quality, connectors, identity, observability, recovery, and cost.

Interactive performance improved from three-to-five seconds to under 800 milliseconds, training cost fell 22%, and sustained-use engagement rose 25%. The production-conversion rate is intentionally not invented. A demo is an experiment; only an operable workflow is a product.

### Context must be governed before it compounds

At Rakuten, I [replaced a generic merchant chatbot with governed context](./projects/merchant-ai-governed-knowledge-graph.md). Merchant, catalog, policy, and performance knowledge became a reusable control plane rather than prompt input.

In investment operations, [intelligent document processing](./projects/investment-operations-intelligent-document-processing.md) made every extracted field typed, validated, and attributable. Comparable processing cost fell roughly 70%, eligible ingestion moved from hours to seconds, and the work saved an estimated 15 person-weeks annually. Automation expanded only where evidence supported it.

### Authority should scale with consequence

[The regulated enterprise-agent platform](./projects/regulated-enterprise-agents-secure-deployment-platform.md) combined enterprise identity, private connectivity, persistent task state, permissioned tools, policy and human checkpoints, isolated execution, and customer-owned traces into one golden path. It grew from zero to more than 5,000 tenants and supported $20 million in commercial scope; workflow-level time savings remain scoped to deployments that measured them.

The key product question was not whether an agent could call a tool, but who could grant authority, what could be done, when a person had to intervene, and how the customer could reconstruct the act.

### Explanations must change the next action

[Wealth-management next-best actions](./projects/wealth-management-explainable-next-best-actions.md) turned an accurate but scarcely used churn score into an adviser card with a recommendation, client-specific reasons, source evidence, limits, and a recorded human choice. Preparation effort fell 50%, false positives fell 18%, and a controlled regional pilot recorded 12% lower churn.

[The retail analytics product factory](./projects/retail-analytics-product-factory-agile-hindcasting.md) used controlled store tests to create demand evidence, then constrained optimization with SKU economics, customer guardrails, evidence cards, and overrides. The publish cycle fell from six weeks to under one, overrides were below 5% by month two, and a rotating 1% sample kept the system learning.

## Ownership story: regulated enterprise agents

**Tell me about a product you owned end to end.**

I owned the product strategy and operating contract for a regulated enterprise-agent platform that grew from no tenants on the new path to more than 5,000 and supported $20 million in commercial scope.

Customers needed a stateful, tool-using agent inside existing identity, network, data, approval, and audit boundaries—not simply a more capable model. Discovery exposed six recurring blockers: private connectivity, fragmented task state, inconsistent tool permissions, bolted-on human review, insufficient execution isolation, and traces that mixed sensitive reasoning with operational evidence.

I defined the deployable-agent contract: enterprise identity, private runtime, persistent task state, permissioned tools, policy or human checkpoints, and customer-owned traces. I vetoed blanket autonomy and default observability that exposed sensitive reasoning. Engineering evaluated runtime, networking, state, sandbox, and tracing options through RFCs; I captured hard-to-reverse permission and trace decisions as ADRs and used workflow risk to set approval depth.

Promotion required identity tests, private-path evidence, tool scopes, human checkpoints, rollback, incident ownership, cost limits, support readiness, and customer acceptance. I measured qualified demand, grounded activation, repeated successful operation, workflow expansion, and supported revenue—not created agents.

Private-system connection moved from weeks to minutes. One bank audit workflow moved from weeks to days with 60% more output; one clinical deployment saved roughly two hours per clinician per day. Those results remain scoped to the deployments that measured them.

The central trade-off was immediate customer need versus scalable architecture. Temporary enablement handled one-off blockers; reusable identity, state, permission, isolation, and trace primitives handled repeated needs. I owned the customer problem, boundary, priorities, launch gates, adoption model, and outcome account; Engineering owned implementation, Risk retained approval, and customers retained workflow authority.

## Product standard

Across AWS, Rakuten, Microsoft, D. E. Shaw, and McKinsey, I have owned product definitions, roadmap trade-offs, launch and promotion gates, evaluation systems, data and permission contracts, adoption loops, and executive outcome accounts.

The product is complete when a customer can use it repeatedly, understand its limits, recover from failure, govern its actions, and show that it improves a decision worth making.
