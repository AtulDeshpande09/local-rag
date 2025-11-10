# Local RAG

## Overview

This project implements a fully local Retrieval-Augmented Generation (RAG) pipeline that does not rely on external APIs or hosted inference services. All inference, embedding, retrieval, and generation steps run locally on a machine with a single GPU. The system is suitable for private knowledge retrieval workflows and offline environments.

## Components

* **LLM:** `microsoft/Phi-3-mini-4k-instruct`
* **Embedding Model:** `sentence-transformers/all-MiniLM-L6-v2`
* **Vector Store:** ChromaDB
* **Hardware Requirement:** Can operate on a GPU with **8 GB VRAM**

## Features

* Ingests and indexes local documents
* Embeds text into vector representations using a compact sentence transformer
* Uses ChromaDB for persistent vector retrieval
* Generates context-aware responses using Phi-3 with retrieved document chunks
* Entire pipeline functions without external network dependencies

## Workflow

1. Load and process documents into text chunks
2. Convert chunks to embeddings using MiniLM
3. Store embeddings and metadata in ChromaDB
4. On query, retrieve top relevant chunks
5. Provide context to Phi-3 for answer generation

## Use Case

Designed for knowledge bases, internal notes, offline reference systems, and environments requiring full data privacy with no cloud dependency.

## Notes

* Performance and responsiveness depend on prompt design and chunking strategy.
* Additional storage backends or different embedding models can be substituted as needed.
