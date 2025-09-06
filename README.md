# RAG using LangChain & OpenAI

This project demonstrates a **Retrieval-Augmented Generation (RAG)** pipeline built with **LangChain**, **OpenAI LLMs**, and **FAISS vector database**.  
The pipeline can take transcripts (e.g., from YouTube) or documents, split them into chunks, embed them into a vector database, and then retrieve relevant context to generate more accurate, grounded answers.

---

## Features
- **Retriever**: Uses LangChain’s `as_retriever` interface to fetch relevant chunks with similarity/MMR search.  
- **Vector Database**: FAISS for storing and searching embeddings.  
- **LLM**: OpenAI’s `ChatOpenAI` (via `langchain-openai`) for generating answers.  
- **Embeddings**: OpenAI embeddings (with optional HuggingFace embeddings).  
- **Prompt Engineering**: Custom `PromptTemplate` to guide model responses.  
- **Evaluation**: Uses BLEU score (NLTK) for text quality comparison.  
- **Transcript Support**: Integrates with `youtube-transcript-api` to load video transcripts.  

---

## Architecture

User Query

│

▼

[Retriever] ──> (Search in FAISS vector DB)

│

▼

Relevant Chunks + Query

│

▼

[OpenAI Chat Model] ──> Generate Answer

---

## Tech Stack
- **LLM**: OpenAI (via `langchain-openai`)  
- **API**: OpenAI API  
- **Vector Database**: FAISS (with option to experiment with Chroma)  
- **Retriever**: LangChain retriever wrapping FAISS  
- **Embeddings**: OpenAI Embeddings (optionally HuggingFace)  
- **Libraries**:  
  - LangChain  
  - youtube-transcript-api  
  - FAISS  
  - NLTK (for BLEU evaluation)  
  - tiktoken  
  - python-dotenv  
