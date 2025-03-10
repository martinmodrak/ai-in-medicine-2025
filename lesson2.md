---
title: "Lesson 2 - Machine learning, validation, overfitting"
output: html_document
---

## Neural networks

- Neural network is "just" another function
  - Yo mama is "just" another function
- Refresh perceptron, backpropagation
- [Task 1](lesson2-tasks.html)
- Modern ideas for neural networks
   - [ReLU](https://en.wikipedia.org/wiki/Rectifier_(neural_networks))
   - [Autoencoders](https://en.wikipedia.org/wiki/Autoencoder)
      - [Semi supervised learning](https://en.wikipedia.org/wiki/Weak_supervision#Semi-supervised_learning)!
   - [Convolution](https://en.wikipedia.org/wiki/Convolutional_neural_network)
   - [Data augmentation](https://en.wikipedia.org/wiki/Data_augmentation)
   - [Dropout](https://en.wikipedia.org/w/index.php?title=Dropout_(neural_networks)&redirect=no) (regularization more broadly)


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
- [Task 2](lesson2-tasks.html)
