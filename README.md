# MenuRAG-Intelligent Menu Question Answering using Retrieval Augmented Generation

## 📌 Overview

MenuRAG is a lightweight, fully open-source Retrieval-Augmented Generation (RAG) system designed for conversational querying over restaurant menu PDFs. It enables users to explore menu items, pricing, and available options through natural language interaction.

The system focuses on Semantic retrieval and response Generation using local, open source models without reliance on external APIs.


 🚀 Key Features

* 📄 PDF-based menu ingestion
* 🔍 Semantic search using FAISS vector database
* 🤖 Response generation via FLAN-T5
* ⚡ Fully local and free (no paid APIs)
* 💬 Interactive command-line chatbot

 🧠 Architecture

1. Document Loading → PyPDFLoader
2. Text Splitting → Chunk-based processing
3. Text Embedding → Sentence Transformers (MiniLM)
4. Vector Store → FAISS
5. Retrieval → Top-k semantic search
6. Generation → FLAN-T5 (HuggingFace)

  🛠️ Tech Stack

* Python
* LangChain
* FAISS
* HuggingFace Transformers
* Sentence Transformers

 ⚙️ Installation

```bash
pip install langchain faiss-cpu sentence-transformers pypdf langchain-community transformers
```

---

## ▶️ Usage

1. Run the script
2. Upload a text-based menu PDF
3. Ask questions such as:

   * "Show the pizza menu"
   * "List available items"
   * "What are the prices?"
   * "What items are available?"

---

## 📊 Example Queries

| Query                     | Response                                                                                |
| ------------------------- | --------------------------------------------------------------------------------------- |
| Show pizza menu           | Displays menu section including items like Margherita, Pepperoni, BBQ Chicken, Hawaiian |
| List prices               | $10.50, $8.00, $9.25, $10.50, $10.50                                                    |
| What items are available? | Cheese Me, Margherita, Pepperoni, Sweet n Spicy Chicken, Meat Madness, Hawaiian         |
| Cheapest item             | $8.00 (price identified; item association may vary)                                     |


  ⚠️ Limitations

* Responses may include partially unstructured or concatenated menu text
* Item to price mapping is not always precise
* Occasional repetitive or noisy outputs may occur
* Limited reasoning capability due to small LLM (FLAN-T5)
* Works best with clean, text-based PDFs (not scanned documents)

  📌 Technical Notes

This project implements a **baseline RAG pipeline**, where:

* Relevant document chunks are retrieved using vector similarity
* A lightweight transformer generates responses conditioned on retrieved context

Performance depends on:

* document structure
* chunking strategy
* retrieval parameters
* model size

  🔮 Future Work

* Improved prompt engineering for cleaner outputs
* Integration of larger or instruction tuned LLMs
* Deployment as an API (FastAPI + Docker)



