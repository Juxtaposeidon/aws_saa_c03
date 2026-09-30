# Load Balancing & Resilience

**NLB:** 1 static IP per AZ, supports static/Elastic IP. PrivateLink support. **Layer 4.** TCP/TLS/UDP ports. Best performance. Helps *whitelist a fixed IP*. **Regional.**

- **Instance ID targets:** NLB always routes to the target's **primary private IP**.
- **IP address targets:** you can route to any IP — primary, secondary, etc.

**ALB:** **Layer 7.** HTTP, HTTPS, gRPC, WebSocket. Routes by path, hostname, header/query string. **Regional** — use Global Accelerator or Route 53 for cross-region.

- **SNI (Server Name Indication):** lets 1 ALB serve/host many HTTPS domains, each with its own **TLS** certificate. Many secure websites can share 1 IP address and port
- **X-Forwarded-For:** use when the *app* needs the client IP behind the ALB
- **Health checks:** instance reachability behind the ALB depends on them. Unhealthy instances are removed from rotation. An **ASG**, if configured with ELB health checks, auto-terminates and replaces them

**GWLB:** **Layer 3.** IP packets (GENEVE). Third-party app firewalls. Intrusion Detection/Prevention Systems.

- **Route 53 (DNS)** survives a REGION dying (DNS failover — minutes, TTL-bound)
- **ELB** survives an INSTANCE dying (in-path, near-instant rerouting)
- **ASG** REPLACES the dead instance (self-healing capacity)

---

[← Networking & VPC](03-networking-vpc.md) · [Contents](../README.md#contents) · [EBS Volume Types →](05-ebs-volume-types.md)
