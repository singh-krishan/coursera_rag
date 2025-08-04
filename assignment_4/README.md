# Assignment 4: Developing a RAG-based Chatbot for Fashion Forward Hub

This project implements a sophisticated Retrieval-Augmented Generation (RAG) system for an online clothing store chatbot. The assignment focuses on building a production-ready chatbot that can handle FAQ queries, product recommendations, and creative outfit suggestions using advanced RAG techniques.

## Directory Structure

```
assignment_4/
  ├── C1M4_Assignment.ipynb      # Main Jupyter notebook for the assignment
  ├── dataset/
  │   ├── clothes.csv             # Clothing dataset (4.1MB)
  │   ├── clothes_json.joblib     # Processed clothing data (3.6MB)
  │   └── faq.joblib             # FAQ dataset for customer support
  ├── clothing_ft_format.csv      # Fine-tuning dataset in CSV format
  ├── unittests.py                # Unit tests for all functions
  ├── utils.py                    # Utility functions for LLM calls and chatbot
  ├── flask_app.py                # Flask application for serving the system
  └── weaviate_server.py          # Weaviate server configuration
```

## Dataset

### **Products Database**
- **clothes.csv**: 4.1MB clothing dataset with detailed product information
- **clothes_json.joblib**: Processed clothing data in JSON format
- **Product Features**:
  - Gender (Men, Women, Unisex)
  - Master Category (Apparel, Footwear)
  - Sub Category (Topwear, Bottomwear, etc.)
  - Article Type (Shirts, Jackets, etc.)
  - Base Colour, Season, Year, Usage
  - Product Display Name, Price, Product ID

### **FAQ Database**
- **faq.joblib**: Customer support FAQ dataset
- **Structure**: List of dictionaries with question, answer, and type
- **Purpose**: Handle common customer inquiries and support questions

## Main Components

### 1. Task Routing System

#### **Exercise 1: Query Classification**
```python
def check_if_faq_or_product(query: str) -> str
```
- **Purpose**: Determines if a user query is FAQ or Product-related
- **Output**: Returns "FAQ" or "Product" classification
- **Features**: Hardcoded prompt with examples for accurate classification
- **Use Case**: Routes queries to appropriate handling systems

#### **Exercise 2: FAQ Question Handling**
```python
def answer_faq_question(query: str, faq_data: list) -> str
```
- **Purpose**: Answers FAQ questions using the FAQ database
- **Method**: Searches through FAQ data for relevant answers
- **Output**: Provides accurate customer support responses

#### **Exercise 3: Query Nature Analysis**
```python
def decide_query_nature(query: str) -> str
```
- **Purpose**: Determines if a product query is creative or technical
- **Output**: Returns "Creative" or "Technical" classification
- **Use Case**: Adjusts LLM parameters based on query type

#### **Exercise 4: Parameter Retrieval**
```python
def get_parameters_for_task(query_nature: str) -> dict
```
- **Purpose**: Retrieves appropriate LLM parameters for different query types
- **Parameters**: Temperature, top_p, max_tokens based on query nature
- **Optimization**: Adjusts settings for best response quality

### 2. Metadata Generation and Filtering

#### **Exercise 5: Metadata Generation**
```python
def generate_metadata_from_query(query: str) -> dict
```
- **Purpose**: Extracts product metadata from user queries
- **Features**: Gender, category, color, season, usage extraction
- **Output**: Structured metadata for product filtering
- **Use Case**: Enables precise product recommendations

### 3. Product Retrieval and Context Generation

#### **Product Collection Integration**
- **Weaviate Integration**: Connects to product vector database
- **Metadata Filtering**: Filters products based on extracted metadata
- **Context Generation**: Creates rich context for LLM responses

### 4. Complete RAG System

#### **Main Function**
```python
def fashion_forward_hub_chatbot(query: str) -> str
```
- **Purpose**: Complete chatbot function that handles all query types
- **Features**:
  - Query classification and routing
  - FAQ handling
  - Product recommendations
  - Creative outfit suggestions
  - JSON response generation
- **Output**: Structured responses with product information

#### **Chatbot Interface**
- **Interactive Widget**: User-friendly chat interface
- **Real-time Responses**: Immediate query processing
- **Product Display**: Shows relevant products with images
- **Conversation Memory**: Maintains chat context

## Key Features

### **Advanced Task Routing**
- **Query Classification**: Automatically categorizes user inputs
- **Conditional Processing**: Different handling for FAQ vs Product queries
- **Parameter Optimization**: Adjusts LLM settings based on query type

### **Intelligent Product Recommendations**
- **Metadata Extraction**: Automatically identifies product preferences
- **Vector Search**: Uses semantic similarity for product matching
- **Contextual Filtering**: Combines metadata and vector search

### **JSON Response Generation**
- **Structured Output**: Generates valid JSON with product information
- **Rich Metadata**: Includes price, category, color, and usage details
- **Processing Ready**: Output formatted for further processing

### **Creative and Technical Query Handling**
- **Creative Queries**: Outfit suggestions, style recommendations
- **Technical Queries**: Product specifications, availability, pricing
- **Parameter Adaptation**: Different LLM settings for each type

### **Production-Ready Chatbot**
- **Flask Integration**: Web-based chat interface
- **Error Handling**: Robust error management and logging
- **Scalable Architecture**: Designed for production deployment

## How to Use

1. **Setup Environment**: Ensure Weaviate server is running on port 8079
2. **Load Data**: The clothing and FAQ datasets are pre-loaded
3. **Run Notebook**: Execute `C1M4_Assignment.ipynb` cells in order
4. **Implement Functions**: Complete the 5 exercises for different components
5. **Test Chatbot**: Use the interactive widget to test the complete system

## Requirements

- Python 3.8+
- JupyterLab
- weaviate-client, joblib, requests, flask, httpx, openai, together

Install dependencies with:
```bash
pip install weaviate-client joblib requests flask httpx openai together
```

## Learning Objectives

By completing this assignment, you will:

1. **Master Task Routing**: Implement intelligent query classification
2. **Build Production Chatbots**: Create real-world RAG applications
3. **Handle Multiple Query Types**: FAQ, product, creative, and technical queries
4. **Generate Structured Responses**: JSON output with rich metadata
5. **Optimize LLM Parameters**: Adaptive settings based on query nature
6. **Integrate Vector Databases**: Complete Weaviate integration

## Technical Highlights

### **Query Classification System**
- Hardcoded prompts with examples
- Binary classification (FAQ vs Product)
- Query nature analysis (Creative vs Technical)
- Parameter optimization based on query type

### **Metadata Extraction**
- Automatic extraction of product preferences
- Gender, category, color, season identification
- Usage and occasion detection
- Structured metadata for filtering

### **Product Recommendation Engine**
- Vector similarity search
- Metadata-based filtering
- Contextual information generation
- Rich product information output

### **Production Chatbot Features**
- Interactive web interface
- Real-time query processing
- Product image display
- Conversation memory
- Error handling and logging

## Business Application

### **Fashion Forward Hub Use Cases**
- **Customer Support**: FAQ handling and product inquiries
- **Product Discovery**: Intelligent product recommendations
- **Style Advice**: Creative outfit suggestions
- **Shopping Assistance**: Price, availability, and specification queries

### **Scalable Architecture**
- **Modular Design**: Separate components for different functions
- **Error Handling**: Robust error management
- **Performance Optimization**: Efficient query processing
- **User Experience**: Intuitive chat interface

## Notes

- The Weaviate server must be running for product search functionality
- All datasets are pre-processed and ready for use
- The chatbot supports both FAQ and product-related queries
- JSON responses are structured for easy integration with web applications
- The assignment demonstrates real-world RAG system implementation

## Credits

- Dataset: Fashion Forward Hub clothing database
- Vector Database: [Weaviate](https://weaviate.io/)
- LLM Integration: Together AI and OpenAI APIs
- Assignment: Coursera RAG Course Module 4 