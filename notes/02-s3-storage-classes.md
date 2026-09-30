# S3 Storage Classes

| S3 Class | Retrieval | Min storage duration | Use when | Cost |
| --- | --- | --- | --- | --- |
| **Standard** | Millisec / instant | None | Frequently accessed, hot data | $0.023 — costliest |
| **Intelligent-Tiering** | Millisec | None | **Unknown/unpredictable** access patterns | $0.0025–0.023 — 2nd costliest |
| **Standard-IA** | Millisec | **30 days** | Infrequent access, needs instant retrieval | $0.0125 — 3rd costliest |
| **One Zone-IA** | Millisec | 30 days | **Recreatable**, infrequent access. 1 AZ only | $0.01 — 4th costliest |
| **Glacier Instant Retrieval** | **Millisec** | **90 days** | Archive touched ~quarterly, needed instantly | $0.004 |
| **Glacier Flexible Retrieval** | Expedited **1–5 min**<br>Standard **3–5 hr**<br>Bulk **5–12 hr** | 90 days | Archive, minutes–hours retrieval OK | $0.0036 |
| **Glacier Deep Archive** | Standard **12 hr**<br>Bulk **48 hr** | **180 days** | Cheapest. Retrieval is **12 hr min!** | $0.00099 — cheapest |

**Provisioned retrieval capacity:** purchase it for highly reliable Glacier expedited retrieval under any circumstance. Each unit gives 3 expedited retrievals every 5 minutes and up to 150 MB/s throughput.

---

[← EC2 Pricing Models](01-ec2-pricing-models.md) · [Contents](../README.md#contents) · [Networking & VPC →](03-networking-vpc.md)
