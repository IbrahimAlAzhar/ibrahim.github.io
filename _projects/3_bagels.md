---
layout: page
title: "BAGELS"
description: "Benchmark & PointWise evaluation for limitation extraction and generation (EMNLP Findings 2025)"
importance: 3
category: research
---

**Published:** Findings of EMNLP 2025 · [Paper](https://aclanthology.org/2025.findings-emnlp.1050/) · [arXiv](https://arxiv.org/abs/2505.18207) · [Code](https://github.com/IbrahimAlAzhar/BAGELS_Limitation_Gen) · [Dataset](https://huggingface.co/datasets/IbrahimAlAzhar/limitation-generation-dataset-bagels)

BAGELS is a complete pipeline for the computational analysis of research limitations:

1. A **dataset** of limitations extracted from papers and supplemented with external peer reviews.
2. **Retrieval-augmented generation** methods that produce literature-grounded limitations.
3. **PointWise** — an evaluation that matches atomic **Limitation Units** instead of paragraph-level similarity, so coverage and factual support of individual critiques become inspectable. Keyword and embedding metrics reward superficial overlap; holistic LLM judges blur coverage differences. PointWise addresses both.
