---
domain: learning
title: "A Review of Safe Reinforcement Learning: Methods, Theory and Applications"
aliases:
  - Safe RL Review
type: paper
status: done
created: "2026-05-08"
updated: "2026-05-08"
authors:
  - Shangding Gu
  - Long Yang
  - Yali Du
  - Guang Chen
  - Florian Walter
  - Jun Wang
  - Yaodong Yang
  - Alois Knoll
year: 2022
venue: arXiv
doi: 10.48550/arXiv.2205.10330
url: https://arxiv.org/abs/2205.10330
pdf: "/Users/visomopokoa8/Documents/1 NUS/1 Master/Courses/ISY5003/Practice Module/Proposal/v2.0/References/A Review of Safe Reinforcement Learning.pdf"
research_area: safe_rl
priority: 1
rating: 4
tags:
  - literature/paper
  - safe-rl
  - reinforcement-learning
  - robotics
---

# A Review of Safe Reinforcement Learning: Methods, Theory and Applications

## One-Sentence Summary

This survey organizes safe reinforcement learning around the core question of how agents can learn high-performing policies while satisfying real-world safety constraints.

## Problem

RL succeeds in games and simulation but real systems such as robots, vehicles, and industrial controllers cannot tolerate arbitrary unsafe exploration. Safe RL must answer how to represent safety, how to guarantee it, and how to learn efficiently under constraints.

## Core Framework

The survey frames safe RL across method, theory, and application dimensions:

- Constraint formulation: usually CMDPs, cost constraints, temporal logic, reachability, or stability conditions.
- Algorithm family: model-free, model-based, on-policy, off-policy, single-agent, and multi-agent.
- Safety mechanism: shielding, recovery, constrained optimization, primal-dual methods, trust-region constraints, Lyapunov methods, control barrier functions, Gaussian processes, and formal methods.
- Evaluation: safe benchmarks, sample complexity, violation counts, return-cost tradeoffs, and deployment realism.

## Evidence

The paper is a survey rather than a new algorithm. Its value is taxonomic: it links safe control traditions with modern RL and identifies open deployment questions such as safety complexity, sample efficiency, and benchmark quality.

## Limitations

- As a survey, it does not validate one unified safe RL solution.
- Many covered methods still assume simplified dynamics, known constraints, or simulator access.
- Benchmarks are not yet sufficient proxies for real robot safety.

## Transferable Pattern

Use this as the decision tree for adding safety to embodied AI:

- Is the constraint hard or soft?
- Is the dynamics model known, learned, or unavailable?
- Do we need zero violations during learning or only safer final policies?
- Can a shield or recovery controller override the policy?
- Are safety costs observable at every step?

## Relationship To Other Papers

- Provides the taxonomy for [[10-learning/Literature/Safe Exploration in Continuous Action Spaces]] and [[10-learning/Literature/Stable and Safe Reinforcement Learning via BLAC]].
- Exposes a gap in [[10-learning/Literature/OpenVLA]], [[10-learning/Literature/CogACT]], and [[10-learning/Literature/ChatVLA-2]]: VLA success metrics are not enough for physical safety.
- Connects to [[10-learning/Literature/Do As I Can Not As I Say - SayCan]] through feasibility filtering, but SayCan lacks formal safety guarantees.

## Links

- [[10-learning/Literature/VLA and Safe RL Paper Relationship Map]]
- [[20-ideas/Ideas Index|Embodied AI]]
