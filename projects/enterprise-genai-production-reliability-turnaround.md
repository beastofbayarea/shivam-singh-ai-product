# Resetting an enterprise GenAI roadmap around production use

I led product strategy for an enterprise generative-AI platform during my AWS role. I found that customers could demonstrate the technology but could not depend on it inside everyday work. I worked with enterprise users, technology and risk leaders, engineering, sales, customer success, support, finance, and product executives.

## I audited the roadmap against customer evidence

Feature delivery was active while 90% of deployments remained in test. Closed-lost evidence attributed 70% of lost deals to reliability rather than an absent feature. Customers experienced three-to-five-second inference, two-to-four-minute brownouts while new capacity started, missing connectors, unclear controls, and workflows with no stable owner or input standard.

Those figures described different populations. The 90% applied to deployments, the 70% to lost deals, and the latency to the measured inference path. I did not combine them into an adoption score.

My diagnosis was that the roadmap’s unit of value was wrong. A model endpoint, demo, or feature was not the product. The product was a consequential customer workflow that could operate repeatedly—with acceptable speed, quality, recovery, governance, support, and economics.

I paused lower-priority expansion and rewrote the roadmap around four constraints: production reliability, integration, workflow readiness, and accountable operation.

## A maturity model replaced the word “production”

I introduced four states with observable promotion evidence:

| State | Customer reality | Evidence needed to advance |
|---|---|---|
| Experiment | sporadic calls and exploration | named problem, eligible users, baseline, owner, and value hypothesis |
| Workflow | repeatable task on real company data | stable procedure, validated inputs, quality evaluation, and human fallback |
| Integration | daily operation across systems | connectors, identity, monitoring, rollback, support, and change ownership |
| Scale | sustained material use | user-facing objectives, capacity plan, incident process, cost controls, and expansion evidence |

An account stalled for more than 30 days triggered an integration workshop. Product then aggregated repeated blockers across those workshops so connectors, auditability, or data readiness could outrank a highly visible demonstration feature.

The ladder also exposed non-technical failure. One legal workflow churned because its intake fields were inconsistent. More model speed would only have automated disorder. I added a workflow-readiness gate: a stable procedure, accountable business owner, defined inputs, reachable systems, review policy, and measurable outcome had to exist before production promotion.

## The brownout became a product problem

CPU-only autoscaling reacted after queues formed. Large workloads then needed two to four minutes to add capacity, creating a user-visible brownout.

I set a product requirement around the experience rather than a particular infrastructure mechanism. The team added queue depth, time per token, workload class, and priority to scaling decisions; held warm buffer capacity for latency-sensitive traffic; and used checkpointed interruptible capacity where training work could safely resume. The trade-off was deliberate: some idle capacity for important real-time requests, interruption complexity for lower training cost, and LLM-specific telemetry in exchange for earlier control.

Latency, capacity, model behavior, and workflow success could not share one SLO. I required a measurement tree:

- time to first response and end-to-end completion by workload class and percentile;
- queue wait, generation time, errors, timeouts, and capacity additions;
- task quality and groundedness on a versioned evaluation set;
- successful workflow completion, human takeover, and recovery; and
- cost per completed eligible task, not cost per token in isolation.

[Google’s SRE guidance on service-level objectives](https://sre.google/sre-book/service-level-objectives/) supports the customer-first logic: an indicator should represent behavior users care about and an objective should inform decisions. The [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) supplied a current external benchmark for monitoring, graceful degradation, fault isolation, recovery, and resilience exercises.

## The feature conflict that made the strategy real

A banking customer requested voice while its existing text workflow was failing 15% of requests. Engineering estimated that immediate voice load could push failure toward 30%. The 30% figure was a scenario, not an observed result.

I framed the customer decision plainly: add a new interface to a failing core now, or fix timeouts and capacity before a later voice launch. The customer chose stability. I kept reversible preparation moving while blocking the dependency that would compound production harm.

That choice reset how sales and engineering discussed reliability. It was no longer undifferentiated internal work. It was a customer capability with an explicit cost, release gate, and commercial argument.

## What the retained scorecard supports

| Measure | Baseline | Intended direction | Recorded result | Defensible interpretation |
|---|---:|---:|---:|---|
| Inference latency | 3–5 s | sub-second | <800 ms | at least 73.3% and as much as 84% lower than the stated range; timestamp boundary and percentile are not retained |
| Scale-out brownout | 2–4 min | serve priority traffic without cold-start impairment | warm-buffer design introduced | no post-change brownout duration retained |
| Training cost | index 100 | reduce without losing completed work | index 78 | 22% lower; absolute spend, workload mix, and measurement window absent |
| Engagement | index 100 | increase sustained product use | index 125 | 25% increase; cohort, event definition, and window absent, so not claimed as causal adoption lift |
| Deployments in test | 90% | move ready workflows into operation | no final rate retained | important baseline; no defensible production-conversion result |

Leadership had also identified a projected cost opportunity above 20% from GPU waste. That forecast helped prioritize the work; it is not an additional realized saving and should not be added to the recorded 22% training-cost change.

The [NIST Generative AI Profile](https://doi.org/10.6028/NIST.AI.600-1), published in 2024, reinforces why readiness must extend beyond uptime: production risk includes model evaluation, data and privacy, human oversight, monitoring, incident handling, and misuse. I use it as an external benchmark rather than evidence of the internal implementation.

## The product leadership I owned

I owned the diagnosis, maturity model, roadmap reset, customer segmentation, readiness criteria, feature trade-offs, cross-functional priorities, and executive success account. Engineering owned architecture and operation. Customer teams owned their workflows and controls. Sales and customer success owned account commitments and intervention. Risk specialists retained approval authority.

The strongest defensible outcome is a platform and organization reoriented from features shipped to workflows operated, accompanied by the recorded latency, cost, and engagement changes. The project record does not establish the final share of deployments that reached production, incremental revenue, or the observation definitions behind every headline figure, so I do not invent them.

## Sources and boundaries

- The retained project record provides the adoption mismatch, latency, brownout, scaling, maturity, customer decision, cost, and engagement evidence.
- [Google SRE: Service Level Objectives](https://sre.google/sre-book/service-level-objectives/) — external design basis for user-centred indicators and decision-linked objectives.
- [AWS Well-Architected Framework: Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) — current external reliability benchmark.
- [NIST AI 600-1: Generative Artificial Intelligence Profile](https://doi.org/10.6028/NIST.AI.600-1) — 2024 external benchmark for GenAI-specific risk and measurement.
