# Wide-Column vs Columnar Databases

## Objective
This repository documents a comparative study between **Wide-Column** and **Columnar** database models, focusing on:
- Architecture
- Workload patterns
- Query models
- Typical use cases
- Trade-offs and limitations

## Database model Comparison Table

| Dimension | Wide-Column | Columnar-Oriented |
|---------|------------|-------------------|
| **Workload** | OLTP | OLAP |
| **Model** | Generally classified as NoSQL | Generally exposes a SQL interface |
| **Focus** | Write performance | Read performance and analytics |
| **Schema** | Flexible | Fixed |
| **Data organization** | Row-oriented access (with many columns) | Column-oriented access (with many rows) |
| **Aggregations** | Weak / limited | Extremely efficient |
| **Data compression** | Basic | Excellent |
| **Ad-hoc queries** | Limited | Strong |

## Database Models Overview

### Wide-Column Databases

**What is it?​**
- Stores data in column families, where each row can have a different set of columns.​
- Columns are not fixed, allowing each row to contain different columns.​
- A single row can have hundreds or even thousands of columns.​
- Typically part of the NoSQL data model.​
- Query-oriented data modeling.

**What is it used for?​**
- OLTP workloads​
- Row-oriented writes (low latency)​
- Large volume of data​
- Semi-structured data​
- Key-based optimized reads (partition key / row-oriented access)​

**Examples:**
- Apache Cassandra​
- ScyllaDB​
- Azure Cosmos DB for Apache Cassandra​
- Google BigTable


### Columnar Databases

**What is it?**
- It stored data physically by column, not by row.​
- All columns exist for all rows (fixed schema).​
- Typically exposes na SQL interface (analytical SQL).

**What is it used for?**
- OLAP workloads​
- Massive read operations​
- Large volume of data​
- Aggregations / analytical queries / BI​
- Reads optimized for column scans and aggregations

**Examples**
- ClickHouse
- Snowflake
- Google BigQuery

## Some key techonologies

| Dimension | Apache Cassandra | ScyllaDB | CosmosDB (Cassandra API) | ClickHouse | Snowflake |
|---------|------------------|----------|--------------------------|------------|-----------|
| **Category** | Wide-Column | Wide-Column | Wide-Column | Columnar-Oriented | Columnar-Oriented |
| **Query language** | CQL | CQL | CQL (partial) | SQL | SQL |
| **OLTP or OLAP** | OLTP | OLTP | OLTP | OLAP | OLAP |
| **Aggregations** | Limited | Limited | Limited | Yes | Yes |
| **Schema flexible** | Yes | Yes | Yes | No | No |
| **Transactions** | No | No | No | No | Limited (statement-level) |
| **Write pattern** | Row-based writes | Row-based writes | Row-based writes | Batch writes | Batch writes |
| **Read pattern** | Key-based reads | Key-based reads | Key-based reads | Aggregation-based reads | Aggregation-based reads |
| **Typical use cases** | Events / Metrics | Events / Metrics | Global SaaS | Analytics | BI / Data Warehouse |

