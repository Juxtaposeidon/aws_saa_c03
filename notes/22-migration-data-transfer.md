# Migration & Data Transfer

**DataSync:** **accelerated** bulk **data/file migration** or transfer from on-prem to AWS. **One-time or scheduled.** Fast, replaces manual scripts. Needs good internet (or Direct Connect). Needs the **DataSync agent unless it's AWS-to-AWS**. Moves between S3 ↔ EFS ↔ FSx ↔ **NFS** ↔ **SMB** shares.

**Database Migration Service (DMS):** migrate databases to AWS with **near-zero downtime**, with the **Schema Conversion Tool**. **Continuous** data replication (**Change Data Capture**) — ongoing streaming. Sources/targets include SQL/NoSQL, S3, Redshift, Redis, Kafka. Supports heterogeneous migration.

**AWS Transfer Family:** managed **SFTP/FTPS/FTP** server/endpoint for file transfers in/out of **S3/EFS**.

**Data Transfer Terminal:** physical facility where you bring your storage devices to quickly transfer data in minutes. No network **bandwidth** needed.

**Snow Family:**

- **Snowcone:** fast, tiny.
- **Snowball Edge Compute Optimized:** edge processing, limited bandwidth.
- **Snowball Edge Storage Optimized:** 50–500 TB.
- **Snowmobile:** 10–100 PB shipping-container truck.
- Snowball **can't write directly to Glacier** — land in S3, then use a lifecycle policy.

**Application Migration Service (MGN) / AWS Transform:** **lift-and-shift.** Migrate hundreds of physical/virtual **servers** to EC2 with **minimal downtime**, continuous automated block-level replication. 90 days free.

**Elastic Disaster Recovery:** MGN's twin (continuous automated block-level replication) but for **disaster recovery**. **Cheap DR** *for physical/virtual/cloud servers.* RPO: seconds. RTO: 5–20 mins.

**Application Discovery Service:** plan cloud migration by collecting usage and configuration data about on-prem servers. **Migration Hub:** aggregates migration info for visibility.

**Quick picks:** Minimal downtime → DMS, MGN. Low bandwidth → Data Transfer Terminal, Snowball.

---

[← Containers](21-containers.md) · [Contents](../README.md#contents) · [Application Integration →](23-application-integration.md)
