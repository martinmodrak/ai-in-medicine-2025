---
title: "Lesson 2 - Machine learning, validation, overfitting"
output: html_document
---

- Review last time:
  - Perceptron (we'll get there)

## Validation

- Example with Stable diffusions "blue grass, green sky"
- Example with ChatGPT
  - "I pick 25 people at random. What is the probability that at least two were born on the same day of year?"
  - "I pick 25 people at random. What is the probability that at least two were born in the same year?"
- Why is this happening?
- Note: ChatGPT improved in this substantially in the past year or so
- ChatGPT is at its a core a function from "the dialogue so far" to "probability distribution over next words"
  - Yo mama is at its core ...
  - There's a lot of details missing here
- We don't just want a function to pass through training points!
  - Overfitting!
  - The goal is generalization
  - Question: how can we check generalization?
- Validation
  - Internal validation
    - Crossvalidation
  - External validation
- Back to simple functions
  - Refresher: lines, polynomials
- Task 1

## Neural networks

- Neural network is "just" another function
  - Yo mama is "just" another function
- Refresh perceptron (1940s)
- First revival (1980s)
  - Hebb rule, [Hopfield network](https://en.wikipedia.org/wiki/Hopfield_network)
  - Backpropagation
    - Biologically questionable, but see e.g. [Song et al. 2020](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7610561/)
  - 3 layers are enough?!
- Bright future
   - Deep learning (~2011)
   - GPU
- Modern ideas for neural networks
   - ReLU
   - Autoencoders
      - Semi supervised learning!
   - Convolution
   - Word embeddings

## Notes for next le
