# Suncorp Interview Prep - RAG Agent

A sophisticated Retrieval-Augmented Generation (RAG) system built with LangChain and LangGraph for interview preparation and document analysis. This project demonstrates an intelligent agent that can process multiple documents, answer questions, and provide relevant information for interview scenarios.

## 🚀 Features

### Core Functionality
- **Multi-Document RAG**: Process and query multiple PDF documents simultaneously
- **Intelligent Query Processing**: Automatic query rewriting and relevance assessment
- **Document Relevance Grading**: AI-powered evaluation of retrieved document relevance
- **Conversation Logging**: Comprehensive logging of all interactions and metrics
- **Vector Database**: ChromaDB integration for efficient document storage and retrieval

### Advanced Capabilities
- **Agentic Decision Making**: The system decides when to retrieve information vs. provide direct answers
- **Query Transformation**: Automatically rewrites queries when retrieved documents are irrelevant
- **Performance Metrics**: Tracks retrieval accuracy and provides detailed analytics
- **Streaming Responses**: Real-time response generation with progress tracking

## 📁 Project Structure

```
suncorp-interview-prep/
├── chroma_db/                    # Vector database storage
├── logs/                         # Conversation and performance logs
├── pdfs/                         # Source documents
│   ├── 20250806_CV_Xiaoshi Lu (Alexandra).pdf
│   └── suncorp_job_description.pdf
├── suncorp-interview-prep.ipynb              # Single document RAG implementation
├── suncorp-interview-prep-multi-files.ipynb  # Multi-document RAG implementation
├── original-langgraph-agentic-rag.ipynb      # Original reference implementation
├── requirements.txt              # Python dependencies
├── plan.txt                      # Future development plans
└── README.md                     # This file
```

## 🛠️ Installation

### Prerequisites
- Python 3.8+
- OpenAI API key

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd suncorp-interview-prep
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   ```

4. **Prepare documents**
   Place your PDF documents in the `pdfs/` directory.

## 📖 Usage

### Single Document RAG (`suncorp-interview-prep.ipynb`)
This implementation focuses on querying a single document (CV) with intelligent retrieval and response generation.

**Key Features:**
- Processes individual CV documents
- Intelligent query routing
- Relevance assessment
- Detailed conversation logging

### Multi-Document RAG (`suncorp-interview-prep-multi-files.ipynb`)
This enhanced version can handle multiple documents simultaneously, making it perfect for interview scenarios where you need to cross-reference different sources.

**Key Features:**
- Multi-document processing
- Cross-document information synthesis
- Enhanced query transformation
- Comprehensive performance metrics

### Running the System

1. **Open the desired notebook** in Jupyter or VS Code
2. **Execute all cells** to set up the environment
3. **Run the test cases** to see the system in action

Example usage:
```python
# Initialize the system
config = {"configurable": {"thread_id": "interview", "questions": []}}
logs = []

# Ask questions
deal_with_single_question(logs, graph, "What are Xiaoshi Lu's technical skills?", config)
deal_with_single_question(logs, graph, "Is she eligible for the Suncorp position?", config)
```

## 🔧 Technical Architecture

### Core Components

1. **Vector Store (ChromaDB)**
   - Document embedding and storage
   - Semantic search capabilities
   - Persistent storage with version control

2. **LangGraph Workflow**
   - State management
   - Conditional routing
   - Tool integration

3. **Intelligent Agent**
   - Decision making for retrieval vs. direct response
   - Tool calling capabilities
   - Context-aware responses

4. **Document Processing**
   - PDF loading and chunking
   - Text splitting with overlap
   - Metadata management

### Workflow Steps

1. **Query Input**: User asks a question
2. **Agent Decision**: System decides whether to retrieve documents
3. **Document Retrieval**: If needed, searches vector database
4. **Relevance Assessment**: AI evaluates if retrieved documents are relevant
5. **Query Transformation**: If irrelevant, rewrites the query
6. **Response Generation**: Generates final answer based on context
7. **Logging**: Records all interactions and metrics

## 📊 Performance Metrics

The system tracks several key metrics:
- **Retrieval Count**: Number of document retrievals per conversation
- **Rewrite Count**: Number of query rewrites needed
- **Relevance Percentage**: Accuracy of document retrieval
- **Response Quality**: Based on context relevance

## 🔮 Future Development

According to `plan.txt`, upcoming features include:
- **RAGAS Integration**: Enhanced retriever quality evaluation
- **Advanced Analytics**: More sophisticated performance metrics
- **UI Improvements**: Better visualization of results

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📝 License

This project is for educational and interview preparation purposes.

## 🆘 Troubleshooting

### Common Issues

1. **OpenAI API Key Not Set**
   - Ensure your `.env` file contains the correct API key
   - Check that the key has sufficient credits

2. **ChromaDB Issues**
   - Clear the `chroma_db/` directory if experiencing corruption
   - Ensure write permissions in the project directory

3. **PDF Loading Errors**
   - Verify PDF files are not corrupted
   - Check file paths in the notebook

### Getting Help

If you encounter issues:
1. Check the logs in the `logs/` directory
2. Review the error messages in the notebook output
3. Verify all dependencies are installed correctly

---

**Note**: This system is designed for interview preparation and demonstrates advanced RAG capabilities. It processes real documents (CV and job descriptions) to provide relevant, contextual responses for interview scenarios.
