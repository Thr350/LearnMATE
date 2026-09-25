# LearnMATE

An AI-powered STEM tutoring app for primary school students, built as my Final Year Project (BSCS, University of Agriculture Peshawar).

LearnMATE uses a Retrieval-Augmented Generation (RAG) pipeline to generate explanations and practice questions tailored to a student's grade level and learning gaps, rather than relying on generic, one-size-fits-all content.

## What it does

- Takes curriculum content and breaks it into chunks suited for retrieval
- Embeds and stores that content in a vector database (ChromaDB)
- Retrieves the most relevant, grade-appropriate context for a student's query
- Uses an LLM (LLaMA, via Groq) to generate a personalized explanation or practice question grounded in that retrieved context
- Serves this through a FastAPI backend to a Flutter mobile frontend

## Architecture

Flutter (frontend)
      │
      ▼
FastAPI (backend)
      │
      ▼
RAG Pipeline
  ├── Chunking & embedding of curriculum data
  ├── ChromaDB (vector store / retrieval)
  └── LLaMA via Groq (generation)

## My contribution

I designed and implemented the RAG pipeline end-to-end: chunking curriculum data, embedding it, storing it in ChromaDB, and retrieving relevant context to feed the LLM. I also built the FastAPI backend and connected it to the Flutter frontend.

The hardest problem was tuning retrieval so it surfaced content that was not just semantically similar, but pedagogically appropriate for young learners — the right explanation for a child's level, not just the closest match in the embedding space. I also debugged a set of cross-platform issues (file paths, environment differences) that came up moving development between Windows and Mac.

## Tech stack

- **Backend:** FastAPI
- **Frontend:** Flutter
- **Vector store:** ChromaDB
- **LLM inference:** LLaMA via Groq
- **Language:** Python, Dart

## Status

Completed and defended as a Final Year Project.


## Screenshots
<img width="580" height="274" alt="Screenshot 2026-07-03 at 5 06 48 PM" src="https://github.com/user-attachments/assets/eca560ef-7c7c-48e1-a109-fd2754ac7fd6" />

<img width="580" height="274" alt="Screenshot 2026-07-03 at 5 06 48 PM" src="https://github.com/user-attachments/assets/c3669b62-d008-4d13-9421-f85f5882faaa" />





