---
layout: page
title: LLM Shepherding for Cost-Efficient Inference
description: Research project on token-budgeted SLM-LLM collaboration.
img: assets/img/9.jpg
importance: 1
category: featured
---

This project studies how to reduce inference cost while keeping high task accuracy by combining small and large language models.

Paper: [Pay for Hints, Not Answers: LLM Shepherding for Cost-Efficient Inference (arXiv:2601.22132)](https://arxiv.org/abs/2601.22132)

### Summary
Instead of asking an LLM for a full answer every time, the framework requests only a short prefix hint and lets an SLM complete the task. This creates a fine-grained cost/quality tradeoff that is more flexible than standard routing or cascading.

### Key Results
- Hint lengths of around 10-30% of full LLM output can significantly improve SLM performance on math and coding tasks.
- The method reports 42-94% cost reduction versus LLM-only inference.
- It achieves up to 2.8x cost reduction compared with strong routing/cascading baselines while matching accuracy.

### My Role
- Built and evaluated the LLM Shepherding pipeline for reasoning and code-generation benchmarks.
- Implemented predictor-based decision logic for hint usage and token budget allocation.
