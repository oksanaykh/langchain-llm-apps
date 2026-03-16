# LangChain LLM Applications Course

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![LangChain](https://img.shields.io/badge/LangChain-LLM%20Framework-green)
![OpenAI](https://img.shields.io/badge/OpenAI-API-black)
![LLM](https://img.shields.io/badge/LLM-AI-orange)
![Status](https://img.shields.io/badge/status-learning-brightgreen)

Notes and practical experiments from the course
**LangChain for LLM Application Development** by
Harrison Chase and
Andrew Ng.

The course focuses on building applications powered by **LLMs** using the
LangChain framework.

The core idea of the course is to treat an LLM as a **reasoning engine** capable of:

* planning actions
* working with external data sources
* using tools
* building complex processing pipelines

---

# What Was Covered

The course explored the key architectural components of LLM applications:

### Models

Working with chat models (`ChatOpenAI`)

* temperature
* controlling determinism
* prompt engineering
* direct OpenAI API calls and their comparison with LangChain abstractions

---

### Prompts

Using prompt templates:

* `ChatPromptTemplate`
* system instructions
* reusable prompts with dynamic variable substitution

---

### Output Parsers

Converting LLM responses into structured data:

* `JsonOutputParser`
* extracting structured fields from raw model output

---

### LCEL (LangChain Expression Language)

The modern way to build pipelines using the `|` operator:

```
Prompt Template | Model | Output Parser
```

* modular and readable chain composition
* used throughout the course notebooks (L1–L3)

---

### Memory

Managing conversation history using the modern LangChain API:

* `RunnableWithMessageHistory` — attaching history to a chain
* `trim_messages` — limiting context by token budget
* **Buffer Memory** — storing the full conversation history
* **Window Memory** — keeping the last K messages (sliding window)
* **Token-Limited Memory** — limiting context by token count
* **Summary Memory** — compressing long history via summarization

---

### Chains

Building multi-step processing pipelines with LCEL:

* **LLMChain** — basic chain: prompt → model → parser
* **SimpleSequentialChain** — linear sequence of steps
* **SequentialChain** — multiple inputs and outputs between steps
* **RouterChain** — dynamically selecting a chain based on input

Example SequentialChain from the notebook: translate review → summarize → detect language → generate follow-up response

---

### RAG (Retrieval Augmented Generation)

Building question-answering systems over documents:

* document loaders — loading source data (`OutdoorClothingCatalog_1000.csv`)
* `RecursiveCharacterTextSplitter` — splitting documents into chunks
* embeddings — vector representation of text (`OpenAIEmbeddings`)
* **FAISS** — vector store for similarity search
* retriever — finding relevant chunks for a query
* QA chain — generating answers based on retrieved context

RAG architecture:
```
User Question → Embedding → Vector Search → Relevant Chunks → LLM → Answer
```

---

### Evaluation

Testing LLM applications:

* manually writing evaluation examples (question–answer pairs)
* auto-generating test examples from documents using an LLM
* **LLM-as-a-judge** — evaluating answer quality using another language model
* analyzing results: which questions were answered correctly, where mistakes occurred

---

### Agents

LLM as a decision-making engine.

Approach used:

* `create_react_agent` + `AgentExecutor` — modern LangChain API

Custom tools defined with the `@tool` decorator:

* `calculator` — evaluates mathematical expressions
* `wikipedia_search` — searches Wikipedia
* `time` — returns the current date

Agent reasoning loop (ReAct):
```
Thought → Action → Observation → Thought → ... → Final Answer
```

---

# Project Structure

```bash
langchain-course/
│
├── notebooks/
│   ├── L1-Model_prompt_parser.ipynb
│   ├── L2-Memory.ipynb
│   ├── L3-Chains.ipynb
│   ├── L4-QnA.ipynb
│   ├── L5-Evaluation.ipynb
│   └── L6-Agents.ipynb
│
├── data/
│   └── OutdoorClothingCatalog_1000.csv
│
└── README.md
```

---

# Tech Stack

* Python 3.10+
* LangChain (LCEL, modern API)
* OpenAI API (`gpt-3.5-turbo` / `gpt-4`)
* OpenAI Embeddings
* FAISS (vector store)
* RAG architecture
* Prompt Engineering

---

# Key Concepts

**LCEL (LangChain Expression Language)**
The `|` syntax for building modular chains: `prompt | model | parser`.

**Embeddings**
Vector representations of text meaning; the foundation of semantic search.

**Vector Stores**
Databases for storing embeddings and performing similarity search. FAISS is used in this course.

**Tokens**
The basic unit of text for LLMs; token management is critical for memory and RAG.

**ReAct Framework**
A prompting strategy for agents combining:

```
Thought → Action → Observation
```

**LLM-as-a-judge**
Using a language model to automatically evaluate the quality of another model's answers.

---

# Repository Goal

This repository contains:

* course notes
* practical LangChain examples
* architectural patterns for LLM applications
* experiments with RAG and agents

---
