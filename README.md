## ▶️ Run the Agentic Flow in Google Colab

You can open and run the **Agentic Flow notebook** directly in Google Colab.

Click the badge below:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/adil-998/Project1/blob/main/agents.ipynb)

This will launch the notebook in **Google Colab**, where you can explore the agent workflow, run the code, and interact with the system.

Notebook link:
https://colab.research.google.com/github/adil-998/Project1/blob/main/agents.ipynb


# 🧠 AI Multi-Tool Assistant (Medical + Insurance)

A **LangGraph + LangChain powered AI assistant** that can answer medical questions, explain medicine side effects, and provide insights about an insurance prediction project.

The system uses **Retrieval Augmented Generation (RAG)**, **vector databases (FAISS)**, and **LLMs (Gemini / Groq models)** to provide contextual answers.

It also includes a **Gradio web interface** for chatting with the assistant.

---

# 🚀 Features

### 🏥 Medical Assistant

* Answers general health and mental health questions
* Uses a **medical guidebook PDF** as context
* Provides supportive responses for users experiencing stress or depression
* Uses RAG for grounded answers

### 💊 Medicine Side Effects Explainer

* Explains **common and rare side effects of medicines**
* Describes how medicines impact the body
* Encourages consulting a doctor
* Avoids prescribing medication

### 💰 Insurance Project Assistant

* Reads an **insurance ML notebook**
* Explains the **insurance price prediction model**
* Helps understand features, predictions, and project logic
* Uses notebook content as context for answers

### 🤖 Tool-Based Agent

The system uses a **LangGraph agent** that automatically decides which tool to use:

| Tool                         | Purpose                             |
| ---------------------------- | ----------------------------------- |
| `medical_help`               | General medical assistance          |
| `medicine_side_effects`      | Explains medicine side effects      |
| `insurance_price_prediction` | Explains insurance prediction model |

---

# 🧱 Architecture

```
User Question
      │
      ▼
LangGraph Agent
      │
      ▼
Tool Selection
 ├── Medical RAG Tool
 ├── Medicine Side Effects Tool
 └── Insurance Notebook RAG Tool
      │
      ▼
LLM Response (Gemini / Groq)
      │
      ▼
Gradio Chat Interface
```

Technologies used:

* **LangChain**
* **LangGraph**
* **FAISS Vector Database**
* **HuggingFace Embeddings**
* **Google Gemini LLM**
* **Groq LLaMA Models**
* **Gradio UI**
* **PyMuPDF Document Loader**

---

# 📦 Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/ai-medical-assistant.git
cd ai-medical-assistant
```

Install dependencies:

```bash
pip install langchain
pip install langchain-community
pip install langchain-core
pip install langchain-huggingface
pip install langchain-google-genai
pip install langchain-groq
pip install faiss-cpu
pip install pymupdf
pip install sentence-transformers
pip install transformers
pip install gradio
```

---

# 🔑 Environment Variables

Set your API keys before running:

```python
os.environ["GOOGLE_API_KEY"] = "your_google_api_key"
os.environ["GROQ_API_KEY"] = "your_groq_api_key"
```

---

# 📂 Project Structure

```
project/
│
├── medical_guidebook.pdf
├── insurance_project.ipynb
│
├── app.ipynb
│
├── vector_db/
│
└── README.md
```

---

# ⚙️ How It Works

### 1️⃣ Document Loading

Medical documents are loaded using:

```python
PyMuPDFLoader()
```

Insurance notebook is loaded using:

```python
NotebookLoader()
```

---

### 2️⃣ Text Chunking

Documents are split into smaller chunks:

```python
RecursiveCharacterTextSplitter
```

This improves retrieval accuracy.

---

### 3️⃣ Embeddings

Text is converted to vector embeddings using:

```
sentence-transformers/all-MiniLM-L6-v2
```

---

### 4️⃣ Vector Database

Embeddings are stored in **FAISS** for fast similarity search.

---

### 5️⃣ Retrieval Augmented Generation (RAG)

When a user asks a question:

1. Relevant chunks are retrieved
2. Context is added to the prompt
3. LLM generates a grounded response

---

### 6️⃣ LangGraph Agent

The agent decides whether to:

* Use **medical knowledge**
* Explain **medicine side effects**
* Answer **insurance project questions**

---

# 💬 Gradio Chat Interface

The system includes a **simple web chat interface**.

Run the app:

```python
demo.launch()
```

Then open the generated **local URL** in your browser.

Example UI:

```
AI Medical Assistant

Ask health-related questions and get AI guidance.
```

---

# 🧪 Example Questions

### Medical Questions

```
Why do people get depression?
How can stress affect the body?
What causes anxiety?
```

### Medicine Side Effects

```
What are the side effects of paracetamol?
Explain side effects of antibiotics.
```

### Insurance Project

```
Explain the insurance price prediction model.
How does the model calculate insurance cost?
What features affect insurance price?
```

---

# ⚠️ Disclaimer

This project provides **educational information only**.

It **does NOT replace professional medical advice**.
Always consult a **qualified doctor or healthcare professional** for medical concerns.

---

# 🔮 Future Improvements

* Add **voice assistant**
* Add **medical symptom checker**
* Deploy using **FastAPI**
* Use **MongoDB vector storage**
* Improve UI with **streaming responses**
* Add **multi-PDF knowledge base**

---

# 👨‍💻 Author

Built using:

* LangChain
* LangGraph
* FAISS
* HuggingFace
* Gemini LLM
* Gradio

---

⭐ If you found this project helpful, consider giving it a star!
