# AWS Solutions Architect Associate (SAA-C03) — Study Notes

Condensed, exam-focused notes for the **AWS Certified Solutions Architect – Associate (SAA-C03)** exam, covering compute, storage, networking, databases, integration, security, analytics, migration, cost and disaster recovery.

Written while preparing for the exam and **fact-checked against AWS documentation**.

## Why these notes

- **Confusable pairs side by side.** Security Groups vs NACL, Multi-AZ vs read replicas, SSE-S3 vs SSE-KMS vs SSE-C, CloudFront vs Global Accelerator, Cognito User Pools vs Identity Pools.
- **Caveats that cost real points.** Limitations and gotchas the exam loves to test.
- **Exam triggers.** Scenario phrases mapped straight to the service that answers them ("On-prem + S3 + SMB/NFS + cache" → S3 File Gateway).
- **Current limits, not stale ones.** Where AWS has recently raised a limit, the notes give the current figure *and* the older one.

## Disclaimer

These aren't foundational. To understand the concepts, you'll need a full course that covers the fundamentals, plus hands-on labs. These are cheat sheets with the most important details and triggers for the exam.

## How to use

- **Browse by topic** using the contents below. Every page links to the previous/next topic.
- **Prefer one document?** [Download the full PDF](https://github.com/kennielima/aws_saa_c03/blob/main/pdf/AWS_SAA_Study_Notes.pdf) 📄or [view on Google Docs](https://docs.google.com/document/d/15-K-u6Yxu5JlswaSEd3mkbqK2KCZPsZGCOEKbND60_c/edit?usp=sharing) 📝
- **Review strategy:** pair these notes with timed practice exams. Notes build recall; practice questions build the pattern recognition the scenario-based exam actually tests.

## Contents

### Compute

- [EC2 Pricing Models](notes/01-ec2-pricing-models.md)
- [EC2 Instance Types](notes/06-ec2-instance-types.md)
- [Placement Groups](notes/27-placement-groups.md)
- [Lambda & Edge Compute](notes/14-lambda-edge-compute.md)
- [Containers](notes/21-containers.md)
- [Compute, Caching & Databases](notes/26-compute-caching-databases.md)

### Storage

- [S3 Storage Classes](notes/02-s3-storage-classes.md)
- [S3 Features](notes/12-s3-features.md)
- [EBS Volume Types](notes/05-ebs-volume-types.md)
- [Instance & File Storage](notes/07-instance-file-storage.md)

### Networking & Content Delivery

- [Networking & VPC](notes/03-networking-vpc.md)
- [Load Balancing & Resilience](notes/04-load-balancing-resilience.md)
- [CloudFront & Global Accelerator](notes/16-cloudfront-global-accelerator.md)
- [Route 53](notes/17-route-53.md)

### Databases

- [RDS](notes/09-rds.md)
- [Aurora](notes/10-aurora.md)
- [DynamoDB](notes/11-dynamodb.md)

### Integration & Messaging

- [SQS / SNS](notes/13-sqs-sns.md)
- [API Gateway & Step Functions](notes/15-api-gateway-step-functions.md)
- [EventBridge](notes/18-eventbridge.md)
- [Application Integration](notes/23-application-integration.md)

### Security, Identity & Compliance

- [IAM Policy Types](notes/08-iam-policy-types.md)
- [Identity & Directory Services](notes/24-identity-directory-services.md)
- [Security Services](notes/25-security-services.md)

### Analytics

- [Analytics & Big Data](notes/20-analytics-big-data.md)

### Management, Monitoring & Cost

- [Monitoring & Auditing](notes/19-monitoring-auditing.md)
- [CloudFormation](notes/29-cloudformation.md)
- [Cost Management](notes/30-cost-management.md)
- [Operations & Management](notes/31-operations-management.md)
- [Other Services](notes/32-other-services.md)

### Migration & Resilience

- [Migration & Data Transfer](notes/22-migration-data-transfer.md)
- [Disaster Recovery Strategies](notes/28-disaster-recovery-strategies.md)

### Quick Reference

- [CIDR Cheat Sheet](notes/33-cidr-cheat-sheet.md)
- [Common Ports](notes/34-common-ports.md)
- [ARN Format](notes/35-arn-format.md)

## Exam at a glance

| Domain | Weight |
| --- | --- |
| Design Secure Architectures | 30% |
| Design Resilient Architectures | 26% |
| Design High-Performing Architectures | 24% |
| Design Cost-Optimized Architectures | 20% |

65 questions · 130 minutes · passing score 720/1000.

## Contributing

Spotted an error or an outdated limit? Open an issue or a pull request, ideally with a link to the AWS docs page.

## License

Notes are shared under [CC BY 4.0](LICENSE): free to share and adapt with credit.

*Not affiliated with or endorsed by Amazon Web Services.*
