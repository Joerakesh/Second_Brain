# 03 – Applications of Artificial Neural Networks

## 1. Why are ANNs useful?

Many real-world problems involve relationships that are difficult to describe using a fixed set of rules. For example, recognising a face requires identifying patterns in thousands or millions of pixel values.

Instead of manually writing every possible rule, an ANN can learn patterns from examples. After training, it can use what it has learned to make predictions on new inputs.

The usefulness of an ANN depends on the quality of its data, the suitability of its architecture and how carefully it is trained and evaluated.

## 2. Major applications

### 2.1 Computer vision
ANNs can analyse images and identify objects, faces and visual patterns.

**Example:** A system receives an image and predicts whether it contains a car, person or bicycle.

The image pixels are converted into numerical inputs. The network learns visual features that help it distinguish between objects.

### 2.2 Healthcare
Neural networks can assist in interpreting medical images and identifying patterns that may be relevant to diagnosis.

**Example:** A model can analyse an X-ray image and flag areas that may need a doctor's attention.

The model is a support tool. Its output should not be treated as a replacement for professional medical judgement.

### 2.3 Retail and recommendation systems
Recommendation systems use information such as past purchases, interests and user activity to estimate what a person may prefer.

**Example:** An online shopping platform recommends products based on previous orders and browsing behaviour.

A simplified flow is:

**Past orders + interests + context → Feature vector → ANN prediction → Ranked recommendations**

### 2.4 Finance and fraud detection
ANNs can identify unusual patterns in financial transactions.

**Example:** A model may consider transaction amount, device information, location and recent transaction frequency to calculate a risk score.

A high score can trigger additional verification or human review. It is not proof that a transaction is fraudulent.

### 2.5 Environmental and sensor-data analysis
ANNs can process measurements collected from sensors and identify patterns over time or across locations.

**Example:** A model can analyse environmental sensor readings to estimate pollution levels or identify unusual changes.

## 3. Classification and regression applications

ANNs can be used for different types of prediction.

| Classification | Regression |
|---|---|
| Predicts a category or class | Predicts a numerical value |
| Example: fraud or not fraud | Example: predict delivery time |
| Output may be a class score or probability | Output is usually a continuous number |

The architecture and output activation are selected according to the task.

## 4. Recommendation example explained

Imagine an online store with a record of a customer's previous purchases.

1. The system collects relevant information, such as previous orders and interests.
2. It converts this information into numerical features.
3. The ANN processes the feature vector.
4. The network predicts preference scores for possible products.
5. Products are ranked and shown to the customer.

A deployed recommendation system must also consider updated user feedback, privacy and changes in user behaviour. A model that was accurate earlier may become less useful if preferences change.

## 5. Transfer learning and hybrid models

Two related ideas are introduced in the professor's slides:

- **Transfer learning:** Reuses representations learned by a model on a larger, related task. For example, a pretrained vision network can be adapted to classify a smaller animal-image dataset.
- **Hybrid models:** Combine complementary network structures or combine neural networks with other rules or methods.

When using transfer learning, the source and target datasets may differ. This difference is called domain shift and should be considered.

## 6. Conclusion

ANNs are useful because they can learn patterns from data and apply those patterns to new examples. Their applications include image recognition, healthcare support, recommendations, finance and sensor analysis. However, predictions must be evaluated carefully and used responsibly.

*Professor's slides: pages 8–11 and 21–22.*
