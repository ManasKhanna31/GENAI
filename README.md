# GENAI
Intelligent Study Material Query System using RAG

An AI-powered conversational learning platform that enables students to interact with study materials using natural language queries. The system uses Retrieval-Augmented Generation (RAG) to provide context-aware answers from uploaded PDF and DOCX documents.

📌 Overview

Traditional document searching is time-consuming and inefficient, especially for students dealing with lengthy study material. This project solves that problem by combining:

Semantic Search
Vector Databases (FAISS)
Embedding Models
Large Language Models (LLMs)

The platform converts uploaded documents into an intelligent searchable knowledge base and allows users to ask questions conversationally.

🚀 Features
📄 Upload and process PDF & DOCX files
💬 Natural language question-answering
🔍 Semantic search using embeddings
🧠 Context-aware AI-generated responses
⚡ Fast retrieval using FAISS vector database
📚 Interactive study material exploration
🏗️ System Architecture

The RAG pipeline follows these steps:

Upload Documents
Extract Text
Chunk Text
Generate Embeddings
Store in FAISS Vector Database
Retrieve Relevant Chunks
Generate Answers using LLM
🛠️ Technologies Used
Programming Language
Python
Libraries & Frameworks
LangChain
FAISS
HuggingFace Transformers
Sentence Transformers
Embedding Model
sentence-transformers/all-MiniLM-L6-v2
Text Chunking
RecursiveCharacterTextSplitter
Vector Database
FAISS
📂 Project Workflow
Step 1: Document Upload

Users upload study material in:

PDF format
DOCX format
Step 2: Text Extraction

The system extracts textual content from uploaded files.

Step 3: Text Chunking

Documents are split into smaller chunks for efficient retrieval.

Example configuration:

splitter = RecursiveCharacterTextSplitter(
    chunk_size=200,
    chunk_overlap=50
)
Step 4: Embedding Generation

Each chunk is converted into vector embeddings using HuggingFace embeddings.

embedding_model = HuggingFaceEmbeddings(
    model_name="sentence-transformers/all-MiniLM-L6-v2"
)
Step 5: FAISS Vector Store Creation
vectorstore = FAISS.from_documents(
    chunks,
    embedding_model
)
Step 6: Semantic Retrieval

Relevant chunks are retrieved based on query similarity.

docs = vectorstore.similarity_search(
    question,
    k=3
)
Step 7: Response Generation

The retrieved context is passed to the LLM to generate grounded answers.

📊 Experimental Results

The project evaluated different chunk sizes to analyze retrieval performance.

Parameter	Chunk Size 200	Chunk Size 500
Retrieval Precision	High	Medium
Context Coverage	Low	High
Retrieval Noise	Low	Medium
Answer Detail	Concise	Detailed
Processing Speed	Faster	Slower
Best Use Case	Fact Q&A	Conceptual Learning
Key Insights
Smaller chunks improve factual precision.
Larger chunks provide richer context.
Hybrid chunking offers balanced performance.
🎯 Objectives

The system was designed with the following goals:

Intelligent document querying
Conversational AI for learning
Semantic similarity search
Multi-format document support
Context-grounded responses
🔮 Future Scope

The project can be extended with:

Hybrid Chunking
Voice AI Tutor
Personalized Learning
Multimodal RAG
Cloud Deployment
✅ Conclusion

This project demonstrates how Retrieval-Augmented Generation (RAG) can transform traditional study material into an interactive AI-powered learning assistant. By integrating semantic retrieval with LLMs, the system provides accurate, fast, and context-aware answers directly from educational documents.
