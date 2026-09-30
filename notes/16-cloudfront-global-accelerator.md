# CloudFront & Global Accelerator

**CloudFront:** CDN. **Caches** content at the edge — **static assets** (images, videos, JS/CSS, downloadable files, API responses) and **cacheable dynamic content**. Layer 7 (HTTP/HTTPS). **Signed URL: access ONE file. Signed Cookies: MANY files.** Brings CONTENT closer (at the edge).

- **Origin failover:** auto-switch from primary to secondary in **origin groups** on failure.
- **Origin Access Control:** makes the S3 bucket private and grants CloudFront alone the right to read it.

**Global Accelerator:** routes traffic to the closest edge location via Anycast — 2 static anycast IPs (fixed IPs for whitelisting). Makes the JOURNEY/traffic faster. **TCP/UDP**, Layer 4 (gaming, IoT, VoIP). Dynamic/real-time. No caching. Instant failover.

- **CloudFront** → global DOWNLOAD/view of content (HTTP)
- **Global Accelerator** → global TCP/UDP apps
- **S3 Transfer Acceleration** → global UPLOAD to S3 via CloudFront edge

---

[← API Gateway & Step Functions](15-api-gateway-step-functions.md) · [Contents](../README.md#contents) · [Route 53 →](17-route-53.md)
