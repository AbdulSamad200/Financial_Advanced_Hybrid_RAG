# Financial QA System using Advanced Hybrid RAG

## Overview

This project implements an advanced Hybrid Retrieval-Augmented Generation (RAG) system for answering questions from SEC 10-K financial reports.

The system combines semantic search, keyword search, reranking, citation generation, and experiment tracking to deliver accurate and grounded financial answers.

Unlike basic RAG systems that rely solely on vector search, this project uses a production-style retrieval pipeline consisting of:

- Gemini Embeddings
- Qdrant Vector Database
- BM25 Sparse Retrieval
- Reciprocal Rank Fusion (RRF)
- Gemini-based Reranking
- Citation-Aware Answer Generation
- MLflow Experiment Tracking

---

## Key Highlights

✅ Hybrid Retrieval (BM25 + Vector Search)

✅ Gemini-Based Reranking

✅ Citation-Aware Responses

✅ Qdrant Vector Database

✅ MLflow Experiment Tracking

✅ Production-Oriented Architecture

## Features

### Data Processing
- Financial 10-K dataset ingestion
- Data validation and cleaning
- Adaptive chunking with overlap
- Parent-child document structure
- Metadata enrichment

### Retrieval Pipeline
- Dense retrieval using Gemini Embeddings
- Sparse retrieval using BM25
- Hybrid retrieval architecture
- Reciprocal Rank Fusion (RRF)
- Gemini-powered reranking

### Answer Generation
- Context-aware answer generation
- Citation support
- Hallucination reduction through grounded retrieval
- Financial question answering

### Evaluation & Monitoring
- Retrieval evaluation metrics
- MLflow experiment tracking
- Reproducible experimentation
- Performance comparison across retrieval strategies

---

## Architecture

```text
Financial Documents
        │
        ▼
Data Cleaning & Validation
        │
        ▼
Adaptive Chunking
        │
 ┌──────┴──────┐
 │             │
 ▼             ▼
BM25      Gemini Embeddings
Index            │
 │               ▼
 │          Qdrant Vector DB
 └──────┬────────┘
        ▼
 Hybrid Retrieval
        ▼
 Reciprocal Rank Fusion
        ▼
 Gemini Reranker
        ▼
 Context Assembly
        ▼
 Gemini LLM
        ▼
 Answer + Citations
        ▼
 Evaluation + MLflow
```

---

## Tech Stack

### LLM & Embeddings
- Google Gemini
- Gemini Embedding Models

### Vector Database
- Qdrant

### Retrieval
- BM25
- Hybrid Search
- Reciprocal Rank Fusion (RRF)

### Experiment Tracking
- MLflow

### Data Processing
- Pandas
- NumPy

### Development Environment
- Python
- Jupyter Notebook

---

## Retrieval Workflow

### 1. Query Processing

The user question is converted into embeddings using Gemini Embedding Models.

### 2. Hybrid Retrieval

Two retrieval systems run in parallel:

#### Dense Retrieval
- Gemini Embeddings
- Qdrant Vector Search

#### Sparse Retrieval
- BM25 Keyword Search

### 3. Reciprocal Rank Fusion

Results from both retrievers are merged using RRF to improve recall and ranking quality.

### 4. Gemini Reranking

Gemini evaluates retrieved chunks and reranks them according to their relevance to the user's question.

### 5. Context Construction

The highest-ranked chunks are assembled into the final context.

### 6. Answer Generation

Gemini generates a grounded answer using the retrieved context and provides source citations.

---

## Metadata Support

Each chunk is enriched with metadata such as:

- Company Name
- Ticker Symbol
- Filing Information
- Parent Document Reference
- Chunk Identifier

This metadata enables better traceability and supports future metadata-based filtering strategies.

---

## Project Structure

```text
Financial_QA_10K_Advanced_Hybrid_RAG_Gemini_Qdrant.ipynb

├── Data Validation
├── Adaptive Chunking
├── Parent-Child Documents
├── Gemini Embeddings
├── Qdrant Vector Storage
├── BM25 Retrieval
├── Hybrid Search
├── Reciprocal Rank Fusion
├── Gemini Reranking
├── Answer Generation
├── Citation Generation
├── Evaluation
└── MLflow Tracking
```

---

## Why Hybrid RAG?

Financial documents contain both:

- Exact financial terminology
- Long-form semantic information

### BM25 Strengths

- Exact keyword matching
- Company names
- Ticker symbols
- Financial metrics
- Numerical values

### Vector Search Strengths

- Semantic understanding
- Natural language queries
- Synonym matching
- Conceptual similarity

Combining both methods improves retrieval accuracy and robustness.

---

## Example Questions

- What were Nvidia's major risk factors?
- How did Microsoft describe its cloud growth strategy?
- What were Apple's primary revenue drivers?
- What supply-chain risks did Tesla mention?
- How did Amazon discuss operating expenses?

---

## Evaluation

The system evaluates:

### Retrieval Metrics

- Hit@K
- Recall@K
- Ranking Quality

### Generation Quality

- Grounded responses
- Citation correctness
- Context relevance

All experiments are tracked using MLflow for reproducibility and comparison.

---

## Future Improvements

- Metadata-based filtering
- Query rewriting and expansion
- Contextual compression
- Agentic RAG workflows
- LangGraph orchestration
- Multi-document reasoning
- Advanced observability with Langfuse or Phoenix

---

## Results

This project demonstrates:

- Advanced Hybrid RAG architecture
- Dense + Sparse Retrieval
- RRF-based Fusion
- LLM Reranking
- Citation-Aware Generation
- Experiment Tracking with MLflow

The architecture is designed to resemble real-world enterprise RAG systems used in financial document intelligence applications.

---

## Author

**Khaja Abdul Samad**

AI Engineer | Generative AI | RAG Systems | Agentic AI

- BS Artificial Intelligence
- Experience building production-ready AI applications
- Focused on RAG, Agentic Workflows, LLM Engineering, and Cloud AI Solutions
