# 🇭🇰 Smart Policy Assistant: HK I&T Blueprint Analyzer

![Python](https://img.shields.io/badge/Python-3.11-blue)
![LangChain](https://img.shields.io/badge/LangChain-0.3-green)
![Llama 3.2](https://img.shields.io/badge/Model-Llama3.2-orange)
![Privacy](https://img.shields.io/badge/Privacy-100%25-red)

## 📖 Description
This project implements a **Secure, Local Retrieval-Augmented Generation (RAG)** system to analyze complex government policy documents, specifically the **Hong Kong Innovation & Technology Development Blueprint**.

### 💡 The Problem
Analyzing lengthy government reports (100+ pages) manually is time-consuming. While cloud-based AI (like GPT-4) is powerful, uploading sensitive or internal policy documents to public servers poses significant **data privacy and security risks**.

### 🚀 The Solution
This system runs entirely **offline** on a local machine. By leveraging **Ollama (Llama 3.2)** and local vector embeddings, it allows users to query, summarize, and extract strategic insights from documents with **zero data leakage** and **zero API costs**.

---

## 🏗️ Architecture
The system follows a standard RAG pipeline optimized for local inference:
1.  **Ingestion:** Loads complex PDF documents (`PyPDFLoader`).
2.  **Chunking:** Uses `RecursiveCharacterTextSplitter` (Size: 3000) to preserve context in long policy sections.
3.  **Embedding:** HuggingFace `all-MiniLM-L6-v2` (CPU-optimized).
4.  **Retrieval:** ChromaDB (Top-10 semantic search).
5.  **Generation:** Llama 3.2 (via Ollama) with a custom "Policy Analyst" persona.

## 📸 Demo Result
**Query:** *"List and explain the 4 broad development directions in the HK I&T Blueprint."*

> **AI Output:**
> 1. Enhance the I&T ecosystem and promote "new industrialisation".
> 2. Enlarge the I&T talent pool.
> 3. Promote digital economy and develop Hong Kong into a smart city.
> 4. Proactively integrate into the overall development of the country.

*(See `assets/demo_result.png` for the full terminal output proving citation accuracy)*

## 🛠️ Installation & Usage

### Prerequisites
* Python 3.11+
* [Ollama](https://ollama.com/) installed and running
* Git

### Setup
```bash
# 1. Clone the repo
git clone [https://github.com/lky012/HK-IT-Blueprint-RAG.git](https://github.com/lky012/HK-IT-Blueprint-RAG.git)

# 2. Install dependencies
pip install -r requirements.txt

# 3. Pull the model
ollama run llama3.2
