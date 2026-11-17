---
layout: page
title: "SciSec"
description: "Attacks and provenance-aware defenses for LLM-assisted peer review"
importance: 5
category: research
---

**Status:** manuscript under review — *Who Controls the Review?*

As LLMs enter peer review, a manuscript itself becomes an attack surface. SciSec studies:

- **SciAttack-BB / WB** — manuscript-native rhetorical and instruction attacks, plus gradient-optimized white-box attacks. SciAttack-BB reached **95.3% attack success on Qwen3-8B**.
- **SciDefense** — provenance-aware multi-agent verification, span localization, and selective sanitization. On rhetorical attacks it achieved **0.640 F1 vs. 0.555 for Spotlighting**, with false-positive rate cut from **0.238 to 0.083**.

A key lesson: *detecting* attack text, *removing* it, and *recovering* the evidence-consistent decision are different problems — full-review repair remains open.

**Related:** mechanistic interpretability of evidence-grounded decisions under prompt injection (Qwen, Gemma, Mistral) using counterfactual evidence pairs, activation patching, and attention-head / MLP / residual-stream interventions.
