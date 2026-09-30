# Compute, Caching & Databases

**Elastic Fabric Adapter (EFA):** **network interface** for EC2 apps with high levels of inter-node communication at scale; accelerates HPC/ML workloads (performance, latency, bandwidth). Essentially an **ENA (higher PPS) with OS bypass** — communicates directly with the network interface. OS bypass is Linux only, not Windows.

**Elastic Beanstalk:** PaaS. Deploy/upload code; AWS auto-handles provisioning, load balancing, scaling, but you retain control over the resources. Stores logs in S3, CloudWatch.

**ElastiCache Redis:** data durability. HA (Multi-AZ, read replicas). **Sorted sets** for real-time gaming leaderboards.

**ElastiCache Memcached:** simple, multithreaded, non-persistent. Multi-node partitioning/sharding. Auto Discovery identifies cluster nodes.

**Neptune:** managed graph DB (relationships between entities, e.g. social networks). **Neptune Streams:** real-time ordered sequence of changes. HTTP REST API.

**DocumentDB:** managed, MongoDB-compatible document database.

**Keyspaces:** managed, Cassandra-compatible wide-column NoSQL database.

---

[← Security Services](25-security-services.md) · [Contents](../README.md#contents) · [Placement Groups →](27-placement-groups.md)
