# Resetting an enterprise GenAI roadmap around production use

Ninety percent of deployments were still in test. Seventy percent of closed-lost deals cited reliability rather than a missing feature. Customers were experiencing three-to-five-second inference, two-to-four-minute brownouts while capacity started, incomplete connectors, and workflows with no stable owner or input standard.

These were different populations and measures, but they pointed to one product failure: the roadmap rewarded demonstrations while customers needed repeatable operations.

During my AWS role, the product-strategy reset became my mandate across enterprise users, technology/risk leaders, Engineering, Sales, Customer Success, Support, Finance, and product executives. I paused lower-priority expansion and made **production promotion**—not endpoint creation, demos, or shipped features—the unit of strategy.

## What counted as the product

I defined the product as a consequential customer workflow that could operate repeatedly with acceptable speed, quality, recovery, governance, support, and cost. The model endpoint was only one dependency.

That definition produced a four-stage maturity ladder:

| Stage | Customer reality | Promotion evidence |
|---|---|---|
| Experiment | Sporadic calls exploring a use case | Named problem, eligible users, baseline, accountable owner, value hypothesis |
| Workflow | Repeatable task on real company data | Stable procedure and inputs, quality evaluation, human fallback |
| Integration | Daily operation across systems | Connectors, identity, monitoring, rollback, support, change ownership |
| Scale | Sustained material use | User-facing objectives, capacity plan, incident process, cost controls, expansion proof |

Accounts stalled for more than 30 days triggered an integration workshop. I aggregated the blockers: if several customers could not resolve identity, audit, connector, or data-readiness issues, that shared constraint could outrank a visible new feature.

The maturity ladder also stopped technical teams from automating organizational disorder. One legal workflow churned because intake fields were inconsistent. Faster inference would have failed faster. Production readiness therefore required a stable procedure, business owner, defined input, reachable system, review policy, and measurable operating outcome.

## Reliability became a roadmap capability

The platform’s CPU-only scaling signal reacted after queues formed. Large workloads then waited two to four minutes for capacity, creating a customer-visible brownout.

I set requirements from the experience backward. Scaling incorporated queue depth, time per token, workload class, and priority. Latency-sensitive traffic received warm buffer capacity; interruptible training workloads used checkpoints where safe resume was possible. The trade was explicit: pay for some idle capacity to protect high-value real-time work, accept interruption complexity to reduce lower-priority training cost, and invest in LLM-specific telemetry to act before a generic CPU threshold moved.

I refused a single “AI uptime” metric. The measurement tree separated:

- time to first response and end-to-end completion by workload class and percentile;
- queue wait, generation, errors, timeouts, and capacity-addition events;
- groundedness and task quality on a versioned evaluation set;
- completed workflow, human takeover, and recovery;
- cost per completed eligible task; and
- account progression through the maturity ladder.

[Google’s SRE guidance on SLOs](https://sre.google/sre-book/service-level-objectives/) informed the user-centered indicator design. The [AWS Well-Architected Reliability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html) supplied an external benchmark for graceful degradation, fault isolation, recovery, and resilience exercises. Neither source substitutes for the internal results.

## The banking decision made the reset credible

A banking customer asked for voice while its text workflow was failing 15% of requests. Engineering estimated that adding voice immediately could push failure toward 30%. That was a capacity scenario, not an observed outcome.

I gave the customer and sales team a real choice: add a new interface to an unstable core, or fix timeouts and capacity first while preserving reversible preparation for voice. The customer chose stability.

This changed the organizational conversation. Reliability was no longer anonymous “platform work.” It became a customer capability with a commercial argument, a release gate, and an acknowledged opportunity cost.

## Executive result account

| Decision | Baseline → target → recorded result | Measurement boundary |
|---|---|---|
| Interactive performance | 3–5 s → sub-second → <800 ms | Same request class and timestamp boundary at stated percentile; 73.3–84% lower across the recorded baseline range |
| Cold-start impairment | 2–4 min → priority traffic served without brownout → warm-buffer design introduced | Post-change duration not retained; architecture shipped is not a quantified outcome |
| Training economics | cost index 100 → reduce without lost work → 78 | Completed comparable training workload; 22% lower |
| Sustained use | engagement index 100 → increase with workflow completion → 125 | Cohort, qualifying event, and window must remain constant; recorded 25% rise is not automatically causal adoption |
| Production conversion | 90% of deployments in test → promote ready workflows → final share not retained | Deployment maturity state with explicit promotion evidence |

Leadership also identified a projected GPU-waste opportunity above 20%. That forecast justified prioritization but is not additive to the recorded 22% cost change.

The [NIST Generative AI Profile](https://doi.org/10.6028/NIST.AI.600-1) reinforces the broader readiness perimeter—evaluation, data, privacy, oversight, monitoring, incidents, and misuse—but postdates part of the work and is presented only as an external benchmark.

The diagnosis, production definition, maturity system, roadmap reallocation, segmentation, readiness gates, banking trade-off, and executive measurement account were the decisions I carried. Engineering retained architecture/operations; customers retained workflows/controls; Sales and Customer Success retained commitments; Risk retained approval.

The turnaround mattered because it changed what the organization was willing to call progress. A demo became an experiment. A feature became a dependency. Only a workflow that customers could operate, support, govern, and afford became a product.
