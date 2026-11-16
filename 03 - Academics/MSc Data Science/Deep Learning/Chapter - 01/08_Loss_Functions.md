# 08 – Loss Functions

## 1. Why does an ANN need a loss function?

A neural network produces predictions, but a prediction alone does not tell us whether the model is performing well.

To improve the model, we need a way to compare its prediction with the correct answer. A **loss function** measures the error for a prediction or a group of predictions.

The training process aims to reduce this loss.

A smaller loss generally indicates that predictions are closer to the targets according to the selected loss measure. However, loss alone does not describe every aspect of model performance.

## 2. Mean Squared Error (MSE)

Mean Squared Error is commonly used for regression problems, where the model predicts a continuous numerical value.

\[
MSE=\frac{1}{N}\sum_{i=1}^{N}(y_i-\hat y_i)^2
\]

Where:

- \(N\) – number of observations
- \(y_i\) – actual value
- \(\hat y_i\) – predicted value

### Why are the errors squared?

Squaring prevents positive and negative errors from cancelling each other. It also gives larger errors a stronger penalty.

### Example

Suppose the actual delivery time is 30 minutes and the predicted time is 25 minutes.

\[
MSE=(30-25)^2=25
\]

For a single observation, the squared error is 25. For multiple observations, MSE is the average of their squared errors.

**Application:** Predicting delivery time, house price or energy consumption.

## 3. Binary Cross-Entropy (BCE)

Binary cross-entropy is commonly used for binary classification problems, where the target belongs to one of two classes.

\[
L_{BCE}=-\frac{1}{N}\sum_{i=1}^{N}
[y_i\ln(\hat p_i)+(1-y_i)\ln(1-\hat p_i)]
\]

Where:

- \(y_i\) – actual binary label, 0 or 1
- \(\hat p_i\) – predicted probability for the positive class
- \(N\) – number of observations

### How does it work?

BCE evaluates the predicted probability against the actual class.

If the actual label is 1, a prediction close to 1 produces a small loss. A prediction close to 0 produces a large loss.

If the actual label is 0, a prediction close to 0 produces a small loss, while a prediction close to 1 produces a large loss.

This means BCE strongly penalises confident incorrect predictions.

### Example

Suppose the actual label is 1.

If the predicted probability is 0.6:

\[
L=-\ln(0.6)\approx0.511
\]

If the predicted probability is 0.9:

\[
L=-\ln(0.9)\approx0.105
\]

The second prediction has a smaller loss because it assigns a higher probability to the correct class.

**Application:** Predicting whether a transaction needs review or whether an email is spam.

## 4. MSE and BCE compared

| MSE | Binary cross-entropy |
|---|---|
| Commonly used for regression | Commonly used for binary classification |
| Measures squared numerical error | Measures mismatch between binary labels and predicted probabilities |
| Penalises large errors quadratically | Strongly penalises confident incorrect predictions |
| Example: delivery-time prediction | Example: fraud/not-fraud prediction |

The loss function should match the task and the model's output representation.

## 5. Loss and the training process

The loss function is connected to the optimizer through the training loop:

**Prediction → Loss calculation → Gradient calculation → Parameter update**

The loss gives a numerical measure of error. The gradient tells us how the loss changes when parameters change. The optimizer uses this information to update the parameters.

A loss function measures how wrong the model is; it does not itself decide how the weights should be updated.

## 6. Conclusion

Loss functions provide a measurable objective for training a neural network. MSE is commonly used for regression, while binary cross-entropy is commonly used for binary classification. Choosing an appropriate loss function is important because it determines what kind of prediction error the training process tries to reduce.

*Professor's slides: page 19.*

## Related notes

- [[00_Learning_Roadmap|Chapter 1 learning roadmap]]
- [[03_Applications_of_ANN|Classification and regression tasks]]
- [[06_Activation_Functions|Activation functions and model outputs]]
- [[07_Learning_Methods_and_Training_Process|The complete ANN training cycle]]
- [[09_Optimizers_and_Gradient_Descent|How gradients and optimizers reduce loss]]
