# 07 – Learning Methods and the ANN Training Process

## 1. What does learning mean in an ANN?

An ANN begins with initial values for its weights and biases. These initial values usually do not produce accurate predictions.

Learning is the process of adjusting those trainable parameters using data so that the network becomes better at performing its task.

In simple terms, the network makes a prediction, measures how wrong it is and uses that information to improve its next prediction.

## 2. Learning from examples

In supervised learning, the training data contains both input features and their correct target values.

\[
D=\{(x_i,y_i)\}_{i=1}^{N}
\]

Here:

- \(x_i\) is an input example.
- \(y_i\) is the correct target.
- \(N\) is the number of training examples.

For example, a transaction dataset may contain features such as amount and device information, along with a label indicating whether the transaction is fraudulent or legitimate.

The ANN learns a mapping from the input features to the target.

## 3. Common learning paradigms

The following are broad machine-learning learning paradigms. They help distinguish how training information is provided.

### Supervised learning
The model receives inputs together with known target answers. It learns by comparing predictions with those answers.

**Example:** Predicting whether an email is spam or not spam using labelled emails.

### Unsupervised learning
The model receives data without supplied target labels. It attempts to discover structure or patterns in the data.

**Example:** Grouping customers according to similar purchasing behaviour.

### Reinforcement learning
An agent learns by interacting with an environment and receiving rewards or penalties for its actions.

**Example:** Training an agent to choose actions in a game to maximise its total reward.

These paradigms describe different sources of learning feedback. The Chapter 1 slides mainly demonstrate supervised prediction and its training/optimization loop.

## 4. The ANN training cycle

A basic training cycle can be understood through the following stages:

**1. Input data:** The network receives training features.

**2. Forward pass:** Each layer calculates weighted sums and applies activation functions.

**3. Prediction:** The output layer produces the predicted value or class score.

**4. Loss calculation:** A loss function compares the prediction with the correct target.

**5. Parameter update:** An optimizer uses gradient information to adjust weights and biases.

**6. Repeat:** The process continues over many training examples and training cycles.

This is the basic idea behind neural network training.

## 5. What is an epoch?

An epoch is one complete pass through the training dataset.

For example, if the training dataset contains 1,000 records, one epoch means that the model has processed all 1,000 records once. Training for 20 epochs means the model makes 20 passes through the training data, subject to the training procedure being used.

An epoch is not necessarily one parameter update. The number of updates depends on the batch size and training method.

## 6. Batch, stochastic and mini-batch learning

These terms describe how many training examples are used to calculate an update.

| Method | Data used for one update | Behaviour |
|---|---:|---|
| Batch gradient descent | Entire training dataset | More stable gradient estimate, but an update can be expensive |
| Stochastic gradient descent (SGD) | One training example | Frequent, noisy updates |
| Mini-batch gradient descent | A small group of examples | Balances computational efficiency and update stability |

For example, with 1,000 training records and a mini-batch size of 100, the model processes 10 mini-batches per epoch.

Mini-batch training is widely used in deep learning.

## 7. Training, validation and test data

The dataset is commonly divided into three parts:

- **Training set:** Used to learn model parameters.
- **Validation set:** Used to evaluate progress and guide choices such as model settings or early stopping.
- **Test set:** Kept separate until final evaluation to estimate performance on unseen data.

Preprocessing must also be handled carefully. For example, a scaler should be fitted using training data only and then applied to validation and test data. Otherwise, information from the evaluation data can leak into training.

## 8. What happens after training?

After training, the network can receive an unseen input and produce a prediction. This is called inference.

Training adjusts the model's parameters. Inference uses the learned parameters to make predictions without performing the usual training updates.

## 9. Conclusion

Learning in an ANN means improving its trainable parameters using information from data. The network performs a forward pass, calculates a loss and updates its parameters repeatedly. Understanding this cycle prepares us to study loss functions and optimizers.

*Professor's slides: pages 19–24. The broader supervised, unsupervised and reinforcement learning definitions are additional background to clarify the syllabus phrase “learning methods”.*

## Related notes

- [[00_Learning_Roadmap|Chapter 1 learning roadmap]]
- [[04_ANN_Architecture_and_Feed_Forward_Networks|Forward pass through the network]]
- [[05_Weights_Biases_and_Parameters|Trainable weights and biases]]
- [[06_Activation_Functions|Activation functions in the forward pass]]
- [[08_Loss_Functions|Step 4: calculate the loss]]
- [[09_Optimizers_and_Gradient_Descent|Step 5: update parameters]]
