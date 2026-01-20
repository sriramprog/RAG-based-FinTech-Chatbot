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
- Notebooks can be read independently; there is no strict execution order.
- Each notebook focuses on a specific analysis task (e.g., OCR accuracy,
  extracted fields, document structure).
- Outputs and observations are documented inline within each notebook.

### Important context:
- These notebooks represent exploratory analysis, not final system design.
- The same documents may appear in later folders to support controlled
  comparisons across different techniques.
- Cleaned notebook versions are provided for GitHub preview compatibility.

This folder establishes the document-level understanding required before
retrieval optimization, RAG pipeline construction, and UI development.
