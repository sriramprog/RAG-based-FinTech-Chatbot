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
Financial teams frequently need fast, reliable answers from complex documents such as statements, agreements, and lender forms. However, extracting information from these documents typically requires manual review, repeated lookups, and contextual interpretation across pages.

This project developed an interactive Retrieval-Augmented Generation (RAG) chatbot that allows users to upload finance-related PDFs and ask natural-language questions to retrieve grounded, explainable answers directly from document content. The system transforms unstructured financial documents into a searchable knowledge layer using OCR and semantic retrieval, then generates responses anchored to source text for transparency.

The goal was to reduce document review time, improve answer consistency, and demonstrate a scalable approach to AI-assisted financial document understanding aligned with Outamation’s document automation workflows.

### Business Problem
Finance and operations teams rely heavily on long, inconsistently formatted PDFs for routine and ad-hoc decision-making. These documents are difficult to search and require manual scanning, increasing time cost and the risk of missed or inconsistent answers.

As document volume grows, manual review does not scale. Teams need a system that can:
1. Retrieve relevant information quickly
2. Preserve context across sections and pages
3. Provide answers that are traceable back to source documents

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
Step 1: Document Ingestion & Parsing
- Processed scanned and digital financial PDFs
- Applied OCR where necessary to extract machine-readable text

Step 2: Chunking, Embeddings & Vector Storage
- Split documents into semantically meaningful chunks
- Generated embeddings and stored them in a vector database for retrieval

Step 3: Retrieval & Answer Generation
- Retrieved top-K relevant chunks based on query similarity
- Constructed prompts combining user queries with retrieved context
- Generated responses using an LLM grounded in document content

Step 4: Evaluation & Iteration
- Tested query phrasing, chunking strategies, and retrieval parameters
- Evaluated answer quality, faithfulness, and failure cases
- Iterated on segmentation, routing, and model selection

### Skills
- Retrieval-Augmented Generation (RAG)
- OCR & document parsing
- Semantic search & vector databases
- Chunking and embedding strategies
- LLM-based question answering
- Python, notebooks, and modular pipeline design
- Model evaluation and error analysis

### Results & Business Recommendations
**Results**
- Enabled natural-language question answering over complex financial PDFs, including scanned mortgage documents, contracts, and fee worksheets
- Reduced the need for manual page-by-page document scanning by surfacing contextually relevant sections on demand
- Improved answer reliability by grounding responses in retrieved document chunks rather than free-form generation
- Demonstrated explainable Q&A, where responses can be traced back to specific portions of source documents
- Validated that a modular RAG pipeline can generalize across multiple financial document types without document-specific rules

**Overall Outcome:** the system shows how AI-assisted document understanding can significantly streamline financial review workflows while preserving transparency and auditability.

**Business Recommendations**
- Embed RAG-based Q&A into document automation workflows to reduce time spent on repetitive financial document review
- Introduce document-type classification and routing (e.g., mortgage, contract, payslip) to further improve retrieval precision
- Add inline source highlighting and citations to support compliance, audit, and trust requirements
- Monitor retrieval quality using query logs and feedback to iteratively tune chunking and embedding strategies
- Deploy as an internal tool for finance, compliance, or operations teams handling high document volumes before external-facing use

### Live Demo
<img width="1891" height="906" alt="Chatbot landing page" src="https://github.com/user-attachments/assets/0843d9dd-8ead-478c-bd37-fc8afe434fdb" />
_**NOTE: A few screenshots of the UI in action will be included here.
**_

A short walkthrough video is included below to demonstrate the system end-to-end, including PDF ingestion, retrieval configuration, and question answering.

📹 Demo: AI-Powered Financial Q&A Chatbot – Live Walkthrough
(Upload video file here or embed link)
_The demo highlights system behavior under real document inputs rather than curated examples._

Once uploaded, GitHub will render the video inline for easy viewing.

### Limitations & Next Steps
**Current Limitations**
1. Retrieval quality depends on chunking strategy
While the system performs well on most queries, answer quality is sensitive to how documents are segmented. Poor chunk boundaries can occasionally omit relevant context or retrieve partially related sections.

2. No persistent feedback loop
The current implementation does not store user feedback or query performance metrics, limiting automated evaluation and continuous improvement over time.

3. Document processing is synchronous
PDF ingestion and indexing occur in a single workflow, which may introduce latency for large or multi-document uploads in a production setting.

4. Limited citation surfacing in the UI
Although answers are grounded in retrieved chunks, the UI does not yet expose fine-grained inline citations or page-level highlighting.

**Next Steps**
1. Introduce adaptive chunking and metadata-aware retrieval
Incorporate document structure (sections, headers, page numbers) and metadata to improve retrieval precision and reduce context fragmentation.

2. Add retrieval evaluation and feedback logging
Capture query logs, retrieved chunks, and user feedback to enable systematic evaluation and tuning of retrieval performance.

3. Implement asynchronous document processing
Move ingestion and indexing to background jobs to support larger documents and higher throughput.

4. Enhance explainability with source highlighting
Surface exact page references and highlighted text spans to improve trust, auditability, and usability for financial workflows.

5. Extend to multi-document and cross-document queries
Expand support for questions that require reasoning across multiple related financial documents.
