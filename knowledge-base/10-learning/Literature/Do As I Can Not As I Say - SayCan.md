---
domain: learning
title: "Do As I Can, Not As I Say: Grounding Language in Robotic Affordances"
aliases:
  - SayCan
  - Do As I Can Not As I Say
type: paper
status: done
created: "2026-05-08"
updated: "2026-05-08"
authors:
  - Michael Ahn
  - Anthony Brohan
  - Noah Brown
  - Yevgen Chebotar
  - Chelsea Finn
  - Sergey Levine
  - Brian Ichter
year: 2022
venue: arXiv
doi: 10.48550/arXiv.2204.01691
url: https://arxiv.org/abs/2204.01691
pdf: "/Users/visomopokoa8/Documents/1 NUS/1 Master/Courses/ISY5003/Practice Module/Proposal/v2.0/References/Do As I Can, Not As I Say.pdf"
research_area: embodied_ai
priority: 1
rating: 5
tags:
  - literature/paper
  - embodied-ai
  - robotics
  - llm-planning
  - affordance
---

# Do As I Can, Not As I Say: Grounding Language in Robotic Affordances

## One-Sentence Summary

SayCan grounds LLM planning by multiplying what the language model thinks is useful with what pretrained robot skills can actually execute in the current state.

## Problem

LLMs contain task and commonsense knowledge, but they are not grounded in robot embodiment. If an LLM directly plans robot actions, it may suggest steps that are semantically plausible but physically impossible for the current robot, scene, or skill set.

## Core Method

- Maintain a library of low-level robot skills, each with an affordance or value function estimating whether that skill can succeed from the current state.
- Ask the LLM to score candidate next skills by usefulness for completing the language instruction.
- Score each candidate with `LLM usefulness * affordance feasibility`.
- Execute the best grounded skill, observe the new state, append the result to the prompt, and repeat.

## Evidence

The paper evaluates long-horizon kitchen tasks on a real mobile manipulator. The key evidence is not only task success; it is the ablation logic: language-only planning fails because it ignores feasibility, while affordance-only selection lacks high-level task semantics. The combined score performs better because it joins semantic intent and physical executability.

## Limitations

- The robot can only choose among predefined skills; it does not synthesize arbitrary new continuous actions.
- The affordance model must be trained or specified for the available skill set.
- Long-horizon robustness depends on the quality of state estimation and skill termination.
- The LLM is planner-like, not a fully embodied world model.

## Transferable Pattern

Use this paper when designing a modular robot stack:

- Put LLM/VLM reasoning at the symbolic or skill-selection layer.
- Put learned control, planning, or value functions at the feasibility layer.
- Combine them through an explicit arbitration score rather than trusting language alone.

## Relationship To Other Papers

- Precursor to [[10-learning/Literature/RT-2]]: SayCan keeps language planning and robot skills separate, while RT-2 moves toward end-to-end VLA control.
- Complements [[10-learning/Literature/Voyager]]: both use LLMs as planners over executable skills, but Voyager grows a code skill library in Minecraft while SayCan selects robot skills.
- Useful safety bridge to [[10-learning/Literature/A Review of Safe Reinforcement Learning]]: the affordance score is a weak safety filter, but it is not a formal safety guarantee.
- Contrasts with [[10-learning/Literature/OpenVLA]] and [[10-learning/Literature/CogACT]]: those papers train generalist policies; SayCan is a compositional planner over existing skills.

## Links

- [[10-learning/Literature/VLA and Safe RL Paper Relationship Map]]
- [[20-ideas/Ideas Index|Embodied AI]]
- [[20-ideas/Ideas Index|Vision-Language-Action Models]]
