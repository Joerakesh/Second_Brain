# 06 – Activation Functions

## 1. Why does a neural network need activation functions?

A neuron first calculates a weighted sum and bias:

\[
z=\sum_{i=1}^{n}w_ix_i+b
\]

If the network simply passed this value from one layer to another without applying any non-linear operation, stacking multiple layers would still produce an overall linear transformation.

That would limit the kinds of relationships the network could learn.

An **activation function** transforms the neuron's weighted sum into its output. Non-linear activation functions allow a network to learn more complex patterns and decision boundaries.

The activation function is therefore not just an extra calculation. It is one of the reasons multilayer networks can represent complex relationships.

## 2. Binary step function

The binary step function produces one of two outputs depending on whether the input reaches a threshold.

\[
f(x)=
\begin{cases}
1 & x\geq 0\\
0 & x<0
\end{cases}
\]

**How it works:** If the input is zero or positive, the output is 1. Otherwise, the output is 0.

**Example:** If \(x=2\), the output is 1. If \(x=-0.5\), the output is 0.

**Use:** It is associated with basic threshold neurons such as the McCulloch–Pitts neuron and the perceptron.

**Limitation:** It is not suitable for ordinary gradient-based learning because its derivative is zero almost everywhere and is undefined at the threshold.

## 3. Sigmoid function

The sigmoid function converts any real-valued input into a value strictly between 0 and 1.

\[
\sigma(x)=\frac{1}{1+e^{-x}}
\]

**How it works:** Large positive inputs produce outputs close to 1. Large negative inputs produce outputs close to 0. An input of zero produces 0.5.

**Example:**

\[
\sigma(0)=\frac{1}{1+e^0}=0.5
\]

**Use:** It is commonly used in the output layer for binary classification, where the output can represent a model's estimated positive-class probability when the model is appropriately trained and calibrated.

**Advantages:**
- Smooth curve.
- Output is bounded between 0 and 1.
- Useful for binary output scores.

**Limitations:**
- It can saturate for very large positive or negative inputs.
- Its gradients become very small in saturated regions, which can slow learning in deep networks.
- Its outputs are not automatically well-calibrated probabilities.

## 4. ReLU – Rectified Linear Unit

ReLU keeps positive values and changes negative values to zero.

\[
f(x)=\max(0,x)
\]

Equivalently:

\[
f(x)=
\begin{cases}
x & x>0\\
0 & x\leq0
\end{cases}
\]

**Example:**

- \(f(3)=3\)
- \(f(-2)=0\)
- \(f(0)=0\)

**Use:** ReLU is widely used in hidden layers.

**Advantages:**
- Simple and computationally efficient.
- Does not saturate on the positive side.
- Often helps train deep networks more effectively than sigmoid hidden units.

**Limitation:** A neuron can become inactive if it repeatedly receives negative inputs and produces zero. This is commonly called the *dying ReLU* problem.

## 5. Leaky ReLU

Leaky ReLU is designed to address the zero-gradient region of ReLU for negative inputs.

\[
f(x)=
\begin{cases}
x & x\geq0\\
\alpha x & x<0
\end{cases}
\]

Here, \(\alpha\) is a small positive constant.

**Example:** If \(\alpha=0.01\) and \(x=-2\):

\[
f(-2)=0.01(-2)=-0.02
\]

Unlike ordinary ReLU, it allows a small negative output for negative inputs.

**Advantage:** The negative side has a small slope, so the gradient is not zero there.

**Limitation:** The slope parameter must be selected, and Leaky ReLU is not guaranteed to improve every model.

## 6. ELU – Exponential Linear Unit

ELU behaves linearly for positive inputs and uses an exponential curve for negative inputs.

\[
f(x)=
\begin{cases}
x & x>0\\
\alpha(e^x-1) & x\leq0
\end{cases}
\]

Here, \(\alpha\) controls the negative saturation value.

**How it works:** Positive values pass through unchanged. Negative values approach a lower saturation level rather than becoming exactly zero.

**Advantages:**
- Provides a smooth negative region.
- Allows negative outputs.
- Can produce activations closer to zero-centred values.

**Limitation:** It uses an exponential calculation and may be more computationally expensive than ReLU.

## 7. SELU – Scaled Exponential Linear Unit

SELU is a scaled version of ELU. Its purpose is to encourage self-normalising behaviour under particular conditions.

\[
\operatorname{SELU}(x)=\lambda
\begin{cases}
x & x>0\\
\alpha(e^x-1) & x\leq0
\end{cases}
\]

Here, \(\lambda\) and \(\alpha\) are specific scaling constants used by the SELU definition.

**How it works:** SELU scales both the positive and negative parts of the ELU-style function. Under suitable assumptions and network design, activations can tend towards a stable mean and variance.

**Use:** It is associated with self-normalising neural networks.

**Important limitation:** The self-normalising behaviour depends on conditions such as suitable initialization and compatible network design. SELU does not automatically normalise every arbitrary network.

## 8. Comparison of the six functions

| Function | Main behaviour | Output range | Main point |
|---|---|---|---|
| Binary step | Hard threshold | \(\{0,1\}\) | Binary decision |
| Sigmoid | Smooth S-shaped curve | \((0,1)\) | Binary output score |
| ReLU | Negative values become zero | \([0,\infty)\) | Common hidden activation |
| Leaky ReLU | Small negative slope | All real values | Keeps negative-side gradient |
| ELU | Exponential negative side | \((-\alpha,\infty)\) for \(\alpha>0\) | Smooth negative saturation |
| SELU | Scaled ELU | Depends on fixed constants | Self-normalising design |

## 9. How should an activation function be selected?

The choice depends on the network architecture and the task.

- ReLU is a common starting point for hidden layers.
- Leaky ReLU may be considered when inactive ReLU units are a concern.
- ELU provides a smooth negative region.
- SELU is intended for compatible self-normalising architectures.
- Sigmoid is commonly used for a single binary-classification output.
- A step function is useful for understanding threshold logic, but not normally for gradient-based training.

There is no single activation function that is best for every situation.

## 10. The most important examination concept

**Why are non-linear activation functions important?**

Without non-linear activation functions, stacking several linear layers is mathematically equivalent to a single linear transformation. Therefore, the network would not gain the ability to learn complex non-linear relationships simply by adding more layers.

Non-linear activation functions allow the network to learn more flexible decision boundaries.

## 11. Conclusion

Activation functions determine how a neuron transforms its weighted input into an output. Step and sigmoid provide threshold-like and bounded responses, while ReLU and its variants are widely used in modern hidden layers. Selecting a suitable activation function helps the network learn the type of relationship required by the problem.

*Professor's slides: pages 16–18. The syllabus specifically lists Binary step, Sigmoid, ReLU, Leaky ReLU, ELU and SELU.*
