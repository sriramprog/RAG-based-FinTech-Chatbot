# Initial Analysis – How to Read This Folder

This folder contains early-stage analysis notebooks and supporting documents
used to explore, validate, and understand financial PDFs before building the
full RAG system.

### Purpose of this folder:
- Examine scanned and unstructured financial documents
- Evaluate OCR quality and layout preservation
- Validate document suitability for downstream retrieval and QA tasks

### What’s included:
- Jupyter notebooks focused on document inspection and OCR experiments
- Example financial PDFs (e.g., mortgage documents, fee worksheets) used as
  consistent inputs across analyses

### How to navigate:
1. _analyze_scanned_pdf_ consists of code to analyze a scanned PDF that extracts key sections of the mortgage document and includes the PDF file showing the highlighted sections.
2. _query_chunking_embedding_ consists of 2 independent notebooks that explains how to process queries if worded differently, and goes over chunking and embedding techniques used as part of experimentation.
3. _initial_rag_pipeline_ consists of code to demonstrate an open-source model (Gemini) from parsing PDF to chunking and embedding, and demonstrates the overall design workflow.

### Important context:
- These notebooks represent exploratory analysis, not final system design.
- The same documents may appear in later folders to support controlled
  comparisons across different techniques.
