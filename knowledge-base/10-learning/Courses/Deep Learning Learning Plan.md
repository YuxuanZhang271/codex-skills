---
domain: learning
title: "Deep Learning Learning Plan"
type: course
status: active
created: "2026-05-08"
updated: "2026-05-08"
research_area: deep_learning
tags:
  - course/deep-learning
  - machine-learning
  - linear-algebra
  - neural-networks
  - transformers
---

# Deep Learning Learning Plan

## Purpose

This note is a structured self-study plan for learning deep learning from the mathematical foundations to neural networks and transformers. The goal is not only to watch courses, but to build enough theory, implementation fluency, and paper-reading ability to support robotics, VLA, and embodied-AI research.

## Learning Principle

Use one main path and a small number of high-quality references. For each stage:

1. Watch the selected lectures.
2. Write a short idea note in this vault.
3. Implement at least one small notebook or script.
4. Mark the stage as complete only after answering the checkpoint questions.

## Core YouTube Course List

These courses were checked on YouTube on 2026-05-08.

| Stage | Primary Resource | Why It Is Useful | Link |
| --- | --- | --- | --- |
| Linear algebra intuition | 3Blue1Brown, Essence of linear algebra | Best first pass for geometric intuition: vectors, span, basis, linear transformations, eigenvectors. | [YouTube playlist](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) |
| Formal linear algebra | MIT 18.06 Linear Algebra, Gilbert Strang | Complete university-level foundation for matrices, subspaces, rank, orthogonality, determinants, eigenvalues, and SVD. | [YouTube playlist](https://www.youtube.com/playlist?list=PLE7DDD91010BC51F8) |
| Neural network intuition | 3Blue1Brown, Neural networks | Visual introduction to gradient descent, backpropagation, and what neural networks compute. | [YouTube playlist](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) |
| Neural networks from scratch | Andrej Karpathy, Neural Networks: Zero to Hero | Builds backpropagation, micrograd, language modeling, and GPT-style components from code. | [YouTube playlist](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ) |
| General deep learning | MIT 6.S191: Introduction to Deep Learning | Compact modern survey covering neural networks, sequence modeling, attention, transformers, generative models, and RL. | [YouTube playlist](https://www.youtube.com/playlist?list=PLtBw6njQRU-rwp5__7C0oIVt26ZgjG9NI) |
| NLP and transformer path | Stanford CS224N: NLP with Deep Learning, Spring 2024 | Strong route from word vectors and language models to sequence models, attention, transformers, and LLM topics. | [YouTube playlist](https://www.youtube.com/playlist?list=PLoROMvodv4rOaMFbaqxPDoLWjDaRAdP9D) |
| Transformer survey | Stanford CS25: Transformers United | Guest-lecture style overview of transformer applications across NLP, CV, RL, and modern deep-learning systems. | [YouTube playlist](https://www.youtube.com/playlist?list=PLoROMvodv4rNiJRchCzutFw5ItR_Z27CM) |

## Recommended Learning Order

### Stage 1: Linear Algebra Foundations

Target duration: 3-4 weeks.

Main resources:

- 3Blue1Brown, Essence of linear algebra.
- MIT 18.06 Linear Algebra.

Topics:

- Vectors, matrices, matrix multiplication.
- Linear combinations, span, basis, dimension.
- Linear transformations and change of basis.
- Systems of linear equations and Gaussian elimination.
- Rank, column space, null space, row space.
- Orthogonality, projections, least squares.
- Eigenvalues, eigenvectors, diagonalization.
- Singular value decomposition.

Checkpoint:

- [ ] Explain why a matrix can be viewed as a linear transformation.
- [ ] Explain rank, null space, and column space without relying only on formulas.
- [ ] Derive the normal equation for least squares.
- [ ] Explain why eigenvectors matter for repeated linear transformations.
- [ ] Connect SVD to dimensionality reduction and representation learning.

Output notes:

- [[20-ideas/Ideas Index|Linear Algebra for Deep Learning]]
- [[20-ideas/Ideas Index|Matrix Factorization]]
- [[20-ideas/Ideas Index|Eigenvalues and SVD]]

### Stage 2: Minimal Calculus, Probability, and Optimization

Target duration: 2 weeks.

Purpose:

Deep learning does not require a full pure-math sequence at the beginning, but it does require a working understanding of gradients, chain rule, probability distributions, expectations, and optimization.

Topics:

- Derivatives, partial derivatives, gradients.
- Chain rule and computational graphs.
- Probability distributions, expectation, variance.
- Maximum likelihood and cross entropy.
- Gradient descent, stochastic gradient descent, momentum, Adam.
- Overfitting, regularization, validation split.

Checkpoint:

- [ ] Compute gradients through a small computational graph by hand.
- [ ] Explain why cross entropy appears in classification.
- [ ] Explain the difference between training loss, validation loss, and test performance.
- [ ] Explain why learning rate is often more important than model size in early experiments.

Output notes:

- [[20-ideas/Ideas Index|Backpropagation]]
- [[20-ideas/Ideas Index|Cross Entropy]]
- [[20-ideas/Ideas Index|Gradient Descent]]

### Stage 3: Neural Networks From Scratch

Target duration: 4 weeks.

Main resources:

- 3Blue1Brown, Neural networks.
- Andrej Karpathy, Neural Networks: Zero to Hero.

Topics:

- Perceptron and multilayer perceptron.
- Activation functions.
- Loss functions.
- Backpropagation.
- Autograd.
- Embeddings.
- Basic language modeling.
- Training loop structure.
- Debugging training curves.

Implementation tasks:

- [ ] Implement a small MLP with NumPy.
- [ ] Implement scalar autograd or follow micrograd and annotate every core line.
- [ ] Train a small character-level language model.
- [ ] Write down one training bug and how it was diagnosed.

Checkpoint:

- [ ] Explain forward pass, backward pass, and parameter update as three separate steps.
- [ ] Explain why nonlinearity is necessary.
- [ ] Explain what embeddings learn in a language model.
- [ ] Explain exploding or vanishing gradients at a practical level.

Output notes:

- [[20-ideas/Ideas Index|Neural Networks]]
- [[20-ideas/Ideas Index|Autograd]]
- [[20-ideas/Ideas Index|Language Modeling]]

### Stage 4: Modern Deep Learning Survey

Target duration: 3 weeks.

Main resource:

- MIT 6.S191: Introduction to Deep Learning.

Topics:

- Deep learning foundations.
- CNNs.
- RNNs and sequence modeling.
- Attention and transformers.
- Generative models.
- Reinforcement learning.
- Model robustness and deployment considerations.

Checkpoint:

- [ ] Explain when CNNs are still useful even in the transformer era.
- [ ] Explain why sequence models need memory or attention.
- [ ] Explain the difference between discriminative and generative modeling.
- [ ] Connect one lecture topic to robotics or VLA research.

Output notes:

- [[20-ideas/Ideas Index|Convolutional Neural Networks]]
- [[20-ideas/Ideas Index|Sequence Modeling]]
- [[20-ideas/Ideas Index|Attention Mechanism]]

### Stage 5: Transformers and Language Models

Target duration: 5-6 weeks.

Main resources:

- Stanford CS224N: NLP with Deep Learning.
- Stanford CS25: Transformers United.
- Karpathy Zero to Hero transformer/GPT material.

Topics:

- Word vectors and embeddings.
- Language modeling.
- RNNs, LSTMs, and sequence-to-sequence models.
- Attention.
- Transformer encoder and decoder.
- Positional encoding.
- Pretraining and fine-tuning.
- Prompting, instruction tuning, and alignment basics.
- Scaling, context length, and efficient attention.

Implementation tasks:

- [ ] Implement scaled dot-product attention.
- [ ] Implement a minimal transformer block.
- [ ] Train or fine-tune a tiny language model on a toy dataset.
- [ ] Read and summarize "Attention Is All You Need".
- [ ] Compare a transformer block to the policy backbone used in one robotics or VLA paper.

Checkpoint:

- [ ] Explain self-attention with query, key, and value matrices.
- [ ] Explain why positional information is needed.
- [ ] Explain the difference between encoder-only, decoder-only, and encoder-decoder architectures.
- [ ] Explain pretraining versus fine-tuning.
- [ ] Explain why transformers are useful for multimodal and VLA systems.

Output notes:

- [[20-ideas/Ideas Index|Transformers]]
- [[20-ideas/Ideas Index|Self-Attention]]
- [[20-ideas/Ideas Index|Large Language Models]]
- [[20-ideas/Ideas Index|Vision-Language-Action Models]]

## Weekly Plan

| Week | Focus | Main Output | Status |
| --- | --- | --- | --- |
| 1 | Linear algebra intuition: vectors, span, basis | Concept note on vectors and basis | [ ] |
| 2 | Matrix operations, transformations, rank | Concept note on matrix transformations | [ ] |
| 3 | Orthogonality, least squares, eigenvalues | Worked examples and summary | [ ] |
| 4 | SVD and linear algebra review | One-page linear algebra map | [ ] |
| 5 | Calculus and gradient basics | Computational graph gradient notes | [ ] |
| 6 | Probability, loss functions, optimization | Cross entropy and SGD notes | [ ] |
| 7 | Neural network intuition and MLPs | NumPy MLP implementation | [ ] |
| 8 | Backpropagation and autograd | micrograd annotated notes | [ ] |
| 9 | Embeddings and character language model | Tiny language model experiment | [ ] |
| 10 | Training/debugging neural networks | Training curve debugging note | [ ] |
| 11 | MIT 6.S191 foundations and CNN/RNN survey | Survey summary | [ ] |
| 12 | Attention and transformers overview | Attention mechanism idea note | [ ] |
| 13 | CS224N word vectors and language models | NLP foundation notes | [ ] |
| 14 | Sequence models and attention | RNN vs attention comparison | [ ] |
| 15 | Transformer architecture | Minimal transformer block | [ ] |
| 16 | Transformer applications and VLA connection | Transformer-to-VLA synthesis note | [ ] |
| 17 | Buffer week: redo weak topics | Updated weak-topic notes | [ ] |
| 18 | Final review | Deep learning roadmap summary | [ ] |

## Study Check-In Template

Use this section for weekly tracking. Copy one block per week.

```markdown
### Week N Check-In

- Date:
- Course videos watched:
- Notes created or updated:
- Code implemented:
- Main concepts understood:
- Questions still open:
- Next action:
- Status: planned / active / blocked / done
```

## Current Backlog

- [ ] Create [[20-ideas/Ideas Index|Linear Algebra for Deep Learning]].
- [ ] Create [[20-ideas/Ideas Index|Backpropagation]].
- [ ] Create [[20-ideas/Ideas Index|Attention Mechanism]].
- [ ] Create [[20-ideas/Ideas Index|Transformers]].
- [ ] Set up a `deep-learning-from-scratch` local practice folder or repo.
- [ ] Decide whether to use PyTorch notebooks, plain Python scripts, or both for implementation practice.

## Completion Criteria

This learning plan is complete when:

- [ ] The linear algebra checkpoint questions can be answered without notes.
- [ ] A small MLP and a minimal transformer block have been implemented.
- [ ] At least five permanent idea notes have been created in `20-ideas`.
- [ ] At least one paper note connects transformer architecture to robotics, VLA, or embodied AI.
- [ ] The final review note explains the path from vectors to neural networks to transformers in the learner's own words.
