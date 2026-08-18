RAG Student Support Chatbot

A RAG-powered AI chatbot built with n8n as part of the Agentic AI & Automation Mastery program.

Overview

This workflow creates an AI-powered course information assistant for BrightPath Academy. It uses documents stored in Google Drive as a knowledge base, processes them into vector embeddings, and uses a Pinecone vector store to provide accurate, context-based responses.

Workflow

The workflow follows a RAG-based automation pipeline:

1. Knowledge Base Ingestion — Monitors a Google Drive folder and detects newly added documents.
2. Document Processing — Downloads the uploaded files and prepares them for processing.
3. Embedding Generation — OpenAI text-embedding-3-large converts document content into vector embeddings.
4. Vector Storage — Stores the embeddings in a Pinecone vector database.
5. User Query — Receives student questions through a webhook.
6. AI Retrieval — The AI Agent searches Pinecone for relevant information before generating a response.
7. Conversation Memory — Maintains short-term chat history using session-based memory.
8. Response — Returns the AI-generated answer through the webhook.

Tech Stack

* n8n — Workflow automation & orchestration
* OpenAI GPT-5 Mini — AI response generation
* OpenAI Embeddings — Document vectorization
* Pinecone — Vector database & semantic search
* Google Drive — Knowledge base
* Webhook — Chatbot API endpoint

Key Skills

RAG • Vector Databases • Semantic Search • AI Agents • Embeddings • Prompt Engineering • Conversational Memory • Workflow Automation • API Integration
