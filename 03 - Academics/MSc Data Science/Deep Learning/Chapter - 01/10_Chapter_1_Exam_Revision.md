# Chapter 1 – Examination Revision

## 1. The chapter in one connected explanation

An artificial neural network is a computational model inspired by biological neural networks. It consists of connected artificial neurons arranged into layers.

Each artificial neuron receives input features, multiplies them by weights, adds a bias and applies an activation function:

\[
z=\sum_{i=1}^{n}w_ix_i+b,\qquad \hat y=f(z)
\]

The input layer receives data, hidden layers learn intermediate representations and the output layer produces the final prediction. In a feed-forward network, information moves from input to output without feedback loops during the forward pass.

During training, the network makes predictions and compares them with target values using a loss function. An optimizer uses gradient information to update the weights and biases. This process repeats so that the model can learn useful input-output relationships.

## 2. Important formulas

**Artificial neuron**

\[
z=\sum_{i=1}^{n}w_ix_i+b,\qquad \hat y=f(z)
\]

**Sigmoid**

\[
\sigma(x)=\frac{1}{1+e^{-x}}
\]

**ReLU**

\[
f(x)=\max(0,x)
\]

**Leaky ReLU**

\[
f(x)=
\begin{cases}
x & x\geq0\\
\alpha x & x<0
\end{cases}
\]

**ELU**

\[
f(x)=
\begin{cases}
x & x>0\\
\alpha(e^x-1) & x\leq0
\end{cases}
\]

**Mean Squared Error**

\[
MSE=\frac{1}{N}\sum_{i=1}^{N}(y_i-\hat y_i)^2
\]

**Binary Cross-Entropy**

\[
L_{BCE}=-\frac{1}{N}\sum_{i=1}^{N}
[y_i\ln(\hat p_i)+(1-y_i)\ln(1-\hat p_i)]
\]

**Dense-layer parameter count**

\[
\text{Parameters}=(n_{in}+1)n_{out}
\]

**Gradient descent**

\[
\theta_{t+1}=\theta_t-\eta\nabla_\theta L(\theta_t)
\]

## 3. Important differences

### Biological neuron vs artificial neuron
A biological neuron receives and transmits electrochemical signals. An artificial neuron performs a numerical calculation using inputs, weights, bias and an activation function.

### Weight vs bias
A weight controls the influence of an input connection. A bias shifts the neuron's response independently of the input values.

### Input vs hidden vs output layer
The input layer receives features. Hidden layers learn intermediate representations. The output layer produces the prediction.

### MSE vs binary cross-entropy
MSE is commonly used for regression. Binary cross-entropy is commonly used for binary classification.

### Backpropagation vs optimizer
Backpropagation calculates gradients. The optimizer uses those gradients to update parameters.

## 4. Parameter-counting practice

For a network with architecture 5 → 4 → 2:

Input to hidden:
- Weights = 5 × 4 = 20
- Biases = 4

Hidden to output:
- Weights = 4 × 2 = 8
- Biases = 2

Total:

\[
20+4+8+2=\boxed{34}
\]

## 5. Questions to test understanding

1. Why are artificial neural networks inspired by biological neurons?
2. Explain the difference between a biological neuron and an artificial neuron.
3. Describe the important milestones in the evolution of ANN.
4. Explain any five applications of ANN.
5. Draw and explain the architecture of a feed-forward neural network.
6. What is the difference between input, hidden and output layers?
7. Explain the role of weights and biases in an artificial neuron.
8. Calculate the trainable parameters in a 5 → 4 → 2 network.
9. Why are activation functions necessary in a neural network?
10. Explain Binary step, Sigmoid, ReLU, Leaky ReLU, ELU and SELU.
11. What is a learning method? Explain supervised, unsupervised and reinforcement learning.
12. Explain the training process of an ANN.
13. Explain MSE and binary cross-entropy with formulas.
14. What is an optimizer? Explain gradient descent.
15. Differentiate between backpropagation and an optimizer.

## 6. How to approach answers by marks

**2 marks:** Give a direct definition and one important point or example.

**5 marks:** Introduce the concept, explain its working and include the main characteristics or a suitable example.

**10 marks:** Use a clear introduction, meaningful subheadings, formulas or diagrams where relevant, a worked example and a short conclusion.

**20 marks:** Explain the complete concept, connect related ideas, include relevant formulas, diagrams, examples and limitations. Include calculations or a program only when the question requires them.

## 7. Final understanding check

Before moving to Chapter 2, make sure you can explain this without looking at the notes:

**How does an ANN turn input data into a prediction, measure its error and improve itself?**

If you can explain the neuron equation, the role of layers and activations, the loss function and the optimizer as one connected process, you have understood the foundation of Chapter 1.

## Related notes

- [[00_Learning_Roadmap|Chapter 1 learning roadmap]]
- [[01_Biological_and_Artificial_Neurons|Biological vs artificial neurons]]
- [[02_Evolution_of_Artificial_Neural_Networks|Evolution of ANN]]
- [[03_Applications_of_ANN|Applications of ANN]]
- [[04_ANN_Architecture_and_Feed_Forward_Networks|ANN architecture]]
- [[05_Weights_Biases_and_Parameters|Weights, biases and parameter counting]]
- [[06_Activation_Functions|Activation functions]]
- [[07_Learning_Methods_and_Training_Process|Learning methods and training]]
- [[08_Loss_Functions|Loss functions]]
- [[09_Optimizers_and_Gradient_Descent|Optimizers and gradient descent]]
