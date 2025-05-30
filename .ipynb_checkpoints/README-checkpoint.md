# 📚 Multilingual PDF Chatbot

A conversational chatbot that allows users to interact intelligently with PDF documents using local large language models and retrieval-augmented generation (RAG).

---

## 🔍 Retrieval-Augmented Generation (RAG)

Retrieval-Augmented Generation enhances an LLM's responses by retrieving relevant document chunks from a custom dataset at runtime.

This architecture is especially useful for question answering on personalized or private data such as PDFs.

![Chatbot Architecture](./images/ragchatbotpdf.png)

---

## 🧠 Overview

This chatbot works as follows:

1. Loads and reads a PDF using `PyPDFLoader`.
2. Splits the content into smaller chunks using `RecursiveCharacterTextSplitter`.
3. Generates embeddings locally with `OllamaEmbeddings`.
4. Stores and retrieves embeddings using `DocArrayInMemorySearch`.
5. Uses `ConversationalRetrievalChain` to generate accurate answers with context, powered by a local LLM (`OllamaLLM`).
6. Responds in a conversational format with memory and source tracking.

---

## ⚙️ Requirements

Ensure you have the following dependencies installed:

- Python 3.x
- [`langchain`](https://python.langchain.com/)
- [`langchain-ollama`](https://pypi.org/project/langchain-ollama/)
- `docarray`
- `pypdf`
- Ollama installed and configured locally ([Download Ollama](https://ollama.com/download))

---

## 💾 Installation

Install required dependencies:

```bash
pip install langchain langchain-ollama pypdf docarray
ollama pull nomic-embed-text:latest
ollama pull qwen2.5:1.5b