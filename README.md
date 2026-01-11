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

## ☁️ How to Run the Application (AWS Cloud)

This section describes how to deploy and run **KTC-ChatGPT** on AWS using
**Docker**, **Amazon ECR**, **Amazon ECS (EC2 launch type)**, and **GitHub Actions CI/CD**.

---

### Step 1: Create an Amazon ECR Repository

1. Go to **AWS Console → Amazon ECR**
2. Click **Create repository**
3. Repository name:
4. Save the **ECR repository URI**, for example: <account-id>.dkr.ecr.<region>.amazonaws.com/ktc-chatgpt
   
---

### Step 2: Create an ECS Cluster (EC2)

1. Go to **AWS Console → Amazon ECS → Clusters**
2. Click **Create cluster**
3. Select **EC2 Linux + Networking**
4. Cluster name: ktc-chatgpt-cluster
   
---

### Step 3: Launch EC2 Instances for ECS

1. Use **ECS-Optimized Amazon Linux 2 AMI**
2. Instance type: `t3.small` or higher
3. Ensure the EC2 instance:
- Is associated with the ECS cluster
- Has outbound internet access
- Security Group allows your application port (e.g. `5000` or `80`)

Verify in ECS: ECS Cluster → Infrastructure → ECS Instances


You should see at least **one registered EC2 instance**.

---

### Step 4: Create an ECS Task Definition (EC2)

1. Go to **ECS → Task Definitions → Create**
2. Launch type: **EC2**
3. Container settings:
   - Image: `<your-ecr-uri>:latest`
   - Port mapping: `5000`
4. Add environment variables or secrets:
   - `OPENAI_API_KEY`
   - `PINECONE_API_KEY`
     
---

### Step 5: Create an ECS Service

1. Go to **ECS Cluster → Services → Create**
2. Launch type: **EC2**
3. Task definition: `ktc-chatgpt-task`
4. Desired tasks: `1`

The service will run your container on the EC2 instance.

---

### Step 6: Configure GitHub Actions CI/CD

Create the following GitHub secrets:

1. AWS_ACCESS_KEY_ID
2. AWS_SECRET_ACCESS_KEY
3. AWS_REGION
4. ECR_REPOSITORY
5. OPEN_AI_KEY
6. PINECONE_API_KEY

GitHub Actions will:
1. Build Docker image
2. Push image to Amazon ECR
3. Update ECS task definition
4. Redeploy the ECS service automatically

---

### Step 7: Access the Application

Access the Web Application that deployed in AWS :

<p align="center">
  <img src="docs/KTC-AI-Chatbot-AWS.jpeg" width="800" />
</p>

## 🏗️ System Architecture

<p align="center">
  <img src="docs/KTC-AI-Chatbot.png" width="800" />
</p>

This diagram illustrates the end-to-end flow of KTC-ChatGPT,
from document ingestion to response generation and deployment.
