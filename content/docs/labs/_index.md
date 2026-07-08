---
title: Hands-On Labs
weight: 4
---

These labs are the **proof layer** of this site. Each one deploys a scaled-down but architecturally honest version of a scenario playbook using the Azure CLI and Bicep, verifies it works, and tears everything down.

## Lab catalog

| Lab | Architecture style | Est. time | Est. cost |
|-----|--------------------|-----------|-----------|
| [Lab 1 — N-Tier Web App](lab-01-n-tier) | N-tier | 60 min | < $1 |
| [Lab 2 — Web-Queue-Worker](lab-02-web-queue-worker) | Web-Queue-Worker | 60 min | < $1 |
| [Lab 3 — Serverless API](lab-03-serverless-api) | Serverless | 45 min | < $1 |
| [Lab 4 — Event-Driven Messaging](lab-04-event-driven) | Event-Driven | 60 min | < $1 |
| [Lab 5 — Microservices on AKS](lab-05-aks-microservices) | Microservices | 90 min | ~$2 |
| [Lab 6 — Data Analytics Pipeline](lab-06-data-pipeline) | Big Data | 90 min | ~$2 |
| [Lab 7 — Hub-Spoke Network](lab-07-hub-spoke) | Network foundation | 75 min | ~$2 |
| [Lab 8 — Multi-Region HA](lab-08-multi-region-ha) | Global routing | 90 min | ~$2 |
| [Lab 9 — CI/CD with GitHub Actions OIDC](lab-09-cicd-pipeline) | Delivery pipeline | 60 min | < $1 |

## Ground rules

{{% steps %}}

### Prerequisites

Every lab assumes:

```bash
az --version        # Azure CLI 2.60+
az login            # an active subscription
az bicep version    # Bicep CLI (bundled with az)
```

### One resource group per lab

Each lab creates exactly one resource group, so teardown is always a single command:

```bash
az group delete --name <LAB_RG> --yes --no-wait
```

### Record your evidence

Before teardown, capture what you built — a resource list, a diagram, and the key decision you made. This becomes your [career portfolio](../career) input.

{{% /steps %}}

{{< callout type="error" >}}
Always run the teardown step. Labs use the cheapest viable SKUs, but forgotten resources — especially AKS clusters, firewalls, and gateways — bill by the hour.
{{< /callout >}}
