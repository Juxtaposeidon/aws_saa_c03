# Monitoring & Auditing

**CloudWatch:** performance/health metrics, logs, alarms (can terminate, stop, reboot, recover an instance). **Container Insights:** monitor EKS and ECS metrics/logs.

- **Custom metrics:** memory, disk space/swap, logs, page file. Use the **CloudWatch agent**. Mnemonic: **DSSM-PLC**
- **Default metrics:** CPU, network, and disk read/write ops. Mnemonic: **RWNDA-CPU**

**CloudTrail** = **API audit.** Free 90-day event history. For longer: **Trail → S3 + log file integrity validation.** **CloudTrail Lake:** SQL querying.

- **Management events:** account/admin-level actions — create/terminate/modify resources.
- **Data events:** data-level actions — S3 **object** ops, Lambda invokes. Disabled by default.
- **Log file integrity validation:** proves CloudTrail log files haven't been modified, deleted or tampered with (SHA-256 digest files).
- **CloudTrail Insights:** detects **unusual API activity** (e.g. sudden spike in TerminateInstances).

**Config:** view and record configuration changes on a timeline. SNS notifications for alerts.

- **Config rules:** audit, evaluate **compliance**; **EventBridge** for notifications on **non-compliance**.
- **SSM remediation:** fix non-compliant resources with **SSM Automation documents**, retries possible. (To *prevent* changes, use SCP/IAM.)

---

[← EventBridge](18-eventbridge.md) · [Contents](../README.md#contents) · [Analytics & Big Data →](20-analytics-big-data.md)
