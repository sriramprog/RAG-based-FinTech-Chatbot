## Initial Analysis – How to Read This Folder
This folder contains early-stage analysis notebooks and supporting documents used to explore, validate, and understand scanned and unstructured financial PDFs before designing the full Retrieval-Augmented Generation (RAG) system.

The work here focuses on document understanding, OCR quality, layout preservation, and feasibility validation, laying the groundwork for all downstream pipeline and optimization decisions.

# Purpose of This Folder
- Examine scanned and semi-structured financial documents
- Evaluate OCR accuracy and layouts on real-world PDFs
- Understand document structure and key field locations
- Validate document suitability for chunking, embedding, and retrieval tasks

# What’s Included
1. Scanned PDF Analysis
Task_Analyze_a_Scanned_PDF.ipynb:
- Analyzes a scanned mortgage document end-to-end
- Explores OCR output, text quality, and layout issues
- Identifies challenges such as noise, misalignment, and missing fields

Extract Key Fields (Scanned Mortgage PDF).pdf:
- Reference PDF highlighting important mortgage fields
- Used to visually validate OCR and extraction accuracy

2. Chunking, Embeddings, and Retrieval Foundations
Task_Implementing_Chunking_&_Embeddings_in_LlamaIndex.ipynb:
- Experiments with chunking strategies and embedding workflows
- Tests how document segmentation choices impact retrieval quality
- Establishes a baseline ingestion approach using LlamaIndex

Task_Hands_On_Query_Processing_&_Retrieval_Optimization.ipynb:
- Hands-on experimentation with query phrasing and retrieval behavior
- Evaluates how differently worded queries surface results
- Highlights early failure cases and retrieval limitations

3. Initial RAG Pipeline Baseline
Task_Build_and_Optimize_a_RAG_pipeline.ipynb:
- Demonstrates a baseline, end-to-end RAG workflow: PDF parsing → chunking → embedding → retrieval → answer generation
- Serves as the first “full loop” prototype before later optimizations
= Establishes the initial system design workflow used as a reference point for future comparisons

# How to Navigate
Notebooks are best read top-down, starting with scanned PDF analysis

Each notebook isolates a specific question:
- Can this document be reliably parsed?
- Is OCR good enough for QA tasks?
- How does chunking affect retrieval?
- PDFs are included as ground truth references and reused across later stages

# Important Context
These notebooks are exploratory and diagnostic, not final system designs
Code prioritizes clarity and inspection over performance or abstraction

Findings here directly inform:
- Segmentation strategies
- Metadata design
- Model evaluation experiments in later folders
