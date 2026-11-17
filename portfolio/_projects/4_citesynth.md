---
layout: page
title: "CiteSynth"
description: "Citation-grounded literature synthesis with process-level, verifiable RL"
importance: 4
category: research
---

**Status:** ongoing manuscript

CiteSynth trains literature-synthesis agents using **checkable retrieval actions and claim–source relationships** rather than holistic LLM-judge scores. It builds a label-free benchmark in which each seed paper's cited set supplies gold evidence and weighted key points (**585 seed papers; 8,064-abstract corpus**).

**Findings.**

- **Trajectory-level DPO + step-attributed GRPO** on verifiable rewards gave the best score among non-oracle systems.
- **Outcome-only RL raised its own training reward (0.507 → 0.551) without improving held-out quality** — a reward-hacking signal.
- A holistic LLM judge **ranked ungrounded answers above grounded ones**, showing why verifiable rewards matter.

Because an author's citations are neither exhaustive nor always correct, citation-derived labels are treated as *proxies* that require independent tests.
