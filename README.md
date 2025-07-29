# ⚕️ Medical Questions Chatbot

Welcome to the Medical Questions Chatbot! This interactive web application is designed to answer your medical questions based on a specialized, local knowledge base. It's a smart and intuitive tool built to provide information quickly and accurately, right from your browser.

<img width="1640" height="1043" alt="image" src="https://github.com/user-attachments/assets/7861bbd0-c5ad-4a54-b035-c27d5fe258ee" />


## 🤔 What is this?

This chatbot is more than just a simple Q&A bot. It's a Retrieval-Augmented Generation (RAG) system. This means it doesn't just guess answers from a massive, general-purpose AI model. Instead, it:
1.  **Searches** a curated database of medical information for relevant documents.
2.  **Augments** the AI's knowledge with these specific documents.
3.  **Generates** a precise answer based on the information it found.

This approach ensures that the answers are grounded in the provided context, making them more reliable and accurate for specialized topics like medicine.

---

## ✨ Features

* **Interactive Chat Interface:** A clean and simple UI built with Streamlit.
* **Context-Aware Answers:** The chatbot uses a local FAISS vector store to find relevant medical documents before answering.
* **Fast & Powerful LLM:** Powered by Groq and the Llama3 model for near-instantaneous responses.
* **Source Citing:** The bot shows you the source documents it used to generate the answer, so you can verify the information yourself.
* **Secure:** Your API keys and data stay local. The application uses environment variables to keep your secrets safe.

---

## 🛠️ How It Works (The Tech Stack)

This project brings together several powerful open-source tools:

* **Frontend:** [Streamlit](https://streamlit.io/) for creating the interactive web app interface.
* **Core Logic:** [LangChain](https://www.langchain.com/) for orchestrating the RAG pipeline (retrieval, prompt management, and LLM interaction).
* **LLM & Inference:** [Groq](https://groq.com/) provides the blazing-fast API to run the `llama3-8b-8192` language model.
* **Embeddings:** `sentence-transformers/all-MiniLM-L6-v2` from [Hugging Face](https://huggingface.co/) to convert text documents into numerical vectors.
* **Vector Store:** [FAISS](https://github.com/facebookresearch/faiss) from Meta AI for efficient similarity search on the medical document vectors.

---

## 🚀 Getting Started

Ready to run the chatbot on your own machine? Follow these steps.

### Prerequisites

* Python 3.8 or newer
* Access to a terminal or command prompt
* A [Groq API Key](https://console.groq.com/keys)

### 1. Clone the Repository

First, clone this repository to your local machine:
```bash
git clone <your-repository-url>
cd <your-repository-directory>
```

### 2. Set Up a Virtual Environment

It's highly recommended to use a virtual environment to keep your project dependencies isolated.

```bash
# Create the virtual environment
python -m venv venv

# Activate it
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### 3. Configure Your Environment

You need to provide your Groq API key.

* Create a file named `.env` in the root of your project directory.
* Add your API key to this file:

```
GROQ_API_KEY="your-groq-api-key-goes-here"
```

### 4. Set Up the Vector Store

This application requires a local FAISS vector store. Make sure you have your `db_faiss` directory inside a `vectorstore` folder in your project's root. The structure should look like this:

```
your-project/
├── vectorstore/
│   └── db_faiss/
│       ├── index.faiss
│       └── index.pkl
├── app.py
├── .env
└── README.md
```

### 5. Run the App!

You're all set! Start the Streamlit application with this command:

```bash
streamlit run your_script_name.py
```

Open your web browser and navigate to the local URL provided by Streamlit (usually `http://localhost:8501`).

---

## 📜 Disclaimer

This chatbot is a proof-of-concept and for informational purposes only. The information provided is not a substitute for professional medical advice, diagnosis, or treatment. Always seek the advice of your physician or other qualified health provider with any questions you may have regarding a medical condition.


