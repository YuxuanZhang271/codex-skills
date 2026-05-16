---
domain: learning
title: "ChatVLA-2: Vision-Language-Action Model with Open-World Embodied Reasoning from Pretrained Knowledge"
aliases:
  - ChatVLA-2
type: paper
status: done
created: "2026-05-08"
updated: "2026-05-08"
authors:
  - Zhongyi Zhou
  - Yichen Zhu
  - Junjie Wen
  - Chaomin Shen
  - Yi Xu
year: 2025
venue: NeurIPS
doi: 10.48550/arXiv.2505.21906
url: https://arxiv.org/abs/2505.21906
pdf: "/Users/visomopokoa8/Documents/1 NUS/1 Master/Courses/ISY5003/Practice Module/Proposal/v2.0/References/ChatVLA-2.pdf"
research_area: embodied_ai
priority: 1
rating: 4
tags:
  - literature/paper
  - embodied-ai
  - robotics
  - vla
  - reasoning
---

# ChatVLA-2: Vision-Language-Action Model with Open-World Embodied Reasoning from Pretrained Knowledge

## One-Sentence Summary

ChatVLA-2 targets a key VLA failure mode: robot fine-tuning can erase pretrained VLM reasoning, so the model uses mixture-of-experts and staged training to preserve open-world reasoning while learning actions.

## Problem

End-to-end VLA training can degrade the original VLM's visual, textual, OCR, spatial, and math reasoning abilities. A robot model that loses those abilities may execute familiar actions but fail when a task requires open-world semantic reasoning.

## Core Method

- Use a dynamic mixture-of-experts VLA architecture.
- Separate training into stages so the model preserves VLM competencies while learning robot action following.
- Emphasize two capabilities:
  - Open-world embodied reasoning: recognize and reason over concepts inherited from the VLM.
  - Reasoning following: translate reasoning results into executable robot behavior.

## Evidence

The project reports stronger performance than OpenVLA, DexVLA, and pi-0 style baselines on tasks involving OCR, math matching, spatial placement, and open-world reasoning. The important experimental signal is not just action success; it is whether the robot can use pretrained knowledge after fine-tuning.

## Limitations

- Reasoning benchmarks may not cover contact-rich manipulation or long-horizon recovery.
- Preserving reasoning does not guarantee physical safety.
- Mixture-of-experts systems can be harder to debug and deploy.
- The model still needs embodiment-specific action data.

## Transferable Pattern

When fine-tuning foundation models for robotics, track **capability preservation** as an evaluation axis:

- Did visual recognition degrade?
- Did OCR or symbolic reasoning degrade?
- Did spatial reasoning degrade?
- Did robot success improve at the cost of general understanding?

## Relationship To Other Papers

- Extends the VLA line from [[10-learning/Literature/RT-2]] and [[10-learning/Literature/OpenVLA]] by focusing on retained reasoning, not only action success.
- Complements [[10-learning/Literature/CogACT]]: ChatVLA-2 addresses cognition preservation; CogACT addresses action-module quality.
- Related to [[10-learning/Literature/Voyager]] because both treat reusable knowledge and reasoning as central to embodied generalization.
- Still needs safe-control ideas from [[10-learning/Literature/Stable and Safe Reinforcement Learning via BLAC]] for physical deployment.

## Links

- [[10-learning/Literature/VLA and Safe RL Paper Relationship Map]]
- [[20-ideas/Ideas Index|Vision-Language-Action Models]]
