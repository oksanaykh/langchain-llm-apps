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
* прямые вызовы OpenAI API и их сравнение с LangChain-абстракциями

---

### Prompts

Использование шаблонов:

* `ChatPromptTemplate`
* системные инструкции
* reusable prompts с динамической подстановкой переменных

---

### Output Parsers

Преобразование ответа LLM в структурированные данные:

* `JsonOutputParser`
* извлечение структурированных полей из текстового ответа модели

---

### LCEL (LangChain Expression Language)

Современный способ построения пайплайнов через оператор `|`:

```
Prompt Template | Model | Output Parser
```

* модульная и читаемая композиция цепочек
* используется во всех ноутбуках курса (L1–L3)

---

### Memory

Управление историей диалога с использованием современного API LangChain:

* `RunnableWithMessageHistory` — подключение истории к цепочке
* `trim_messages` — ограничение контекста по количеству токенов
* **Buffer Memory** — хранение полной истории диалога
* **Window Memory** — хранение последних K сообщений (скользящее окно)
* **Token-Limited Memory** — ограничение по бюджету токенов
* **Summary Memory** — сжатие длинной истории через суммаризацию

---

### Chains

Создание многошаговых пайплайнов обработки через LCEL:

* **LLMChain** — базовая цепочка: prompt → model → parser
* **SimpleSequentialChain** — линейная последовательность шагов
* **SequentialChain** — поддержка нескольких входов и выходов между шагами
* **RouterChain** — динамический выбор цепочки в зависимости от входа

Пример SequentialChain из ноутбука: перевод отзыва → суммаризация → определение языка → генерация ответа

---

### RAG (Retrieval Augmented Generation)

Реализация question-answering систем над документами:

* document loaders — загрузка источников (`OutdoorClothingCatalog_1000.csv`)
* `RecursiveCharacterTextSplitter` — разбивка документов на чанки
* embeddings — векторное представление текста (`OpenAIEmbeddings`)
* **FAISS** — векторное хранилище для similarity search
* retriever — поиск релевантных фрагментов по запросу
* QA chain — генерация ответа на основе retrieved-контекста

RAG-архитектура:
```
User Question → Embedding → Vector Search → Relevant Chunks → LLM → Answer
```

---

### Evaluation

Тестирование LLM-приложений:

* ручное составление оценочных примеров (question–answer pairs)
* автогенерация тестовых примеров с помощью LLM из документов
* **LLM-as-a-judge** — оценка качества ответов другой языковой моделью
* анализ результатов: какие вопросы решены корректно, где ошибки

---

### Agents

LLM как механизм принятия решений.

Используемый подход:

* `create_react_agent` + `AgentExecutor` — современный API LangChain

Кастомные инструменты через декоратор `@tool`:

* `calculator` — вычисление математических выражений
* `wikipedia_search` — поиск по Википедии
* `time` — получение текущей даты

Логика работы агента (ReAct loop):
```
Thought → Action → Observation → Thought → ... → Final Answer
```

---

# Структура проекта

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

# Ключевые концепции

**LCEL (LangChain Expression Language)**
Синтаксис `|` для построения модульных цепочек: `prompt | model | parser`.

**Embeddings**
Векторное представление смысла текста; основа семантического поиска.

**Vector Stores**
Базы данных для хранения embeddings и выполнения similarity search. В курсе используется FAISS.

**Tokens**
Базовая единица текста для LLM; управление токенами критично для memory и RAG.

**ReAct Framework**
Стратегия prompting для агентов, объединяющая:

```
Thought → Action → Observation
```

**LLM-as-a-judge**
Использование языковой модели для автоматической оценки качества ответов другой модели.

---

# Цель репозитория

Этот репозиторий содержит:

* конспект курса
* практические примеры LangChain
* архитектурные паттерны LLM-приложений
* эксперименты с RAG и агентами

---
