## Medical

## 🩺 MediBot – Medical Chatbot Setup Guide

### 🚀 How to Run the Project

---

### 📦 Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/medibot.git
cd medibot
```

---

### 🐍 Step 2: Set Up the Conda Environment

```bash
conda create -n medibot python=3.10 -y
conda activate medibot
```

---

### 📦 Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 🔐 Step 4: Add Environment Variables

Create a `.env` file in the root directory with the following content:

```
PINECONE_API_KEY=your-pinecone-api-key
OPENAI_API_KEY=your-openai-api-key
```

---

### 🧠 Step 5: Generate Embeddings

```bash
python store_index.py
```

---

### 💬 Step 6: Run the App

```bash
python app.py
```

Now, open your browser and visit:

```
http://localhost:5000
```

---

## 🛠️ Tech Stack

* **Python**
* **LangChain**
* **Flask**
* **OpenAI GPT**
* **Pinecone**
* **AWS Deployment via GitHub Actions**

---

## ☁️ AWS Deployment Instructions (CI/CD)

---

### 1️⃣ Set Up AWS IAM

* Go to AWS Console
* Create a new IAM user for deployment
* Attach the following policies:

```text
AmazonEC2FullAccess
AmazonEC2ContainerRegistryFullAccess
```

---

### 2️⃣ Create an ECR Repository

* Save the URI (Example):

  ```
  315865595366.dkr.ecr.us-east-1.amazonaws.com/medibot
  ```

---

### 3️⃣ Launch EC2 Instance (Ubuntu)

* SSH into your EC2
* Install Docker:

```bash
sudo apt-get update -y
sudo apt-get upgrade -y

curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

sudo usermod -aG docker ubuntu
newgrp docker
```

---

### 4️⃣ Set Up EC2 as GitHub Runner

* In your GitHub repo:

  ```
  Settings > Actions > Runners > New self-hosted runner
  ```
* Choose OS (Ubuntu) and follow setup commands provided

---

### 5️⃣ Configure GitHub Secrets

Add the following secrets to your GitHub repo:

| Key                     | Value                    |
| ----------------------- | ------------------------ |
| `AWS_ACCESS_KEY_ID`     | Your IAM user access key |
| `AWS_SECRET_ACCESS_KEY` | Your IAM user secret     |
| `AWS_DEFAULT_REGION`    | e.g., `us-east-1`        |
| `ECR_REPO`              | Your ECR URI             |
| `PINECONE_API_KEY`      | Your Pinecone API key    |
| `OPENAI_API_KEY`        | Your OpenAI API key      |

---

## ✅ Deployment Steps

1. Build Docker image for the project
2. Push the image to AWS ECR
3. Launch EC2 instance
4. Pull Docker image from ECR to EC2
5. Run the container
