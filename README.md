# RAG-based Accident Investigation QA System

This project implements a **Retrieval-Augmented Generation (RAG)** system for querying accident investigation reports using vector search and Large Language Models (LLMs).

This is a part of **INDIVIDUAL STUDY IN COMPUTER ENGINEERING (2110392)**.

---

## 📌 Overview

The system retrieves relevant document chunks from accident investigation reports and generates grounded answers using a 2-stage LLM pipeline.

Architecture:

1. Document Loading (.docx)
2. Text Chunking
3. Embedding (BAAI/bge-m3)
4. ChromaDB Vector Store
5. Retriever (Top-k)
6. Tool-calling LLM
7. Final Reasoning LLM
8. Similarity-based Evaluation

---

## ⚙️ Core Components

### 🔹 Embedding Model

* `BAAI/bge-m3`
* Multilingual support (Thai compatible)

### 🔹 Vector Database

* ChromaDB (persistent: `./chroma_db`)
* Top-k retrieval (k=3)

### 🔹 LLM

* Model: `qwen2.5` (via Ollama)
* Temperature: 0 (deterministic output)

### 🔹 RAG Pipeline

```python
run_pipeline(question: str)
```

* LLM1 → Tool selection
* search_db → Vector retrieval
* LLM2 → Final grounded answer

LangSmith tracing enabled.

---

## 📊 Evaluation

Validation uses embedding similarity between:

* Model prediction
* Ground truth (val_measure)

Metrics:

* Individual similarity scores
* Average similarity score

Test set supports prediction and optional scoring (if ground truth provided).

---

## 🗂 Dataset Structure

```
dataset/
├── train/
├── val/
├── val_measure/
└── test/
```

---

## 🎯 Key Features

* Thai-language RAG system
* Persistent vector database
* Tool-based LLM agent
* Embedding similarity evaluation
* Modular train / val / test functions

---

Developed for academic experimentation in Retrieval-Augmented Generation and vector database engineering.
