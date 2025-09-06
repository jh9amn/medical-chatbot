# medical-chatbot
I am trying medical chatbot.. And diving into the the AI field. Starting a beautiful journey set 5th 2025. Looking forward to the future.. 🤞🤞



Alright ✅ I’ll give you a **complete `README.md` file** with everything you listed (setup + AWS deployment steps), formatted cleanly and ready to drop into your project.

Here’s the full code:

````markdown
# 🏥 Medical Chatbot with LLMs, LangChain, Pinecone, Flask & AWS

This project demonstrates how to build a **Medical Chatbot** using **Large Language Models (LLMs)**, **LangChain**, **Pinecone**, **Flask**, and deploy it using **AWS EC2 + ECR with GitHub Actions**.

---

## 🚀 How to Run Locally

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/jh9amn/medical-chatbot.git
cd Build-a-Complete-Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask-AWS || medical-chatbot
````

---

### 2️⃣ Create Conda Environment

```bash
conda create -n medibot python=3.10 -y
conda activate medibot
```

---

### 3️⃣ Install Requirements

```bash
pip install -r requirements.txt
```

---

### 4️⃣ Setup Environment Variables

Create a `.env` file in the **root directory** and add your Pinecone & OpenAI credentials:

```ini
PINECONE_API_KEY = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
OPENAI_API_KEY   = "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

---

### 5️⃣ Store Embeddings to Pinecone

```bash
python store_index.py
```

---

### 6️⃣ Run the Application

```bash
python app.py
```

Now open in browser:

```
http://localhost:5000
```

---

## ⚡ Tech Stack

* Python
* LangChain
* Flask
* GPT
* Pinecone
* AWS (CI/CD Deployment with GitHub Actions)

---

## ☁️ AWS Deployment Guide

### 1️⃣ AWS Setup

* Login to AWS Console
* Create an **IAM User** for deployment with the following access:

  * **EC2** (Virtual Machine)
  * **ECR** (Elastic Container Registry for Docker images)

---

### 2️⃣ Required IAM Policies

* `AmazonEC2ContainerRegistryFullAccess`
* `AmazonEC2FullAccess`

---

### 3️⃣ Create an ECR Repository

Example URI:

```
315865595366.dkr.ecr.us-east-1.amazonaws.com/medicalbot
```

---

### 4️⃣ Launch EC2 Machine (Ubuntu)

#### Install Docker in EC2

```bash
# Optional
sudo apt-get update -y
sudo apt-get upgrade -y

# Required
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

---

### 5️⃣ Configure EC2 as GitHub Self-Hosted Runner

1. Go to **GitHub Repo → Settings → Actions → Runners → New self-hosted runner**
2. Select OS (Ubuntu)
3. Run the given commands one by one in your EC2 instance

---

### 6️⃣ Setup GitHub Secrets

In your repository:
**Settings → Secrets and variables → Actions**, add:

* `AWS_ACCESS_KEY_ID`
* `AWS_SECRET_ACCESS_KEY`
* `AWS_DEFAULT_REGION`
* `ECR_REPO`
* `PINECONE_API_KEY`
* `OPENAI_API_KEY`

---

## 📦 Deployment Workflow

1. Build Docker image of the source code
2. Push Docker image to **ECR**
3. Launch **EC2 instance**
4. Pull Docker image from **ECR** inside EC2
5. Run Docker container in **EC2**

---

## ✅ Policies Recap

* `AmazonEC2ContainerRegistryFullAccess`
* `AmazonEC2FullAccess`

---

## 🔮 Future Improvements

* Integrate authentication (user login/signup)
* Add monitoring/logging with AWS CloudWatch
* Deploy with Kubernetes (EKS) for scalability

```

---

⚡ This is the **entire `README.md` file** — you can copy-paste it directly.  

Do you also want me to create a **`.github/workflows/deploy.yml` GitHub Actions file** so pushing to `main` will automatically build & deploy your Docker image to AWS?
```
