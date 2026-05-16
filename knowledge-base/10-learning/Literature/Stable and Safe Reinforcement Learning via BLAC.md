---
domain: learning
title: "Stable and Safe Reinforcement Learning via a Barrier-Lyapunov Actor-Critic Approach"
aliases:
  - BLAC
  - Barrier-Lyapunov Actor-Critic
type: paper
status: done
created: "2026-05-08"
updated: "2026-05-08"
authors:
  - Liqun Zhao
  - Konstantinos Gatsis
  - Antonis Papachristodoulou
year: 2023
venue: IEEE CDC
doi: 10.1109/CDC49753.2023.10383742
url: https://arxiv.org/abs/2304.04066
pdf: "/Users/visomopokoa8/Documents/1 NUS/1 Master/Courses/ISY5003/Practice Module/Proposal/v2.0/References/Stable and Safe Reinforcement Learning via a Barrier-Lyapunov Actor-Critic Approach.pdf"
research_area: safe_rl
priority: 2
rating: 4
tags:
  - literature/paper
  - safe-rl
  - control-barrier-function
  - lyapunov
---

# Stable and Safe Reinforcement Learning via a Barrier-Lyapunov Actor-Critic Approach

## One-Sentence Summary

BLAC combines control barrier functions for safety and control Lyapunov functions for stability inside an actor-critic RL framework.

## Problem

For real control systems, avoiding unsafe states is not enough; the learned controller should also maintain stability. Standard RL optimizes reward and may violate both safety and stability during training or deployment.

## Core Method

- Define safety through control barrier function constraints.
- Define stability through control Lyapunov function constraints.
- Build these constraints from replay-buffer samples.
- Use an augmented Lagrangian actor-critic update so the policy learns while respecting safety and stability pressure.

## Evidence

The paper evaluates the framework as a control-oriented safe RL approach. Its contribution is conceptual integration: CBF handles forward invariance of safe sets, CLF handles convergence or stability, and actor-critic learning handles performance optimization.

## Limitations

- Requires meaningful CBF and CLF formulations, which are not trivial for high-dimensional perception-driven robots.
- The guarantee quality depends on modeling assumptions and sampled data coverage.
- Less directly applicable to black-box VLA policies unless paired with a lower-level control layer.

## Transferable Pattern

Use BLAC as the safety-control layer beneath a learned robot policy:

- VLA or planner proposes a desired action or subgoal.
- A CBF/CLF-aware controller filters or tracks it.
- Actor-critic learning improves performance inside the safety and stability envelope.

## Relationship To Other Papers

- More control-theoretic than [[10-learning/Literature/Safe Exploration in Continuous Action Spaces]].
- Fits into the Lyapunov and barrier-function branch of [[10-learning/Literature/A Review of Safe Reinforcement Learning]].
- Provides a candidate safety substrate for [[10-learning/Literature/OpenVLA]], [[10-learning/Literature/CogACT]], and [[10-learning/Literature/ChatVLA-2]] when moving from benchmark manipulation to physical systems.

## Links

- [[10-learning/Literature/VLA and Safe RL Paper Relationship Map]]
