# CloudFormation

**CloudFormation:** infrastructure as code. Model, provision and version-control your entire infra in a text file.

- **Change Sets:** **preview** what an update would create/modify/delete *before* you apply it.
- **Drift Detection:** detect manual changes to resources.
- **Stack Policies:** protect specific resources in a stack **from being modified by stack updates**.
- **StackSets:** deploy **one template to MANY accounts and regions** in one operation. *"Roll out a security baseline across the organization."*
- **Nested Stacks:** stacks inside stacks; package common patterns (e.g. a standard VPC) as reusable components.
- **DeletionPolicy:** per-resource instruction on stack deletion — **Retain** or **Snapshot** (RDS, EBS, etc.).
- **Instance Scheduler on AWS:** an AWS Solution deployed via a CloudFormation template — automatically starts/stops EC2 and RDS instances on a schedule to cut costs (up to 70% for non-24/7 workloads).

---

[← Disaster Recovery Strategies](28-disaster-recovery-strategies.md) · [Contents](../README.md#contents) · [Cost Management →](30-cost-management.md)
