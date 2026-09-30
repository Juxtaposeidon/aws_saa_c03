# S3 Features

**S3:** objects up to **50 TB** (via multipart upload). **Single PUT 5 GB max. Single GET 5 TB max** — use concurrent/byte-range GETs for bigger objects. Data is assigned an object key used for retrieval. Strong read-after-write consistency.

- **S3 Transfer Acceleration** → global UPLOAD speedup to 1 S3 bucket. Routes upload via CloudFront edge to reduce distance/latency.
- **Multi-Region Access Points:** single unified global endpoint for closest / lowest-latency bucket routing based on requester location.
- **S3 Access Points:** **dedicated access policy** per team, optional **VPC restriction**.
- **S3 Cross-Region Replication:** only replicates new objects by default. **Enable versioning** first. For compliance, DR, low latency. Near real time.
- **S3 Batch Replication:** replicates existing objects.
- **S3 Lifecycle rules:** expiration actions, transition actions. Can delete or move after a period.
- **Object Lock:** WORM — prevents overwrite and delete. Requires **versioning**. **Compliance mode:** nobody can overwrite/delete, not even root. **Governance mode:** admins with special permission can. **Legal hold:** nobody, indefinitely, until lifted — **no retention period**.
- **Multipart upload** → split a large upload into chunks. Recommended if data > 100 MB.
- **Byte-range fetch** → download part of an object, e.g. header/footer of a huge file.
- **S3 Bucket Key:** fixes heavy traffic hitting **KMS API request limits**, cutting **KMS API costs by up to 99%.** Trade-off: coarser per-object audit trail in CloudTrail.
- **Directory bucket:** stores objects in S3 Express One Zone. For low latency.
- **Table bucket:** Apache Iceberg format. For ML analytics, tabular data. Athena, Redshift, Spark.
- **S3 Batch Operations:** perform bulk operations on existing S3 objects with a single request.

## S3 encryption

| Option | Who manages the key | Notes |
| --- | --- | --- |
| **SSE-S3** | S3/AWS auto-manages keys and rotation | **AES-256**. Default for new objects. Simplest |
| **SSE-KMS** (header `aws:kms`) | KMS-managed | Key usage **audit logs in CloudTrail**, access control via key policy |
| **SSE-KMS — AWS managed key** | KMS auto-manages the key, **rotates yearly** | No control over rotation or key policy |
| **SSE-KMS — customer managed key** | You create/manage the key in KMS | You choose whether to enable rotation, control key policy, can disable/delete |
| **SSE-C** (customer-provided keys) | **You** supply the key with every request; S3 encrypts/decrypts, **AWS never stores the key** | HTTPS required. You handle rotation |
| **Client-side encryption** | You encrypt **before upload**, you manage keys and rotation | AWS never sees plaintext |

## S3 caveats

- S3 CRR/SRR only replicate new objects by default; to replicate existing objects, use **S3 Batch Replication**.
- **Versioning must be enabled** for Cross-Region Replication and Object Lock.
- S3 event notification has **one destination per event rule**, so apply SNS fan-out to multiple SQS queues/other services.
- S3 event notification destinations accept Standard SNS, never SNS/SQS FIFO. Free.
- Event notifications only fire on new events, not for existing objects.
- **Supported event destinations: SNS, SQS, Lambda, EventBridge.**

---

[← DynamoDB](11-dynamodb.md) · [Contents](../README.md#contents) · [SQS / SNS →](13-sqs-sns.md)
