# Enterprise Banking Data Platform — an explorable model

*Work-derived model, fully generalized · 2025–2026*

**[Explore the live model →](https://halkhoori2000.github.io/Data-Platform-Confluent-Kafka/)**

This is an interactive model of a real enterprise banking data platform — the kind that turns dozens of source systems, event streams, and years of files into governed, queryable data products. You move around the estate like a map: the top level shows the whole landscape (sources → ingest → transform → serve → consume, with security and governance running underneath), and every zoom reveals more — planes, then tools, then how each tool actually works inside. Kafka goes all the way down to its commit log; Delta Lake to its transaction log.

Technically, the model covers a lakehouse platform built on Confluent Kafka (CDC streaming with Kafka Connect and Schema Registry), Azure Data Factory (control-table-driven batch with watermark incrementality), and Databricks on ADLS Gen2 + Delta Lake (Auto Loader, Delta Live Tables, Spark + Photon, Workflows), organized as Bronze → Silver → Gold, served through Databricks SQL and Delta Sharing, consumed via Power BI + Copilot and AI/BI Genie, and governed end-to-end by Unity Catalog with Entra ID, Key Vault, and private networking as the security rail. Three animated micro-demos show the internals live: a Kafka partition's append-only log with replication and consumer offsets, Delta's transaction log with time travel, and a Spark job executing as stages, shuffles, and tasks. Four "journeys" show the platform at work — including the [Historic Data Loading](https://halkhoori2000.github.io/Historic-Data-Loading/) delivery, which ran on this platform.

## Use Cases

- **Explaining a modern data platform** — one navigable picture from source system to dashboard, at whatever depth the audience needs: executives stop at the landscape, engineers descend to the commit log
- **Learning the streaming + lakehouse stack** — Kafka, CDC, Schema Registry, Delta Lake, medallion architecture, and lakehouse governance, each explained where it sits in the whole
- **Architecture reference** — the patterns (metadata-driven ingestion, watermark incrementality, deterministic quality rules, IaC-provisioned environments) are industry-standard and reusable
- **Portfolio deep-dive** — the journeys connect the model to real, documented deliveries

## Challenges

- **Depth without drowning** — the same page has to work for someone who wants five boxes and someone who wants offsets and ISR mechanics; semantic zoom (content changes with depth, not just size) is the answer
- **Honesty at every level** — tool internals are public engineering knowledge, but delivery claims appear only in the journey pages, where they're backed by their own case studies
- **Confidentiality by construction** — the model generalizes an actual estate: no institution names, no internal system names, no configurations, no data appear anywhere
- **A model that stays true** — the architecture shown follows the real build: incremental batches directly into a governed gold layer, control-table watermarks, and one conformed table per source system

## Repository structure

```
index.html   ← the entire explorable model (GitHub Pages) — no build step, no dependencies
```
