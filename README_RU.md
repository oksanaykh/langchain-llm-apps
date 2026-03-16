# LangChain LLM Applications Course

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![LangChain](https://img.shields.io/badge/LangChain-LLM%20Framework-green)
![OpenAI](https://img.shields.io/badge/OpenAI-API-black)
![LLM](https://img.shields.io/badge/LLM-AI-orange)
![Status](https://img.shields.io/badge/status-learning-brightgreen)

Конспект и практические эксперименты по курсу
**LangChain for LLM Application Development** от
Harrison Chase и
Andrew Ng.

Курс посвящен разработке приложений на базе **LLM** с использованием фреймворка
LangChain.

Основная идея курса — рассматривать LLM как **reasoning engine**, способный:

* планировать действия
* работать с внешними источниками данных
* использовать инструменты
* строить сложные пайплайны обработки

---

# Что изучено

В рамках курса были разобраны ключевые архитектурные компоненты LLM-приложений:

### Models

Работа с чат-моделями (`ChatOpenAI`)

* temperature
* управление детерминированностью
* prompt engineering

---

### Prompts

Использование шаблонов:

* `ChatPromptTemplate`
* системные инструкции
* reusable prompts

---

### Output Parsers

Преобразование ответа LLM в структурированные данные:

* `StructuredOutputParser`
* `ResponseSchema`

---

### Memory

Управление историей диалога:

* ConversationBufferMemory
* ConversationBufferWindowMemory
* ConversationTokenBufferMemory
* ConversationSummaryBufferMemory

---

### Chains

Создание пайплайнов обработки:

* `LLMChain`
* `SequentialChain`
* `SimpleSequentialChain`
* `RouterChain`

---

### RAG (Retrieval Augmented Generation)

Реализация question-answering систем:

* document loaders
* embeddings
* vector stores
* similarity search

Методы обработки документов:

* Stuff
* Map Reduce
* Refine
* Map Rerank

---

### Evaluation

Тестирование LLM-приложений:

* `QAGenerateChain`
* `QAEvalChain`
* LLM-as-a-judge
* debugging (`langchain.debug`)

---

### Agents

LLM как механизм принятия решений.

Используемый агент:

```
CHAT_ZERO_SHOT_REACT_DESCRIPTION
```

Поддержка внешних инструментов:

* Wikipedia
* DuckDuckGo
* custom tools через `@tool`

---

# Структура проекта

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
* RAG architecture
* Prompt Engineering

---

# Ключевые концепции

**Embeddings**
Векторное представление смысла текста.

**Vector Stores**
Базы данных для хранения embeddings и similarity search.

**Tokens**
Базовая единица текста для LLM.

**ReAct Framework**
Стратегия prompting, объединяющая:

```
Thought → Action → Observation
```

---

# Цель репозитория

Этот репозиторий содержит:

* конспект курса
* практические примеры LangChain
* архитектурные паттерны LLM-приложений
* эксперименты с RAG и агентами

---

