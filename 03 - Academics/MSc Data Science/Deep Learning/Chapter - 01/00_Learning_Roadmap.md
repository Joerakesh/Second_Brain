# Chapter 1 – Introduction to Neural Networks
## Learning roadmap

### The central question
How can a group of simple mathematical neurons learn complicated relationships between inputs and outputs?

An artificial neural network (ANN) answers this by connecting simple computational units. Each unit performs a small calculation. During learning, the network adjusts its weights and biases so that its predictions become closer to the expected answers.

### How the topics connect
1. **Biological inspiration:** Understand the idea that inspired artificial neurons.
2. **Artificial neuron:** Learn the basic calculation performed by one neuron.
3. **Evolution:** See how neural networks developed from fixed threshold rules to trainable multilayer systems.
4. **Applications:** Understand the kinds of problems ANNs can solve.
5. **Architecture:** Learn how neurons are arranged into input, hidden and output layers.
6. **Weights, biases and parameters:** Understand what the network actually learns.
7. **Activation functions:** Understand how networks represent non-linear relationships.
8. **Learning methods:** Understand how examples are used to improve a network.
9. **Loss functions:** Measure how far predictions are from the correct answers.
10. **Optimizers:** Use the loss information to update the network's parameters.

### The complete learning cycle
**Input data → Neuron calculations → Activation → Prediction → Loss calculation → Parameter update → Repeat**

The network performs the first four stages to make a prediction. The loss function measures the error, and the optimizer uses that information to improve the parameters.

### What comes from the professor's slides?
These notes follow Chapter 1 of *Deep Learning – Artificial Neural Networks and Supervised Learning* (Dr. S. Maria Jesu Raja). The slides cover biological inspiration, ANN evolution, applications, architecture, parameter counting, activations, loss functions, the optimization loop, and classification and regression examples.

Some explanations in these notes add background needed to understand the syllabus. Those additions are explanations, not claims that every detail appeared in the slides.

### How to study this chapter
Do not try to memorise all the formulas at once. First understand the artificial neuron. Then understand how neurons are connected. Once that is clear, activation, loss and optimization will make much more sense.
