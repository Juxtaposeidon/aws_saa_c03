# DynamoDB

**DynamoDB Streams:** CRUD modifications. Real-time, async. 24 hrs retention. Uses Lambda triggers or the DynamoDB Streams Kinesis Adapter.

**DynamoDB Global Tables:** **multi-region active-active** DR. Apps can READ/WRITE to the tables in any region simultaneously, all active, low latency. DynamoDB Streams must be enabled.

**DynamoDB Auto Scaling:** dynamically adjusts provisioned throughput capacity (including GSIs' RCU/WCU) to handle sudden increases in traffic without throttling.

**Adaptive Capacity:** DynamoDB auto-shifts throughput capacity when partitions aren't evenly distributed.

**DynamoDB Accelerator (DAX):** in-memory cache. **Microsecond** reads, API-compatible, zero code change.

**GSI:** different partition + sort key, create anytime, deletable. Independent provisioned capacity (RCUs/WCUs).

**LSI:** same partition key / different sort key, table creation time only, can't delete, shares base table RCU/WCU. Never use for unknown data size / unpredictable growth — 10 GB item collection limit. Can't add for a new query pattern in prod. Strongly consistent reads.

---

[← Aurora](10-aurora.md) · [Contents](../README.md#contents) · [S3 Features →](12-s3-features.md)
