# AURORA QUERY ENGINE SPECIFICATION

## Version 0.1

---

# 1. Purpose

This document defines how users interact with AURORA through queries.

The Query Engine allows users to:

* search knowledge
* discover relationships
* compare resources
* explore ecosystems
* ask questions

---

# 2. Query Philosophy

AURORA should not depend entirely on an LLM.

The preferred approach:

```text id="x8m4q2"

Structured Query

↓

Database Search

↓

Metadata Filtering

↓

Graph Traversal

↓

Semantic Search

↓

Optional AI Reasoning

```

---

# 3. Query Types

AURORA supports multiple query modes.

---

# 3.1 Direct Lookup

Example:

```text id="p4n7m8"

Find Qwen models
```

Process:

Database search.

Returns:

* models
* metadata
* links

---

# 3.2 Filter Query

Example:

```text id="c5m8x1"

Find:

70B models

+

GGUF format

+

published after 2025

```

Uses:

* metadata
* filters

---

# 3.3 Similarity Query

Example:

```text id="v9k2m5"

Find models similar to DeepSeek-R1

```

Uses:

* embeddings
* vector search

---

# 3.4 Relationship Query

Example:

```text id="z6p3q8"

What tools work with this model?

```

Uses:

Knowledge Graph.

Example:

```text id="j5m8x4"

Model

↓

Runtime

↓

Tool

```

---

# 3.5 Ecosystem Query

Example:

```text id="b7n4m2"

Show everything from Hugging Face related to agents

```

Process:

Source filter:

```text id="w2q6p9"

source = huggingface

```

*

category:

Agents

---

# 4. Query Processing Pipeline

```text id="n8v5m3"

User Question

↓

Intent Detection

↓

Query Classification

↓

Search Strategy Selection

↓

Retrieve Knowledge

↓

Generate Response

```

---

# 5. Search Layers

AURORA uses multiple search layers.

---

# Layer 1 — Structured Search

Technology:

PostgreSQL

Used for:

* categories
* dates
* metadata

Example:

```sql id="m4q8v1"

SELECT models

WHERE parameters='70B';

```

---

# Layer 2 — Full Text Search

Used for:

* descriptions
* documentation
* text content

---

# Layer 3 — Vector Search

Used for:

semantic similarity.

Example:

Input:

```text id="c8m2x5"

local coding assistant

```

Finds:

* coding models
* agents
* tools

---

# Layer 4 — Knowledge Graph Search

Used for:

relationships.

Example:

```text id="r7k3m9"

Model

↓

Created By

↓

Organization

↓

Related Models

```

---

# 6. Hybrid Search

Best results come from combining:

```text id="p9x5m1"

SQL

+

Text Search

+

Vector Search

+

Graph Search

```

---

# 7. Natural Language Questions

Example:

User:

```text id="s4m8q2"

Which open-source coding models released after 2025 support local inference?

```

AURORA:

Breaks into:

```text id="d7v3m8"

Category:

Coding Models


License:

Open Source


Date:

After 2025


Runtime:

Local

```

---

# 8. Answer Construction

AURORA responses should include:

* answer
* sources
* evidence
* confidence

Example:

```text id="k8m4v2"

Answer:

Found 15 matching models


Sources:

Hugging Face

GitHub


Confidence:

0.91

```

---

# 9. Query Memory

Future capability:

Remember:

* common searches
* user collections
* preferences

---

# 10. AI Reasoning Layer

Optional layer.

Used when:

* complex comparison
* summarization
* explanation

Example:

"Compare these three agent frameworks."

---

# 11. Query Examples

---

Question:

"What are the best local LLM runtimes?"

Process:

```text id="t5m8q1"

Category:

Inference Engines


Search:

Runtime resources

```

---

Question:

"Find resources similar to this repository."

Process:

```text id="h7v3m9"

Embedding Search

+

Graph Expansion

```

---

# 12. Future Capabilities

Possible additions:

* voice queries
* automated reports
* research mode
* agent-assisted investigation

---

# Summary

AURORA Query Engine transforms:

```text id="m2q7v4"

Question

↓

Knowledge Retrieval

↓

Evidence

↓

Answer

```

---

# End of Document
