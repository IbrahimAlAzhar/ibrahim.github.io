---
layout: page
title: "SciLimAgents"
description: "Preference-aligned multi-agent RAG for research limitation generation"
importance: 1
category: research
---

**Status:** manuscript under review

SciLimAgents is a hierarchical multi-agent framework that critiques scientific papers the way a panel of expert reviewers would. It extends [LimAgents]({{ '/projects/2_limagents/' | relative_url }}) with:

- **13 empirically derived specialist roles** (methodology, data, generalizability, evaluation, reproducibility, ...), each following a structured three-hop *search → verify → synthesize* trajectory.
- **Hybrid BM25/dense retrieval over a ~120K-paper evidence index**, with reranking and citation graphs.
- **Student-generated, procedure-diversified rollouts**, cross-family process rewards, and **role-specific SFT/DPO** — rather than assuming one training objective suits every specialist.

**Results.** An aligned **Qwen3-4B reaches 71.88 limitation-unit F1**, +10.7 points over the strongest evaluated zero-shot frontier baseline; process supervision alone adds +9.5 F1. Optimization helped some roles and hurt others — training novelty-only agents the same way degraded performance — which motivates role-aware alignment.

**Stack:** vLLM · Ray · tensor parallelism · LoRA/QLoRA · TRL (SFT/DPO) · FAISS · BM25
