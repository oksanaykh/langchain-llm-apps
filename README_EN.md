# README_EN.md

# LangChain LLM Applications Course

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![LangChain](https://img.shields.io/badge/LangChain-LLM%20Framework-green)
![OpenAI](https://img.shields.io/badge/OpenAI-API-black)
![LLM](https://img.shields.io/badge/LLM-AI-orange)
![Status](https://img.shields.io/badge/status-learning-brightgreen)

Notes and experiments from the course
**LangChain for LLM Application Development** created by
Harrison Chase and
Andrew Ng.

The course focuses on building applications with **Large Language Models (LLMs)** using
LangChain.

The key idea is to treat an LLM as a **reasoning engine** capable of:

* planning actions
* interacting with external data
* calling tools
* building complex AI pipelines

---

# Topics Covered

The course explores the core building blocks of LLM applications.

---

### Models

Working with chat models (`ChatOpenAI`)

* temperature control
* deterministic outputs
* prompt engineering

---

### Prompts

Reusable prompt templates:

* `ChatPromptTemplate`
* system prompts
* prompt abstraction

---

### Output Parsers

Transforming LLM output into structured data:

* `StructuredOutputParser`
* `ResponseSchema`

---

### Memory

Managing conversation context:

* ConversationBufferMemory
* ConversationBufferWindowMemory
* ConversationTokenBufferMemory
* ConversationSummaryBufferMemory

---

### Chains

Building processing pipelines:

* `LLMChain`
* `SequentialChain`
* `SimpleSequentialChain`
* `RouterChain`

---

### Retrieval Augmented Generation (RAG)

Building question-answering systems using external documents.

Key components:

* document loaders
* embeddings
* vector stores
* similarity search

Document processing strategies:

* Stuff
* Map Reduce
* Refine
* Map Rerank

---

### Evaluation

Testing and debugging LLM applications:

* `QAGenerateChain`
* `QAEvalChain`
* LLM-as-a-judge
* debug mode (`langchain.debug`)

---

### Agents

LLMs acting as decision-making systems.

Agent used in the course:

```
CHAT_ZERO_SHOT_REACT_DESCRIPTION
```

Agents can interact with external tools such as:

* Wikipedia
* DuckDuckGo
* custom Python tools via `@tool`

---

# Project Structure

```bash
langchain-course/
│
├── notebooks/
│   ├── 01_models_prompts_parsers.ipynb
│   ├── 02_memory.ipynb
│   ├── 03_chains.ipynb
│   ├── 04_question_answering_rag.ipynb
│   ├── 05_evaluation.ipynb
│   └── 06_agents.ipynb
│
├── data/
│   └── example_documents.csv
│
├── utils/
│   └── helper_functions.py
│
└── README.md
```

---

# Tech Stack

* Python
* LangChain
* OpenAI API
* Vector Embeddings
* Retrieval Augmented Generation (RAG)
* Prompt Engineering

# Key Concepts

**Embeddings**
Vector representations of semantic meaning.

**Vector Stores**
Databases designed for similarity search.

**Tokens**
The basic unit of text processed by LLMs.

**ReAct Framework**

Reasoning pattern used by agents:

```
Thought → Action → Observation
```

---

# Repository Goal

This repository includes:

* course notes
* LangChain experiments
* RAG implementation examples
* LLM application architecture patterns

---

