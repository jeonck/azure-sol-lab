---
title: "Azure Engineer Skill Matrix"
weight: 2
---

Job titles are noisy; capabilities are not. This matrix defines what **Junior**, **Mid**, **Senior**, and **Architect** actually mean for an Azure engineer across eight skill areas, as concrete can-do statements. Assess yourself honestly against each row, then use the [gap-driven learning plan](#gap-driven-learning-plan) at the bottom to pick your next lab.

{{< callout type="info" >}}
Rate yourself at a level only if you can do everything in that cell today, without looking it up, and have an artifact that proves at least one item. Aspirational self-ratings collapse in interviews.
{{< /callout >}}

## How to read the levels

- **Junior** — can execute a documented task correctly.
- **Mid** — can build the thing independently and debug it when it breaks.
- **Senior** — can choose between alternatives and justify the choice with trade-offs.
- **Architect** — can design the system, set the standards, and defend the design under challenge.

## Compute

| Level | Can do |
|-------|--------|
| Junior | Deploy an App Service and a VM from the portal or CLI; explain the difference between App Service plans and Consumption Functions; restart, scale, and read logs |
| Mid | Choose between App Service, Functions, Container Apps, and AKS for a given workload; configure autoscale rules and deployment slots; containerize an app and run it on Azure |
| Senior | Operate AKS in anger — node pools, upgrades, workload identity, HPA; justify Consumption vs Premium Functions with cold-start and cost data; design compute for spiky vs steady traffic |
| Architect | Set the compute selection standard for an organization; design the AKS vs Container Apps decision tree tied to team topology; own capacity, quota, and reserved-instance strategy |

**Built by:** [Lab 1](../../labs/lab-01-n-tier), [Lab 3](../../labs/lab-03-serverless-api), [Lab 5](../../labs/lab-05-aks-microservices)

## Networking

| Level | Can do |
|-------|--------|
| Junior | Create a VNet and subnets; explain NSGs vs firewalls; associate an NSG and read its effective rules |
| Mid | Build VNet peering and private endpoints; configure user-defined routes; expose an app through Application Gateway with TLS |
| Senior | Design and deploy hub-spoke with centralized egress through Azure Firewall; plan address space for growth; debug asymmetric routing and DNS resolution across VNets |
| Architect | Define the landing-zone network topology for an enterprise; make the ExpressRoute vs VPN call with bandwidth and SLA data; own the segmentation and inspection standard |

**Built by:** [Lab 1](../../labs/lab-01-n-tier), [Lab 7](../../labs/lab-07-hub-spoke), [Lab 8](../../labs/lab-08-multi-region-ha)

## Data

| Level | Can do |
|-------|--------|
| Junior | Provision Azure SQL and a storage account; connect an app with a connection string; explain blob tiers |
| Mid | Choose between Azure SQL, Cosmos DB, and PostgreSQL for a workload; configure backup, PITR, and firewall rules; model a Cosmos DB partition key that avoids hot partitions |
| Senior | Design a medallion lakehouse on ADLS Gen2; decide file formats and partitioning with measured scan-size impact; plan geo-replication and failover for the data tier |
| Architect | Own the data platform strategy — lakehouse vs warehouse, Fabric vs Databricks; define RPO per data class; set data lifecycle, retention, and cost governance standards |

**Built by:** [Lab 1](../../labs/lab-01-n-tier), [Lab 3](../../labs/lab-03-serverless-api), [Lab 6](../../labs/lab-06-data-pipeline)

## Messaging and Integration

| Level | Can do |
|-------|--------|
| Junior | Send and receive messages on a Storage Queue; explain queue vs topic; describe at-least-once delivery |
| Mid | Implement Web-Queue-Worker with a dead-letter path; use Service Bus sessions and duplicate detection; wire Event Grid subscriptions with filters |
| Senior | Pick Event Grid vs Service Bus vs Event Hubs from workload characteristics and defend it; design idempotent consumers; handle poison messages and replay |
| Architect | Define the organization-wide eventing backbone; design schema evolution and versioning for events; set delivery-guarantee and ordering standards per integration class |

**Built by:** [Lab 2](../../labs/lab-02-web-queue-worker), [Lab 4](../../labs/lab-04-event-driven)

## Security and Identity

| Level | Can do |
|-------|--------|
| Junior | Assign RBAC roles at the right scope; explain managed identity vs service principal; store a secret in Key Vault and read it from an app |
| Mid | Replace all connection-string secrets with managed identities; configure private endpoints to remove public data-plane exposure; apply deny-by-default NSGs |
| Senior | Design workload identity for AKS; implement least-privilege RBAC with custom roles where built-ins overreach; run a threat-model pass on an architecture before deployment |
| Architect | Define the identity and network security baseline for a landing zone; own Conditional Access and PIM strategy; set the standard for secret-less architectures across teams |

**Built by:** [Lab 5](../../labs/lab-05-aks-microservices), [Lab 7](../../labs/lab-07-hub-spoke) — and every lab that uses managed identity instead of keys

## IaC and DevOps

| Level | Can do |
|-------|--------|
| Junior | Deploy a provided Bicep or Terraform template; read a template and predict what it creates; use az deployment what-if before applying |
| Mid | Author Bicep modules from scratch with parameters and outputs; structure a repo for multiple environments; wire a CI pipeline that lints and deploys on merge |
| Senior | Design the module and state strategy for a team; implement what-if gates and drift detection; choose Bicep vs Terraform for a context and defend it |
| Architect | Own the IaC standard across an organization — module registry, policy as code, environment promotion; design deployment safety with progressive rollout and rollback |

**Built by:** every lab — all eight are deployed and torn down with Bicep and the Azure CLI, starting with [Lab 1](../../labs/lab-01-n-tier)

## Observability

| Level | Can do |
|-------|--------|
| Junior | Read metrics and activity logs in the portal; set a metric alert; find an error in App Service log stream |
| Mid | Configure Application Insights with distributed tracing; write KQL queries against Log Analytics; build a dashboard for the four golden signals |
| Senior | Define SLIs and SLOs for a service and alert on burn rate; trace a request across queue and worker boundaries; use health probes to drive automated failover |
| Architect | Set the observability standard — what every service must emit; design the workspace and retention topology with cost controls; make reliability targets contractual per tier |

**Built by:** [Lab 2](../../labs/lab-02-web-queue-worker), [Lab 5](../../labs/lab-05-aks-microservices), [Lab 8](../../labs/lab-08-multi-region-ha)

## Architecture Design

| Level | Can do |
|-------|--------|
| Junior | Name the core architecture styles and one Azure service set for each; redraw a reference architecture that was explained to you |
| Mid | Map a business requirement to a style using the [style decision tree](../../architecture-styles); produce a diagram and a written rationale for a small system |
| Senior | Run a design review — surface requirements, propose two options, present trade-offs, and make a recommendation; combine styles deliberately, such as microservices core with event-driven integration |
| Architect | Design for explicit RTO, RPO, and cost envelopes; write decision records that survive challenge; anticipate failure modes per style and design their mitigations up front |

**Built by:** every [scenario playbook](../../scenarios) paired with its lab; [Lab 8](../../labs/lab-08-multi-region-ha) is the capstone

## Gap-driven learning plan

The matrix is only useful if it changes what you do next. The algorithm:

1. **Score every area** — write down your honest level for each of the eight rows.
2. **Find the anchor gap** — the lowest-scoring area that appears in job descriptions for your target role. For most Azure engineering roles the screening order is IaC and DevOps, Compute, Networking, then Messaging.
3. **Pick the lab that attacks it** — use the mappings above. One lab, completed with artifacts, typically moves you one level in one or two areas.
4. **Re-score only after the artifact exists** — the level is earned when the repository, diagram, and decision record exist, not when the lab is merely finished.

Typical paths:

- **Weak on IaC** — redo [Lab 1](../../labs/lab-01-n-tier) but author every Bicep file yourself instead of using the provided templates.
- **Junior in Networking, Mid elsewhere** — go straight to [Lab 7](../../labs/lab-07-hub-spoke); networking is the most common senior-interview filter.
- **Mid across the board, targeting senior** — [Lab 5](../../labs/lab-05-aks-microservices) and [Lab 8](../../labs/lab-08-multi-region-ha) generate the strongest design-review stories.
- **Strong build skills, weak design vocabulary** — read two [scenario playbooks](../../scenarios) end to end and write your own decision record for each before touching the next lab.

{{< callout type="warning" >}}
Do not grind the same area past the level your target role needs. A senior role rarely requires Architect-level depth in all eight areas — it requires Senior in three or four and Mid everywhere else. Breadth of honest Mid beats fragile claimed Senior.
{{< /callout >}}

When a gap closes, feed the result straight into your [LinkedIn experience statements](../linkedin-experience) and rehearse it with the [interview prep](../interview-prep) questions.
