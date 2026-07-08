---
title: Architecture Styles
weight: 2
---

An **architecture style** is a named family of architectures that share constraints and characteristics. Choosing the right style is the highest-leverage decision in any Azure solution — it determines your scaling model, failure modes, cost profile, and team topology before a single service is picked.

## The core styles

| Style | Best for | Key Azure services |
|-------|----------|--------------------|
| [N-tier](n-tier) | Traditional business apps, lift-and-shift migrations | App Service, Azure SQL, Application Gateway |
| [Web-Queue-Worker](web-queue-worker) | Web apps with background processing | App Service, Storage Queues, Functions |
| [Microservices](microservices) | Large, evolving domains with independent teams | AKS, Container Apps, API Management |
| [Event-Driven](event-driven) | Real-time processing, decoupled producers/consumers | Event Grid, Event Hubs, Service Bus |
| [Big Data](big-data) | Batch and streaming analytics over large datasets | Microsoft Fabric, Databricks, Data Lake |
| [Big Compute](big-compute) | HPC, simulation, large-scale parallel workloads | Azure Batch, HPC VMs |
| [Serverless](serverless) | Spiky traffic, event-triggered logic, minimal ops | Functions, Logic Apps, Cosmos DB |

## How to choose

```mermaid
flowchart TD
    A[New workload] --> B{Independent teams and<br/>bounded contexts?}
    B -- Yes --> C[Microservices]
    B -- No --> D{Event streams or<br/>async integration?}
    D -- Yes --> E[Event-Driven]
    D -- No --> F{Heavy analytics or<br/>ML pipelines?}
    F -- Yes --> G[Big Data]
    F -- No --> H{Massive parallel<br/>computation?}
    H -- Yes --> I[Big Compute]
    H -- No --> J{Background jobs behind<br/>a web front end?}
    J -- Yes --> K[Web-Queue-Worker]
    J -- No --> L{Spiky, event-triggered,<br/>low-ops preference?}
    L -- Yes --> M[Serverless]
    L -- No --> N[N-tier]
```

{{< callout type="warning" >}}
Styles are starting points, not prescriptions. Production systems routinely combine styles — a microservices core with an event-driven integration layer and a serverless edge is common.
{{< /callout >}}
