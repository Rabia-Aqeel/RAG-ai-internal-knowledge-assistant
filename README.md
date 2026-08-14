
RAG AI Internal Knowledge Assistant

An AI-powered RAG workflow that allows users to ask questions and receive answers based on internal company documents, built with n8n, Google Gemini, and Groq.

Overview

RAG AI Internal Knowledge Assistant automates document ingestion, semantic retrieval, and AI-powered question answering using a Retrieval-Augmented Generation (RAG) architecture.

Documents are uploaded to Google Drive, processed into embeddings, and stored in a vector store. When a user asks a question, the AI Agent retrieves relevant information from the knowledge base and generates a grounded answer.

Workflow

Workflow Overview

Document Ingestion Flow

Google Drive Trigger
        ↓
Download File
        ↓
Extract PDF Text
        ↓
Document Loader
        ↓
Gemini Embeddings
        ↓
Simple Vector Store

Question Answering Flow

Chat Trigger
      ↓
AI Agent
      ↓
Vector Store Retriever
      ↓
Relevant Knowledge
      ↓
Groq Chat Model
      ↓
AI Answer

Workflow Screenshot

The complete n8n workflow is shown below:

Paste your annotated workflow screenshot here

workflow-screenshot.png

How It Works

1. Document Ingestion

When a new document is added to the configured Google Drive folder, the workflow downloads the file and extracts its PDF text.

The extracted content is processed through the Document Loader and Gemini Embeddings before being stored in the Simple Vector Store for semantic retrieval.

2. Knowledge Retrieval

When a user asks a question through the Chat Trigger, the AI Agent uses the Vector Store Retriever to search the stored knowledge and retrieve relevant information.

3. AI Answer Generation

The retrieved information is passed to the AI Agent, which uses the Groq Chat Model to generate a clear answer based on the available knowledge.

The agent is instructed to use only information retrieved from the knowledge base and not invent information.

4. Testing & Evaluation

The workflow also includes an automated testing flow.

User Question
      ↓
Knowledge Retrieval
      ↓
AI Answer
      ↓
JavaScript Processing
      ↓
Test ID Generation
      ↓
Google Sheets

Test results are stored with Test ID, Question, AI Answer, and Result.

Key Features

* Automated document ingestion from Google Drive
* PDF text extraction
* Gemini-powered embeddings
* Vector-based semantic retrieval
* AI Agent for knowledge-based question answering
* Groq-powered chat model
* Knowledge-grounded responses
* Automated AI response testing
* Google Sheets test result storage

Tech Stack

* n8n — Workflow automation
* Google Drive — Document storage
* Google Gemini — Text embeddings
* Simple Vector Store — Semantic retrieval
* Groq / Qwen 3.6 27B — AI chat model
* Google Sheets — Testing and results
* JavaScript — Response processing

Use Cases

* Internal company knowledge assistants
* HR policy assistants
* SOP and documentation search
* Employee support systems
* Internal documentation Q&A

Project Structure

RAG-ai-internal-knowledge-assistant/
│
├── RAG-ai-internal-knowledge-assistant-GitHub.json
├── README.md
└── workflow-screenshot.png

Author

Rabia Aqeel

BS Computer Science Student | AI Automation & AI Agent Development
