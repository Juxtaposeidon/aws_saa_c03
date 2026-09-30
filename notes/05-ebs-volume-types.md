# EBS Volume Types

**SSD** = random small, frequent I/O operations. Boot volumes. IOPS.

- **gp3** — **General purpose.** Good price/performance, cheap. Baseline **3,000 IOPS / 125 MiB/s** at any size; scales to **80,000 IOPS / 2,000 MiB/s, 64 TiB** (previously 16K IOPS — older exam material may still say 16K). IOPS independent of size. **gp2** is the older version (IOPS tied to size, 3 IOPS/GB).
- **io1 / io2** — Critical business apps, Provisioned IOPS, sustained IOPS performance. **io1:** up to **64,000 IOPS**, 50 IOPS/GB — for I/O-intensive workloads. **io2 Block Express** (all io2 volumes are Block Express since April 2025): up to **256,000 IOPS, 4,000 MB/s, 64 TiB, 1,000 IOPS/GB**, sub-millisecond latency, 99.999% durability — highest performance, lowest latency, same price as io1. **Multi-Attach:** up to 16 Nitro instances in 1 AZ can attach the same volume.

**HDD** = can't be boot volumes.

- **st1:** Throughput Optimized. Frequent access. Big, sequential data. Log processing. Cheap.
- **sc1:** Cold archive. Infrequent access. Cheapest.
- **Magnetic volumes:** even cheaper, for infrequent access. Legacy.

| Category | Types | Boot volume? |
| --- | --- | --- |
| SSD | gp2, gp3, io1, io2 | Yes |
| HDD | st1, sc1, Magnetic (legacy) | No |

---

[← Load Balancing & Resilience](04-load-balancing-resilience.md) · [Contents](../README.md#contents) · [EC2 Instance Types →](06-ec2-instance-types.md)
