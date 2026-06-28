# AURORA Component Map v0.1

## System Modules and Responsibilities


---

# 1. Purpose

This document defines the functional components of AURORA.

Each component has:

- responsibility
- inputs
- outputs
- dependencies


---

# 2. Component Overview


                AURORA


                API Layer


                   |

| | | |

Ingest Metadata Search Evolution

| | | |

Parser Extractor Indexer Analyzer

                   |


             Knowledge Layer


                   |


          PostgreSQL + Neo4j


---

# 3. Resource Ingestion Component


## Responsibility

Accept external information sources.


## Input


URL
Document
Repository



## Output

Resource Object


Example:

```json
{
"url":"",
"title":"",
"source":""
}
Dependencies
Fetcher
Parser
Storage
4. Content Processing Component
Responsibility

Normalize incoming data.

Handles:

HTML
Markdown
PDF
Code repositories

Output:

Clean content representation

5. Metadata Intelligence Component
Responsibility

Generate structured understanding.

Tasks:

classification
entity extraction
capability extraction
summarization

Input:

Content

Output:

{
"type":"AI_FRAMEWORK",

"capabilities":[
"training"
]
}
6. Schema Registry Component
Responsibility

Determine resource structure.

Example:

Input:

GitHub URL

Output:

CODE_REPOSITORY schema

Stores:

fields
validation rules
rendering rules
7. Entity Resolution Component
Responsibility

Identify known entities.

Example:

Input:

"DeepSpeed by Microsoft"

Output:

DeepSpeed

Entity Type:
Framework


Microsoft

Entity Type:
Organization

8. Knowledge Graph Component

Technology:

Neo4j

Responsibility:

Store relationships.

Example:

DeepSpeed

RELATED_TO

Megatron-LM

9. Search Component

Technology:

Elasticsearch/OpenSearch

Responsibilities:

indexing
filtering
ranking
retrieval

Search inputs:

Query

+

Metadata

+

Vector similarity

+

Graph context

10. Vector Intelligence Component

Responsibility:

Semantic understanding.

Creates embeddings from:

title
metadata
summary
concepts

Used for:

similarity search
clustering
11. Evolution Component

Responsibility:

Improve AURORA's understanding.

Detects:

missing categories
missing relationships
new concepts

Output:

Proposal:

{
"type":"NEW_CATEGORY",

"name":"AI Memory Systems"
}
12. Dynamic UI Component

Responsibility:

Generate interfaces from schemas.

Flow:

Schema

↓

Renderer

↓

Page


Examples:

AI Model Page

Repository Page

Research Paper Page

13. Agent Layer

Future capability.

Agents:

Research Agent

Finds resources.

Metadata Agent

Improves metadata.

Schema Agent

Maintains schemas.

Evolution Agent

Suggests improvements.

14. Component Dependency Map
Ingestion

    ↓

Processing

    ↓

Metadata

    ↓

Schema

    ↓

Entities

    ↓

Knowledge Graph

    ↓

Search

    ↓

UI

    ↓

Evolution

15. MVP Components

First implementation requires only:

Phase 1:

Resource Ingestion

+

Metadata Storage

+

Basic Search

+

Simple UI


Phase 2:

Entity Extraction

+

Knowledge Graph


Phase 3:

Evolution Engine

+

Agents
Document Status

Version:

v0.1

Status:

Implementation Reference
