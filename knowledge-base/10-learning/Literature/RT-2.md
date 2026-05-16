---
domain: learning
title: "RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control"
aliases:
  - RT-2
type: paper
status: done
created: "2026-05-08"
updated: "2026-05-08"
authors:
  - Anthony Brohan
  - Noah Brown
  - Justice Carbajal
  - Yevgen Chebotar
  - Chelsea Finn
  - Brian Ichter
  - Sergey Levine
year: 2023
venue: arXiv
doi: 10.48550/arXiv.2307.15818
url: https://arxiv.org/abs/2307.15818
pdf: "/Users/visomopokoa8/Documents/1 NUS/1 Master/Courses/ISY5003/Practice Module/Proposal/v2.0/References/RT-2.pdf"
research_area: embodied_ai
priority: 1
rating: 5
tags:
  - literature/paper
  - embodied-ai
  - robotics
  - vla
---

# RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control

## One-Sentence Summary

RT-2 turns a pretrained vision-language model into a robot controller by representing robot actions as language-like tokens and co-fine-tuning on web vision-language data plus robot trajectories.

## Problem

Robots need semantic generalization beyond their robot datasets. Pure imitation learning can learn seen manipulation behaviors, but it usually cannot use Internet-scale visual and language knowledge to recognize novel objects, infer semantic relations, or follow more abstract instructions.

## Core Method

- Start from large VLM backbones such as PaLI-X or PaLM-E style models.
- Mix robot trajectory data with web-scale vision-language tasks during fine-tuning.
- Encode robot actions as discrete tokens, so the same sequence model can emit text or actions.
- Train the model to map camera observations and language instructions to action-token sequences.

## Evidence

The paper reports improved generalization and emergent semantic reasoning in real robot manipulation tasks compared with non-VLA robot policies. The important experimental idea is that web-pretrained semantic knowledge transfers into action selection when actions share the model's token interface.

## Limitations

- Actions are discretized into tokens, which can lose precision for contact-rich or dexterous continuous control.
- The system is large and closed compared with later open models.
- Real-time deployment can be compute-heavy.
- The model still depends on robot demonstration coverage for low-level motor competence.

## Transferable Pattern

RT-2's key abstraction is **action-as-token**. This makes robot control compatible with the machinery of language modeling, but it also exposes the weakness of quantized action spaces. Use this idea when the task benefits from semantic transfer more than from high-bandwidth continuous control.

## Relationship To Other Papers

- Extends [[10-learning/Literature/Do As I Can Not As I Say - SayCan]] from skill selection to direct VLA action generation.
- Predecessor baseline for [[10-learning/Literature/OpenVLA]], which makes a similar VLA direction open and more accessible.
- Contrasted by [[10-learning/Literature/CogACT]], which argues that simple action quantization is not enough and adds a specialized diffusion action module.
- Related to [[10-learning/Literature/ChatVLA-2]], which focuses on preserving VLM reasoning after robot fine-tuning.

## Links

- [[10-learning/Literature/VLA and Safe RL Paper Relationship Map]]
- [[20-ideas/Ideas Index|Vision-Language-Action Models]]
