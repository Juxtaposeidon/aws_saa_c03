# Route 53

- **Public hosted zone:** answers queries from the whole internet.
- **Private hosted zone:** answers queries **only from inside VPCs you attach it to**.
- **Multivalue answer routing:** returns up to **8 healthy IP addresses** for a single DNS query, automatically excludes unhealthy ones, works across regions.
- **Geoproximity routing:** route based on the location of users and resources, with a **bias** to shift more or less traffic to a resource.

**Active-active failover:** when you want all your resources available the majority of the time. All records with the same name/type (A or AAAA) and same routing policy (**weighted or latency**) are active unless Route 53 considers them unhealthy.

**Active-passive failover:** primary resource available most of the time, secondary resource on standby. To configure:

- **1 primary and 1 secondary resource:** use Failover routing policy + health check.
- **Multiple primary and secondary resources:** Failover routing + Weighted routing set to primary. Give each record the same name, type, routing policy.

## DNS Records

- **A:** hostname → IPv4 (literal, fixed IP)
- **AAAA:** hostname → IPv6 (literal, fixed IP)
- **CNAME:** hostname → another hostname (DNS name that has an A/AAAA IP), e.g. ELB DNS, CDN, S3 website endpoint. **Illegal at root/apex.** Queries cost money.
- **Alias:** hostname → another AWS resource's hostname (ALB, CDN, S3 endpoint). CAN exist at the root/apex. Free.
- Alias, A, AAAA can point at the root apex — not CNAME.
- Alias/CNAME can point to changeable DNS (CDN/ALB/S3) — not A/AAAA (fixed IPs; CDN/ALB IPs change).
- **Root domain + AWS = Alias.**

---

[← CloudFront & Global Accelerator](16-cloudfront-global-accelerator.md) · [Contents](../README.md#contents) · [EventBridge →](18-eventbridge.md)
