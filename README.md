# AI-Powered Financial Q&A Chatbot Project

<p align="center">
  <img
    src="https://github.com/user-attachments/assets/08b6c346-c5ab-4816-bb82-c997b4110d1d"
    alt="Outamation"
    style="max-width: 70%; height: auto;"
    />
</p>

*Conducted as part of a consulting externship in collaboration with Outamation through Extern.*

## Executive Summary
Financial teams often need fast, reliable answers from complex documents such as statements, agreements, and lender forms. However, extracting the right information typically requires manual review and repeated lookups. This project built an interactive, Retrieval-Augmented Generation (RAG) chatbot that allows users to upload finance-related PDFs and ask natural-language questions to instantly retrieve grounded answers from the document content. The system converts unstructured documents into a searchable knowledge layer using OCR and semantic retrieval, then generates responses that are anchored to the source text for transparency. The goal was to reduce time spent on document review, improve consistency in Q&A, and demonstrate a scalable approach to AI-assisted financial document understanding for Outamation’s document automation workflows.

### Business Problem
The primary goal was to reduce the time, effort, and risk associated with extracting answers from unstructured financial documents used in routine and ad hoc decision-making. Finance and operations teams rely on long, inconsistently formatted PDFs that are difficult to search, requiring manual scanning, contextual interpretation, and repeated verification across pages. This process does not scale with document volume and increases the likelihood of missed details or inconsistent responses when timely answers are needed in document-driven workflows.

# Basic Retrieval-Augmented Generation (RAG) Pipeline

<img width="2587" height="2338" alt="basic rag pipeline" src="https://github.com/user-attachments/assets/825e99ff-5f56-4acc-a37a-6dc5045fed0c" />

This diagram above illustrates a standard Retrieval-Augmented Generation (RAG) workflow, divided into two main stages: Data Indexing and Data Retrieval & Generation.

1. Data Indexing

In the indexing stage, source documents are prepared for retrieval:
- Documents are loaded from external sources (e.g., PDFs).
- The text is split into smaller chunks to preserve context while enabling efficient search.
- Each chunk is converted into a vector embedding, capturing its semantic meaning.
- These embeddings are stored in a vector database, which serves as the searchable knowledge store.

This stage is performed once per document (or whenever documents change).

2. Data Retrieval & Generation

In the query stage, user questions are answered using the indexed data:
- A user query is embedded into the same vector space as the document chunks.
- The vector database performs similarity search to retrieve the top-K most relevant chunks.
- The retrieved chunks are provided as context to a large language model (LLM).
- The LLM generates a grounded response based on both the user query and the retrieved document context.

3. Why RAG?
By grounding LLM responses in retrieved source content, RAG improves:
- Factual accuracy
- Explainability (answers can be traced back to source chunks)
- Domain adaptability without retraining the model

This pipeline forms the foundation for scalable, document-aware question-answering systems.

### Methodology
1. [Step 1 – data ingestion / document parsing]
2. [Step 2 – chunking / embeddings / vector DB]
3. [Step 3 – retrieval + prompt + response generation]
4. [Step 4 – evaluation + iteration / improvements]

### Skills
- [Skills list]

### Results & Business Recommendations
**Results**
- [What the chatbot enables / improves]

**Business Recommendations**
- [How a team could implement/extend]
