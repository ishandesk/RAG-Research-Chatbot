# AI-Assisted Research Chatbot (RAG + LangChain + FAISS)

**Author:** Ishan — Final Year Student, NIT Delhi  
**Role:** AI/ML Developer  
**Summary:** A Retrieval-Augmented Generation (RAG) chatbot that indexes domain documents and answers questions grounded in retrieved context. Built with LangChain, FAISS/Chroma, and OpenAI/HuggingFace backends. This is a polished, personally-authored restructure of my RAG project with consistent code style, docs, and evaluation hooks.

---

## ✨ Features
- 📥 Ingestion pipeline for PDFs/TXT (chunking, embeddings)
- 🔎 Vector search (FAISS/Chroma) with tunable `chunk_size`, `overlap`, `top_k`
- 🧠 LLM backends: OpenAI / HuggingFace (local) — easily switchable via `.env`
- 💬 CLI and Streamlit UI for interactive Q&A
- 📊 Evaluation hooks to compare **RAG vs Base LLM**
- 🧪 Clean, modular code with docstrings and standardized naming

---

## 🧱 Project Structure
```
Ishan-RAG-Research-Chatbot/
├─ README.md
├─ requirements.txt
├─ LICENSE
├─ .gitignore
├─ data/                 # place your PDFs/TXTs here (optional)
├─ artifacts/            # vector index persisted here (gitignored)
├─ docs/                 # screenshots / notes
└─ src/
   ├─ data_ingestion.py  # parse docs → chunk → embed → index
   ├─ rag_pipeline.py    # retrieval + generation (CLI-friendly)
   ├─ app_streamlit.py   # simple Streamlit UI for Q&A
   └─ utils/             # helper modules (prompts, loaders, etc.)
```

---

## ⚙️ Setup
```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# Linux/Mac:
source .venv/bin/activate

pip install -r requirements.txt
```

Create a `.env` file in the project root:
```dotenv
BACKEND=openai          # or 'hf' for HuggingFace
OPENAI_API_KEY=sk-...   # required if BACKEND=openai
OPENAI_MODEL=gpt-3.5-turbo
HF_MODEL=google/flan-t5-base
EMBEDDING_MODEL=all-MiniLM-L6-v2
```

---

## 🏗️ Build Index
Use the ingestion script to load documents, chunk them, and create a FAISS index:
```bash
python src/data_ingestion.py --input_dir data --chunk_size 600 --chunk_overlap 80 --store faiss
```

---

## 💬 Ask Questions (CLI)
```bash
python src/rag_pipeline.py --question "What is retrieval-augmented generation?" --k 5
```

---

## 🖥️ Streamlit UI
```bash
streamlit run src/app_streamlit.py
```

---

## 📊 Evaluation (RAG vs Base)
Use the placeholders in `src/` to evaluate semantic similarity against context as a proxy for factual grounding. (I keep evaluation lightweight for quick demos.)

---

## 🧪 What I Learned
- Designing a **RAG** system that grounds LLM answers in retrieved context
- Practical **hyperparameter tuning** (chunk size/overlap, `top_k`, embedding model)
- Trade-offs between **FAISS vs Chroma** and **OpenAI vs HF** backends
- Building quick **Streamlit** demos and clean CLIs

---


MIT — see `LICENSE`.

---
