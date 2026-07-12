---
tags:
  - learning
  - AI
  - LLM
  - demo
title: How Large Language Models Work
created: 2026-05-15
source: Personal notes from various papers + courses
---

## ScholarPilot answer

I have added more detail about the Transformer architecture to your note, as requested. The "Key components" section in "Learning - How LLMs Work.md" now includes explanations of Positional Encodings and Multi-Head Self-Attention.


- **[00:05](https://www.youtube.com/watch?v=-dwLbaCB-_I&t=5)** sfvsdfvsdbs

## My Notes

- **[00:05](https://www.youtube.com/watch?v=-dwLbaCB-_I&t=5)** sfvsdfvsdbs

## My Notes

- **[00:05](https://www.youtube.com/watch?v=-dwLbaCB-_I&t=5)** sfvsdfvsdbs

## My Notes

- **[00:05](https://www.youtube.com/watch?v=-dwLbaCB-_I&t=5)** sfvsdfvsdbs
- **[00:25](https://www.youtube.com/watch?v=-dwLbaCB-_I&t=25)** zfvdfd

# 🤖 How Large Language Models Work

> *Use the AI Browser Chat to ask questions about any section of this note — select text and run "Send selected text to AI" from the command palette.*

 

---

## What is a Language Model?

A language model assigns a **probability distribution** over sequences of tokens. Given a sequence of previous tokens, it predicts: *what token comes next?*

A large language model (LLM) does this at massive scale — billions of parameters trained on trillions of tokens of text.

## The Transformer Architecture

Modern LLMs are built on the **Transformer** (Vaswani et al., 2017, "Attention Is All You Need").

### Key components

**Tokenization**
Text is split into tokens — roughly word-level chunks, but subwords for rare words (e.g. "unhappiness" → ["un", "happiness"]).

**Embeddings**
Each token is mapped to a high-dimensional vector (e.g. 4096 dimensions). Similar tokens have similar vectors.

**Positional Encodings**
Because the Transformer contains no recurrence or convolution, in order for the model to make use of the order of the sequence, we must inject some information about the relative or absolute position of the tokens in the sequence. These are added to the input embeddings at the bottoms of the encoder and decoder stacks.

**Multi-Head Self-Attention**
This is a core mechanism. Instead of one, it has multiple attention "heads" running in parallel. This allows the model to jointly attend to information from different representation subspaces. The outputs are concatenated and projected to the final values.

Every token can "look at" every other token in the context window and weight how much it should pay attention to each. The attention calculation is:

$$\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V$$

Where Q = queries, K = keys, V = values. This lets the model learn relationships like subject–verb agreement across long distances.

**Feed-Forward Layers**
After attention, a position-wise MLP processes each token independently. This is where most "knowledge" is thought to be stored.

**Residual Connections & Layer Norm**
These stabilise training and allow very deep networks (100+ layers) to be trained effectively.

## Training

LLMs are trained via **next-token prediction** (also called causal language modelling):

1. Take a chunk of text
2. Feed tokens 1…n to the model
3. Predict token n+1
4. Compute cross-entropy loss against the actual next token
5. Backpropagate and update weights

This is done over **trillions of tokens** using thousands of GPUs for weeks or months.

### RLHF — Aligning to Human Preferences

Raw pretrained LLMs are good at completion but bad at following instructions. **Reinforcement Learning from Human Feedback (RLHF)** fine-tunes them to be helpful:

1. Collect human preference data (which response is better?)
2. Train a **reward model** to predict human preference scores
3. Use PPO (Proximal Policy Optimisation) to fine-tune the LLM to maximise the reward model's score

More recent approaches include **DPO (Direct Preference Optimisation)** which skips the explicit reward model.

## Capabilities & Limitations

### What LLMs are good at
- Summarising and rewriting text
- Code generation and debugging
- Question answering over provided context
- Translation and language tasks
- Brainstorming and ideation

### What LLMs struggle with
- Precise arithmetic (they tokenise numbers, not compute them)
- Remembering exact facts reliably (hallucination risk)
- Long-horizon reasoning over many steps
- Knowing what they don't know

## Context Window

The **context window** is the maximum number of tokens the model can "see" at once. As of 2026:

| Model | Context Window |
|---|---|
| GPT-4o | 128k tokens |
| Claude 3.7 Sonnet | 200k tokens |
| Gemini 1.5 Pro | 1M tokens |
| Llama 3 70B | 128k tokens |

Longer context ≠ better attention across the whole window — models tend to pay more attention to the start and end of the context ("lost in the middle" problem).

## Key Papers to Read

1. "Attention Is All You Need" — Vaswani et al. 2017
2. "Language Models are Few-Shot Learners" (GPT-3) — Brown et al. 2020
3. "Training language models to follow instructions with human feedback" (InstructGPT) — Ouyang et al. 2022
4. "Direct Preference Optimization" — Rafailov et al. 2023
5. "Scaling Laws for Neural Language Models" — Kaplan et al. 2020

## Questions to Explore with AI

- *"Explain the attention mechanism to me like I'm a software engineer, not an ML researcher"*
- *"What's the intuition behind why more parameters = better performance?"*
- *"What is the difference between fine-tuning and RAG for adding custom knowledge?"*
- *"Why do LLMs hallucinate and what are the current best mitigations?"*



---

feat/update-the-name