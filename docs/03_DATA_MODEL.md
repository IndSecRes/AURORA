# AURORA DATA MODEL SPECIFICATION

## Version 0.1

---

# 1. Purpose

This document defines the data structure used by AURORA.

The purpose of the data model is to represent:

* resources
* sources
* categories
* metadata
* relationships
* evidence

Every item stored inside AURORA should be understandable, searchable, and traceable.

---

# 2. Core Resource Concept

The fundamental object in AURORA is:

```text id="m5q2x8"
Resource
```

A resource can be:

* AI model
* GitHub repository
* research paper
* dataset
* article
* documentation
* hardware
* tool
* application

---

# 3. Resource Record

Example:

```yaml id="p4n7k2"

id:

unique_identifier


title:

Resource Name


url:

Original URL


source_domain:

github


resource_type:

repository


category:

AI Tools


subcategory:

Agent Framework


tags:

- agents
- automation
- python


created_date:

2026-01-01


captured_date:

2026-06-26

```

---

# 4. Required Fields

Every resource should contain:

| Field         | Purpose                  |
| ------------- | ------------------------ |
| id            | Unique identifier        |
| title         | Resource name            |
| url           | Original location        |
| source_domain | Origin website           |
| resource_type | Type of object           |
| category      | Top-level classification |
| subcategory   | Detailed classification  |
| captured_date | When AURORA collected it |

---

# 5. Source Information

AURORA separates:

Resource:

```text id="m3b8x1"
What is it?
```

from:

Source:

```text id="w8n4k6"
Where did it come from?
```

Example:

```yaml id="r7q1v9"

source_domain:

huggingface


source_type:

model_repository


source_url:

https://huggingface.co/example/model

```

---

# 6. Taxonomy Model

Classification hierarchy:

```text id="m9x5v2"

Category

↓

Subcategory

↓

Tags

↓

Attributes

```

Example:

```text id="k8v3m1"

Models

↓

Coding Models

↓

Quantized

↓

GGUF

```

---

# 7. Model Specific Metadata

For AI models:

Additional fields:

```yaml id="y4m7p9"

parameters:

70B


architecture:

Transformer


model_family:

Llama


format:

GGUF


quantization:

Q4_K_M


context_length:

128k


license:

Apache-2.0

```

---

# 8. Repository Specific Metadata

For GitHub projects:

```yaml id="t2k8p5"

language:

Python


stars:

10000


forks:

500


license:

MIT


topics:

- AI
- Agents

```

---

# 9. Research Paper Metadata

For papers:

```yaml id="n6q3v8"

authors:

...


publication_date:

2026


arxiv_id:

...


topics:

- LLM
- Agents

```

---

# 10. Evidence Model

Every resource keeps evidence.

Example:

```yaml id="x8m4p1"

evidence:

original_url

capture_timestamp

source_snapshot

collector_used

```

---

# 11. Relationship Model

AURORA stores connections.

Example:

```text id="c9v2m7"

Model

|

created_by

|

Organization


Model

|

uses

|

Runtime


Model

|

trained_on

|

Dataset

```

---

# 12. Similarity Model

Resources can have similarity scores.

Example:

```yaml id="z7p4m8"

similar_resources:

- resource_A
- resource_B


similarity_score:

0.94

```

---

# 13. Freshness Model

AURORA prioritizes recent information.

Fields:

```yaml id="b3x8q6"

published_date

updated_date

last_checked

```

Priority rule:

Newer resources receive higher discovery priority.

---

# 14. Quality Model

Resources may contain quality indicators.

Example:

```yaml id="v5m2n9"

source_quality:

0.90


metadata_completeness:

0.85


confidence:

0.88

```

---

# 15. Duplicate Detection

AURORA should identify:

* identical URLs
* duplicate resources
* renamed projects

Example:

```text id="q8n4m3"

Duplicate Found

Resource A

=

Resource B

```

---

# 16. Export Format

AURORA should support:

* JSON
* CSV
* Markdown

Example:

```json
{
"title":"Example Model",
"source":"huggingface",
"category":"Models"
}
```

---

# 17. Future Expansion

Future metadata:

* usage statistics
* popularity trends
* community activity
* dependency graph
* performance benchmarks

---

# Summary

The AURORA data model ensures:

```text id="j5k8p3"

Every Resource

↓

Has Identity

↓

Has Source

↓

Has Classification

↓

Has Evidence

↓

Has Relationships

```

---

# End of Document
