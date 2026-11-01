# Modernizing data platforms

[Back to profile](https://github.com/ejiod2025)

**Context:** Nordstrom · Senior Analytics Engineer

**Focus:** Orchestration, CDC, lakehouse ingestion, and reliable delivery

## The problem

Supply-chain reporting depends on data moving reliably from operational systems into analytical platforms. My work covers 18 enterprise source systems, including legacy IBM i / AS400 environments. Modernization involved more than replacing a scheduler: ingestion, transformations, incremental changes, and downstream reporting all had to work together.

## My contribution

I completed the migration from Talend to Airflow, including substantial Java development. I also built custom Java / Apache Flink CDC connectors to capture changes from legacy systems and move them through Kafka into downstream platforms.

For batch and streaming ingestion, I worked with Hudi and Delta Lake to handle incremental processing, updates and deletes, and schema evolution. My Airflow and Cloud Composer workflows also launch Google Dataflow Flex Template jobs. Manhattan WMS workflows cover warehouse productivity refreshes, CSV exports, schema extraction, and replication.

The surrounding engineering work includes validation, source-to-target mappings, data contracts, observability, lineage, and replay and recovery. CI/CD, Terraform, Liquibase, and release-validation standards support repeatable pipeline and database changes.

## Engineering considerations

- **Orchestration and processing have different responsibilities.** Airflow coordinates workflows; the processing jobs and connectors handle data movement and transformation.
- **CDC needs more than inserts.** Updates, deletes, and changing schemas matter when downstream consumers need an accurate view of operational state.
- **Recovery is part of the design.** Historical backfills and streaming changes need validation and a defined recovery approach so a rerun does not silently produce inconsistent results.
- **A successful migration must support its consumers.** Source mappings and downstream checks connect platform changes to the reporting that depends on them.

## Outcome and current work

The Talend-to-Airflow migration is complete. My broader responsibilities span ingestion, CDC, storage, transformation, and delivery for supply-chain analytics.

I am also evaluating analytical serving options for an Aurora/PostgreSQL-based architecture, including StarRocks and other OLAP systems. That work considers materialized views, concurrency, caching, freshness, infrastructure sizing, and cost. **Status: architecture evaluation.**

This case study is a high-level account of professional experience. It does not include employer source code, internal schemas, or operational data.
