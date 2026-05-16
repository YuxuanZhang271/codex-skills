---
domain: learning
title: "OpenVLA: An Open-Source Vision-Language-Action Model"
aliases:
  - OpenVLA
type: paper
status: done
created: "2026-05-08"
updated: "2026-05-08"
authors:
  - Moo Jin Kim
  - Karl Pertsch
  - Siddharth Karamcheti
  - Ted Xiao
  - Chelsea Finn
  - Percy Liang
  - Sergey Levine
year: 2024
venue: arXiv
doi: 10.48550/arXiv.2406.09246
url: https://arxiv.org/abs/2406.09246
pdf: "/Users/visomopokoa8/Documents/1 NUS/1 Master/Courses/ISY5003/Practice Module/Proposal/v2.0/References/OpenVLA.pdf"
research_area: embodied_ai
priority: 1
rating: 5
tags:
  - literature/paper
  - embodied-ai
  - robotics
  - vla
  - open-source
---

# OpenVLA: An Open-Source Vision-Language-Action Model

## One-Sentence Summary

OpenVLA provides an open 7B VLA model trained on diverse real robot demonstrations, showing that accessible foundation robot policies can be fine-tuned for new manipulation tasks.

## Problem

VLA models were promising but difficult to adopt because strong models were closed and the field lacked a practical recipe for efficient fine-tuning on new robot tasks.

## Core Method

- Build a 7B VLA with a language-model backbone and visual encoders that fuse pretrained visual features.
- Train on a large mixture of real-world robot demonstrations from Open X-Embodiment style data.
- Preserve the VLA recipe of mapping vision and language inputs to robot actions.
- Provide fine-tuning workflows, including parameter-efficient adaptation and quantized serving.

## Evidence

The paper reports strong generalist manipulation results across multiple tasks and embodiments, including comparisons against larger closed VLA models and from-scratch imitation learning. The important engineering evidence is that the model can be fine-tuned on practical hardware with low-rank adaptation and served efficiently with quantization.

## Limitations

- The policy remains imitation-heavy; it does not automatically solve safety, exploration, or recovery.
- Cross-embodiment action representation is still a bottleneck.
- Real-world robustness depends on demonstration diversity and sensor/action compatibility.
- Open-source availability improves adoption but does not remove deployment validation requirements.

## Transferable Pattern

OpenVLA is the practical baseline for a research stack:

- Start from a generalist VLA.
- Fine-tune on your robot and task distribution.
- Add external modules for safety, recovery, tactile feedback, or planning when the task leaves the training distribution.

## Relationship To Other Papers

- Inherits the VLA direction from [[10-learning/Literature/RT-2]] but emphasizes openness, reproducibility, and efficient fine-tuning.
- Serves as a baseline that [[10-learning/Literature/CogACT]] and [[10-learning/Literature/ChatVLA-2]] try to improve.
- Needs safety mechanisms from [[10-learning/Literature/Safe Exploration in Continuous Action Spaces]] or [[10-learning/Literature/Stable and Safe Reinforcement Learning via BLAC]] for high-risk continuous-control settings.
- Complements [[10-learning/Literature/Voyager]]: OpenVLA learns direct actions, while Voyager shows how an agent can accumulate reusable skills.

## Links

- [[10-learning/Literature/VLA and Safe RL Paper Relationship Map]]
- [[20-ideas/Ideas Index|Vision-Language-Action Models]]
