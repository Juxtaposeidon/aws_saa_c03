# Networking & VPC

**VPC:** allows you to choose your IP address range, create subnets, configure route tables, network gateways, securely connect AWS to on-premises.

**VPC Flow Logs:** for internal traffic, IP address.

## On-prem ↔ VPC connections

**Site-to-Site VPN:** **encrypted** on-prem ↔ AWS **over internet, IPsec, fast to set up (hours), cheap.** Can be used as a failover for dedicated Direct Connect links: **DX + VPN failover**.

- **Customer Gateway (CGW):** your **on-prem** router in the VPN connection
- **Virtual Private Gateway (VGW):** AWS-side VPN endpoint, attached to 1 VPC. **IPv4 only** for Site-to-Site VPN traffic (IPv6 VPN needs a Transit Gateway)
- **VPN tunnel** runs in the middle. **2 tunnels per VPN connection** for redundancy (typically 1 carries traffic, 1 is failover)
- **Transit Gateway:** equal-cost multi-path (**ECMP**) routing, many VPCs over many VPN tunnels

**Direct Connect (DX):** on-prem ↔ AWS on a **private + dedicated** connection via **VIF**. Weeks–months setup, for consistent bandwidth/performance, large regular data. Not encrypted by default.

**Virtual Interfaces:** how you connect on-prem ↔ AWS and sort traffic on Direct Connect.

- **Private VIF:** on-prem → **1 VPC** via **Virtual Private Gateway**
- **Public VIF:** connects to **AWS services**, e.g. S3
- **Transit VIF:** on-prem → **many VPCs** via **Transit Gateway**. TGW supports **ECMP** routing over many VPN tunnels

**VPN CloudHub:** communicate with multiple sites over the internet using VPN, with/without VPC.

## VPC ↔ VPC connections

**VPC Peering:** 1-to-1 VPC peering, connect 2–3 VPCs, full network access. Not transitive. **No CIDR overlap. Cheap.**

**Transit Gateway:** **many VPCs + VPN. On-prem to many VPCs** (Site-to-Site, Direct Connect). Transitive routing. Supports IP multicast (1-to-many) and many-to-many via **ECMP**.

**PrivateLink:** privately connect VPC to 1 **specific service** (AWS service, VPC-exposed service, SaaS partner's service). No network merge, **CIDRs can overlap.**

## Internet access

**NAT Gateway:** sits in a **public subnet/IP.** Lets resources in a private subnet (via its route table) connect to the internet through the internet gateway. 1 NAT per AZ. Internet can't initiate on its own — outbound only.

`Private subnet (route table) → NAT GW (public subnet) → Internet Gateway → INTERNET → IGW → NAT GW → Private subnet`

**Public subnet in a non-default VPC:** no automatic IP is assigned. To access the internet → associate an Elastic/public IP + configure the route table + attach an IGW.

**Egress-only IGW:** outbound-only, IPv6 NAT equivalent.

## VPC Endpoints

**VPC Endpoint:** **private access** to reach AWS services or PrivateLink.

- **Gateway Endpoint:** **route-table entry.** VPC connects to **S3, DynamoDB.** Free.
- **Interface Endpoint:** creates an **ENI** with a **private IP** in the subnet. For PrivateLink and other AWS services. **Reachable** over peering/Transit Gateway/VPN. Pay per hr/GB.

## Security Groups vs NACLs

| Firewall / traffic control | SG | NACL |
| --- | --- | --- |
| Rules | **Allow only**, default deny | Allow and deny |
| Scope | **EC2** network interface firewall | **Subnet** firewall |
| State | Stateful | Stateless |
| Inbound traffic | Default deny | **Custom NACL:** default deny<br>**Default NACL** (auto-created with VPC): default allow |
| Outbound traffic | Default allow | **Custom NACL:** default deny<br>**Default NACL:** default allow |

**Inbound access rules:** `/32` CIDR = 1 IP. `/0` = all IPs.

**Bastion Host:** EC2 sitting in a **public subnet / Elastic IP for SSH/RDP** access (define this in SG) to private EC2 from the internet. Also called a **jump box**.

**Session Manager:** newer way to access private instances **without SSH keys or an open inbound port 22**, minimal operational overhead — just use the **SSM agent**.

**ENI:** virtual network card in a VPC you can attach to a new instance on failover within 1 AZ. **1 AZ**, unlike Elastic IP. Used for Lambda networking into VPCs. **Dual-homing:** attach multiple network interfaces to 1 instance. Components: private/secondary/public IPv4, Elastic IP, SG, MAC address.

**Service Quotas for ENI/IP** are important, esp. with Lambda. If the ENI quota limit is reached, it may fail to scale and cause errors. If Lambda can't provision the ENIs/IPs it needs: **EC2ThrottledException**.

**Network Firewall:** **managed firewall for the whole VPC**, **Layers 3–7.** Intrusion detection/prevention, domain filtering, traffic inspection/filtering, stateful rules.

---

[← S3 Storage Classes](02-s3-storage-classes.md) · [Contents](../README.md#contents) · [Load Balancing & Resilience →](04-load-balancing-resilience.md)
