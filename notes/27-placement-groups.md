# Placement Groups

- Specify the number of instances you need at launch and use 1 instance type, else you might get an insufficient capacity error. Stop and restart the instances if it happens.
- You can't merge placement groups. An instance can only be in 1 placement group at a time.
- **Dedicated Hosts not supported.** Spot Instances configured to **stop or hibernate** on interruption not supported.

| Cluster placement group | Spread placement group | Partition placement group |
| --- | --- | --- |
| Many instances per rack. No rack limit (1 AZ, packed close together) | Many racks (7/AZ), 1 instance each | Many partitions (7/AZ), each with many racks and many instances |
| Lowest latency / HPC / tightly coupled | Few critical instances, isolate failures. SOLO | Hadoop / Cassandra / Kafka at scale. Big distributed systems. Packed |
| No 7-per-AZ cap | 7 instances per AZ | 7 partitions per AZ |

---

[← Compute, Caching & Databases](26-compute-caching-databases.md) · [Contents](../README.md#contents) · [Disaster Recovery Strategies →](28-disaster-recovery-strategies.md)
