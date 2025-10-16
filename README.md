# 🧠 AI-Assisted Research Chatbot (RAG + LangChain + FAISS)

**Author:** Ishan — Final Year Student, NIT Delhi  
**Project Type:** Research-Oriented Generative AI Application  
**Tech Stack:** Python | LangChain | FAISS | Sentence-Transformers | OpenAI API | Streamlit  

---

## 🚀 Overview
This project implements a **Retrieval-Augmented Generation (RAG)** chatbot that can read and understand custom research papers or PDFs and answer questions grounded in factual retrieved context.  
It combines **semantic retrieval** (FAISS vector search) with **large language model generation** (OpenAI / Hugging Face).

---

## ✨ Key Features
- 📚 Ingests and indexes your PDFs or text files into a FAISS vector database.  
- 🔎 Retrieves the most relevant text chunks for each query using embeddings.  
- 💬 Generates context-aware responses through OpenAI or local LLMs.  
- ⚙️ Supports easy hyperparameter tuning — chunk size, overlap, and top-k retrieval.  
- 🧠 Offers both a **CLI** and **Streamlit web UI** for quick interaction.  
- 🧪 Includes hooks for evaluating RAG vs Base LLM performance.  

---

## 📂 Folder Structure
Ishan-RAG-Research-Chatbot/
├── README.md
├── requirements.txt
├── data/ # place PDFs or text files here
├── artifacts/ # vector index saved here
└── src/
├── data_ingestion.py
├── rag_pipeline.py
├── app_streamlit.py
└── utils/
