---
domain: learning
title: "Safe Exploration in Continuous Action Spaces"
aliases:
  - Safe Exploration
type: paper
status: done
created: "2026-05-08"
updated: "2026-05-08"
authors:
  - Gal Dalal
  - Krishnamurthy Dvijotham
  - Matej Vecerik
  - Todd Hester
  - Cosmin Paduraru
  - Yuval Tassa
year: 2018
venue: arXiv
doi: 10.48550/arXiv.1801.08757
url: https://arxiv.org/abs/1801.08757
pdf: "/Users/visomopokoa8/Documents/1 NUS/1 Master/Courses/ISY5003/Practice Module/Proposal/v2.0/References/Safe Exploration in Continuous Action Spaces.pdf"
research_area: safe_rl
priority: 1
rating: 4
tags:
  - literature/paper
  - safe-rl
  - reinforcement-learning
  - continuous-control
---

# Safe Exploration in Continuous Action Spaces

## One-Sentence Summary

This paper adds a safety layer on top of a continuous-control RL policy, analytically correcting unsafe actions before they violate constraints.

## Problem

Physical systems such as robots or datacenter controllers cannot allow exploratory actions to violate critical constraints. Reward penalties are not enough because the agent may still discover unsafe actions during learning.

## Core Method

- Learn a local linearized model of safety-signal dynamics from prior trajectories.
- At each state, inspect the policy's proposed continuous action.
- If the action is unsafe, solve a closed-form correction that minimally changes the action while satisfying the safety constraint.
- Apply the corrected action to the environment.

## Evidence

The paper demonstrates zero constraint violations in representative continuous-control environments where reward shaping fails. The useful lesson is that safety should be enforced in the action channel, not merely encouraged in the reward.

## Limitations

- The safety model relies on smooth dynamics and local linearization.
- Constraints must be observable and expressible through the safety layer.
- The method handles immediate action correction better than complex long-horizon safety.
- It may be conservative if the learned safety model is inaccurate.

## Transferable Pattern

For a robot policy, wrap the learned controller with an action-correction layer:

- Let the policy propose.
- Let the safety layer project or modify.
- Log corrections as training signals for future safer policies.

## Relationship To Other Papers

- A concrete algorithmic instance within the taxonomy of [[10-learning/Literature/A Review of Safe Reinforcement Learning]].
- More action-level and immediate than [[10-learning/Literature/Stable and Safe Reinforcement Learning via BLAC]], which combines safety and stability constraints with actor-critic learning.
- Relevant to [[10-learning/Literature/OpenVLA]] and [[10-learning/Literature/CogACT]] because VLA policies can propose actions but usually do not guarantee constraint satisfaction.

## Links

- [[10-learning/Literature/VLA and Safe RL Paper Relationship Map]]
