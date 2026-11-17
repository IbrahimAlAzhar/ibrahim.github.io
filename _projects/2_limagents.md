---
layout: page
title: "LimAgents"
description: "Multi-agent LLMs + RAG for scientific limitation generation (JCDL 2026)"
importance: 2
category: research
---

**Published:** ACM/IEEE JCDL 2026 · [Live demo](https://limagents-novagents-live.onrender.com) · [Dataset](https://huggingface.co/datasets/iaadlab/LimAgents_limitation_data_scientific_papers_with_cited_papers)

Authors often under-report the weaknesses of their own work. LimAgents is a **training-free** framework in which specialist agents (extractor, analyzer, reviewer, citation, ...), leader agents, and a master agent collaboratively identify a paper's limitations, grounded in **retrieval over the paper's cited literature** and refined with **iterative feedback**.

**Results.** Limitation-unit F1 improved from **37.91 → 52.36 on Mistral-7B** and **19.14 → 53.32 on Qwen2.5-3B** over zero-shot baselines. Feedback gains varied by model.
