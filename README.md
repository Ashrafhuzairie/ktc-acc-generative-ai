# KTC-ChatGPT – Enterprise Generative AI Assistant

This project is an **end-to-end Generative AI assistant** designed for enterprise use cases.  
KTC-ChatGPT enables intelligent, context-aware responses by combining **Large Language Models (LLMs)** with **vector search**, **retrieval-augmented generation (RAG)**, and **cloud-native deployment**.

The system is built to support scalable, secure, and production-ready AI applications.

---

## 🧠 Solution Overview

KTC-ChatGPT performs the following:

- Ingests structured and unstructured documents
- Converts content into embeddings using LLMs
- Stores embeddings in a **vector database (Pinecone)**
- Retrieves relevant context using similarity search
- Generates responses using **OpenAI GPT models**
- Serves responses through a **Flask web application**
- Supports automated deployment using **AWS CI/CD pipelines**

---

## 🚀 How to Run the Application (Local)

### Step 1: Clone the Repository

## 🚀 How to Run the Application (Local)

### Step 1: Clone the Repository

```bash
git clone https://github.com/<your-username>/KTC-ChatGPT.git
cd KTC-ChatGPT
```

### Step 2: Create and Activate Conda Environment

```bash
conda create -n ktc-chatgpt python=3.10 -y
conda activate ktc-chatgpt
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Configure Environment Variables

```bash
PINECONE_API_KEY="xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
OPENAI_API_KEY="xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

### Step 5: Generate and Store Embeddings

```bash
python store_index.py
```

### Step 6: Run the Application

```bash
python app.py
Open the application in browser : http://localhost:5000
```

## 🏗️ System Architecture

<p align="center">
  <img width="3428" height="2724" alt="image" src="https://github.com/user-attachments/assets/de4e4d4f-c40a-4739-9563-c41b36d707f9" />
</p>

This diagram illustrates the end-to-end flow of KTC-ChatGPT,
from document ingestion to response generation and deployment.
