# RAG News Assignment

This project is an educational implementation of a simple Retrieval-Augmented Generation (RAG) system using a news dataset. The goal is to enable a language model to answer questions with up-to-date information by retrieving relevant news articles and incorporating them into the model’s prompt.

## Directory Structure

```
assignment_1/
  ├── C1M1_Assignment.ipynb      # Main Jupyter notebook for the assignment
  ├── embeddings.joblib          # Precomputed embeddings for the news dataset
  ├── news_data_dedup.csv        # News dataset (deduplicated)
  ├── unittests.py               # Unit tests for core functions
  └── utils.py                   # Utility functions for retrieval, formatting, and LLM calls
```

## Dataset

- **news_data_dedup.csv**: Contains thousands of news headlines and metadata (title, description, url, published date, etc.) from BBC News and other sources, focused on 2024.

## Main Components

### 1. Retrieval

- Uses precomputed embeddings (`embeddings.joblib`) and a SentenceTransformer model to find the most relevant news articles for a given query.
- The `retrieve` function in `utils.py` returns the indices of the top-k most similar articles.

### 2. Data Formatting

- The `format_relevant_data` function takes a list of news articles and formats them into a readable string, including title, description, published date, and URL.

### 3. Prompt Generation

- The `generate_final_prompt` function combines the user’s query and the formatted relevant news into a single prompt for the language model.

### 4. LLM Integration

- The `generate_with_single_input` function sends the prompt to a large language model (LLM) via the Together API or a proxy endpoint.
- The `llm_call` function orchestrates the retrieval, formatting, and LLM call, supporting both RAG and non-RAG modes for comparison.

### 5. Interactive Widget

- The notebook includes a Jupyter widget (`display_widget`) for experimenting with queries and comparing LLM responses with and without RAG.

### 6. Testing

- `unittests.py` provides test cases for the main functions, ensuring correctness and helping with grading.

## How to Use

1. **Open `C1M1_Assignment.ipynb` in JupyterLab.**
2. **Run the cells in order.**  
   - The notebook will guide you through loading the data, retrieving relevant articles, formatting them, and generating LLM responses.
   - You will implement and test key functions as exercises.
3. **Experiment with your own queries** using the provided widget or by calling `llm_call` directly.

## Requirements

- Python 3.8+
- JupyterLab
- pandas, numpy, scikit-learn, sentence-transformers, joblib, requests, together, ipywidgets, dateutil

Install dependencies with:
```bash
pip install pandas numpy scikit-learn sentence-transformers joblib requests together ipywidgets python-dateutil
```

## Notes

- The LLM is accessed via the Together API. You may need an API key or use the provided proxy.
- The assignment is designed for educational purposes and is part of a course on Retrieval-Augmented Generation (RAG) systems.

## Credits

- Dataset: [Kaggle News Headlines 2024](https://www.kaggle.com/datasets/dylanjcastillo/news-headlines-2024)
- Assignment and code: Coursera RAG Course 