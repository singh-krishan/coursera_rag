# Assignment 5: Improving a RAG System - Cost Monitoring, Tracing, and Performance Optimization

This is the final assignment of the RAG course, focusing on optimizing and monitoring a production-ready RAG system for Fashion Forward Hub. The assignment addresses real-world challenges of cost management, performance optimization, and system observability in RAG applications.

## Directory Structure

```
assignment_5/
  ├── C1M5_Assignment.ipynb      # Main Jupyter notebook for the assignment
  ├── dataset/
  │   ├── clothes.csv             # Clothing dataset (4.1MB)
  │   ├── clothes_json.joblib     # Processed clothing data (3.6MB)
  │   ├── clothing_ft_format.csv  # Fine-tuning formatted dataset (751KB)
  │   └── faq.joblib             # FAQ dataset for evaluation
  ├── unittests.py               # Comprehensive unit tests (14KB, 369 lines)
  ├── utils.py                   # Advanced utility functions (29KB, 664 lines)
  ├── flask_app.py               # Flask application for serving the vector database
  └── weaviate_server.py         # Weaviate server configuration
```

## Project Overview

This assignment simulates a real-world scenario where a successful RAG chatbot at Fashion Forward Hub faces operational challenges:

### 🚨 **Business Challenges Addressed:**
1. **Rising Operational Costs** - Need for cost monitoring and optimization
2. **High Response Times** - Performance optimization for better user experience
3. **Lack of Observability** - Implementation of comprehensive tracing system

### 🎯 **Core Objectives:**
- Monitor and control costs and response times effectively
- Enhance prompts to balance cost, performance, and speed
- Implement comprehensive tracing for system observability
- Optimize the RAG framework for production use

## Key Technical Components

### 1. **Cost Monitoring & Analysis**
- **Token Usage Tracking**: Monitor input/output tokens for cost calculation
- **Model Cost Comparison**: Compare costs between different LLM models
- **Cost Per Query Analysis**: Track operational costs at query level
- **Budget Optimization**: Strategies for reducing operational expenses

### 2. **Phoenix Tracing Integration**
- **OpenTelemetry Integration**: Complete observability setup
- **Span Tracking**: Monitor individual operations and their performance
- **Cost Per Operation**: Track costs at the operation level
- **Performance Metrics**: Response time, token usage, and success rates

### 3. **Advanced Task Routing**
- **Improved Query Classification**: Better routing between FAQ and product queries
- **Enhanced Decision Logic**: Optimized decision trees for task routing
- **Performance Optimization**: Faster response times through better routing

### 4. **Metadata-Based Filtering**
- **Dynamic Filter Generation**: Create filters from natural language queries
- **Product Search Optimization**: Enhanced metadata extraction and filtering
- **Context Optimization**: Better context generation for improved responses

### 5. **Prompt Engineering & Optimization**
- **Response Time Optimization**: Streamlined prompts for faster generation
- **Cost-Performance Balance**: Optimized prompts that maintain quality while reducing costs
- **Model Selection Strategy**: Choose appropriate models based on query complexity

## Learning Objectives

By completing this assignment, you will learn to:

1. **Production RAG Challenges**:
   - Understand real-world operational challenges in RAG systems
   - Learn cost optimization strategies for LLM-based applications
   - Implement monitoring and observability in production systems

2. **System Observability**:
   - Set up comprehensive tracing with Phoenix and OpenTelemetry
   - Monitor system performance and identify bottlenecks
   - Track costs and optimize resource usage

3. **Performance Optimization**:
   - Optimize prompts for speed and cost efficiency
   - Implement efficient task routing and decision logic
   - Balance quality, speed, and cost in RAG systems

4. **Advanced RAG Techniques**:
   - Implement sophisticated metadata filtering
   - Optimize context generation and retrieval
   - Handle complex multi-step reasoning tasks

## Technical Stack

### **Core Technologies:**
- **Vector Database**: Weaviate for semantic search and storage
- **LLM Integration**: Together AI with Llama models
- **Tracing**: Phoenix with OpenTelemetry for observability
- **Data Processing**: Pandas, joblib for data management
- **Web Framework**: Flask for API services

### **AI/ML Components:**
- **Language Models**: 
  - meta-llama/Llama-3.2-3B-Instruct-Turbo (cost-optimized)
  - meta-llama/Meta-Llama-3.1-8B-Instruct-Turbo (performance-optimized)
- **Embeddings**: Vector embeddings for semantic search
- **Retrieval**: Hybrid search with metadata filtering

## Dataset Information

### **Fashion Forward Hub Dataset:**
- **Products Database**: 4.1MB clothing dataset with rich metadata
- **Features**: Gender, category, subcategory, color, season, price, brand
- **Size**: Comprehensive product catalog for e-commerce simulation
- **FAQ Database**: Customer service questions and answers

## Exercises Overview

### **Exercise 1: Task Classification Optimization**
- Refactor the function to decide between FAQ and product-related questions
- Improve accuracy and reduce response time
- Implement better decision logic

### **Exercise 2: FAQ Query Optimization**
- Optimize FAQ querying for faster responses
- Implement efficient retrieval strategies
- Balance accuracy with speed

### **Exercise 3: Creative vs Technical Query Classification**
- Improve decision logic for product query types
- Optimize routing for different query complexities
- Implement cost-aware routing

### **Exercise 4: Metadata-Based Filtering**
- Implement advanced metadata extraction from queries
- Create dynamic filters for product search
- Optimize filtering for performance and accuracy

## Key Features

### **🔍 Advanced Query Processing:**
- Intelligent task routing between FAQ and product queries
- Context-aware response generation
- Metadata extraction and filtering

### **💰 Cost Management:**
- Real-time cost tracking and monitoring
- Token usage optimization
- Model selection based on cost-performance ratio

### **📊 Comprehensive Tracing:**
- End-to-end request tracing with Phoenix
- Performance metrics and bottleneck identification
- Cost attribution at operation level

### **⚡ Performance Optimization:**
- Response time optimization strategies
- Efficient prompt engineering
- Streamlined processing pipelines

## Usage Instructions

### **Setup:**
1. Install required dependencies
2. Start Weaviate server and Flask application
3. Initialize Phoenix tracing system
4. Load datasets and configure vector database

### **Running the Assignment:**
1. Open `C1M5_Assignment.ipynb` in JupyterLab
2. Follow the step-by-step exercises
3. Monitor costs and performance in Phoenix UI
4. Implement optimization strategies

### **Monitoring:**
- Access Phoenix UI for real-time tracing: `http://localhost:6006/`
- Monitor costs, performance, and system health
- Analyze traces for optimization opportunities

## Requirements

```
weaviate-client
together
opentelemetry-api
arize-phoenix
pandas
joblib
flask
ipywidgets
markdown
httpx
openai
```

## Assignment Structure

The notebook is organized into 7 main sections:
1. **Introduction & Setup** - Environment and tracing configuration
2. **Database Recap** - Understanding the data structures
3. **LLM Integration** - Enhanced model calls with tracing
4. **Task Handling Optimization** - Improved routing and decision logic
5. **Metadata Retrieval** - Advanced filtering and search
6. **Integration** - Complete system integration
7. **ChatBot Interface** - Production-ready chatbot implementation

## Success Metrics

### **Performance Targets:**
- Response time under 3 seconds for standard queries
- Cost reduction of 20-30% through optimization
- 95%+ accuracy in task classification
- Complete traceability for all operations

### **Key Improvements:**
- Optimized prompt engineering for faster responses
- Intelligent model selection based on query complexity
- Comprehensive cost monitoring and optimization
- Production-ready observability and monitoring

This assignment represents the culmination of the RAG course, providing hands-on experience with real-world challenges in deploying and optimizing RAG systems at scale.