## Medical

# 🩺 MediBot – AI-Powered Medical Chatbot

**MediBot** is an intelligent medical assistant powered by OpenAI’s GPT models, LangChain, and Pinecone. It is designed to answer health-related queries with context awareness, combining AI with medical domain knowledge.

Whether you're building a telemedicine platform, health education tool, or just experimenting with LLMs in healthcare — MediBot is your starting point.

---

## 🚀 Features

- 💬 **Chat with GPT**: Ask medical questions, get intelligent answers.
- 📚 **Contextual Search**: Uses vector embeddings and Pinecone to retrieve relevant context before generating a response.
- 🧠 **Smart Embeddings**: Converts medical docs into searchable vector space.
- 🌐 **Web Interface**: Flask-powered local server for easy interaction.
- ☁️ **CI/CD-Ready Deployment**: Easily deploy to AWS using Docker and GitHub Actions.

---

## 🧪 Tech Stack

- **Python 3.10**
- **OpenAI GPT-4 / GPT-3.5**
- **LangChain**
- **Pinecone** (Vector DB)
- **Flask**
- **Docker**
- **GitHub Actions**
- **AWS EC2 + ECR**

---

## 💻 Local Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/medibot.git
cd medibot
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

### 4️⃣ Add Environment Variables

Create a `.env` file in the root directory and add:

```env
PINECONE_API_KEY=your_pinecone_api_key
OPENAI_API_KEY=your_openai_api_key
```

---

### 5️⃣ Index the Knowledge Base

```bash
python store_index.py
```

---

### 6️⃣ Run the Application

```bash
python app.py
```

Go to `http://localhost:5000` to start chatting with MediBot.

---

## 🐳 Docker (Optional)

To run MediBot inside a Docker container:

```bash
docker build -t medibot .
docker run -p 5000:5000 medibot
```

---

## ☁️ AWS Deployment (Optional)

You can deploy MediBot to AWS using GitHub Actions and Docker. This includes:

1. Building and pushing Docker image to **AWS ECR**
2. Launching an **EC2** instance
3. Pulling and running the container in EC2
4. Automating this with **GitHub Actions**

---

### 🔐 Required GitHub Secrets

| Name                    | Description           |
| ----------------------- | --------------------- |
| `AWS_ACCESS_KEY_ID`     | IAM access key        |
| `AWS_SECRET_ACCESS_KEY` | IAM secret key        |
| `AWS_DEFAULT_REGION`    | e.g. `us-east-1`      |
| `ECR_REPO`              | Your AWS ECR repo URI |
| `PINECONE_API_KEY`      | Pinecone API key      |
| `OPENAI_API_KEY`        | OpenAI API key        |

---

## 📸 Screenshots

> *Add screenshots of your chatbot interface here to show how it works visually.*

---

## 🔮 Roadmap

* Add memory for user conversation history
* Integrate authentication system
* Dashboard for viewing logs or user questions
* Voice assistant capabilities
* Connect with EHR systems or health APIs

---

## 🤝 Contributing

Contributions are welcome! Here's how:

1. Fork the repository
2. Create a new branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add new feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Submit a pull request

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.

---

## 📬 Contact

For any questions, feedback, or collaborations, feel free to reach out:

📧 **[nileshshendkar2005@gmail.com](mailto:nileshshendkar2005@gmail.com)**

