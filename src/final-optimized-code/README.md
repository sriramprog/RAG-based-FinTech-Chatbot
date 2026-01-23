## Final Optimized Code – How to Read This Folder

This folder contains the application-layer code for a Document Intelligence RAG system.
Its purpose is to wire together PDF ingestion, retrieval configuration, and question answering into a single, inspectable interface that demonstrates how the backend pipeline is orchestrated end to end.
The UI is best read as executable documentation for how the RAG components interact, not as a deployed product.

# Purpose of This Folder
- Show how optimized RAG components are composed into an application layer/
- Demonstrate how retrieval parameters are exposed and passed downstream

Provide a concrete reference for:
- PDF ingestion
- Index construction
- Retrieval configuration
- Answer generation with source grounding

# What the Code Does
1. Defines a lightweight UI layer (Gradio-based) that:
- Accepts a PDF input
- Triggers document parsing, chunking, and indexing
- Stores document metadata for downstream filtering

2. Exposes retrieval controls that map directly to backend logic:
- Number of chunks to retrieve
- Document-type filtering
- Optional query routing logic

3. Connects user queries to:
- Vector-based retrieval
- Context assembly
- LLM-based answer generation

4. Surfaces intermediate states (processing, routing, retrieval) to make system behavior inspectable

# How to Read the Code
- Start with the PDF processing handler to understand how documents enter the system
- Follow how document metadata and embeddings are created and stored
- Trace how retrieval settings flow from the UI controls into the retriever
- Inspect the query-handling logic to see how retrieved chunks are passed to the LLM
- The UI components themselves are thin by design; the value lies in how they bind together the RAG pipeline stages.

# Important Context
- This folder focuses on interaction and usability, not model training or experimentation
- Backend logic and optimization experiments live in earlier folders
- UI errors typically indicate upstream processing or component integration issues rather than retrieval logic flaws
