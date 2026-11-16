# 04 – Architecture of an Artificial Neural Network

## 1. What is ANN architecture?

ANN architecture describes how neurons are arranged and connected in a neural network.

A network is not simply a collection of unrelated neurons. The neurons are organised into layers, and each layer performs a stage of computation. The output of one layer becomes the input to the next layer.

A basic feed-forward ANN contains three types of layers:

**Input layer → Hidden layer(s) → Output layer**

## 2. Input layer

The input layer receives the features supplied to the network.

For example, if a model predicts house prices using area, number of bedrooms and building age, the input layer receives these three features.

The input layer mainly holds and passes the input data. It does not usually contain trainable weights and biases of its own.

## 3. Hidden layer

A hidden layer performs calculations using weights, biases and activation functions.

It is called a hidden layer because its intermediate values are not usually the final output shown to the user.

Hidden layers help the network learn useful intermediate representations. In an image task, for example, early layers may learn simple visual patterns, while later layers may combine them into more complex patterns.

A network may contain one hidden layer or several hidden layers.

## 4. Output layer

The output layer produces the network's final prediction.

Its design depends on the problem:

- For binary classification, one output with a sigmoid activation is commonly used.
- For multi-class classification, a softmax output is commonly used.
- For regression, a linear output is often used when the target can take unrestricted real values.

The output layer should match the type of result the model is expected to produce.

## 5. What is a feed-forward network?

A feed-forward network is a neural network in which information moves from the input layer towards the output layer without travelling backwards through feedback loops during the forward computation.

For example:

1. The input layer receives the features.
2. The first hidden layer calculates weighted sums and applies activation functions.
3. The next layer receives those activations and performs its own calculations.
4. The output layer produces the final prediction.

This movement from input to output is called the **forward pass**.

The fact that a network is feed-forward does not mean it cannot be trained. During training, gradients are calculated and parameters are updated. The forward pass and the training update are different parts of the learning process.

## 6. Dense layer

A dense layer is also called a fully connected layer. Every neuron in the previous layer is connected to every neuron in the current layer.

Suppose a layer receives 3 input values and contains 4 neurons. Each of the 4 neurons receives all 3 values. Therefore, the layer contains:

- 3 × 4 = 12 weights
- 4 bias values

This is why dense layers can have many trainable parameters.

## 7. Mathematical representation of a layer

For layer \(\ell\):

\[
z^{(\ell)} = W^{(\ell)}a^{(\ell-1)} + b^{(\ell)}
\]

\[
a^{(\ell)} = f^{(\ell)}(z^{(\ell)})
\]

Where:

- \(a^{(\ell-1)}\) – activations from the previous layer
- \(W^{(\ell)}\) – weight matrix of the current layer
- \(b^{(\ell)}\) – bias vector
- \(z^{(\ell)}\) – weighted sums before activation
- \(f^{(\ell)}\) – activation function
- \(a^{(\ell)}\) – output activations of the current layer

The same process is repeated for each layer until the network produces its prediction.

## 8. Example architecture: 3 → 4 → 2

Consider a network with:

- 3 input features
- 4 hidden neurons
- 2 output neurons

The architecture is written as **3 → 4 → 2**.

The first layer transforms 3 input values into 4 hidden activations. The output layer then uses those 4 activations to produce 2 output values.

The architecture tells us how many neurons are present in each layer. It does not, by itself, tell us the actual learned weights.

## 9. Conclusion

ANN architecture determines how information is processed through a network. The input layer receives features, hidden layers learn intermediate representations, and the output layer produces a prediction. In a feed-forward network, information moves from input to output through connected layers.

*Professor's slides: pages 12 and 15.*

## Related notes

- [[00_Learning_Roadmap|Chapter 1 learning roadmap]]
- [[01_Biological_and_Artificial_Neurons|The artificial neuron building block]]
- [[05_Weights_Biases_and_Parameters|Weights, biases and parameter counting]]
- [[06_Activation_Functions|Activation functions inside each layer]]
- [[07_Learning_Methods_and_Training_Process|Forward pass and training process]]
