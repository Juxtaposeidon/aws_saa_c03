# Operations & Management

**AWS Systems Manager (SSM):** **operate AWS/on-prem infra at scale** without SSH/RDP access.

- **Session Manager:** secure shell access without opening inbound ports or managing SSH keys.
- **Run Command:** execute commands or scripts **remotely, across many instances simultaneously**, without logging into each one.
- **Patch Manager:** automates **OS patching** across an EC2 fleet.
- **State Manager:** ensures **instance state/configuration**; continuously checks and corrects drift.
- **Automation:** custom maintenance workflows, triggerable via **EventBridge**.
- **Inventory:** collects instance metadata (installed applications, OS versions, network configs) for visibility and compliance audits.
- **Fleet Manager:** console to view/manage groups of instances.
- **Parameter Store:** cheap/free config and env store. **SecureString** parameters are encrypted with KMS. No built-in rotation (use Secrets Manager for that).

**AWS Backup:** centralized backups across multiple resources — schedules, retention, etc.

**Batch:** queued batch or scheduled jobs. **ParallelCluster:** traditional HPC cluster management.

**Health Dashboard:** personalized view of AWS service health/issues affecting your account.

**License Manager:** track and manage software licenses (plus BYOL) across AWS resources.

**Service Catalog:** admins curate pre-approved, configured stack **resources** for teams to self-serve.

**Well-Architected Tool:** self-service review tool; checks architecture against AWS's best-practice pillars.

**Managed Grafana:** managed dashboards/visualization for metrics.

**Managed Prometheus:** managed metrics collection/monitoring, Prometheus-compatible.

---

[← Cost Management](30-cost-management.md) · [Contents](../README.md#contents) · [Other Services →](32-other-services.md)
