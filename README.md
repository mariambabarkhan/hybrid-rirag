```markdown
# A Hybrid Framework for Regulatory Information Retrieval and Question Answering

## Overview

This repository contains the implementation of a hybrid framework designed for the **Regulatory Information Retrieval and Answer Generation (RIRAG)** shared task. The framework effectively retrieves and processes complex regulatory information to generate contextually accurate and concise answers. It integrates graph-based, vector-based, and statistical retrieval methods to enhance precision and relevance, making it well-suited for domain-specific question-answering tasks.

## Features

- **Hybrid Retrieval Framework**:
  - Combines **Neo4j Graph Database**, **BM25**, and **FAISS** for comprehensive and precise information retrieval.
  - Uses score-based fusion to refine results and ensure relevance.
- **Answer Generation**:
  - Leverages the **LLAMA3-70b** model for generating accurate, context-aware responses.
- **Dataset**:
  - Tested on the **ObliQA dataset**, containing regulatory documents from Abu Dhabi Global Markets (ADGM).

## Architecture

The hybrid framework comprises the following components:

1. **Graph-Based Retrieval**:
   - Structures queries and passages in Neo4j, capturing relationships within the data.
   - Retrieves relevant passages using cosine similarity.

2. **Statistical Retrieval**:
   - Implements BM25 for keyword-based matching and relevance scoring.

3. **Vector-Based Retrieval**:
   - Uses LegalBERT embeddings and FAISS for semantic similarity searches.

4. **Fusion and Re-ranking**:
   - Merges results from the above methods and recalculates relevance for the top passages.

5. **Answer Generation**:
   - Processes retrieved passages with LLAMA3 to produce coherent and regulatory-compliant answers.

![Framework Architecture](https://drive.google.com/uc?id=1udmtRhbgcgxh0dt7RD_pnSJK68Umy3_E)

## Results

### Retrieval Performance

| Model                 | RECALL@10 | MAP@10 |
|-----------------------|-----------|--------|
| BM25                 | 0.76      | 0.62   |
| BM25 + FAISS         | 0.58      | 0.29   |
| Neo4j + BM25 + FAISS | 0.79      | 0.74   |

### Answer Generation Performance

| Model                       | ES   | CS   | OCS  | Re   |
|-----------------------------|------|------|------|------|
| BM25 (PO) + GPT-4           | 0.77 | 0.24 | 0.22 | 0.58 |
| Neo4j + BM25 + FAISS + LLAMA3 | 0.43 | 0.36 | 0.15 | 0.41 |

## Limitations

- Scalability challenges with large and evolving regulatory datasets.
- Limited handling of ambiguous or incomplete relationships in regulatory texts.
- Dependence on pre-trained models that may not fully capture domain-specific nuances.

## Future Work

- Extend the framework with summarization techniques to enhance answer generation.
- Optimize graph-based retrieval for improved scalability and performance.

## Contact

For questions or collaboration, please contact [mariamk.bscs21seecs@seecs.edu.pk](mailto:mariamk.bscs21seecs@seecs.edu.pk).
```
