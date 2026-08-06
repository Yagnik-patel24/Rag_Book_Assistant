# 📚 RAG Book Assistant

A Retrieval-Augmented Generation (RAG) application built with **Streamlit**, **LangChain**, **ChromaDB**, **OpenAI Embeddings**, and **Mistral AI**. Upload any PDF document, create a vector database, and ask natural language questions. The chatbot retrieves the most relevant sections from the document and generates accurate answers based only on the uploaded content.

---

# ✨ Features

* 📄 Upload PDF books, research papers, or documents
* ✂️ Automatic document chunking
* 🧠 Generate embeddings using OpenAI Embeddings
* 💾 Store embeddings locally with ChromaDB
* 🔍 Semantic search using MMR (Maximal Marginal Relevance)
* 🤖 Answer questions using Mistral AI
* 📖 Responses are generated only from the uploaded document
* ⚡ Interactive Streamlit interface

---

# 🛠️ Tech Stack

* Python
* Streamlit
* LangChain
* Mistral AI
* OpenAI Embeddings
* ChromaDB
* PyPDFLoader
* Recursive Character Text Splitter
* python-dotenv

---

# 🏗️ Architecture

```text
                  PDF Upload
                       │
                       ▼
               PyPDFLoader
                       │
                       ▼
      RecursiveCharacterTextSplitter
                       │
                       ▼
            OpenAI Embeddings
                       │
                       ▼
                 ChromaDB
                       │
                       ▼
              MMR Retriever
                       │
                       ▼
              Relevant Chunks
                       │
                       ▼
             Prompt Template
                       │
                       ▼
            Mistral AI (LLM)
                       │
                       ▼
                 Final Answer
```

---

# 📂 Project Structure

```text
RAG-Book-Assistant/
│
├── app.py                 # Streamlit application
├── chroma_db/             # Local vector database (generated automatically)
├── requirements.txt       # Project dependencies
├── .env                   # API keys
├── README.md
└── .gitignore
```

---

# ⚙️ Installation

## 1. Clone the Repository

```bash
git clone https://github.com/your-username/RAG-Book-Assistant.git

cd RAG-Book-Assistant
```

---

## 2. Create a Virtual Environment

### Windows

```bash
python -m venv venv

venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv

source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4. Create a `.env` File

Add your API keys inside a `.env` file.

```env
OPENAI_API_KEY=your_openai_api_key
MISTRAL_API_KEY=your_mistral_api_key
```

---

## 5. Run the Application

```bash
streamlit run app.py
```

---

# 🚀 How It Works

### Step 1

Upload any PDF document.

Examples:

* Books
* Research papers
* Reports
* Documentation
* Notes

---

### Step 2

Click **Create Vector Database**.

The application will:

* Load the PDF
* Split it into smaller chunks
* Generate embeddings
* Store them in ChromaDB

---

### Step 3

Ask questions about the uploaded document.

Example questions:

* What is the main topic of this document?
* Summarize Chapter 2.
* Explain the author's conclusion.
* What are the key findings?
* Who is the target audience?

---

### Step 4

The retriever searches for the most relevant chunks using **MMR**.

---

### Step 5

The retrieved context is sent to Mistral AI, which generates an answer based only on the document.

If the answer is unavailable in the uploaded content, the chatbot responds:

> "I could not find the answer in the document."

---

# 🔍 Retrieval Strategy

The application uses **Maximal Marginal Relevance (MMR)** to improve retrieval quality.

Configuration:

```python
search_type="mmr"

k=4

fetch_k=10

lambda_mult=0.5
```

Benefits:

* Reduces duplicate context
* Improves diversity of retrieved chunks
* Produces more informative answers

---

# 📦 Dependencies

```text
streamlit
langchain
langchain-community
langchain-openai
langchain-mistralai
langchain-text-splitters
chromadb
pypdf
python-dotenv
```

---

# 🔮 Future Improvements

* Support multiple PDF uploads
* Chat memory for follow-up questions
* Source citation with page numbers
* Display retrieved document chunks
* Streaming AI responses
* OCR support for scanned PDFs
* Hybrid search (semantic + keyword)
* Metadata filtering
* FAISS and Pinecone support
* Local embedding models (Ollama, Hugging Face)
* Local LLM support using Ollama

---

# 🤝 Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a new feature branch.

```bash
git checkout -b feature-name
```

3. Commit your changes.

```bash
git commit -m "Add new feature"
```

4. Push the branch.

```bash
git push origin feature-name
```

5. Open a Pull Request.

---

# 📄 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

**Yagnik Patel** 

If you found this project useful, consider giving it a ⭐ on GitHub.
