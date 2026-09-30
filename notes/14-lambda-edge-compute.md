# Lambda & Edge Compute

**Lambda:** 15 min max execution time. Default concurrency limit of 1,000 — request a quota increase or configure concurrency to scale and prevent **throttling**. Scales within seconds, unlike ASG minutes. Pay per use, no expensive overprovisioning. Ephemeral storage 512 MB default, up to 10 GB. **Deployment package limit: 50 MB zipped, 250 MB unzipped** — use **container images** for larger (up to 10 GB).

- **Synchronous:** directly trigger Lambda → API Gateway/ALB waits for response. Real-time processing.
- **Asynchronous invocation:** Lambda responds to events pushed to it, queues them and **retries (2x max)** on failure, then sends to a **Dead Letter Queue/destination**. Invoked by **S3 event notifications, SNS, EventBridge**.
- **Event source mappings (polling):** Lambda reads items from other streams/queues — DynamoDB, SQS, Kinesis, Kafka, MQ, MSK.
- **Provisioned Concurrency:** pre-warmed. Fixes cold-start latency, milliseconds. **You pay for it always**, even when idle.
- **SnapStart:** cached snapshot. Fixes cold-start latency at no extra cost. Java (also Python and .NET).
- **Reserved Concurrency:** sets a cap to limit concurrency and prevent overwhelming downstream systems; also guarantees capacity for the function. No extra charge.
- **Lambda authorizer:** custom Lambda function that checks whether an API Gateway request is authorized.

**CloudFront Functions:** JavaScript, lightweight. Must execute in milliseconds; cheaper and faster than Lambda@Edge. Higher scale per second. Viewer Request and Viewer Response only. 10 KB size.

- **Viewer Request:** modify headers/cookies, normalize cache keys, query strings, URL redirects/rewrites, auth checks, generate HTTP responses.
- **Viewer Response:** insert security headers, modify response codes.

**Lambda@Edge:** Viewer Request/Response **and** Origin Request/Response. Runs Lambda code/capabilities at CloudFront edge. Node.js/Python. Higher latency, 5–10 secs execution time. < 10 MB size. Can access network, filesystem. Can modify HTTP request/response body. For adjustable CPU/memory, third-party libraries, AWS SDK.

---

[← SQS / SNS](13-sqs-sns.md) · [Contents](../README.md#contents) · [API Gateway & Step Functions →](15-api-gateway-step-functions.md)
