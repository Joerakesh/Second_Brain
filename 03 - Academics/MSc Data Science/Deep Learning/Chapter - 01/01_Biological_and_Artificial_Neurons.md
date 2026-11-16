# 01 – Biological Neural Networks vs Artificial Neurons

## 1. Why do we study biological neurons?

The human brain can recognise objects, respond to sounds and learn from experience. It performs these tasks through a large network of interconnected nerve cells called **neurons**.

Artificial neural networks (ANNs) take inspiration from this idea. Instead of reproducing the complete biological brain, they use mathematical units connected to one another. Each unit receives information, processes it and passes a result to another unit.

The important point is that an artificial neuron is a **simplified mathematical analogy**. It is not an accurate simulation of the brain or its physiology.

### Visual example – a biological neuron

![Labelled biological neuron showing dendrites, cell body, axon and axon terminals](https://media.geeksforgeeks.org/wp-content/uploads/20230921102222/Neuron-structure.jpg)

<small>Image source: [GeeksforGeeks – Labelled Diagram of Neuron](https://www.geeksforgeeks.org/biology/diagram-of-neuron/). Use the diagram to identify the parts before reading their functions.</small>
## 2. How does a biological neuron work?

A biological neuron has several important parts:

- **Dendrites:** Receive signals from other neurons.
- **Cell body (soma):** Integrates the incoming signals.
- **Axon:** Carries an electrical impulse away from the cell body.
- **Axon terminals:** Form connections with other cells.
- **Synapse:** The junction through which a signal is communicated from one cell to another.

The basic direction of information flow can be understood as:

**Dendrites → Cell body (soma) → Axon → Axon terminals → Next cell**

In simple terms, a neuron receives information, combines incoming signals and may transmit an electrical impulse to another cell. Communication at synapses involves chemical signalling through neurotransmitters.

### Understand the diagram

- The branch-like structures around the cell body are the dendrites.
- The central region is the soma, which contains the nucleus.
- The long extension is the axon.
- The branches at the end are axon terminals.

Do not confuse the **axon** with the **dendrites**: dendrites mainly receive incoming signals, while the axon carries the signal away from the cell body.
![[Pasted image 20261116213933.png]]

For another explanation with a labelled diagram, see [GeeksforGeeks – Diagram of Neuron](https://www.geeksforgeeks.org/biology/diagram-of-neuron/).
## 3. How does an artificial neuron work?

An artificial neuron receives numerical inputs. Each input is multiplied by a weight, the results are added together, and a bias is included. The total is then passed through an activation function.

### Visual example – an artificial neuron
![[Pasted image 20261116213737.png]]
[Open the interactive artificial-neuron diagram from the University of Toronto](https://www.teach.cs.toronto.edu/~csc311notes/neural_networks/neuron_intro.html).

Look at the section titled **“The Artificial Neuron”**. The diagram shows inputs $x_i$, weights $w_i$, bias $b$, activation function $f$ and the output. It is useful because it shows how the mathematical parts fit together.

### The mathematical representation

First, the neuron calculates the weighted sum and adds the bias:

$$
z = \sum_{i=1}^{n} w_i x_i + b
$$

Then, it applies the activation function:

$$
\hat{y} = f(z)
$$

The same calculation can also be written in vector form:

$$
\hat{y} = f(\mathbf{w}^{T}\mathbf{x} + b)
$$

### Meaning of each symbol

| Symbol | Meaning |
|---|---|
| $x_i$ | Input feature |
| $w_i$ | Weight assigned to the input |
| $b$ | Bias |
| $z$ | Weighted sum before activation |
| $f$ | Activation function |
| $\hat{y}$ | Predicted output |

The superscript $T$ in $\mathbf{w}^{T}$ represents the transpose of the weight vector. The vector form is a compact way of writing the same weighted-sum calculation.

### A simple example

Suppose a model estimates whether a transaction needs attention using two inputs:

- $x_1$: transaction amount score
- $x_2$: unfamiliar-device indicator

Assume the inputs and parameters are:

$$
x_1 = 2,\qquad x_2 = 3
$$

$$
w_1 = 0.4,\qquad w_2 = 0.7,\qquad b = -1
$$

**Step 1 – Multiply each input by its weight and add them.**

$$
z = w_1x_1 + w_2x_2 + b
$$

**Step 2 – Substitute the given values.**

$$
z = (0.4)(2) + (0.7)(3) - 1
$$

$$
z = 0.8 + 2.1 - 1
$$

$$
\boxed{z = 1.9}
$$

If we use the sigmoid activation function:

$$
\hat{y} = \frac{1}{1+e^{-z}}
$$

Substituting $z=1.9$:

$$
\hat{y} = \frac{1}{1+e^{-1.9}} \approx 0.870
$$

The artificial neuron produces an output of approximately $0.870$. In a binary-classification model, this may be interpreted as a positive-class score or estimated probability, depending on how the model has been trained and calibrated.

### What should you understand from this example?

The neuron does not directly understand the meaning of a transaction or a device. It receives numerical values and performs a mathematical calculation. The weights control the influence of the inputs, the bias shifts the calculation, and the activation function transforms the result.

This is the basic operation repeated throughout an ANN.

## 4. Biological neuron and artificial neuron compared

| Biological neural system | Artificial neural network |
|---|---|
| Dendrites receive signals | Inputs receive numerical features |
| Synaptic strength affects signal transmission | Weights control input influence |
| Cell body integrates incoming signals | Weighted sum and bias combine inputs |
| Neuron produces an electrical response | Activation function produces an output |
| Synaptic plasticity changes connection strengths | Learning algorithms update parameters |

### Visual comparison

For a side-by-side illustration of a biological neuron, an artificial neuron and the networks formed from them, see:

![[Pasted image 20261116214349.png]]
On the left is a biological neuron **(a)**, and a biological neural network **(c)**. On the right is an artificial neuron **(b)**, and an artificial neural network **(d)**.
- **Figure A (Biological neuron):** Dendrites take input, pass it on to the cell body (nucleus), and the axon carries the output.
- **Figure B (Artificial neuron):** $[x_1, x_2, x_3, \dots]$ are the inputs; they get passed into the node, which outputs a prediction.
- **Figure C (Biological neural network):** Depicts the connection, called a synapse, between two biological neurons.
- **Figure D (Artificial neural network):** Commonly referred to as an **ANN**, this depicts the connections of artificial neurons. The lines, denoted as $W^{(i)}$ and referred to as *weight-vectors* or *parameters*, are the ANN equivalent of synapses.

#### Reference:
- [Medium – Demystifying Artificial Intelligence](https://medium.com/geekculture/demystifying-artificial-intelligence-bdd9a117d4a6) – scroll to **“Biological Intelligence vs Artificial Intelligence”** and **“Biological Neuron vs Artificial Neuron”**.
- [University of Toronto – Introducing the Neuron](https://www.teach.cs.toronto.edu/~csc311notes/neural_networks/neuron_intro.html) – compare the biological-neuron and artificial-neuron sections.

Use these diagrams to understand the relationship, not to assume that both systems work identically.

## 5. What is the main difference?

Biological neurons communicate through electrochemical processes. Artificial neurons perform numerical calculations using mathematical operations.

Biological learning involves complex changes in the brain, including changes in synaptic connections. In an ANN, learning is generally performed by adjusting numerical parameters such as weights and biases using a training algorithm.

There is a useful similarity: both systems combine information from multiple connections, and the strength of those connections matters. However, the way they process information is fundamentally different.

Therefore, ANNs are **inspired by biological networks, but they work through mathematical computation**.

## 6. Important takeaway

A biological neuron provides the inspiration, while an artificial neuron provides a computational building block. By connecting many artificial neurons, we can construct networks that learn patterns from data.

**For an examination:** Always mention that the biological comparison is an analogy, not an exact reproduction of the human brain.

## 7. Quick self-check

Try answering these without looking back:

1. What are the main parts of a biological neuron?
2. What is the function of dendrites and the axon?
3. What is the role of weights in an artificial neuron?
4. Why is bias added to the weighted sum?
5. What does the activation function do?
6. Why is an artificial neuron considered a simplified analogy rather than a biological copy?

If you can explain the direction of signal flow in a biological neuron and then explain the equation of an artificial neuron in your own words, you have understood the foundation of this topic.

## References and visual resources

1. [Professor's Deep Learning slides – pages 3–5](#) – syllabus reference for biological inspiration, comparison and the artificial-neuron equation.
2. [GeeksforGeeks – Labelled Diagram of Neuron](https://www.geeksforgeeks.org/biology/diagram-of-neuron/) – biological neuron illustration and labelled parts.
3. [University of Toronto – Introducing the Neuron](https://www.teach.cs.toronto.edu/~csc311notes/neural_networks/neuron_intro.html) – clear explanations and interactive biological/artificial neuron diagrams.
4. [Medium – Demystifying Artificial Intelligence](https://medium.com/geekculture/demystifying-artificial-intelligence-bdd9a117d4a6) – visual comparison of biological and artificial neural systems.

*The professor's slides remain the syllabus source. The external resources are included to build visual intuition and provide a second explanation.*
