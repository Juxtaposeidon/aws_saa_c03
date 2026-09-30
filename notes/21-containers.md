# Containers

**EKS:** open-source, cloud-agnostic orchestrator. Managed node (EC2) groups, self-managed nodes, Fargate. `aws-auth ConfigMap` maps IAM users/roles to K8s RBAC via AWS IAM Authenticator for K8s.

- **Cluster Autoscaler:** older, cloud-agnostic, works at ASG/node-group level, simple setup, self-managed.
- **Karpenter:** faster, more lightweight/flexible, cheaper, self-managed autoscaler.
- **EKS Auto Mode:** **fully AWS-managed** autoscaling, built on Karpenter.
- **IRSA (IAM Roles for Service Accounts):** fine-grained IAM permissions for individual Pods in an **EKS** cluster, leveraging an OpenID Connect (OIDC) identity provider.

**ECS:** container platform/orchestrator. For IAM: ECS task roles (defined in task definitions). **EC2 + ASG** to scale yourself, **or capacity providers + Managed Scaling** for autoscaling.

| Role / policy | What it controls |
| --- | --- |
| **ECS Task Execution Role** | Permissions ECS needs **before launch** / before app code runs (pull image from ECR, write logs, fetch secrets) |
| **ECS Task Role** | What the container **CAN DO at runtime** |
| **Lambda Execution Role** | What Lambda **CAN DO** when it needs AWS permissions |
| **Lambda Resource-Based Policy** | **WHO can invoke** it — specify the principal (account/service) |

**EC2 launch type:** you provision and maintain instances **with the ECS agent** (runs on EC2), unlike the **Fargate launch type**. Supports GPUs.

**Fargate:** serverless compute engine (EC2 isn't serverless). Just create task definitions. **No GPU.** Works with ECS and EKS.

**ECR:** stores container images, image vulnerability scans.

**ECS/EKS:** orchestrators. **Fargate/EC2:** compute engines (EC2/Fargate launch types).

**ECS Anywhere:** run ECS-managed containers on your own on-prem/non-AWS infrastructure.

**EKS Anywhere:** EKS Distro + AWS support/tooling; run Kubernetes on your own (customer-managed) infrastructure.

**EKS Distro:** the **open-source** Kubernetes software EKS uses underneath, for running K8s yourself anywhere.

**Wavelength:** edge of 5G telecom networks, ultra-low latency.

**Local Zones:** low latency for large population centers; an extension of a single parent region (not multi-region).

---

[← Analytics & Big Data](20-analytics-big-data.md) · [Contents](../README.md#contents) · [Migration & Data Transfer →](22-migration-data-transfer.md)
