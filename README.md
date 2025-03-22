# 🔍 Intelligent RAG-Based Document Retrieval System

## 📌 Overview
This project implements a **Retrieval-Augmented Generation (RAG) system** for intelligent document search and retrieval. It enables users to extract, preprocess, store, and query text from **PDFs, CSVs, voice files, and web links**, leveraging a **vector database and LLMs** for accurate responses.

## 🏗️ Architecture
```
[ User ] → [ Frontend UI ] → [ API (FastAPI) ] → [ Vector DB (FAISS/Pinecone) ] → [ Embedding Model ] → [ LLM (Hugging Face) ]
```

## 🚀 Features
✅ **Multi-source data ingestion**: PDFs, CSVs, voice files, web links  
✅ **Embeddings-based retrieval**: Efficient search via FAISS/Pinecone  
✅ **LLM-powered responses**: Uses transformers for intelligent answers  
✅ **Transparent retrieval**: Returns top-k chunks with similarity scores  
✅ **Automatic database updates**: Watches for document changes  
✅ **User-friendly UI**: Built with **Streamlit/Gradio**  
✅ **REST API support**: Query system programmatically using FastAPI  

---

## 📂 Project Structure
```
📦 RAG-System
 ┣ 📂 data_ingestion
 ┃ ┣ 📜 extract_pdfs.py
 ┃ ┣ 📜 extract_csvs.py
 ┃ ┣ 📜 extract_voice.py
 ┃ ┗ 📜 extract_web.py
 ┣ 📂 vector_store
 ┃ ┣ 📜 faiss_store.py
 ┃ ┗ 📜 pinecone_store.py
 ┣ 📂 rag_engine
 ┃ ┣ 📜 retriever.py
 ┃ ┣ 📜 generator.py
 ┃ ┗ 📜 query_pipeline.py
 ┣ 📂 ui
 ┃ ┗ 📜 app.py
 ┣ 📜 requirements.txt
 ┣ 📜 README.md
 ┗ 📜 main.py
```

---

## ⚙️ Tech Stack
| Component        | Technology |
|-----------------|------------|
| **Backend**     | Python |
| **Data Parsing**| PyPDF2, pandas, BeautifulSoup, Whisper |
| **Vector DB**   | FAISS / Pinecone |
| **Embeddings**  | Sentence-Transformers (all-MiniLM-L6-v2) |
| **LLM**         | Hugging Face Transformers (facebook/bart-large) |
| **Frontend**    | Streamlit / Gradio |
| **API**         | FastAPI |

---

## 🛠️ Installation
```bash
# Clone the repository
git clone https://github.com/butterpaneermasala/hacko-tech
cd rag-system

# Install dependencies
pip install -r requirements.txt

# run
streamlit run app.py
```

---

## 🚀 Usage
### 1️⃣ Start the API
```bash
python main.py
```
### 2️⃣ Access the UI
```bash
streamlit run ui/app.py
```
### 3️⃣ API Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/ingest` | Upload and process documents |
| GET  | `/query?text=your_query` | Search documents and get responses |
| GET  | `/collections` | List available document collections |

---

## 🔒 Security Measures
✔ Input validation for document uploads  
✔ Confidence thresholds for LLM responses  
✔ Metadata and access controls for stored data  

---

## 📌 Future Enhancements
🔹 Implement cross-encoder for better re-ranking  
🔹 Support additional file formats (JSON, DOCX)  
🔹 Optimize embeddings with knowledge distillation  

📢 **Contributions are welcome!** Feel free to open an issue or submit a PR. 🙌