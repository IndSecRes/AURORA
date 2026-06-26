# AURORA STORAGE ARCHITECTURE SPECIFICATION

## Version 0.1

---

# 1. Purpose

This document defines how AURORA stores:

* structured data
* metadata
* embeddings
* relationships
* logs
* historical snapshots

The storage system must support:

* fast search
* scalable ingestion
* graph traversal
* semantic retrieval
* long-term persistence

---

# 2. Storage Philosophy

AURORA separates storage by function:

```text id="a7m3k9"

Structured Data → PostgreSQL

Semantic Data → Vector Database

Relationships → Graph Database

Logs / History → Append-only Store

```

Each layer is independent but synchronized.

---

# 3. Core Storage Layers

---

# 3.1 Relational Database (System of Record)

Recommended: PostgreSQL

Purpose:

* store canonical resources
* taxonomy
* metadata
* user data
* ingestion state

Example tables:

```text id="p4n8q2"

resources

categories

subcategories

sources

collectors

```

---

## Example Resource Table

```sql id="t7m2x9"
CREATE TABLE resources (
    id TEXT PRIMARY KEY,
    title TEXT,
    url TEXT UNIQUE,
    source_domain TEXT,
    resource_type TEXT,
    category TEXT,
    subcategory TEXT,
    created_date DATE,
    captured_date DATE
);
```

---

# 3.2 Vector Database (Semantic Layer)

Recommended: Qdrant / Weaviate / Milvus

Purpose:

* similarity search
* semantic retrieval
* clustering

Stored:

* embeddings of titles
* embeddings of descriptions
* embeddings of full documents

Example:

```text id="v8m3k1"

"local AI coding assistant"

↓

vector embedding

↓

nearest neighbors

```

---

# 3.3 Graph Database (Relationship Layer)

Recommended: Neo4j (or equivalent)

Purpose:

* model relationships
* traverse ecosystems
* discover dependencies

Example:

```text id="n5m8q3"

Model → uses → Runtime

Model → trained_on → Dataset

Repository → implements → Framework

```

---

# 3.4 Append-Only Event Store

Purpose:

Track history of changes.

Stores:

* ingestion events
* classification updates
* metadata changes
* system logs

Example:

```text id="c6m4x7"

EVENT:

Resource Added

Timestamp: 2026-06-26

Source: GitHub Collector

```

---

# 4. Data Synchronization Model

AURORA ensures consistency across layers.

```text id="q7m2v9"

PostgreSQL (source of truth)
        |
        ↓
Vector DB (semantic index)
        |
        ↓
Graph DB (relationships)
```

---

# 5. Storage Workflow

Example: new URL ingestion

```text id="m3k9v8"

1. Store in PostgreSQL

2. Generate embeddings

3. Store in Vector DB

4. Extract relationships

5. Store in Graph DB

6. Log event
```

---

# 6. Indexing Strategy

AURORA indexes by:

---

## Primary Index

* resource ID
* URL

---

## Secondary Index

* category
* subcategory
* source domain

---

## Search Index

* full-text
* embeddings
* tags

---

# 7. Freshness Handling

Recent data is prioritized:

```text id="x4m7q2"

Higher score if:

- updated after 2025
- frequently accessed
- recently added
```

---

# 8. Deduplication Strategy

Before insertion:

Check:

* exact URL match
* normalized URL match
* semantic similarity

---

# 9. Scaling Strategy

---

## Phase 1 (Local)

* single PostgreSQL instance
* small vector DB
* local graph DB

---

## Phase 2 (Distributed)

* sharded PostgreSQL
* distributed vector storage
* graph clusters

---

## Phase 3 (Cloud Scale)

* multi-region storage
* replication
* caching layers

---

# 10. Caching Layer

Purpose:

Speed up frequent queries.

Cache:

* search results
* embeddings
* graph traversals

---

# 11. Backup Strategy

Includes:

* daily snapshots
* incremental backups
* event log replay

---

# 12. Data Integrity

AURORA ensures:

* no orphan nodes in graph
* no duplicate resources
* consistent taxonomy mapping

---

# 13. Storage APIs

Internal APIs:

* store_resource()
* fetch_resource()
* update_resource()
* delete_resource()
* link_resources()

---

# 14. Performance Goals

System must support:

* fast ingestion
* sub-second search
* scalable graph traversal
* large embedding sets

---

# 15. Future Enhancements

Possible additions:

* distributed graph engines
* real-time streaming ingestion
* cold storage for archival data
* AI-driven compression of embeddings

---

# Summary

AURORA storage system:

```text id="z8m4q1"

Stores Everything

↓

Indexes Everything

↓

Connects Everything

↓

Makes It Searchable

```

---

# End of Document
