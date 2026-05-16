---
domain: learning
title: "Voyager: An Open-Ended Embodied Agent with Large Language Models"
aliases:
  - Voyager
type: paper
status: done
created: "2026-05-08"
updated: "2026-05-08"
authors:
  - Guanzhi Wang
  - Yuqi Xie
  - Yunfan Jiang
  - Ajay Mandlekar
  - Chaowei Xiao
  - Yuke Zhu
  - Linxi Fan
  - Anima Anandkumar
year: 2023
venue: arXiv
doi: 10.48550/arXiv.2305.16291
url: https://arxiv.org/abs/2305.16291
pdf: "/Users/visomopokoa8/Documents/1 NUS/1 Master/Courses/ISY5003/Practice Module/Proposal/v2.0/References/Voyager.pdf"
research_area: embodied_ai
priority: 2
rating: 5
tags:
  - literature/paper
  - embodied-ai
  - llm-agent
  - lifelong-learning
---

# Voyager: An Open-Ended Embodied Agent with Large Language Models

## One-Sentence Summary

Voyager shows how an LLM agent can build lifelong competence by creating, debugging, storing, and reusing executable skills in an open-ended environment.

## Problem

Embodied agents often solve fixed tasks but fail at open-ended exploration and long-term accumulation of reusable skills. The question is how an agent can keep improving without gradient updates or human-provided curricula.

## Core Method

- Automatic curriculum proposes tasks that expand exploration.
- Skill library stores executable code behaviors that can be retrieved and composed later.
- Iterative prompting uses environment feedback, execution errors, and self-verification to repair programs.
- GPT-4 is used as a black-box reasoning engine; the agent improves by changing its code and library rather than updating model weights.

## Evidence

Voyager is evaluated in Minecraft and shows stronger exploration, item discovery, tech-tree progression, and transfer to new worlds than prior baselines. The key evidence is that a growing skill library produces compounding competence instead of starting from scratch for each task.

## Limitations

- Minecraft code actions are cleaner than noisy real robot control.
- Program synthesis assumes a symbolic API, which real robots often lack.
- Safety is mostly software/environment scoped, not physical safety.
- It is an embodied-agent paper, not a robot manipulation policy.

## Transferable Pattern

Use Voyager's design when building a robot learning assistant:

- Turn solved subtasks into callable tools.
- Store skills with descriptions and preconditions.
- Use execution feedback to repair skills.
- Retrieve and compose prior skills before training a new behavior.

## Relationship To Other Papers

- Complements [[10-learning/Literature/Do As I Can Not As I Say - SayCan]]: both are LLM-over-skills systems, but Voyager grows the skill library while SayCan selects from a fixed robot skill set.
- Different from [[10-learning/Literature/OpenVLA]]: Voyager is tool/code-centric; OpenVLA is direct policy-centric.
- Suggests a memory and skill-library layer that could sit above [[10-learning/Literature/CogACT]] or [[10-learning/Literature/ChatVLA-2]].
- Needs safe-exploration mechanisms from [[10-learning/Literature/Safe Exploration in Continuous Action Spaces]] before transfer to physical robots.

## Links

- [[10-learning/Literature/VLA and Safe RL Paper Relationship Map]]
- [[20-ideas/Ideas Index|Embodied AI]]
