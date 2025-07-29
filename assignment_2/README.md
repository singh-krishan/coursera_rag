# Assignment 2: Advanced Retrieval Methods in RAG Systems

This project implements and compares different retrieval algorithms for Retrieval-Augmented Generation (RAG) systems. The assignment focuses on enhancing document retrieval by implementing BM25, semantic search using embeddings, and Reciprocal Rank Fusion (RRF) to combine multiple retrieval methods.

## Directory Structure

```
assignment_2/
  ├── C1M2_Assignment.ipynb      # Main Jupyter notebook for the assignment
  ├── embeddings.joblib          # Precomputed embeddings for semantic search
  ├── news_data_dedup.csv        # News dataset (same as assignment_1)
  ├── unittests.py               # Unit tests for retrieval functions
  └── utils.py                   # Utility functions for LLM calls and similarity metrics
```

## Dataset

- **news_data_dedup.csv**: Contains thousands of news headlines and metadata from BBC News and other sources, focused on 2024 events.
- **embeddings.joblib**: Precomputed embeddings using the BAAI/bge-base-en-v1.5 model for semantic search.

## Main Components

### 1. BM25 Retrieval

- **Purpose**: Implements traditional keyword-based retrieval using the BM25 algorithm
- **Function**: `bm25_retrieve(query, top_k)`
- **Features**:
  - Uses the `bm25s` library for efficient BM25 implementation
  - Tokenizes queries and documents for better matching
  - Returns indices of top-k most relevant documents
  - Effective for exact keyword matching and traditional information retrieval

### 2. Semantic Search

- **Purpose**: Implements semantic search using vector embeddings and cosine similarity
- **Function**: `semantic_search_retrieve(query, top_k)`
- **Features**:
  - Uses SentenceTransformer model (BAAI/bge-base-en-v1.5) for generating embeddings
  - Compares query embeddings with precomputed document embeddings
  - Uses cosine similarity to find semantically similar documents
  - Better for understanding context and meaning beyond exact keyword matches

### 3. Reciprocal Rank Fusion (RRF)

- **Purpose**: Combines results from multiple retrieval systems to improve overall performance
- **Function**: `reciprocal_rank_fusion(list1, list2, top_k, K)`
- **Features**:
  - Implements the RRF formula: Score(d) = Σ(1 / (k + rank_r(d)))
  - Combines BM25 and semantic search results
  - Uses parameter K (default 60) to scale rank contributions
  - Provides more robust retrieval by leveraging strengths of different methods

### 4. Enhanced RAG System

- **Purpose**: Integrates multiple retrieval methods into a complete RAG pipeline
- **Functions**:
  - `generate_final_prompt()`: Creates augmented prompts with retrieved documents
  - `llm_call()`: Orchestrates retrieval, formatting, and LLM generation
- **Features**:
  - Supports multiple retrieval functions (BM25, semantic search, RRF)
  - Formats retrieved documents with title, description, published date, and URL
  - Compares responses with and without RAG
  - Interactive widget for experimentation

### 5. Interactive Experimentation

- **Widget**: `display_widget()` provides a user interface to test different retrieval methods
- **Comparison**: Shows results from:
  - RAG with Semantic Search
  - RAG with BM25
  - RAG with Reciprocal Rank Fusion
  - Without RAG (baseline)

## Key Algorithms Implemented

### BM25 Algorithm
- Traditional information retrieval algorithm
- Scores documents based on term frequency, inverse document frequency, and document length
- Effective for keyword-based queries

### Semantic Search
- Uses vector embeddings to capture semantic meaning
- Cosine similarity for comparing query and document vectors
- Better for understanding context and intent

### Reciprocal Rank Fusion
- Combines multiple ranking systems
- Formula: Score(d) = Σ(1 / (k + rank_r(d)))
- Leverages strengths of different retrieval methods

## How to Use

1. **Open `C1M2_Assignment.ipynb` in JupyterLab**
2. **Run cells in order** to:
   - Load the dataset and embeddings
   - Implement BM25 retrieval
   - Implement semantic search
   - Implement Reciprocal Rank Fusion
   - Test the complete RAG system
3. **Experiment with different queries** using the interactive widget
4. **Compare retrieval methods** to understand their strengths and weaknesses

## Requirements

- Python 3.8+
- JupyterLab
- pandas, numpy, scikit-learn, sentence-transformers, joblib, requests, together, ipywidgets, dateutil, bm25s

Install dependencies with:
```bash
pip install pandas numpy scikit-learn sentence-transformers joblib requests together ipywidgets python-dateutil bm25s
```

## Learning Objectives

By completing this assignment, you will:

1. **Understand different retrieval algorithms** and their trade-offs
2. **Implement BM25** for traditional keyword-based retrieval
3. **Implement semantic search** using embeddings and similarity metrics
4. **Implement Reciprocal Rank Fusion** to combine multiple retrieval methods
5. **Compare retrieval performance** across different methods
6. **Analyze when each method works best** for different types of queries

## Testing

- `unittests.py` provides comprehensive test cases for all retrieval functions
- Tests verify correct implementation of BM25, semantic search, and RRF
- Ensures proper handling of edge cases and parameter variations

## Notes

- The LLM is accessed via the Together API (same as assignment_1)
- Precomputed embeddings are provided to speed up semantic search
- The assignment builds upon concepts from assignment_1, focusing on the retrieval component
- Designed for educational purposes as part of a RAG course

## Credits

- Dataset: [Kaggle BBC News Dataset](https://www.kaggle.com/datasets/gpreda/bbc-news)
- Embeddings: BAAI/bge-base-en-v1.5 model
- Assignment: Coursera RAG Course Module 2 