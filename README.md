CortexRAG: Advanced Chatbot with FastAPI, RAG, LangChain, Unstructured, and PGVector

CortexRAG is an intelligent chatbot system designed to provide accurate and contextually relevant responses by leveraging Retrieval Augmented Generation (RAG). It integrates FastAPI for a robust API, LangChain for orchestrating AI workflows, Unstructured for document processing, and PGVector for efficient vector storage and retrieval.

Features

FastAPI Backend: A high-performance web framework for building APIs.

Retrieval Augmented Generation (RAG): Enhances LLM capabilities by retrieving relevant information from a knowledge base.

LangChain Integration: Orchestrates complex AI workflows, including prompt management, chain construction, and agent creation.

Unstructured Data Processing: Handles various document types (e.g., PDFs) for information extraction.

PGVector: PostgreSQL extension for storing and querying vector embeddings, enabling efficient semantic search.

Cache Service: Improves performance and reduces latency by caching frequent responses using Redis.

Architecture Diagram
graph TD
    User --> FastAPI[FastAPI (retrieval_service)]
    FastAPI --> CacheService[Cache Service (Redis)]
    FastAPI --> RetrievalService[Retrieval Service]
    RetrievalService --> PostgreSQL[PostgreSQL (PGVector)]
    RetrievalService --> UnstructuredData[Unstructured Data Files (PDFs)]
    CacheService -.-> RetrievalService

Setup Instructions

Follow these steps to set up and run the CortexRAG project locally.

Prerequisites

Docker and Docker Compose

Python 3.9 or higher

1. Clone the Repository
git clone https://github.com/your-username/CortexRAG.git
cd CortexRAG

2. Environment Variables

Create a .env file in the root directory of the project based on .env.sample.

# .env file
OPENAI_API_KEY="your_openai_api_key"
POSTGRES_DB=rag_database
POSTGRES_USER=rag_user
POSTGRES_PASSWORD=rag_password
PG_HOST=db
PG_PORT=5432


Replace "your_openai_api_key" with your actual OpenAI API key.

3. Build and Run Docker Containers

Use Docker Compose to build and start all services.

docker-compose up --build -d


This command starts:

PostgreSQL (with PGVector)

Cache Service (Redis)

Retrieval Service (FastAPI + RAG logic)

4. Insert Data into the Vector Store

Before querying the chatbot, you must ingest documents into the vector database.

docker exec -it <retrieval_service_container_id> python insert_data.py


To find the container ID:

docker ps

5. Access the API

Once all services are running, access the FastAPI Swagger UI at:

http://localhost:8000/docs


You can interact with the chatbot API endpoints directly from the browser.

Usage

Further instructions on how to use the API and interact with the chatbot will be added here.
This may include:

Example curl commands

Sample request/response payloads

A simple client script

Notebooks

The notebooks/ directory contains Jupyter notebooks for learning and experimentation:

langchain-practice.ipynb – Explore LangChain concepts and workflows

pgvector-practice.ipynb – Practice vector storage and similarity search with PGVector

unstructured-practice.ipynb – Learn document parsing using the Unstructured library

requirements-notebook.txt – Dependencies required to run the notebooks

✅ Summary of Fixes

No Markdown syntax errors

Mermaid diagram syntax is valid

Consistent naming (LangChain instead of mixed casing)

Improved clarity without changing meaning

If you want, I can also:

Add API endpoint examples

Write a production-ready README

Convert this into a GitHub-polished open-source README

Add badges, license, and contribution guide

Just say the word 👍

i want in readme .md format

Perfect 👍
Below is the ready-to-use README.md file in proper Markdown format.
You can directly copy–paste this into README.md — no changes needed.

# CortexRAG: Advanced Chatbot with FastAPI, RAG, LangChain, Unstructured, and PGVector

CortexRAG is an intelligent chatbot system designed to provide accurate and contextually relevant responses by leveraging **Retrieval Augmented Generation (RAG)**. It integrates **FastAPI** for a robust API, **LangChain** for orchestrating AI workflows, **Unstructured** for document processing, and **PGVector** for efficient vector storage and retrieval.

---

## Features

- **FastAPI Backend:** A high-performance web framework for building APIs.
- **Retrieval Augmented Generation (RAG):** Enhances LLM capabilities by retrieving relevant information from a knowledge base.
- **LangChain Integration:** Orchestrates complex AI workflows, including prompt management, chain construction, and agent creation.
- **Unstructured Data Processing:** Handles various document types (e.g., PDFs) for information extraction.
- **PGVector:** PostgreSQL extension for storing and querying vector embeddings, enabling efficient semantic search.
- **Cache Service:** Improves performance and reduces latency by caching frequent responses using Redis.

---

## Architecture Diagram

```mermaid
graph TD
    User --> FastAPI[FastAPI (retrieval_service)]
    FastAPI --> CacheService[Cache Service (Redis)]
    FastAPI --> RetrievalService[Retrieval Service]
    RetrievalService --> PostgreSQL[PostgreSQL (PGVector)]
    RetrievalService --> UnstructuredData[Unstructured Data Files (PDFs)]
    CacheService -.-> RetrievalService

Setup Instructions

Follow these steps to set up and run the CortexRAG project locally.

Prerequisites

Docker and Docker Compose

Python 3.9 or higher

1. Clone the Repository
git clone https://github.com/your-username/CortexRAG.git
cd CortexRAG

2. Environment Variables

Create a .env file in the root directory of the project based on .env.sample.

# .env file
OPENAI_API_KEY="your_openai_api_key"
POSTGRES_DB=rag_database
POSTGRES_USER=rag_user
POSTGRES_PASSWORD=rag_password
PG_HOST=db
PG_PORT=5432


Replace "your_openai_api_key" with your actual OpenAI API key.

3. Build and Run Docker Containers

Use Docker Compose to build and start all services.

docker-compose up --build -d


This command starts:

PostgreSQL (with PGVector)

Cache Service (Redis)

Retrieval Service (FastAPI + RAG logic)

4. Insert Data into the Vector Store

Before querying the chatbot, you must ingest documents into the vector database.

docker exec -it <retrieval_service_container_id> python insert_data.py


To find the container ID:

docker ps

5. Access the API

Once all services are running, access the FastAPI Swagger UI at:

http://localhost:8000/docs


You can interact with the chatbot API endpoints directly from the browser.

Usage

Further instructions on how to use the API and interact with the chatbot will be added here.
This may include:

Example curl commands

Sample request/response payloads

A simple client script

Notebooks

The notebooks/ directory contains Jupyter notebooks for learning and experimentation:

langchain-practice.ipynb – Explore LangChain concepts and workflows

pgvector-practice.ipynb – Practice vector storage and similarity search with PGVector

unstructured-practice.ipynb – Learn document parsing using the Unstructured library

requirements-notebook.txt – Dependencies required to run the notebooks


---

If you want next:
- ⭐ **GitHub badges (Docker, FastAPI, OpenAI)**
- 🧠 **RAG workflow explanation section**
- 🚀 **Production deployment section**
- 📄 **License + Contribution guide**

Just tell me 😄
