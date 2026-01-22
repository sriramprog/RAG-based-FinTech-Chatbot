## Optimizations – How to Read This Folder

This folder contains focused experiments and optimization tasks designed to evaluate, stress-test, and refine specific components of the RAG pipeline after the initial end-to-end baseline was established.
Work in this folder is deliberately comparative and task-oriented, answering concrete system design questions around segmentation, model selection, and multi-document retrieval.

# Purpose of This Folder
- Optimize document ingestion, segmentation, and routing strategies
- Compare open-source and closed-source LLM performance on realistic financial queries
- Validate multi-document query handling and routing logic
- Stress-test the pipeline using heterogeneous financial document types

# What’s Included
1. Full Segmentation Pipeline:
- Builds and evaluates a complete document segmentation pipeline with metadata outputs
Tests how structured segmentation improves:
- Retrieval accuracy
- Filtering and ranking
- Source attribution in answers

Includes:
- A task notebook for building the full segmentation workflow (Task_Build_the_Full_Segmentation_Pipeline.ipynb)
- Test PDFs used to validate segmentation behavior

2. Open-Source vs Closed-Source Model Evaluation:
Compares Gemini vs Mistral Phi-2 on mortgage and contract-style financial queries

Evaluates:
- Answer correctness
- Relevance to source documents
- Model-specific failure patterns

Includes:
- An evaluation notebook (Task_Evaluate_Gemini_vs_Mistral.ipynb)
- Consistent sample PDFs used across model runs

3. Routing Queries Across Multiple PDFs:
Experiments with query routing and retrieval across multiple financial documents

Tests the system’s ability to:
- Identify relevant documents dynamically
- Avoid cross-document hallucinations
- Handle overlapping financial concepts (fees, contracts, payslips)

Includes:
- Multiple heterogeneous financial PDFs
- A Python task script implementing multi-PDF routing logic (task_route_queries_across_multiple_pdfs.py)

# How to Navigate
Each subfolder represents a self-contained optimization question

Notebooks and scripts typically follow:
- Problem definition
- Experimental setup
- Observations and failure cases
- System-level implications

PDFs are reused intentionally to enable controlled, apples-to-apples comparisons

# Important Context
These are targeted optimization experiments, not exploratory drafts.

Results here directly inform architectural decisions in later pipeline stages.

Some files may appear redundant across folders by design, to preserve experimental consistency.
