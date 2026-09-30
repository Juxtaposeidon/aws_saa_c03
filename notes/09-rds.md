# RDS

**RDS** storage auto scales — you set/provision maximum storage. PITR (automated backup retention up to 35 days). Continuous backups. Multi-AZ standby **synchronous** setup for AZ failure/DR. Up to 15 **async** read replicas within AZ, cross-AZ or cross-region. **Encryption can't be enabled after creation** — snapshot, copy with encryption enabled, then restore.

- **Database Activity Streams:** near-real-time audit feature that captures and streams DB activity events outside the database for monitoring and compliance. Destination: **Kinesis Data Streams**.
- **RDS Proxy:** **Lambda + RDS** connection pool that fixes the "**too many DB connections**" / **connection exhaustion** error, allowing connections to scale to 1000s.
- **RDS Custom / EC2:** custom DB configuration and OS-level access. RDS Custom = managed **Oracle / SQL Server** only.
- **Enhanced Monitoring:** granular OS-level data — OS processes, RDS child processes, load average.
- **RDS event subscriptions:** near-real-time event notifications via **SNS (or EventBridge)** on instance start/stop, failovers, backups, config changes, deletion, maintenance events. Invoke **Lambda functions** directly for data-level events.

| RDS Multi-AZ Deployments | RDS Read Replicas (up to 15) |
| --- | --- |
| Synchronous replication – highly durable | Asynchronous replication – highly scalable |
| Only DB on primary instance is active | All read replicas accessible, used for read scaling |
| Automated backups taken from standby | No backups by default |
| **Automatic** failover to standby for DR (flip CNAME) | **Manually** promoted to a standalone DB instance |
| Span two AZs within a single Region | Can be within an AZ, cross-AZ, or cross-Region |
| DB version upgrades happen on primary | DB upgrade independent from source instance |

---

[← IAM Policy Types](08-iam-policy-types.md) · [Contents](../README.md#contents) · [Aurora →](10-aurora.md)
