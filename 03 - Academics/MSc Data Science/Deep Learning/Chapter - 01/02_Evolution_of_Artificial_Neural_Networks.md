# 02 – Evolution of Artificial Neural Networks

## 1. Why did neural networks evolve?

The first artificial neuron models were simple. They could represent basic logical decisions, but they could not learn complex patterns.

As researchers tried to solve more difficult problems, they needed networks that could adjust their behaviour from examples and combine multiple layers of computation. This led to the development of trainable neural networks and, eventually, modern deep learning.

The evolution can be understood as a move from **fixed threshold rules to trainable multilayer models**.

## 2. Important milestones

### 1943 – McCulloch–Pitts neuron
Warren McCulloch and Walter Pitts introduced a mathematical model of a neuron. It used binary inputs and a threshold to produce a binary output.

Its importance was that it showed how a simple mathematical neuron could represent logical operations.

**Limitation:** The threshold was fixed. The neuron did not learn its parameters from training examples.

### 1958 – Perceptron
Frank Rosenblatt introduced the perceptron, an important step towards trainable neural networks.

Unlike the basic fixed-threshold model, a perceptron can adjust its weights and bias based on prediction errors. It can learn a linear decision boundary.

**Limitation:** A single-layer perceptron cannot solve problems that are not linearly separable, such as XOR.

### 1974 – Backpropagation work
Paul Werbos is associated with early work on applying backpropagation to neural networks.

Backpropagation provides a way to calculate how changes in network parameters affect the error. These gradients can then be used by an optimization method to update the parameters.

### 1989 – CNN digit recognition
Yann LeCun's work demonstrated the usefulness of convolutional neural networks for recognising handwritten digits.

CNNs made neural networks especially useful for image-related tasks because they can learn spatial patterns from image data.

### Today – Deep learning
Modern neural networks use multiple layers and large datasets to learn complex representations. They are applied in computer vision, speech processing, recommendation systems, healthcare and many other areas.

## 3. Evolution at a glance

| Year | Milestone | Main contribution |
|---|---|---|
| 1943 | McCulloch–Pitts | Mathematical binary neuron |
| 1958 | Rosenblatt's perceptron | Learning weights and bias |
| 1974 | Werbos | Early backpropagation work |
| 1989 | LeCun | CNN-based handwritten digit recognition |
| Today | Deep learning | Large-scale multilayer neural networks |

## 4. How did each development address an earlier limitation?

- The MP neuron showed that logical decisions could be represented mathematically.
- The perceptron introduced trainable weights and bias.
- Backpropagation made it possible to calculate gradients through multilayer networks.
- CNNs provided architectures suited to image patterns.
- Modern deep learning combines multilayer architectures, optimization methods and large datasets.

## 5. Conclusion

The development of neural networks was not a single invention. It was a series of improvements, where each stage addressed limitations in earlier models. The overall journey moved from simple fixed rules to networks capable of learning complex patterns from data.

*Professor's slides: page 6. The dates and milestones above follow the timeline presented in the slides.*
