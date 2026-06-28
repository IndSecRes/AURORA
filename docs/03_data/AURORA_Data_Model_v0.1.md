# AURORA Data Model Specification v0.1

## Intelligence Data Structures


---

# 1. Purpose

This document defines how AURORA stores, represents, and connects intelligence.

The data model supports:

- resource storage
- metadata intelligence
- entity extraction
- relationships
- search
- taxonomy evolution


---

# 2. Data Architecture


AURORA uses multiple storage layers.


             AURORA DATA


                 |

    ----------------------------


    |             |            |

PostgreSQL Neo4j Vector Store

    |

Elasticsearch



---

# 3. Core Object: Resource


The Resource is the primary intelligence object.


Example:


```json
{
"resource_id":"",

"url":"",

"title":"",

"resource_type":"",

"source":"",

"metadata":{},


"created_at":"",

"updated_at":""

}
4. Resource Types

Initial supported types:

CODE_REPOSITORY

AI_MODEL

DATASET

RESEARCH_PAPER

ARTICLE

FRAMEWORK

LIBRARY

TOOL

AGENT_SYSTEM

DOCUMENT
5. Metadata Object

Metadata is stored as flexible JSON.

Structure:

{
"identity":{

"name":"",
"author":"",
"organization":""

},


"classification":{

"domain":"",
"category":"",
"tags":[]

},


"technical":{

"languages":[],

"frameworks":[],

"models":[],

"datasets":[]

},


"capabilities":[],

"concepts":[]

}
6. Entity Model

Entities represent known objects.

Entity types:

PERSON

ORGANIZATION

MODEL

FRAMEWORK

DATASET

TECHNOLOGY

CONCEPT

LOCATION

Example:

{
"name":"Transformers",

"type":"FRAMEWORK",

"description":"Machine learning framework"
}
7. Relationship Model

Relationships connect intelligence objects.

Example:

{
"source":"Transformers",

"relationship":

"USED_BY",

"target":"TRL",

"confidence":0.91
}
8. Category Model

Categories organize knowledge.

Example:

Artificial Intelligence


    ├── Models


    ├── Training


    ├── Agents


    └── Infrastructure

Stored:

{
"name":"AI Agents",

"parent":"Artificial Intelligence"
}
9. Schema Model

Schemas define resource understanding.

Example:

AI Model Schema:

{
"name":"AI_MODEL",

"fields":[

"architecture",

"parameters",

"training_method",

"license"

]
}
10. Quality Model

Every resource receives quality indicators.

{
"confidence":0.92,

"source_quality":0.85,

"metadata_completeness":0.90
}
11. PostgreSQL Tables

Initial tables:

resources

resource_versions

metadata

schemas

entities

categories

tags

relationships

evolution_proposals
12. Neo4j Graph Model

Nodes:

Resource

Entity

Technology

Concept

Organization

Model

Dataset

Relationships:

CREATED_BY

USES

DEPENDS_ON

RELATED_TO

TRAINED_WITH

ALTERNATIVE_TO

INSPIRED_BY
13. Search Document Model

Stored in Elasticsearch:

{
"id":"",

"title":"",

"summary":"",

"type":"",

"metadata":{},

"keywords":[],

"embedding":""
}
14. Vector Model

Embeddings generated from:

Title

+

Summary

+

Metadata

+

Capabilities

+

Entities

Purpose:

semantic search
similarity
clustering
15. Evolution Data Model

Stores AURORA improvement suggestions.

Example:

{
"type":

"NEW_CATEGORY",


"name":

"AI Memory Systems",


"confidence":

0.87
}
16. MVP Data Flow

Example:

Input:

GitHub Repository

Processing:

Resource Created

↓

Metadata Generated

↓

Entities Extracted

↓

Relationships Created

↓

Search Indexed


Output:

Queryable Intelligence Object
Document Status

Version:

v0.1

Status:

Database Implementation Reference


---

We now have the minimum required architecture documentation.

Remaining before coding:

1. `AURORA_API_Contract_v0.1.md`  
2. `AURORA_Engineering_Blueprint_v0.1.md`

After those two, we should stop documentation and create:
