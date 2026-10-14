🤖 RAG AI Agent — Intelligent Document Assistant

An AI-powered document assistant built with n8n, Google Drive, Google Gemini, and Supabase Vector Store. This project combines Retrieval-Augmented Generation (RAG) with an AI Agent to help users interact with information stored in documents and receive context-aware answers.

📌 Project Overview

The RAG AI Agent is designed to connect document storage with conversational AI.

It uses an automated workflow to detect newly created files in Google Drive, download them, process their content, generate embeddings, and store the resulting information in a Supabase Vector Store.

A separate conversational workflow allows users to ask questions through a chat interface. The AI Agent can use the stored document information as a tool to retrieve relevant context and generate answers.

✨ Key Features

- Automated Document Ingestion: Detects newly created files in Google Drive through a trigger.
- Document Processing: Downloads files and uses a data loader to prepare their content for ingestion.
- AI Embeddings: Uses Google Gemini embeddings to represent document content as vectors.
- Vector Storage: Stores document information in Supabase Vector Store for semantic retrieval.
- Conversational AI Agent: Uses an AI Agent to handle user questions and coordinate retrieval.
- Chat Model Integration: Uses Google Gemini Chat Model to generate responses.
- Conversation Memory: Integrates Simple Memory to support conversational context.
- Modular Workflow: Separates document ingestion from the user-facing chat workflow.

🛠️ Technologies Used

Technology| Purpose
n8n| Workflow automation and AI orchestration
Google Drive| Source of documents
Google Gemini| Chat responses and text embeddings
Supabase Vector Store| Vector storage and semantic retrieval
Retrieval-Augmented Generation (RAG)| Grounding AI responses in retrieved document content
Simple Memory| Maintaining conversational context

⚙️ How It Works

The project consists of two main workflows.

1. Document Ingestion Workflow

This workflow prepares documents for retrieval.

1. Google Drive Trigger: Detects a newly created file.
2. Download File: Downloads the file from Google Drive.
3. Default Data Loader: Loads and prepares the document content.
4. Google Gemini Embeddings: Converts the supported document content into vector embeddings.
5. Supabase Vector Store: Stores the processed document information for later retrieval.

2. Conversational AI Workflow

This workflow handles user questions.

1. Chat Trigger: Receives a message from the user.
2. AI Agent: Interprets the question and decides how to respond.
3. Google Gemini Chat Model: Generates the response.
4. Supabase Vector Store Tool: Retrieves relevant information from the indexed documents when needed.
5. Simple Memory: Helps maintain conversational context.

The agent combines the user's question with relevant retrieved information to produce a more context-aware answer.

🏗️ System Architecture

Google Drive
     |
     v
Google Drive Trigger
     |
     v
Download File
     |
     v
Default Data Loader
     |
     v
Google Gemini Embeddings
     |
     v
Supabase Vector Store
     |
     | Document Retrieval
     v
AI Agent <---- Chat Trigger
     |
     +---- Google Gemini Chat Model
     |
     +---- Simple Memory
     |
     v
Context-Aware Response

🚀 Getting Started

Prerequisites

Before running the project, you will need:

- An n8n instance.
- A Google account with access to Google Drive.
- Google Gemini API access and the required credentials.
- A Supabase project with the necessary vector storage configuration.
- The required n8n nodes and connections configured correctly.

Setup Instructions

1. Open your n8n instance.
2. Import the workflow if an exported n8n workflow JSON file is available.
3. Configure the Google Drive credentials and select the appropriate source.
4. Configure the Google Gemini credentials for the chat model and embeddings nodes.
5. Connect Supabase and configure the vector store and its required table or collection settings.
6. Configure the document loader to support your intended file types.
7. Connect the AI Agent to the chat model, memory, and vector store tool.
8. Execute the document ingestion workflow and verify that documents are processed and stored successfully.
9. Open the chat interface and test the agent with questions about the indexed documents.

Important: The screenshot shows the workflow structure, but the exact credential settings, database schema, supported file types, and deployment configuration may vary. Verify these settings before running the project.

💡 Example Use Cases

The RAG AI Agent can be adapted for:

- Document-based question answering.
- Searching and retrieving information from personal or organizational documents.
- Knowledge assistants for educational materials.
- Internal knowledge bases for teams.
- AI assistants that answer questions using indexed reference documents.

These are potential applications of the architecture; their effectiveness depends on the documents, configuration, and retrieval quality.

🔒 Security and Privacy

- Keep API keys and database credentials private.
- Use environment variables or n8n credentials to manage secrets securely.
- Configure appropriate Google Drive and Supabase permissions.
- Avoid exposing sensitive documents to unauthorized users.
- Review the data retention and access policies of the services used.

🔮 Future Improvements

Potential enhancements include:

- Support for additional document formats.
- Better document chunking and metadata filtering.
- Source references in AI-generated answers.
- Improved error handling and workflow monitoring.
- Authentication and access control for users.
- Evaluation of retrieval quality and answer accuracy.

👩‍💻 Project Purpose

This project demonstrates practical applications of AI automation, workflow orchestration, vector databases, and Retrieval-Augmented Generation.

It explores how automation tools and large language models can work together to build a document-based conversational assistant.

📄 License

Choose an appropriate open-source license before distributing this project publicly. If you do not intend to grant reuse permissions yet, leave the license unspecified.

---

Built with n8n, Google Gemini, Google Drive, and Supabase.
