# Making the approved enterprise-agent path the easiest path

I led product development for a regulated-enterprise agent platform during my AWS role. I saw that employees wanted AI help but the approved tools could not reliably continue work or reach private systems. I worked with employees, clinicians, bankers, customer technology and risk leaders, product design, engineering, security, privacy, legal, support, sales, and executive sponsors.

## The competition was shadow AI

Regulated organizations were not choosing between AI and no AI. They were choosing between public tools that were easy but uncontrolled and internal tools that were safer but difficult. The internal route exposed three services, lost state across interrupted work, took weeks to connect to a private system, and produced roughly three-second pauses in voice interactions.

I defined a demanding product thesis: the compliant route had to remove more friction than the shadow route while making identity, data use, action, and accountability visible. A policy that merely prohibited public AI would not satisfy the user’s job.

## The contract of a governed agent

I treated an agent as a principal with bounded authority, not as a chatbot with a system prompt. A deployable agent needed all of the following:

**A subject.** The authenticated person or service on whose behalf the agent was operating.

**Its own identity.** An agent identity separate from the end user, with explicit roles, credentials, and revocation.

**A purpose and data scope.** The workflow, records, and context it could retrieve—not generic access inherited from a broad application account.

**An action envelope.** Named tools, allowed operations, transaction and spend limits, rate limits, and prohibited actions.

**State with lifecycle rules.** The minimum memory needed to continue a task, with ownership, retention, deletion, and permission inheritance defined.

**Checkpoints.** Policy or human approval before high-consequence actions, with the approver seeing the proposed action and relevant evidence.

**A trace.** Identity, tool choice, policy decision, latency, error, state transition, and approval recorded so an operator could reconstruct what happened.

[NIST’s Zero Trust Architecture](https://doi.org/10.6028/NIST.SP.800-207) supplied a useful external principle: grant least-privilege access to specific resources after explicit authentication and authorization rather than trusting network location. The [NIST Generative AI Profile](https://doi.org/10.6028/NIST.AI.600-1) broadened the product gate to model behavior, evaluation, human oversight, misuse, monitoring, and incident response.

## The golden path I asked engineering to productize

I led a group of more than 15 engineers to make the full control envelope reusable:

`enterprise identity → private agent runtime → persistent task state → permissioned tool → policy or person → customer-owned trace`

Customer prompts, responses, and detailed tool payloads were designed to remain in customer-controlled storage under a zero-retention provider contract. The provider retained the limited operational metadata needed to run and support the platform: for example, error class, timing, token count, and resource state. Debugging a content defect used an authorized customer trace or a sanitized reproduction, not an undisclosed copy of production content.

That separation was a product decision, not a claim that observability can be “zero data.” Metadata can itself be sensitive, and customer logging still needs retention, access, redaction, and deletion policy.

The tool connection ran inside a customer VPC or on-premises environment. The platform checked agent and user identity, tool, operation, data scope, and budget before returning a result. Private networking reduced exposure to public routing; it did not by itself prove end-to-end authorization or eliminate application-layer risk.

## Two moments where I stopped the roadmap

### Code execution

Sandbox isolation had not passed its proof. I delayed code execution for 30 days while the team continued reversible work on identity, templates, monitoring, and permissions. Three customers challenged the delay and all accepted the validation plan; the source records no churn among those three.

This was not “security versus growth.” Unbounded code execution was a one-way trust decision, while a short feature delay was recoverable. The release gate needed isolation between sessions, constrained filesystem and network access, resource limits, dependency control, timeouts, output handling, audit, and demonstrated escape resistance.

### Setup complexity

The first secure architecture required customers to configure three services. Customer evidence showed that the technically sound route was not adoptable. I replaced it with one launchpad template that provisioned the approved network, identity, state, logging, and tool configuration together. Setup moved from days to hours; the retained record does not preserve the exact endpoints.

## Voice was a separate real-time product

A serial speech-to-text, reasoning, and text-to-speech chain produced pauses near three seconds. I moved the experience requirement to a streaming connection with turn detection and reserved throughput for clinical workloads. The design target was below 500 milliseconds; the record does not contain an observed production result, so I report the target as a target.

That distinction matters. A voice system must measure the user’s turn-end to audible-response interval, interruption and overlap, transcription error, task completion, and clinician takeover. Model inference latency alone does not establish conversational quality.

## Adoption evidence, with denominators kept visible

The strongest causal evidence came from shadow-AI behavior. The team compared a 90-day baseline of unauthorized public-model network traffic with the same measure six months after launch. Departments with the approved platform showed about a 70% decline; groups without access showed minimal change; surveys indicated users had moved work to the internal tool. The design is stronger than a before-and-after total, although sample size, assignment method, and confidence interval are not retained.

The wider source scorecard reports:

- more than 5,000 regulated tenants onboarded and $20 million in contracts supported—the contract figure is not necessarily revenue recognized or solely caused by this product;
- zero recorded data-exfiltration events—an observation bounded by monitoring coverage and classification, not proof that no event occurred;
- private-system integration reduced from weeks to minutes—the integration boundary and distribution are not retained;
- a selected bank audit workflow reduced from weeks to days and increased output 60%;
- a selected clinical deployment reported roughly two hours of administrative time saved per clinician per day; and
- one enterprise-administration use case reported a 50% burden reduction.

Those workflow results belong to specific deployments. I do not average them into a universal productivity claim or multiply them across the tenant population.

## Public AWS context and attribution boundary

AWS announced [Amazon Bedrock AgentCore in preview in July 2025](https://aws.amazon.com/about-aws/whats-new/2025/07/amazon-bedrock-agentcore-preview/) with runtime session isolation, memory, gateway, code interpreter, observability, and identity. [General availability followed in October 2025](https://aws.amazon.com/about-aws/whats-new/2025/10/amazon-bedrock-agentcore-available/) with VPC and PrivateLink support across its services. Those dates fall within my July 2024–present employment and confirm the market and product context. They do not independently prove that I personally authored AgentCore or that every retained project metric is an AgentCore result.

AWS also states that [Amazon Bedrock does not store customer inputs and outputs or use them to train models](https://repost.aws/knowledge-center/amazon-bedrock-model-data-use). That public service behavior supports the privacy context; the customer-owned logging and metadata split described here remains a distinct application-platform design.

## What I owned

I owned the product thesis, user and buyer discovery, control contract, golden-path requirements, sequencing, release gates, code-execution decision, setup simplification, adoption account, and cross-functional alignment. Engineering and security specialists owned implementation and technical proof. Customer risk owners approved use. Workflow leaders owned human accountability and realized operating change.

The project’s strategic value was making control an adoption feature. Persistent state, private tools, explicit agent authority, isolated execution, and observable decisions were not compliance paperwork attached after the experience; they were the product surface that allowed regulated customers to use agents at all.
