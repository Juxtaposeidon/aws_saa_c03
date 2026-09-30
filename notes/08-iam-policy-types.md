# IAM Policy Types

- **Identity-based policies:** attach to user/group/role. AWS managed policy, inline policy (single user/role), customer managed policy (self-managed).
- **Resource-based policies:** grant permissions to a specified principal; attach to a resource: S3 bucket policy (ACLs are legacy), KMS, Lambda, SQS/SNS and **IAM role trust policy.**
- **IAM role trust policy:** resource-based policy for **cross-account access**. Specify your trusted principal (AWS account/resource, federated IdP); they call `sts:AssumeRole` for temporary credentials.
- **Permissions boundaries:** attach to a **user or role**; set the max permissions identity-based policies can grant an entity. Doesn't grant permissions itself.
- **SCP:** policies for **organizational units/accounts** to restrict users and roles/permissions.
- **AWS Resource Access Manager (RAM):** **cross-account sharing** — centrally share resources (e.g. Transit Gateway) with other AWS accounts/OUs.
- **VPC endpoint policies:** control VPC principals and resources, for gateway and interface endpoints.

**IAM/resource policies:** explicit deny wins. **NACL:** lowest rule number wins.

---

[← Instance & File Storage](07-instance-file-storage.md) · [Contents](../README.md#contents) · [RDS →](09-rds.md)
