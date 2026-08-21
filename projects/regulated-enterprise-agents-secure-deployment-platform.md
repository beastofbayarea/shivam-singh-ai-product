# Regulated Enterprise Agents — Secure Deployment Platform

## What I worked on

I completed this work during my [AWS experience from July 2024 to present](https://github.com/beastofbayarea/shivam-singh-ai-product/blob/main/shivam-singh-ai-product.pdf).

I built a secure golden path for stateful, tool-using enterprise agents. The platform standardized private networking, zero retention, customer-owned payload logs, persistent state, permissioned tools, explicit agent identities, and human checkpoints while keeping setup practical.

## At a glance

- I led a secure agent-platform strategy that onboarded more than 5,000 regulated tenants and supported $20M in contracts with zero recorded data-exfiltration events.
- I directed a 15+ engineer squad to standardize permissioned remote-tool connections, reducing private-system integration from weeks to minutes.
- I reduced unauthorized public-AI usage roughly 70% by making the approved platform both safer and easier to adopt.

## The situation

Regulated enterprises were caught between uncontrolled employee use of public AI and internal tools that were too complex. Agents lost state, voice latency approached three seconds, and private systems lacked a safe standard connection.

## What I needed to accomplish

I needed to create a production-ready platform that preserved privacy, identity, observability, performance, and usability without centralizing sensitive customer payloads.

## What I did

- I separated customer-owned prompt, response, and tool traces from provider-owned operational metadata.
- I designed every agent as a governed digital identity with explicit data, action, and budget boundaries.
- I delayed code execution for 30 days until sandbox isolation was proven.
- I introduced a single launchpad template after customer feedback showed the initial three-service setup was too complex.

## The results

- More than 5,000 regulated tenants onboarded.
- The platform supported $20M in contracts and recorded zero exfiltration events.
- Shadow-AI usage declined approximately 70%.
- I selected workflows reduced bank contract-audit time from weeks to days, increased output 60%, and saved clinicians about two hours per day.

## Decisions and trade-offs

- I made the safest deployment path the default and simplest journey.
- I delayed an irreversible code-execution risk while preserving reversible product progress.
- I retained sensitive payloads inside the customer perimeter and debug with metadata plus sanitized reproductions.

## How I led

Balanced product velocity, security, enterprise usability, and customer trust across engineers, risk teams, administrators, and regulated buyers.

## Why I chose this approach

I used [NIST - Generative AI Profile (2024)](https://doi.org/10.6028/NIST.AI.600-1) to ground generative AI risk, governance, and evaluation foundation. I used [NIST - Zero Trust Architecture (2020)](https://doi.org/10.6028/NIST.SP.800-207) to ground least-privilege identity and access architecture.

## Sources and external context

I used independent methodology and market evidence to shape the work. The resume link above is included only to establish the employment timeline.

| Source | How it informed my work | Timing |
|---|---|---|
| [NIST - Generative AI Profile (2024)](https://doi.org/10.6028/NIST.AI.600-1) | I used it to ground generative AI risk, governance, and evaluation foundation. | — |
| [NIST - Zero Trust Architecture (2020)](https://doi.org/10.6028/NIST.SP.800-207) | I used it to ground least-privilege identity and access architecture. | — |
