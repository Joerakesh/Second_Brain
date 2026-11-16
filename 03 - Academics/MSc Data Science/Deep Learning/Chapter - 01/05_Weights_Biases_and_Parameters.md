# 05 – Weights, Biases and Trainable Parameters

## 1. What does a neural network actually learn?

A neural network learns numerical values that control how it responds to input data. The most important trainable values in a basic dense ANN are **weights and biases**.

These values determine how strongly each input affects a neuron and where the neuron's response changes.

## 2. Weights

A weight represents the influence assigned to an input connection.

Suppose a neuron receives two inputs:

- \(x_1\): transaction amount score
- \(x_2\): unfamiliar-device indicator

The neuron calculates:

\[
z=w_1x_1+w_2x_2+b
\]

If \(w_1\) has a larger magnitude than \(w_2\), then changes in \(x_1\) have a stronger effect on the weighted sum, assuming the inputs are on comparable scales.

A positive weight increases the weighted sum when its input increases. A negative weight decreases it.

Weights are not manually chosen in ordinary training. They are adjusted by the learning algorithm based on the model's errors.

## 3. Bias

Bias is an additional trainable value added to the weighted sum.

\[
z=\sum_{i=1}^{n}w_ix_i+b
\]

It allows the neuron to shift its response independently of the input-weight products.

For a simple two-dimensional linear decision boundary:

\[
w_1x_1+w_2x_2+b=0
\]

The weights influence the orientation of the line, while the bias shifts its position.

Without a bias, the boundary is restricted to pass through the origin. Adding a bias makes the model more flexible.

## 4. Worked example: one artificial neuron

Given:

\[
x_1=2,\quad x_2=3
\]

\[
w_1=0.4,\quad w_2=0.7,\quad b=-1
\]

First calculate the weighted sum:

\[
z=w_1x_1+w_2x_2+b
\]

\[
z=(0.4)(2)+(0.7)(3)-1
\]

\[
z=0.8+2.1-1=\boxed{1.9}
\]

If sigmoid is used:

\[
\hat y=\frac{1}{1+e^{-1.9}}\approx\boxed{0.870}
\]

The neuron has converted the two input values into an output score of approximately 0.870. This score should not automatically be treated as a calibrated probability.

## 5. What are parameters?

Parameters are the trainable values that the network adjusts during training.

In a standard dense neural network, the trainable parameters are:

- Weights
- Biases

The architecture determines how many parameters the model contains. Training determines the values those parameters take.

## 6. Counting parameters in a dense layer

For a dense layer:

\[
\text{Parameters}=(n_{in}\times n_{out})+n_{out}
\]

This can also be written as:

\[
\boxed{\text{Parameters}=(n_{in}+1)n_{out}}
\]

Where:

- \(n_{in}\) – number of neurons in the previous layer
- \(n_{out}\) – number of neurons in the current layer
- \(n_{in}\times n_{out}\) – number of weights
- \(n_{out}\) – number of biases, one for each output neuron

## 7. Worked example: network 5 → 4 → 2

**Input to hidden layer:**

- Weights = \(5\times4=20\)
- Biases = \(4\)
- Total = \(24\)

**Hidden to output layer:**

- Weights = \(4\times2=8\)
- Biases = \(2\)
- Total = \(10\)

Therefore:

\[
\text{Total parameters}=20+4+8+2
\]

\[
\boxed{34\text{ trainable parameters}}
\]

The input layer is not counted as having trainable weights and biases in this calculation because it only receives the input values.

## 8. Why does parameter count matter?

Parameter count helps us understand the size and complexity of a model. A model with more parameters has more values to learn, but having more parameters does not automatically make a model better.

If a model is too complex for the available training data, it may overfit. Therefore, architecture should be selected according to the task and the amount and quality of available data.

## 9. Conclusion

Weights control the influence of input connections, while biases shift a neuron's response. Together, they form the main trainable parameters of a basic ANN. Understanding them is essential because learning in a neural network largely means finding suitable values for these parameters.

*Professor's slides: pages 5, 13–15. The worked neuron example follows page 14.*
