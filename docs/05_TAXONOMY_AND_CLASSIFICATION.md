# AURORA TAXONOMY AND CLASSIFICATION SPECIFICATION

## Version 0.1

---

# 1. Purpose

This document defines how AURORA organizes knowledge.

The taxonomy provides a structured hierarchy for:

* classification
* discovery
* filtering
* indexing
* future automation

The goal is to transform a collection of resources into an understandable knowledge ecosystem.

---

# 2. Classification Philosophy

AURORA uses:

```text id="y8m4c1"

Domain

↓

Category

↓

Subcategory

↓

Resource Type

↓

Attributes

↓

Tags

```

---

# 3. Classification Example

Example:

A local AI model:

```text id="p7x2m8"

Domain:

Artificial Intelligence


Category:

Models


Subcategory:

Coding Models


Resource Type:

LLM


Attributes:

70B

GGUF

Quantized


Tags:

local-ai

coding

open-source

```

---

# 4. Top-Level Taxonomy

Initial AURORA domains:

---

# 1. Models & Model Ecosystem

Purpose:

AI models and related resources.

Subcategories:

* Foundation Models
* Large Language Models
* Small Language Models
* Coding Models
* Reasoning Models
* Vision Models
* Multimodal Models
* Uncensored Models
* Abliterated Models
* Quantized Models
* Fine-Tuned Models
* Domain Specific Models

---

# 2. Model Infrastructure

Resources required to run models.

Subcategories:

* Inference Engines
* Runtime Systems
* Model Management
* Deployment
* Optimization
* Hardware Acceleration

Examples:

* llama.cpp
* vLLM
* TensorRT-LLM

---

# 3. AI Agents

Systems that perform autonomous tasks.

Subcategories:

* Agent Frameworks
* Multi-Agent Systems
* Agent Memory
* Agent Skills
* Agent Tools
* Agent Workflows

---

# 4. Retrieval and Knowledge Systems

Systems that connect AI with information.

Subcategories:

* RAG Frameworks
* Vector Databases
* Knowledge Graphs
* Document Processing
* Search Systems

---

# 5. Training and Fine-Tuning

Resources for creating models.

Subcategories:

* Fine-Tuning
* LoRA
* RL Training
* Synthetic Data
* Alignment
* Evaluation

---

# 6. Data Ecosystem

Knowledge and training data.

Subcategories:

* Datasets
* Synthetic Data
* Data Pipelines
* Data Cleaning
* Data Annotation

---

# 7. Research

Scientific knowledge.

Subcategories:

* Papers
* Benchmarks
* Surveys
* Research Organizations

---

# 8. Software Engineering AI

AI tools for developers.

Subcategories:

* Coding Agents
* Code Review
* Code Search
* Programming Assistants
* Development Automation

---

# 9. Vision / Multimodal AI

Visual intelligence.

Subcategories:

* OCR
* Image Generation
* Video Generation
* Document AI
* Vision Models

---

# 10. Automation Systems

Workflow automation.

Subcategories:

* Workflow Platforms
* No-Code AI
* Pipelines
* Integrations

---

# 11. OSINT / Intelligence Systems

Information investigation.

Subcategories:

* OSINT Tools
* SOCMINT
* GEOINT
* Cyber Intelligence
* Investigation Frameworks

---

# 12. Cybersecurity AI

AI security ecosystem.

Subcategories:

* Security Automation
* Threat Intelligence
* Malware Analysis
* Defensive AI

---

# 13. Infrastructure

Technology foundations.

Subcategories:

* Cloud
* Containers
* Kubernetes
* Distributed Computing
* Storage

---

# 14. Hardware / Edge AI

Physical platforms.

Subcategories:

* GPUs
* AI Workstations
* Edge Devices
* NPUs
* Accelerators

---

# 15. Learning Resources

Educational material.

Subcategories:

* Courses
* Books
* Tutorials
* Engineering Guides

---

# 5. Resource Type Classification

Examples:

```text id="n4k8x2"

Repository

Model

Dataset

Paper

Article

Tool

Framework

Hardware

Documentation

Service

```

---

# 6. Metadata Attributes

Each category can define additional attributes.

Example:

Models:

```yaml id="q6m3v8"

parameters:

70B


architecture:

Transformer


format:

GGUF


license:

Apache

```

---

Repositories:

```yaml id="j7p1m9"

language:

Python


stars:

5000


license:

MIT

```

---

# 7. Dynamic Taxonomy

AURORA taxonomy must evolve.

New categories may be suggested by:

* resource growth
* clustering
* similarity analysis

Example:

```text id="v3x8q5"

120 resources detected

↓

Possible new category:

"Agent Memory Systems"

```

---

# 8. Classification Methods

AURORA uses multiple methods:

---

## Rule Based

Example:

github.com

↓

Repository

---

## Metadata Based

Example:

Hugging Face:

Model card detected

↓

Model

---

## AI Assisted

Example:

Description analysis:

↓

Coding Agent

---

# 9. Confidence Score

Every classification should store confidence.

Example:

```yaml id="s5m2q8"

category:

Agent Framework


confidence:

0.92

```

---

# 10. Human Review

Users can:

* correct categories
* merge categories
* create new taxonomy

---

# 11. Goal

The taxonomy allows AURORA to answer:

"What exists?"

"Where does it belong?"

"What is related?"

"What changed?"

---

# End of Document
