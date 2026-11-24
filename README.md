# azure-aks-inventory-order-processing
An 8-week Azure and AKS inventory and order processing prototype

# Azure AKS Inventory & Order Processing Challenge

An eight-week engineering challenge to design and build a prototype for inventory updates and order processing in a fictional large-scale retail scenario.

**This is a working prototype, not a production-ready system.** All project data will be synthetic.

## The challenge

Stores, warehouses, and online shops send inventory updates that can arrive late or more than once. When multiple customers try to order the last available item at the same time, the system must prevent overselling and keep stock records accurate.

This project explores how to handle those challenges through architecture design, implementation, and failure testing on Azure.

## Project goals

- Design an event-processing flow that handles duplicate, delayed, and failed messages.
- Compare optimistic and pessimistic concurrency approaches for stock reservations in Azure SQL.
- Provision Azure infrastructure with Terraform.
- Scale event consumers based on backlog and application services based on resource usage.
- Monitor service health, processing delays, errors, and stock exceptions.
- Test how the prototype responds to and recovers from failures.
- Document design choices, test results, and estimated Azure costs.

## Planned architecture

The prototype is planned to use:

- **Azure Kubernetes Service (AKS)** to run application services and event consumers.
- **Azure Event Hubs** to receive inventory and order events.
- **Azure SQL** to store inventory and reservation data.
- **Azure Container Registry (ACR)** to store container images.
- **KEDA** to scale event consumers based on Event Hubs backlog.
- **HPA** to scale application services based on resource usage.
- **Azure Monitor, Managed Prometheus, and Grafana** for observability.
- **Key Vault, Workload Identity, OIDC, RBAC, and NetworkPolicy** for security.

Architecture decisions will be documented as Architecture Decision Records (ADRs).

## Infrastructure and CI/CD

Terraform will define the Azure network, AKS, and ACR.

GitHub Actions is planned to run checks and create Terraform plans for pull requests. Infrastructure changes will be applied only after approval.

## Failure testing and AI-assisted review

The prototype will simulate delayed and duplicate events, repeated message failures, and service interruptions.

An AI-assisted feature will summarize stock exceptions, suggest possible causes, and recommend investigation steps. Operational decisions will remain with the operations team.

## Eight-week plan

The plan will be refined as the project progresses.

1. Define requirements, architecture, and initial ADRs.
2. Create the application and event-processing prototype.
3. Implement inventory updates and order reservations.
4. Compare concurrency approaches in Azure SQL.
5. Provision Azure infrastructure with Terraform.
6. Add CI checks, identity, access controls, and network policies.
7. Add scaling, monitoring, and failure simulations.
8. Review results, document costs, and publish findings.

## Repository contents

This repository will include source code, Terraform configuration, architecture diagrams, ADRs, test results, and project notes as they are created.

## Progress updates

Progress updates are planned for every Wednesday and will cover completed work, challenges, decisions, and next steps.

## Data and security

All project data is synthetic. Do not commit passwords, access tokens, private keys, or other secrets to this repository.

## Status

**In progress.** Planned components and technologies may change as the project develops.
