# 09 – Optimizers and Gradient Descent

## 1. Why do we need an optimizer?

A loss function tells us how far a prediction is from the correct target. However, calculating the loss does not automatically improve the network.

We need a method to adjust the trainable weights and biases so that future predictions produce a smaller loss. An **optimizer** performs these parameter updates using gradient information.

## 2. Understanding a gradient

A gradient describes how the loss changes when the model's parameters change.

Imagine standing on a hill. If you want to move towards a lower point, you need to know which direction slopes downwards.

In optimization, the gradient points in the direction of the greatest local increase in the loss. Therefore, gradient descent moves in the opposite direction.

## 3. Gradient descent formula

\[
\theta_{t+1}=\theta_t-\eta\nabla_\theta L(\theta_t)
\]

Where:

- \(\theta_t\) – current model parameters
- \(\theta_{t+1}\) – updated parameters
- \(\eta\) – learning rate
- \(\nabla_\theta L\) – gradient of the loss with respect to the parameters
- \(L\) – loss function

The minus sign indicates that the update moves opposite to the gradient.

## 4. What is the learning rate?

The learning rate controls the size of each parameter update.

| Learning rate | What can happen? |
|---|---|
| Too small | Training may progress very slowly |
| Suitable | Training may converge efficiently |
| Too large | Updates may overshoot and the loss may become unstable or diverge |

Choosing a suitable learning rate is important for effective training.

## 5. Worked example: one parameter update

Consider a simple linear neuron:

\[
\hat y=wx+b
\]

Given:

\[
x=2,\quad y=1,\quad w=0.2,\quad b=0,\quad \eta=0.1
\]

Use the loss:

\[
L=\frac12(\hat y-y)^2
\]

**Step 1 – Calculate the prediction**

\[
\hat y=(0.2)(2)+0=0.4
\]

**Step 2 – Calculate the loss**

\[
L=\frac12(0.4-1)^2
=\frac12(0.36)=0.18
\]

**Step 3 – Calculate the gradients**

\[
\frac{\partial L}{\partial w}=(\hat y-y)x
=(-0.6)(2)=-1.2
\]

\[
\frac{\partial L}{\partial b}=\hat y-y=-0.6
\]

**Step 4 – Update the weight and bias**

\[
w_{new}=w-\eta\frac{\partial L}{\partial w}
\]

\[
w_{new}=0.2-0.1(-1.2)=0.32
\]

\[
b_{new}=b-\eta\frac{\partial L}{\partial b}
\]

\[
b_{new}=0-0.1(-0.6)=0.06
\]

**Step 5 – Calculate the new prediction**

\[
\hat y_{new}=(0.32)(2)+0.06=0.70
\]

The prediction has moved from 0.40 towards the actual value of 1. This demonstrates how a gradient-based update can improve a prediction for this example.

## 6. Common optimizers

### Gradient Descent
Uses the gradient of the loss to update parameters in the direction that reduces the loss.

### Stochastic Gradient Descent (SGD)
Updates parameters using the gradient calculated from one training example at a time. It produces frequent updates, but these can be noisy.

### Mini-batch Gradient Descent
Calculates gradients using a small batch of training examples. It is widely used because it balances computational efficiency and update stability.

### Momentum
Adds a running direction based on previous updates. This can help reduce oscillations and accelerate progress in consistent directions.

### RMSprop
Adapts the effective step size for parameters using a moving average of squared gradients.

### Adam
Combines ideas related to momentum and adaptive learning rates. It maintains moving averages of gradients and squared gradients. Adam is a commonly used default optimizer in many neural-network workflows, although the best choice depends on the task.

## 7. Backpropagation and optimization are not the same

These two concepts work together, but they perform different jobs.

- **Backpropagation:** Calculates gradients showing how each parameter contributes to the loss.
- **Optimizer:** Uses those gradients to update the parameters.

A simple way to remember this is: backpropagation calculates the direction and optimizer performs the update.

## 8. Conclusion

Optimizers help neural networks learn by updating weights and biases to reduce the loss. Gradient descent provides the basic update idea, while methods such as SGD, RMSprop and Adam offer different ways to perform parameter updates. The learning rate and optimizer choice influence how effectively training progresses.

*Professor's slides: page 20 introduces the optimization loop and update equation. The numerical gradient-descent example and optimizer descriptions provide supporting explanation beyond the brief slide coverage.*

## Related notes

- [[00_Learning_Roadmap|Chapter 1 learning roadmap]]
- [[05_Weights_Biases_and_Parameters|Parameters being updated]]
- [[07_Learning_Methods_and_Training_Process|The ANN training cycle]]
- [[08_Loss_Functions|Loss functions and gradients]]
- [[10_Chapter_1_Exam_Revision|Chapter 1 formula and concept revision]]
