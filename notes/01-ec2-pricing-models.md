# EC2 Pricing Models

| EC2 Plan | Requirement | Discount | Commitment |
| --- | --- | --- | --- |
| On-Demand | Short-term workload. Most flexible. **Priciest** | None | < 1 year |
| Reserved Instance | Long-term predictable workload | **72%** | **1 or 3 years** |
| **Convertible** Reserved Instances | Long-term. Flexible to change **EC2** reqts. EC2 only | **66%** | 1 or 3 years |
| Savings Plan | Long-term commitment. Flexibility.<br>**Compute savings**: EC2, Fargate, Lambda<br>**Instance savings**: EC2 only. 1 family, region. Bigger discount than compute | Same as RI | **1 or 3 years.** $/hr |
| Spot | Short workloads. Cheapest, least reliable. Stateless. | **90%** | None |
| Dedicated Host | Dedicated physical server/CPUs. BYOL licensing. | **Costliest** | |
| Dedicated Instance | Dedicated/isolated hardware. No host control or sharing | Cheaper than DH | |
| Capacity Reservation (on-demand) | Guaranteed on-demand capacity in 1 AZ | None | None |
| Zonal RI | Guaranteed reserved capacity in 1 AZ (Standard or Convertible) | Same as Standard/Convertible RI | 1 or 3 years |
| Regional RI | Across AZs in a region, no capacity, just discount | | |

---

[Contents](../README.md#contents) · [S3 Storage Classes →](02-s3-storage-classes.md)
