---
title: Overview
weight: 1
next: /docs/architecture-styles
---

**Azure Solution Lab** is a lab-first knowledge base for Azure engineers who want architecture skills they can prove — not just describe.

## How this site is organized

{{< cards >}}
  {{< card link="architecture-styles" title="Architecture Styles" icon="template" subtitle="The core styles: what they are, when to use them, and how they map to Azure services" >}}
  {{< card link="scenarios" title="Scenario Playbooks" icon="globe" subtitle="Reference architectures for real-world workloads, organized by business scenario" >}}
  {{< card link="labs" title="Hands-On Labs" icon="beaker" subtitle="Deployable labs with Azure CLI and Bicep — the proof behind every claim" >}}
  {{< card link="career" title="Career Portfolio" icon="academic-cap" subtitle="Turn lab work into LinkedIn experience statements and interview answers" >}}
{{< /cards >}}

## The learning loop

Each topic follows the same loop, modeled on how experienced engineers actually build credibility:

```mermaid
flowchart LR
    A[Learn the style] --> B[Study a scenario]
    B --> C[Run the lab]
    C --> D[Record evidence]
    D --> E[Publish experience]
    E --> A
```

1. **Learn the style** — understand the architecture pattern, its trade-offs, and the Azure services that implement it.
2. **Study a scenario** — see the style applied to a realistic business workload.
3. **Run the lab** — deploy it yourself with the Azure CLI and Bicep in your own subscription.
4. **Record evidence** — capture resource diagrams, costs, and decisions you made.
5. **Publish experience** — convert the work into a concise, verifiable LinkedIn entry.

{{< callout type="info" >}}
All labs are designed to run in a personal subscription at minimal cost, and every lab ends with a teardown step so you never leave billable resources behind.
{{< /callout >}}
