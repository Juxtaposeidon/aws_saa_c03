# SQS / SNS

**SQS:** decouple, buffer, queue. **SNS:** pub/sub messaging/notifications.

- SNS FIFO topics can ONLY fan out to SQS FIFO queues.
- **SNS Standard topic destinations:** Lambda, standard SQS, email/SMS, HTTP endpoints (plus Firehose, mobile push).
- SQS queue retention — 4 days default, increase to 14 days max with the SetQueueAttributes action.
- SQS visibility timeout — 30 seconds default, max 12 hours. If it expires before the consumer processes/deletes the message, the message becomes visible again.
- **SQS FIFO** — 300 msg/sec without batching, 3,000 msg/sec with batching. Standard SQS is near-unlimited.

**S3 event → Standard SNS only. SNS FIFO → SQS FIFO only.**

---

[← S3 Features](12-s3-features.md) · [Contents](../README.md#contents) · [Lambda & Edge Compute →](14-lambda-edge-compute.md)
