# Analytics & Big Data

**Redshift:** managed **petabyte-scale, columnar data warehouse** for **complex analytical queries** across huge datasets. **OLAP**, PostgreSQL-based, Massively Parallel Processing (MPP). Two modes: provisioned cluster and Serverless. 10x performance. SQL. BI tools, e.g. QuickSight or Tableau. Faster than **Athena** (OLAP, S3 query).

- **Leader node:** query planning, results aggregation.
- **Compute node:** performs queries, sends results to leader.

**Redshift Spectrum:** lets Redshift reach **out** to query S3 directly.

**Glue:** batch ETL. Data Catalog. Serverless. Convert data to Parquet/ORC. For static data, e.g. S3.

- **Glue Job Bookmarks:** prevent re-processing old data.
- **Glue DataBrew:** clean and normalize data using pre-built transformations.
- **Glue Studio:** GUI to create, run and monitor ETL jobs in Glue.
- **Glue Streaming ETL:** process continuous data streams in near real time.

**EMR:** big-data processing/analytics/migration for Hadoop/Spark/Hive clusters, ML, BI. Serverless option available. Used with On-Demand, Reserved, Spot.

- **Master node:** delegates and monitors.
- **Core node:** stores data and processes tasks.
- **Task node:** optional extra processing — use **Spot**.

**Lake Formation:** automates/simplifies **setting up a centralized organization data lake** for analytics and ML. **Granular** permissions. Built on top of Glue. Cleanse, transform, ingest data. S3, RDS, NoSQL.

**Kinesis:** big data streaming/analytics (**ETL**). Log/clickstream analytics, live dashboards/leaderboards, metric generation and reporting, sensor data, IoT, ad tech. Enhanced fan-out.

**Kinesis Data Streams:** big data ingestion/storage (up to 1 year; 24 hrs default). MULTIPLE consumers read the SAME data. Can replay/reprocess. Data ordered in shards, sequenced. Provisioned or On-Demand (pay per use). Can't delete stream data. Metrics and reporting. Real-time. **Kinesis Producer Library (KPL):** continuous writes. **Kinesis Client Library (KCL):** read/query, ordered distributed processing.

**Kinesis Data Firehose:** **loads** stream data into data lakes/storage/analytics, e.g. S3, Redshift, OpenSearch, custom HTTP endpoint. **Basic transform** with Lambda, e.g. convert JSON/CSV to Parquet/ORC. Auto scaling, serverless, pay per use. Managed/no code. Near real time — 60 sec buffer, unlike KDS milliseconds.

**Kinesis Data Analytics / Managed Service for Apache Flink:** real-time **ETL** processing/SQL on a **live stream**.

**Kinesis Video Streams:** ingest and process real-time video streams.

## Quick picks

- **ETL:** Glue (batch), KDA (real-time), Firehose (light transform + load only)
- **Data analytics:** KDA, Redshift, EMR
- **S3 query:** Redshift Spectrum, Athena
- **Storage:** Redshift (OLAP), Lake Formation (centralized, granular), KDS (real-time streams, ordered)

| Service | Role |
| --- | --- |
| S3 | Data lake (raw storage) |
| Redshift | OLAP data warehouse (analytics + storage) |
| Redshift Spectrum | Query S3 from Redshift |
| Athena | Serverless query engine for S3 |
| Glue | **Batch ETL**, prepares data for S3/Redshift, includes Data Catalog |
| Kinesis Data Streams | Temporary live streaming ingestion pipe |
| Kinesis Data Analytics | **Real-time** ETL processing/SQL on the stream |
| Kinesis Firehose | Delivers stream data to S3/Redshift/etc. (with optional light transform) |
| Lake Formation | Centralized governance/security ON TOP of an S3 data lake, granular access control, simplified lake setup |
| EMR | Big data analysis — Hive, Spark, Hadoop |

|  | Kinesis Data Streams | DynamoDB Streams |
| --- | --- | --- |
| Consumers / retention | Many consumers. 1 year max, 24 hrs default | Limited consumers. 24 hours |
| Process with | Lambda, Kinesis Data Analytics, Data Firehose, Glue Streaming ETL | Lambda, DynamoDB Streams Kinesis Adapter |

---

[← Monitoring & Auditing](19-monitoring-auditing.md) · [Contents](../README.md#contents) · [Containers →](21-containers.md)
