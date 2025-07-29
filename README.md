⚕️ Medical Questions Chatbot

Welcome to the Medical Questions Chatbot! This interactive web application is designed to answer your medical questions based on a specialized, local knowledge base. It's a smart and intuitive tool built to provide information quickly and accurately, right from your browser.

(Feel free to replace the placeholder above with a real screenshot of your app!)

🤔 What is this?

This chatbot is more than just a simple Q&A bot. It's a Retrieval-Augmented Generation (RAG) system. This means it doesn't just guess answers from a massive, general-purpose AI model. Instead, it:

Searches a curated database of medical information for relevant documents.

Augments the AI's knowledge with these specific documents.

Generates a precise answer based on the information it found.

This approach ensures that the answers are grounded in the provided context, making them more reliable and accurate for specialized topics like medicine.

✨ Features

Interactive Chat Interface: A clean and simple UI built with Streamlit.

Context-Aware Answers: The chatbot uses a local FAISS vector store to find relevant medical documents before answering.

Fast & Powerful LLM: Powered by Groq and the Llama3 model for near-instantaneous responses.

Source Citing: The bot shows you the source documents it used to generate the answer, so you can verify the information yourself.

Secure: Your API keys and data stay local. The application uses environment variables to keep your secrets safe.

🛠️ How It Works (The Tech Stack)

This project brings together several powerful open-source tools:

Frontend: Streamlit for creating the interactive web app interface.

Core Logic: LangChain for orchestrating the RAG pipeline (retrieval, prompt management, and LLM interaction).

LLM & Inference: Groq provides the blazing-fast API to run the llama3-8b-8192 language model.

Embeddings: sentence-transformers/all-MiniLM-L6-v2 from Hugging Face to convert text documents into numerical vectors.

Vector Store: FAISS from Meta AI for efficient similarity search on the medical document vectors.

🚀 Getting Started

Ready to run the chatbot on your own machine? Follow these steps.

Prerequisites

Python 3.8 or newer

Access to a terminal or command prompt

A Groq API Key

1. Clone the Repository

First, clone this repository to your local machine:

git clone <your-repository-url>
cd <your-repository-directory>


2. Set Up a Virtual Environment

It's highly recommended to use a virtual environment to keep your project dependencies isolated.

# Create the virtual environment
python -m venv venv

# Activate it
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate


3. Install Dependencies

Install all the necessary Python packages using the requirements.txt file.

pip install -r requirements.txt


(Note: If you don't have a requirements.txt file, you can create one by running pip freeze > requirements.txt after installing the packages manually: pip install streamlit langchain-huggingface langchain langchain_community faiss-cpu langchain-groq python-dotenv)

4. Configure Your Environment

You need to provide your Groq API key.

Create a file named .env in the root of your project directory.

Add your API key to this file:

GROQ_API_KEY="your-groq-api-key-goes-here"


5. Set Up the Vector Store

This application requires a local FAISS vector store. Make sure you have your db_faiss directory inside a vectorstore folder in your project's root. The structure should look like this:

your-project/
├── vectorstore/
│   └── db_faiss/
│       ├── index.faiss
│       └── index.pkl
├── app.py
├── .env
└── README.md


6. Run the App!

You're all set! Start the Streamlit application with this command:

streamlit run your_script_name.py


Open your web browser and navigate to the local URL provided by Streamlit (usually http://localhost:8501).

📜 Disclaimer

This chatbot is a proof-of-concept and for informational purposes only. The information provided is not a substitute for professional medical advice, diagnosis, or treatment. Always seek the advice of your physician or other qualified health provider with any questions you may have regarding a medical condition.