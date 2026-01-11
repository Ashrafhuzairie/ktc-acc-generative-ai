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

```bash
git clone https://github.com/<your-username>/KTC-ChatGPT.git
cd KTC-ChatGPT

### Step 2: Create and Activate Conda Environment

conda create -n ktc-chatgpt python=3.10 -y
conda activate ktc-chatgpt

### Step 3: Install Dependencies

pip install -r requirements.txt


### Step 4: Configure Environment Variables

PINECONE_API_KEY="xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
OPENAI_API_KEY="xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"

### Step 5: Generate and Store Embeddings

python store_index.py


### Step 6: Run the Application

python app.py
http://localhost:5000


