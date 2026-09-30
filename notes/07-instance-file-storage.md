# Instance & File Storage

**EBS:** **private**, **persistent** personal network drive; persists even after instance termination (**DeleteOnTermination**: root volume default true, extra data volumes default false). Supports live changes — usable while creating a snapshot, while attached, while detached and reattached, changing volume type/size, reads/writes. **1 AZ**, 1 instance except io1/io2 Multi-Attach. Boot volumes/DBs. Provisioned capacity. **Encrypted** snapshots can't be public. KMS (symmetric keys) for access, **KMS + IAM policy** to share.

**EFS:** **shared** EC2 storage — multi-AZ, multi-instance, **Linux**, POSIX, **NFS**, serverless, autoscales, high IOPS. Pricier than EBS.

**Instance Store:** fast but disposable, not persistent. Cache/buffer.

**Data Lifecycle Manager (DLM):** **automates** EBS backups or snapshot creation, retention, deletion on schedule. EBS snapshots are stored in S3.

**FSx for Windows File Server:** managed Windows file server — **SMB, NTFS**, Active Directory integration, Windows file shares.

**FSx for Lustre:** **HPC, Linux + cluster, massively parallel, high-throughput**, sub-millisecond latency, 100s GB/s throughput, works with S3. ML training, video rendering, genomics, financial modeling.

**FSx for NetApp ONTAP:** **multi-protocol support** — **NFS, SMB, block iSCSI**. Most flexible. **Windows, Linux, Mac.** **Storage efficiency:** deduplication, compression, thin provisioning. **SnapMirror:** continuous data replication across regions. On-prem NetApp → AWS migration.

**FSx for OpenZFS:** snapshots, cloning, compression, high IOPS, sub-millisecond latency. Big data analytics, **NAS** migration, media processing.

## Storage Gateway (Hybrid)

**Storage Gateway:** live, **ongoing** hybrid storage that apps write to/store in — not just migration. NFS, SMB (File Gateway), iSCSI (Volume Gateway).

**S3 File Gateway:** **NFS or SMB** file share access to S3 for on-prem applications, with a **local cache** for low-latency access to recent data.

**FSx File Gateway:** low-latency on-prem access to **FSx for Windows** shares with a local cache. **No longer available to new customers since Oct 2024** — may still appear in older exam questions.

**Volume Gateway:** **block storage** via **iSCSI** volumes. Modes:

- **Cached volumes:** primary data lives in S3, frequently accessed data cached on-prem.
- **Stored volumes:** primary data **on-prem**, low-latency local access, **async backup to S3 as EBS snapshots**.

**Tape Gateway:** replaces **physical tape backup infrastructure** with a **virtual tape library (VTL)**.

## Scenario triggers

- **"On-prem + S3 + SMB/NFS + cache/low latency"** → S3 File Gateway
- **"Windows file server + SMB + AD/NTFS + Windows applications"** → FSx for Windows File Server

## Protocol quick map

| Protocol | Services |
| --- | --- |
| SMB / NFS | S3 File Gateway, FSx for ONTAP |
| SMB / NTFS | FSx for Windows File Server |
| NFS only | EFS |
| Block / iSCSI | Volume Gateway, FSx for ONTAP |
| Block (EC2-attached) | EBS |

---

[← EC2 Instance Types](06-ec2-instance-types.md) · [Contents](../README.md#contents) · [IAM Policy Types →](08-iam-policy-types.md)
