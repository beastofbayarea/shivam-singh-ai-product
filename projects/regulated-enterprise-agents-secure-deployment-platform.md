# Regulated Enterprise Agents — Secure Deployment Platform

I completed this work during my [AWS experience from July 2024 to present](https://github.com/beastofbayarea/shivam-singh-ai-product/blob/main/shivam-singh-ai-product.pdf).

## The trap I needed to escape

Regulated enterprises were choosing between two bad options: uncontrolled employee use of public AI or approved internal tools that were too difficult to use. The internal path required three services, agents lost state, voice latency approached three seconds, and private systems had no consistent connection model.

I defined the product goal as a secure golden path. The approved route had to be both safer and easier than the shadow alternative.

## The trust boundaries

I separated customer content from provider operations. Prompts, responses, and tool payloads stayed inside the customer-controlled environment with zero retention at the provider layer. The platform retained only the operational metadata required to run and support the service.

Every agent became a governed digital identity. Its permissions specified which data it could retrieve, which tools it could call, which actions it could take, how much it could spend, and where human approval was mandatory.

NIST Zero Trust Architecture informed that identity-first, least-privilege model. NIST’s Generative AI Profile extended the risk model to AI behavior, evaluation, monitoring, and human oversight.

## Standardizing private tool use

I directed a team of more than 15 engineers to create permissioned remote-tool connections for private enterprise systems. The standard reduced integration from weeks to minutes because customers no longer had to design identity, network, authorization, and audit behavior from scratch for every agent.

I also added persistent state, private networking, customer-owned payload logs, explicit agent identities, and observable policy decisions to the golden path.

## The code-execution decision

I delayed code execution for 30 days after the sandbox failed its isolation proof. The team continued reversible work on permissions, templates, and monitoring while the irreversible risk remained blocked.

That decision protected product momentum without converting schedule pressure into an enterprise security exception.

## Simplifying the journey

The first design exposed three services and required customers to assemble them correctly. Customer feedback showed that the architecture was secure but not adoptable. I replaced it with one launchpad template that created the approved network, identity, logging, state, and tool configuration together.

This usability change was part of the security strategy. A difficult secure path sends people back to uncontrolled tools.

## What changed

| Outcome | Result |
|---|---:|
| Regulated tenants onboarded | More than 5,000 |
| Contracts supported | $20M |
| Recorded data-exfiltration events | Zero |
| Unauthorized public-AI usage | Approximately -70% |
| Private-system integration | Weeks to minutes |
| Selected bank audit workflow | Weeks to days |
| Selected clinical workflows | Approximately two hours saved per clinician per day |

I treat the workflow outcomes as examples of what the platform enabled, not as one universal productivity claim.

## What I learned

Security controls became product capabilities when buyers could understand, configure, and observe them. The strongest adoption lever was not a lower-friction exception process; it was making the compliant default path genuinely usable.

## Sources and external context

These sources informed the identity, deployment, and AI-risk model. The resume link establishes the employment timeline.

| Source | How it informed my work | Timing |
|---|---|---|
| [NIST — Zero Trust Architecture](https://doi.org/10.6028/NIST.SP.800-207) | I used it to define explicit identity, least privilege, resource-level policy, and continuous evaluation. | 2020 |
| [NIST — Generative AI Profile](https://doi.org/10.6028/NIST.AI.600-1) | I used it to include model risk, evaluation, monitoring, incident response, and human oversight in the deployment model. | 2024 |

