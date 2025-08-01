# Assignment 3: Building RAG Systems with Weaviate Vector Database

This project implements a complete Retrieval-Augmented Generation (RAG) system using the Weaviate vector database API. The assignment focuses on integrating multiple retrieval methods with a vector database to create a production-ready RAG system.

## Directory Structure

```
assignment_3/
  ├── C1M3_Assignment.ipynb      # Main Jupyter notebook for the assignment
  ├── data/
  │   └── bbc_data.joblib        # BBC News dataset (75,256 articles)
  ├── unittests.py                # Unit tests for all retrieval functions
  ├── utils.py                    # Utility functions for LLM calls and data processing
  ├── flask_app.py                # Flask application for serving the vector database
  └── weaviate_server.py          # Weaviate server configuration
```

## Dataset

- **bbc_data.joblib**: Contains 75,256 BBC News articles from 2024 with rich metadata
- **Data Structure**: Each article includes title, pubDate, guid, link, description, article_content, chunk, and chunk_index
- **Vector Dimensions**: 768-dimensional embeddings for semantic search
- **Pre-chunked**: Articles are already processed and chunked for vector database storage

## Main Components

### 1. Weaviate Vector Database Integration

- **Client Connection**: Connects to local Weaviate instance (port 8079)
- **Collection Management**: Loads and manages BBC News collection
- **Vector Operations**: Handles 768-dimensional embeddings for semantic search
- **Metadata Filtering**: Supports filtering by article properties

### 2. Multiple Retrieval Methods

#### **Exercise 1: Metadata Filtering**
```python
def filter_by_metadata(metadata_property: str, values: list[str], collection, limit: int = 5)
```
- Uses `collection.query.fetch_objects` with metadata filters
- Filters by specific properties like title, pubDate, etc.
- Returns objects matching the filter criteria

#### **Exercise 2: Semantic Search**
```python
def semantic_search_retrieve(query: str, collection, top_k: int = 5)
```
- Uses `collection.query.near_text` for vector similarity search
- Leverages 768-dimensional embeddings
- Returns most semantically similar chunks

#### **Exercise 3: BM25 Search**
```python
def bm25_retrieve(query: str, collection, top_k: int = 5)
```
- Uses `collection.query.bm25` for keyword-based search
- Traditional information retrieval algorithm
- Effective for exact keyword matching

#### **Exercise 4: Hybrid Search**
```python
def hybrid_retrieve(query: str, collection, alpha: float = 0.5, top_k: int = 5)
```
- Uses `collection.query.hybrid` to combine semantic and keyword search
- **Alpha parameter**: Balances vector vs keyword search (0.5 = equal weighting)
- Combines strengths of both approaches

#### **Exercise 5: Reranking**
```python
def semantic_search_with_reranking(query: str, rerank_property: str, collection, rerank_query: str = None, top_k: int = 5)
```
- Adds reranking capability to semantic search
- Can rerank based on different properties (title, chunk, etc.)
- Uses separate rerank query if needed

### 3. RAG System Integration

#### **Prompt Generation**
```python
def generate_final_prompt(query: str, top_k: int, retrieve_function: callable, ...)
```
- Integrates retrieved documents into prompt
- Formats documents with title, chunk, pubDate, and URL
- Supports reranking and different retrieval functions

#### **LLM Call Function**
```python
def llm_call(query: str, retrieve_function: callable = None, top_k: int = 5, use_rag: bool = True, ...)
```
- Orchestrates the complete RAG pipeline
- Supports multiple retrieval strategies
- Handles reranking and RAG/non-RAG modes

### 4. Interactive Experimentation

- **Widget Interface**: Compare all retrieval methods side-by-side
- **Real-time Testing**: Test different queries and strategies
- **Performance Comparison**: Evaluate retrieval quality across methods

## Key Features

### **Advanced Retrieval Methods**
- **Semantic Search**: Vector similarity for meaning-based retrieval
- **BM25**: Keyword-based traditional search
- **Hybrid**: Combines both approaches with configurable weighting
- **Reranking**: Post-processes results for better relevance

### **Production-Ready Infrastructure**
- **Weaviate Integration**: Complete vector database implementation
- **Flask Server**: Web interface for vector database operations
- **Error Handling**: Robust error handling and logging
- **Scalable Architecture**: Designed for production deployment

### **Comprehensive Testing**
- **Unit Tests**: Complete test suite for all retrieval functions
- **Integration Tests**: End-to-end RAG system testing
- **Performance Benchmarks**: Compare retrieval methods

## How to Use

1. **Setup Weaviate**: Ensure Weaviate server is running on port 8079
2. **Load Data**: The BBC News dataset is pre-loaded in the collection
3. **Run Notebook**: Execute `C1M3_Assignment.ipynb` cells in order
4. **Implement Functions**: Complete the 5 exercises for different retrieval methods
5. **Test RAG System**: Use the interactive widget to experiment with queries

## Requirements

- Python 3.8+
- JupyterLab
- weaviate-client, joblib, requests, flask, httpx, openai

Install dependencies with:
```bash
pip install weaviate-client joblib requests flask httpx openai
```

## Learning Objectives

By completing this assignment, you will:

1. **Master Weaviate API**: Understand vector database operations
2. **Implement Multiple Retrieval Methods**: Semantic, BM25, hybrid, and reranking
3. **Build Production RAG Systems**: Integrate retrieval with generation
4. **Compare Retrieval Performance**: Evaluate different search strategies
5. **Deploy Vector Database Solutions**: Work with real-world datasets

## Technical Highlights

### **Vector Database Operations**
- Collection management and querying
- Metadata filtering and indexing
- Vector similarity search
- Hybrid search with configurable weights

### **RAG Pipeline Integration**
- Seamless integration of retrieval and generation
- Multiple retrieval strategy support
- Reranking for improved relevance
- Interactive experimentation tools

### **Production Considerations**
- Error handling and logging
- Scalable architecture
- Real-world dataset processing
- Performance optimization

## Notes

- The Weaviate server must be running for the assignment to work
- The BBC News dataset is pre-chunked and vectorized
- All retrieval methods are implemented using Weaviate's native API
- The assignment builds upon concepts from assignments 1 and 2

## Credits

- Dataset: [BBC News Dataset](https://www.kaggle.com/datasets/gpreda/bbc-news)
- Vector Database: [Weaviate](https://weaviate.io/)
- Assignment: Coursera RAG Course Module 3 