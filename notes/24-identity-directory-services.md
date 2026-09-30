# Identity & Directory Services

**Cognito User Pools:** **authentication** (sign-up, sign-in, MFA, password reset) for **end users**. Issues ID, access and refresh tokens (JWT). Supports social/federated IdPs, e.g. Google, Facebook and SAML.

**Cognito Identity Pools:** **authorization** — lets end users access AWS services directly. Exchanges a User Pool JWT (or social/SAML identity) for **temporary AWS credentials via STS**.

**IAM Identity Center:** grants an **organization's staff** access to AWS via **SSO**. Centralized workforce identity and access control, **permission sets** for granular access. Supports AD, the default **Identity Center directory**, SAML, third-party/external IdPs (e.g. Okta). Temporary AWS credentials via STS.

**Managed Microsoft AD:** a real, standalone AD **living in AWS** (new directory). Create a **two-way forest trust relationship** to connect it to on-prem AD for on-prem and AWS Identity Center benefits.

**AD Connector:** **proxy** between AWS and **existing on-prem AD.** Forwards auth requests to on-prem AD. Connects WorkSpaces and AWS console sign-in to on-prem AD.

**Simple AD:** lightweight, cheaper, smaller-scale **Samba-based** directory.

**WorkSpaces:** cloud-hosted **virtual desktop (VDI)** service — users access a full Windows or Linux desktop from any device. Pairs with AD.

## Directory scenario triggers

- **On-prem AD ↔ AWS Managed Microsoft AD** → two-way forest trust
- **On-prem AD used directly by AWS services** → AD Connector
- **Users need Windows desktops with Microsoft AD authentication** → WorkSpaces + Managed Microsoft AD
- **Employees need SSO to multiple AWS accounts** → IAM Identity Center
- **Existing on-prem AD, AWS services should use it** → AD Connector

---

[← Application Integration](23-application-integration.md) · [Contents](../README.md#contents) · [Security Services →](25-security-services.md)
