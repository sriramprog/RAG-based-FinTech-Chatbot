## Optimizations – How to Read This Folder

This folder contains focused experiments and optimization tasks designed to stress-test, compare, and refine specific components of the RAG pipeline after initial feasibility was established.
Unlike the Initial Analysis stage, notebooks and scripts here are deliberately scoped, comparative, and task-driven, with the goal of improving accuracy, robustness, and scalability across real-world financial PDFs.

# Purpose of This Folder
- Optimize document ingestion, segmentation, and routing strategies
- Compare open-source and closed-source LLM performance on realistic financial queries
- Validate multi-document query handling and routing logic
- Stress-test the pipeline using heterogeneous financial document types

# What’s Included
1. Full Segmentation Pipeline:
End-to-end experimentation around document segmentation with metadata outputs
Explores how structured segmentation improves downstream retrieval, filtering, and answer grounding

Includes:
- Task notebook for building the full segmentation pipeline
- Test PDF(s) used to validate segmentation behavior

2. Open-Source vs Closed-Source Model Evaluation
Comparative evaluation of Gemini vs Mistral Phi-2 on mortgage and contract-style queries

Focuses on:
- Answer accuracy
- Relevance to source text
- Failure modes across different model classes

Includes:
- Evaluation notebook
- Sample mortgage / contract PDFs used consistently across runs

3. Routing Queries Across Multiple PDFs
Experiments with query routing and retrieval across multiple financial documents

Tests the system’s ability to:
- Identify the correct document(s)
- Avoid cross-document hallucinations
- Handle overlapping financial concepts (fees, contracts, payslips, disclosures)

Includes:
- Multiple heterogeneous financial PDFs (contracts, fee worksheets, payslips)
- A Python task script implementing multi-PDF routing logic

# How to Navigate
Each subfolder represents a self-contained optimization question

Notebooks typically follow this pattern:
- Problem framing
- Experimental setup
- Observations and failure cases
- Implications for the broader RAG system

PDFs are intentionally reused across tasks to enable controlled comparisons

# Important Context
These notebooks are not exploratory drafts—they are targeted experiments answering specific design questions.

Results here directly inform architectural decisions in later pipeline stages

Some files may appear redundant across folders by design, to preserve experimental consistency
