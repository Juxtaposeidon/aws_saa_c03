# API Gateway & Step Functions

**API Gateway:** REST API, HTTP API (proxy, JWT, cheap), WebSocket API. Throttles on traffic spikes — **429 Too Many Requests.** 29 sec timeout. *"Offer customers different API request limits per pricing tier"* → **Usage Plans + API Keys (REST).** Accepts/processes 100,000s of concurrent API calls, including traffic management, authorization/access control, monitoring, API version management.

**Step Functions:** helps with API Gateway and Lambda timeouts; coordinates sequenced and **parallel** steps with built-in *retries, error handling, long-running workflows*.

---

[← Lambda & Edge Compute](14-lambda-edge-compute.md) · [Contents](../README.md#contents) · [CloudFront & Global Accelerator →](16-cloudfront-global-accelerator.md)
