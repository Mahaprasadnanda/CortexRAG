# CortexRAG: Advanced Chatbot with FastAPI, RAG, Langchain, Unstructured, and PGVector

CortexRAG is an intelligent chatbot system designed to provide accurate and contextually relevant responses by leveraging Retrieval Augmented Generation (RAG). It integrates FastAPI for a robust API, Langchain for orchestrating AI workflows, Unstructured for document processing, and PGVector for efficient vector storage and retrieval.

## Features

*   **FastAPI Backend:** A high-performance web framework for building APIs.
*   **Retrieval Augmented Generation (RAG):** Enhances LLM capabilities by retrieving relevant information from a knowledge base.
*   **Langchain Integration:** Orchestrates complex AI workflows, including prompt management, chain construction, and agent creation.
*   **Unstructured Data Processing:** Handles various document types (e.g., PDFs) for information extraction.
*   **PGVector:** PostgreSQL extension for storing and querying vector embeddings, enabling efficient semantic search.
*   **Cache Service:** Improves performance and reduces latency by caching frequent responses.

## Architecture Diagram

![CortexRAG Architecture](architecture_diagram.png)

(Please generate the `architecture_diagram.png` separately with the description: "A simple architecture diagram for a RAG chatbot. User interacts with FastAPI. FastAPI communicates with a Cache Service and a Retrieval Service. The Retrieval Service interacts with a PostgreSQL database and unstructured data files (PDFs).")

## Setup Instructions

Follow these steps to set up and run the CortexRAG project locally.

### Prerequisites

*   Docker and Docker Compose
*   Python 3.9+

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/CortexRAG.git
cd CortexRAG
```

### 2. Environment Variables

Create a `.env` file in the root directory of the project, based on the `.env.sample` file.

```ini
# .env file
OPENAI_API_KEY="your_openai_api_key"
POSTGRES_DB=rag_database
POSTGRES_USER=rag_user
POSTGRES_PASSWORD=rag_password
PG_HOST=db
PG_PORT=5432
```

Replace `"your_openai_api_key"` with your actual OpenAI API key.

### 3. Build and Run Docker Containers

Use Docker Compose to build and start all services.

```bash
docker-compose up --build -d
```

This will start the PostgreSQL database, cache service, and retrieval service.

### 4. Insert Data

Before you can query the chatbot, you need to insert your data into the vector store.

```bash
docker exec -it <retrieval_service_container_id> python insert_data.py
```

To find the `<retrieval_service_container_id>`, you can run `docker ps`.

### 5. Access the API

Once all services are running, you can access the FastAPI documentation at:

```
http://localhost:8000/docs
```

You can then interact with the chatbot API endpoints.

## Usage

(Further instructions on how to use the API and interact with the chatbot will go here. This might involve example `curl` commands or a simple client script.)

## Notebooks

The `notebooks/` directory contains several Jupyter notebooks for exploring and practicing with the core technologies:

*   `langchain-practice.ipynb`: Learn and experiment with Langchain functionalities.
*   `pgvector-practice.ipynb`: Understand how to use PGVector for vector embeddings.
*   `unstructured-practice.ipynb`: Explore document processing with the Unstructured library.
*   `requirements-notebook.txt`: Dependencies specific to the notebooks.
