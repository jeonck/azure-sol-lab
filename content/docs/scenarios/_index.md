---
title: Scenario Playbooks
weight: 3
---

Architecture styles become useful when applied to a **real business scenario**. Each playbook here takes a workload you will actually meet in the field, selects a style (or combination), and walks through the reference architecture, service choices, and trade-offs — the same reasoning you would present in a design review.

## Playbooks

| Scenario | Primary style | What you practice |
|----------|--------------|-------------------|
| [Scalable E-Commerce Platform](ecommerce) | N-tier + Web-Queue-Worker | Session state, checkout queues, SQL scaling |
| [Serverless API Backend](serverless-api) | Serverless | Functions, API Management, Cosmos DB |
| [Microservices on AKS](microservices-aks) | Microservices | AKS, ingress, service-to-service auth |
| [Event-Driven Order Processing](event-driven-orders) | Event-Driven | Event Grid vs Service Bus, idempotency |
| [IoT Telemetry Pipeline](iot-telemetry) | Event-Driven + Big Data | Event Hubs, Stream Analytics, hot/cold paths |
| [Modern Data Analytics Platform](data-analytics) | Big Data | Medallion lakehouse, Fabric/Databricks |
| [Hybrid Networking with Hub-Spoke](hybrid-networking) | N-tier (network foundation) | Hub-spoke, VPN/ExpressRoute, Azure Firewall |
| [Multi-Region High Availability](multi-region-ha) | N-tier + global routing | Front Door, active-passive vs active-active |
| [AI-Powered RAG Application](ai-rag) | Serverless + Event-Driven | Azure OpenAI, AI Search, embedding pipelines |

{{< callout type="info" >}}
Every playbook links to a hands-on lab where you deploy a scaled-down version of the architecture yourself.
{{< /callout >}}
