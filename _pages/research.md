---
layout: page
permalink: /research/
title: research
description: "Complementary intelligence for science: verifiable, diversity-preserving AI for collective discovery."
nav: true
nav_order: 1
toc:
  sidebar: left
---

## Vision

AI now generates hypotheses, critiques, syntheses, and proposals for science, yet **more output does not automatically mean more knowledge**. Recent work shows that AI tools can raise individual scientists' impact while _contracting_ the collective focus of science, and that generated ideas tend to converge on familiar directions.

My research develops **complementary intelligence for science**: AI that surfaces overlooked evidence, **preserves supported differences** instead of collapsing to consensus, and makes every claim **verifiable**. I call the target _verified difference_ — rewarding distinct, evidence-backed insight rather than novelty without validity.

## Research threads

### 1. Evidence-grounded scientific critique

How can AI identify the real weaknesses and open directions of a paper — not just generic criticism?

- **LimTopic** (JCDL 2024) organized limitation statements with BERTopic + LLM interpretation.
- **BAGELS** (EMNLP Findings 2025) introduced retrieval-grounded critique generation and **PointWise**, which matches atomic _Limitation Units_ rather than paragraph-level similarity.
- **LimAgents** (JCDL 2026) used specialist agents, scholarly retrieval, and feedback: limitation-unit F1 rose from 37.91 → 52.36 (Mistral-7B) and 19.14 → 53.32 (Qwen2.5-3B).
- **SciLimAgents** (under review) scales to **13 specialist roles** over a **~120K-paper** index with role-specific SFT/DPO; an aligned Qwen3-4B reaches **71.88 F1**, +10.7 over the strongest zero-shot frontier baseline.
- **FutureGen / FutureLens / FutureScope** study generation and long-term patterns of future-work statements across thousands of ACL papers.

### 2. Verifiable learning

Can we train agents on rewards that stay meaningful under optimization?

- **CiteSynth** trains citation-grounded literature-synthesis agents with checkable retrieval actions and claim–source links. Outcome-only RL raised its own training reward (0.507 → 0.551) **without** held-out gains, and a holistic LLM judge ranked ungrounded answers above grounded ones — evidence that process-level, verifiable rewards matter.
- I compare outcome-only, summed-step, and **step-attributed** rewards under matched reward density and compute to separate credit assignment from extra feedback.

### 3. Preserving distinctive knowledge

When does synthesis lose valuable insight?

- In a pilot, specialist agents collectively recovered **79.0%** of reference limitations, but synthesis kept only **49.7%**. Critiques raised by multiple agents survived far more often than unique ones (85.5% vs. 57.5%), and outputs across eight systems were **1.18–1.63×** more homogeneous than human references.
- I am building an **expert-adjudicated benchmark** that separates supported findings, valid-but-unrecorded findings, redundancy, and unsupported claims, and **aggregation methods that preserve verified minority findings** while discouraging fabricated novelty.
- Human–AI studies will test whether evidence-preserving AI actually helps researchers find more _uniquely useful_ insights — not just more suggestions.

### 4. Trustworthy AI-assisted judgment

- **SciSec** (under review) studies manuscript-embedded attacks on LLM-assisted peer review and **provenance-aware defenses** — SciDefense reaches 0.640 F1 vs. 0.555 for Spotlighting while cutting false positives from 0.238 to 0.083.
- **Mechanistic interpretability** experiments use counterfactual evidence pairs and activation patching to ask how adversarial content changes sensitivity to legitimate evidence — and show that fixing a constrained rating does not necessarily repair a full review.

## Manuscripts under review & in preparation

- **SciLimAgents:** A Preference-Aligned Multi-Agent RAG Framework for Research Limitation Generation. _Under review._
- **Who Controls the Review? SciSec:** Attacks and Provenance-Aware Defense for LLM-Assisted Peer Review. _Under review._
- **CiteSynth:** Citation-Grounded Scientific Literature Synthesis with Process-Level RL. _In preparation._
- **Hallucination Detection and Repair in Direct and Decomposed Agent Workflows** — a 2×2 study across three tasks and open models (26,962 runs). _Collaborative, submitted._
- **A Comprehensive Survey of RAG Evaluation and Benchmarks:** Perspectives from Information Retrieval and LLMs. _Preprint._
- **Beyond Generic Criticism:** Scientific Critique Homogenization. _Preliminary experiments._

## Collaborative work in progress

- Scientific knowledge transfer with LLMs: recommending methods across disciplines.
- LLMs and the readability of scientific articles.
- Benchmarking and classification of scientific figures.
- SocioLimitShield: evidence-grounded biomedical and societal impact analysis.

## Methods & tools

- **LLM learning & agents:** SFT, DPO, GRPO, preference learning, verifiable/process rewards, LoRA/QLoRA, multi-agent coordination, tool-use trajectories, AutoGen, LangGraph, MCP.
- **Retrieval:** RAG, BM25/dense hybrid search, reranking, FAISS, citation/knowledge graphs, GraphSAGE.
- **Systems:** vLLM, Ray, multi-GPU tensor parallelism, FP16/BF16, quantization, GPU-hour / latency / throughput profiling.
- **Interpretability & robustness:** activation patching, representation probing, prompt-injection attacks and defenses.
