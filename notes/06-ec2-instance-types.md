# EC2 Instance Types

- **Storage optimized (I, D):** high, sequential read/write access to big data. Low-latency, high random IOPS. OLTP systems, SQL/NoSQL on local disk, data warehouses, distributed systems.
- **Compute optimized (C):** high **C**PU. Batch processing, media transcoding, HPC, ML, game servers, scientific modeling.
- **Memory optimized (R, X):** **R**AM. In-memory cache, real-time big data analytics. **X** — extreme RAM, large scale, SAP HANA. SQL/NoSQL DBs, BI.
- **General purpose (M, T):** balanced CPU/memory/network. **T** — spiky, idle, burstable. **M** — general, fixed performance.
- **Accelerated computing (G, P, Inf):** **G** — GPU graphics. **P** — power graphics, ML training. **Inf** — ML inference (AWS Inferentia chips).

**Amazon Machine Image (AMI):** customization (OS, software, config) of EC2. The image EC2 uses to spin up a new instance.

**Launch template:** the template an ASG uses to launch EC2. You specify instance info, e.g. AMI ID, instance type, key pair, SGs, block device mapping. Supports mixed groups of spot and on-demand instances. Templates can be versioned.

**Launch config:** Older, legacy version of launch template. Can't be modified — create a new version instead. Contains only one type of EC2 instance. May appear in older test material. 

**Nitro:** newer EC2 hypervisor/hardware platform — higher performance and throughput ceilings, especially relevant to EBS IOPS limits (e.g. io2 Block Express 256K, io1 64K need Nitro).

---

[← EBS Volume Types](05-ebs-volume-types.md) · [Contents](../README.md#contents) · [Instance & File Storage →](07-instance-file-storage.md)
