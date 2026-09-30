# Security Services

**CloudHSM:** dedicated, single-tenant hardware security modules in your VPC. **FIPS 140-2 Level 3** validated (US govt crypto standard). Strict **regulation/compliance.** You manage your keys.

**Control Tower:** **set up/govern a multi-account environment** with governance, compliance, guardrails. **Account Factory:** self-service account creation with pre-approved configs. **Preventive guardrails:** SCPs. **Detective guardrails:** Config rules. Account drift notifications, logging, audit, SSO.

**GuardDuty:** threat detection. Continuously monitors for **malicious/unauthorized activity** with ML. Escalate to **Detective**. Sources: CloudTrail logs, VPC Flow Logs, DNS logs, EKS audit logs, S3 data events.

**Inspector:** vulnerability scans on EC2, container images (ECR), Lambda.

**Macie:** ML-powered **PII / sensitive data discovery** in S3.

**Artifact:** compliance report downloads. **Security Hub:** aggregation dashboard.

**WAF (Web Application Firewall):** protects against common Layer 7 web exploits — XSS, SQL injection, geo-match (block countries), rate-based rules for DDoS.

**Firewall Manager:** centralized WAF, Shield and SG policy management across an Organization.

**Shield:** automatic DDoS protection, Layer 3/4. **Shield Advanced:** paid, AWS DDoS experts, Layer 3–7.

**Secrets Manager:** automatic secret rotation (DB credentials, API keys). **KMS:** key encryption. **Parameter Store:** cheap/free config store.

**KMS envelope encryption / GenerateDataKey:** encrypt a large file with KMS. **Level 2.**

## AWS Certificate Manager (ACM)

**ACM:** create, store, and renew public/private TLS certs. Free auto-renewal. Integrates with ELB/CloudFront/API Gateway. Wildcard certs protect unlimited subdomains. Regional.

**ACM Private CA:** build a public key infrastructure (PKI) inside AWS for private use within an organization (VPN, microservices, laptops, etc.).

- The private key of a **public ACM certificate can't be exported.** If you need the cert outside AWS, use an external CA (e.g. Let's Encrypt) + **IAM certificate store**, or better still:
- **Private CA certs** and their private keys **can be exported** for your PKI outside AWS.
- Certificates for **CloudFront MUST live in us-east-1** (any region works for a regional ALB).
- You can't add/remove domains on an existing certificate — request a **new** cert. Can't delete a certificate in use either.
- To use with EC2, use a load balancer (with the public cert) or export a Private/third-party CA cert.
- TLS/SSL encrypts in-flight data — use **ACM**. **KMS** encrypts data at rest.
- To renew an external/imported certificate, obtain a new cert from your issuer, then manually reimport it into ACM.

---

[← Identity & Directory Services](24-identity-directory-services.md) · [Contents](../README.md#contents) · [Compute, Caching & Databases →](26-compute-caching-databases.md)
