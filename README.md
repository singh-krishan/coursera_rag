# Coursera RAG Course - Complete Project Repository

This repository contains all assignments and projects from the Coursera course on **Retrieval-Augmented Generation (RAG) Systems**. The course covers the complete journey from basic RAG implementation to production-ready systems with advanced monitoring and optimization.

## 🎯 Course Overview

This comprehensive course teaches you to build, deploy, and optimize RAG systems through hands-on projects. You'll progress from basic retrieval methods to sophisticated production systems with cost monitoring, tracing, and performance optimization.

## 📁 Project Structure

```
coursera_rag/
├── assignment_1/                 # Basic RAG System with News Dataset
│   ├── C1M1_Assignment.ipynb     # News-based RAG implementation
│   ├── embeddings.joblib         # Precomputed embeddings
│   ├── news_data_dedup.csv       # News dataset
│   ├── unittests.py              # Unit tests
│   ├── utils.py                  # Utility functions
│   └── README.md                 # Detailed documentation
│
├── assignment_2/                 # Advanced Retrieval Methods
│   ├── C1M2_Assignment.ipynb     # BM25, Semantic Search, RRF
│   ├── embeddings.joblib         # Precomputed embeddings
│   ├── news_data_dedup.csv       # News dataset
│   ├── unittests.py              # Unit tests
│   ├── utils.py                  # Utility functions
│   └── README.md                 # Detailed documentation
│
├── assignment_3/                 # Weaviate Vector Database Integration
│   ├── C1M3_Assignment.ipynb     # Vector database RAG system
│   ├── data/bbc_data.joblib      # BBC News dataset
│   ├── unittests.py              # Unit tests
│   ├── utils.py                  # Utility functions
│   ├── flask_app.py              # Flask application
│   ├── weaviate_server.py        # Weaviate server config
│   └── README.md                 # Detailed documentation
│
├── assignment_4/                 # RAG-based Chatbot Development
│   ├── C1M4_Assignment.ipynb     # Fashion Forward Hub chatbot
│   ├── dataset/                  # Clothing and FAQ datasets
│   ├── clothing_ft_format.csv    # Fine-tuning dataset
│   ├── unittests.py              # Unit tests
│   ├── utils.py                  # Utility functions
│   ├── flask_app.py              # Flask application
│   ├── weaviate_server.py        # Weaviate server config
│   └── README.md                 # Detailed documentation
│
├── assignment_5/                 # Production RAG System Optimization
│   ├── C1M5_Assignment.ipynb     # Cost monitoring and tracing
│   ├── dataset/                  # Complete datasets
│   ├── unittests.py              # Comprehensive tests
│   ├── utils.py                  # Advanced utilities
│   ├── flask_app.py              # Flask application
│   ├── weaviate_server.py        # Weaviate server config
│   └── README.md                 # Detailed documentation
│
├── utils.py                      # Shared utility functions
└── README.md                     # This overview file
```

## 🚀 Learning Journey

### **Assignment 1: Basic RAG System**
- **Focus**: Introduction to RAG concepts with news dataset
- **Key Skills**: Document retrieval, prompt engineering, LLM integration
- **Technologies**: SentenceTransformers, Together AI, pandas
- **Outcome**: Working RAG system that retrieves relevant news articles

**Key Features:**
- Document retrieval using semantic similarity
- News article formatting and context generation
- Interactive widget for experimentation
- Comparison between RAG and non-RAG responses

### **Assignment 2: Advanced Retrieval Methods**
- **Focus**: Multiple retrieval algorithms and their combination
- **Key Skills**: BM25, semantic search, Reciprocal Rank Fusion (RRF)
- **Technologies**: BM25, vector embeddings, cosine similarity
- **Outcome**: Enhanced retrieval system with multiple strategies

**Key Features:**
- BM25 keyword-based retrieval
- Semantic search with vector embeddings
- Reciprocal Rank Fusion for result combination
- Performance comparison across retrieval methods

### **Assignment 3: Vector Database Integration**
- **Focus**: Production-ready RAG with Weaviate vector database
- **Key Skills**: Vector database operations, metadata filtering, hybrid search
- **Technologies**: Weaviate, Flask, OpenTelemetry
- **Outcome**: Scalable RAG system with advanced search capabilities

**Key Features:**
- Weaviate vector database integration
- Multiple retrieval methods (semantic, BM25, hybrid)
- Metadata filtering and reranking
- Production-ready API with Flask

### **Assignment 4: RAG-based Chatbot**
- **Focus**: Building intelligent chatbots with task routing
- **Key Skills**: Query classification, metadata extraction, context generation
- **Technologies**: Weaviate, advanced prompting, task routing
- **Outcome**: Production-ready chatbot for e-commerce

**Key Features:**
- Intelligent task routing (FAQ vs Product queries)
- Metadata-based product filtering
- Creative vs technical query handling
- Complete chatbot interface

### **Assignment 5: Production Optimization**
- **Focus**: Cost monitoring, performance optimization, system observability
- **Key Skills**: Cost analysis, tracing, prompt optimization
- **Technologies**: Phoenix, OpenTelemetry, cost monitoring
- **Outcome**: Production-optimized RAG system with full observability

**Key Features:**
- Comprehensive cost monitoring and analysis
- Phoenix tracing with OpenTelemetry
- Performance optimization strategies
- Production-ready monitoring and observability

## 🛠 Technical Stack

### **Core Technologies**
- **Vector Database**: Weaviate for semantic search and storage
- **Language Models**: Together AI (Llama models)
- **Embeddings**: SentenceTransformers (BAAI/bge-base-en-v1.5)
- **Web Framework**: Flask for API services
- **Data Processing**: Pandas, NumPy, joblib
- **Testing**: Comprehensive unit tests for all functions

### **Advanced Technologies**
- **Tracing**: Phoenix with OpenTelemetry for observability
- **Cost Monitoring**: Token usage tracking and cost analysis
- **Retrieval Algorithms**: BM25, semantic search, hybrid search, RRF
- **Task Routing**: Intelligent query classification and routing
- **Metadata Filtering**: Dynamic filter generation and application

## 📊 Datasets

### **News Datasets**
- **assignment_1/2**: News headlines from 2024 (BBC News and other sources)
- **assignment_3**: BBC News dataset (75,256 articles with rich metadata)

### **E-commerce Datasets**
- **assignment_4/5**: Fashion Forward Hub clothing dataset (4.1MB)
  - Product information: gender, category, color, season, price
  - FAQ dataset for customer support
  - Fine-tuning formatted data

## 🎓 Learning Outcomes

By completing this course, you will have mastered:

### **RAG Fundamentals**
- Understanding of retrieval-augmented generation concepts
- Document retrieval and similarity search techniques
- Prompt engineering and context generation
- LLM integration and response generation

### **Advanced RAG Techniques**
- Multiple retrieval algorithms (BM25, semantic search, hybrid)
- Vector database integration and operations
- Metadata filtering and reranking
- Task routing and query classification

### **Production Skills**
- Cost monitoring and optimization
- System observability and tracing
- Performance optimization strategies
- Production-ready deployment

### **Real-world Applications**
- E-commerce chatbot development
- News analysis and summarization
- Customer support automation
- Content recommendation systems

## 🚀 Getting Started

### **Prerequisites**
```bash
# Python 3.8+
pip install pandas numpy scikit-learn sentence-transformers joblib requests together ipywidgets python-dateutil weaviate-client flask opentelemetry-api arize-phoenix
```

### **Quick Start**
1. **Clone the repository**
   ```bash
   git clone https://github.com/singh-krishan/coursera_rag.git
   cd coursera_rag
   ```

2. **Start with Assignment 1**
   - Open `assignment_1/C1M1_Assignment.ipynb`
   - Follow the step-by-step instructions
   - Experiment with the interactive widgets

3. **Progress through assignments**
   - Each assignment builds upon the previous one
   - Complete exercises and tests
   - Review detailed README files for each assignment

## 📈 Project Progression

| Assignment | Focus | Complexity | Key Outcome |
|------------|-------|------------|-------------|
| 1 | Basic RAG | Beginner | Working RAG system |
| 2 | Advanced Retrieval | Intermediate | Multiple retrieval methods |
| 3 | Vector Database | Intermediate | Production-ready RAG |
| 4 | Chatbot Development | Advanced | Intelligent chatbot |
| 5 | Production Optimization | Expert | Optimized production system |

## 🔍 Key Features Across All Assignments

### **Comprehensive Testing**
- Unit tests for all core functions
- Automated grading support
- Performance benchmarking

### **Interactive Experimentation**
- Jupyter widgets for real-time testing
- Comparison tools for different approaches
- Visual feedback and results display

### **Production Readiness**
- Scalable architecture design
- Error handling and logging
- API endpoints and web interfaces

### **Documentation**
- Detailed README files for each assignment
- Code comments and explanations
- Usage examples and best practices

## 🤝 Contributing

This repository contains educational assignments from the Coursera RAG course. While the core assignments are fixed, you can:

- Experiment with different datasets
- Implement additional retrieval methods
- Optimize performance and cost
- Share insights and improvements

## 📚 Additional Resources

- **Course Materials**: Coursera RAG Course
- **Documentation**: Individual assignment README files
- **Technologies**: 
  - [Weaviate Documentation](https://weaviate.io/developers/weaviate)
  - [Together AI Documentation](https://docs.together.ai/)
  - [Phoenix Documentation](https://arize.com/docs/phoenix)

## 🎯 Success Metrics

### **Technical Proficiency**
- ✅ Implemented all core RAG components
- ✅ Mastered multiple retrieval algorithms
- ✅ Built production-ready systems
- ✅ Optimized for cost and performance

### **Real-world Application**
- ✅ Developed e-commerce chatbot
- ✅ Implemented news analysis system
- ✅ Created customer support automation
- ✅ Built content recommendation engine

### **Production Skills**
- ✅ Cost monitoring and optimization
- ✅ System observability and tracing
- ✅ Performance optimization
- ✅ Scalable architecture design

---

**🎉 Congratulations on completing the Coursera RAG Course!**

This repository represents a comprehensive journey from basic RAG concepts to production-ready systems. Each assignment builds upon the previous one, providing hands-on experience with real-world challenges and solutions in the field of Retrieval-Augmented Generation.
