# Aurora

**Aurora:** live app transactions, OLTP. Autogrows to 128 TB, no provisioning. **3 AZs, 6 copies (2 per AZ), 15 read replicas.** Self-heals. 3–5x faster than RDS.

- **Failover — single instance:** **create a new primary instance** in the same AZ; for AZ failure, create it in a **different** AZ. **Automatic.**
- **Failover — with replicas:** flip the cluster endpoint (its CNAME) to point to a healthy replica. **Promote replica to new primary/writer.** ~30 secs. **Automatic.**

**Aurora Global Database:** secondary **cross-region replication for active-passive failover / DR**. **Manual** failover. 1 primary region (up to 15 read replicas), up to 10 secondary regions (up to 16 read replicas each). RPO ~1 sec, RTO under 1 min. Low latency.

**Aurora Serverless:** autoscales by usage, pay per use. **Unpredictable/spiky/idle/intermittent work**, e.g. dev DB. **Automated backups — 35 days** PITR (same as DynamoDB/RDS). **Manual snapshots — forever.** **1 Aurora Capacity Unit (ACU) ≈ 2 GB memory.**

**Aurora Endpoints:**

- **Writer / cluster endpoint** → **writes** → primary instance. 1 writer.
- **Reader endpoint** → **reads** → up to 15 read replicas. Load balances. 1 reader endpoint per cluster.
- **Instance endpoint** → targets 1 specific DB instance in a cluster.
- **Custom endpoint** → you define and group your own specific set of instances. Load balances.

---

[← RDS](09-rds.md) · [Contents](../README.md#contents) · [DynamoDB →](11-dynamodb.md)
