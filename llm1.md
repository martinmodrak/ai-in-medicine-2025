---
title: "Lesson 3 - Building ChatGPT"
output: html_document
---

- Review last time:
  - Modern neural networks move away from biology
  - Many layers (deep)
  - Still kind of perceptron-like

## Towards ChatGPT

 - ChatGPT is based on the transformer architecture
 - We will roughly follow http://nlp.seas.harvard.edu/annotated-transformer/ , but note that ChatGPT is (as far as we know) just decoders and has no encoder element
 - Word embeddings - a good detailed writeup at https://jalammar.github.io/illustrated-word2vec/
   - Task 1
 - Attention heads
 - The full transformer
 - [Fine-tuning](https://en.wikipedia.org/wiki/Fine-tuning_(deep_learning))
 - [Reinforcement learning from human feedback](https://en.wikipedia.org/wiki/Reinforcement_learning_from_human_feedback)
 - System prompt

## Working with ChatGPT
 - Task 2
 - Discussion:
   - Some things work pretty well
   - Framing matters
   - Following instructions vs. not being a PR disaster
     - No AI is value free!
     - Jailbreak prompts
 - Task 3
 - Discussion:
   - We don't tech humans with large datasets (mostly)
   - Learning within sessions?
   - OpenAI papers over most of the obvious failures.
