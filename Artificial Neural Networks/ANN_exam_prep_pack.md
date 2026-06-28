# Artificial Neural Networks Exam Prep Pack

Exam format: 50 multiple-choice questions, 60 minutes, no notes, one attempt, possible multiple correct answers, negative grading.

## How To Play The Exam

- You have about 72 seconds per question.
- First pass: answer only what is clear. Spend at most 45-50 minutes.
- Second pass: revisit flagged questions. Spend 8-10 minutes.
- Final check: verify no accidental selections. Spend 2-3 minutes.
- For multi-answer questions, judge each option independently. Do not select an option just because it "sounds related".
- With negative grading, skip or leave unselected any option you cannot justify. A half-known option is dangerous.

## Highest-Yield Topics

1. AI, machine learning, deep learning, and the ML workflow.
2. Perceptron, neuron, weights, biases, layers, MLPs, depth, and non-linearity.
3. Activation functions: linear, binary step, sigmoid, tanh, ReLU, Leaky ReLU, PReLU, Swish, Softmax.
4. Task type mapping: regression, binary classification, multiclass classification, multilabel classification.
5. Data preprocessing: numerical inputs, categorical encoding, scaling, train/validation/test split, leakage.
6. Training cycle: data loading, forward pass, loss, `zero_grad()`, `backward()`, `optimizer.step()`.
7. Losses: MSE, BCE, categorical cross entropy, `BCEWithLogitsLoss`, `CrossEntropyLoss`.
8. Gradient descent, learning rate, backpropagation, chain rule, vanishing/exploding gradients.
9. Optimizers: batch GD, stochastic GD, mini-batch GD, momentum, AdaGrad, RMSProp, Adam.
10. Evaluation and improvement: underfitting, overfitting, bias-variance, early stopping, regularization, hyperparameter tuning.
11. PyTorch practice: tensors, shapes, dtypes, `Dataset`, `DataLoader`, `nn.Module`, `nn.Sequential`, `model.train()`, `model.eval()`, TensorBoard, Optuna.

## Must-Memorize Task Mapping

| Task | Target | Conceptual output activation | Common PyTorch loss | Key warning |
|---|---|---|---|---|
| Regression | Continuous value | Linear / no activation | `nn.MSELoss()` | Output and target should be floats |
| Binary classification | One class among 2 | Sigmoid | `nn.BCEWithLogitsLoss()` | Give raw logits to the loss |
| Multiclass classification | One class among K | Softmax | `nn.CrossEntropyLoss()` | Give raw logits and integer class labels |
| Multilabel classification | Several independent labels | Sigmoid per label | `nn.BCEWithLogitsLoss()` | Target is multi-hot float vector |

## Activation Functions

- Linear: no non-linearity; stacked linear layers collapse to one linear transformation.
- Binary step: original perceptron-style threshold; not useful for gradient-based learning.
- Sigmoid: output in `[0, 1]`; useful for probabilities; can cause vanishing gradients.
- Tanh: output in `[-1, 1]`; zero-centered; can still saturate.
- ReLU: `max(0, z)`; efficient; can suffer dying ReLU.
- Leaky ReLU: keeps a small slope for negative inputs; helps with dying ReLU.
- PReLU: like Leaky ReLU, but the negative slope is learned.
- Swish: smooth non-linear activation; often strong but more expensive.
- Softmax: converts logits into probabilities that sum to 1 for multiclass output.

## PyTorch Training Loop Skeleton

```python
model.train()
for X_batch, y_batch in train_loader:
    y_logits = model(X_batch)
    loss = criterion(y_logits, y_batch)

    optimizer.zero_grad()
    loss.backward()
    optimizer.step()
```

Evaluation usually uses:

```python
model.eval()
with torch.no_grad():
    y_logits = model(X_test)
```

## Classic MCQ Traps

- `BCEWithLogitsLoss` already includes sigmoid internally.
- `CrossEntropyLoss` already includes log-softmax internally.
- `Dropout` behaves differently in training and evaluation modes.
- Scaling must be fit on training data only, then applied to validation/test data.
- Validation data is for tuning; test data is for final evaluation.
- Overfitting: low training error, high validation error.
- Underfitting: high training error and high validation error.
- Increasing model complexity usually decreases bias and increases variance.
- Early stopping watches validation performance, not training loss alone.
- Mini-batch gradient descent is the common deep learning default.
- Adam combines momentum-style first moments and RMSProp-style second moments.
- Batch normalization normalizes activations across mini-batches and stabilizes training.

## 50-Question Practice Quiz

Treat every question as "select all that apply". Some questions have one correct answer; some have several.

1. Which statements correctly distinguish AI, ML, and deep learning?
   A. Deep learning is a subset of machine learning.
   B. Machine learning is a subset of artificial intelligence.
   C. All AI systems must use neural networks.
   D. Deep learning models can learn feature representations from data.

2. In a supervised learning dataset, what is a label?
   A. The target value the model should predict.
   B. A trainable model parameter.
   C. The loss value after one epoch.
   D. The known output paired with input data.

3. Which elements are trainable parameters in a standard dense neural network?
   A. Weights.
   B. Biases.
   C. Learning rate.
   D. Number of epochs.

4. What happens if a deep network contains only linear transformations and no non-linear activation?
   A. It can be reduced to a single linear transformation.
   B. It cannot model complex non-linear relationships.
   C. It automatically becomes more expressive with each layer.
   D. It avoids the need for training.

5. Which activation functions can output values between 0 and 1?
   A. Sigmoid.
   B. Softmax probabilities.
   C. Tanh.
   D. ReLU.

6. Which statements about ReLU are correct?
   A. It returns 0 for negative inputs.
   B. It returns the input for positive inputs.
   C. It is computationally efficient.
   D. It always outputs probabilities.

7. Which activations are designed to reduce or avoid dying ReLU behavior?
   A. Leaky ReLU.
   B. PReLU.
   C. Binary step.
   D. Linear activation.

8. For a regression problem, which choices are usually appropriate?
   A. A continuous numerical target.
   B. A final linear output.
   C. `nn.MSELoss()`.
   D. `nn.CrossEntropyLoss()` with class indices.

9. For binary classification with raw logits in PyTorch, which loss is usually appropriate?
   A. `nn.BCEWithLogitsLoss()`.
   B. `nn.MSELoss()`.
   C. `nn.CrossEntropyLoss()` with one output neuron.
   D. `nn.BCELoss()` after no sigmoid.

10. Which statements about `nn.BCEWithLogitsLoss()` are correct?
    A. It expects raw logits.
    B. It internally combines sigmoid and binary cross entropy.
    C. It should usually be preceded by an explicit sigmoid in the model.
    D. It can be used for multilabel classification.

11. For multiclass classification with one correct class among K classes, which choices are typical?
    A. Model outputs K logits.
    B. Use `nn.CrossEntropyLoss()`.
    C. Target labels are integer class indices.
    D. Apply softmax before `nn.CrossEntropyLoss()`.

12. Which task uses independent yes/no predictions for several labels at once?
    A. Regression.
    B. Binary classification.
    C. Multiclass classification.
    D. Multilabel classification.

13. Which preprocessing steps help neural network training?
    A. Convert categorical variables to numerical representations.
    B. Scale numerical features when magnitudes differ.
    C. Fit scalers on the full dataset before train/test split.
    D. Keep text categories as raw strings in numeric tensors.

14. Which statements about train/validation/test splits are correct?
    A. Training data is used to update model weights.
    B. Validation data is useful for model selection and tuning.
    C. Test data should be kept for final unbiased evaluation.
    D. Test data should guide each hyperparameter decision.

15. What is data leakage?
    A. Information from validation/test data influences training.
    B. A GPU memory problem.
    C. A situation that can make evaluation look too optimistic.
    D. A required step in preprocessing.

16. Which sequence best matches a PyTorch training step?
    A. Forward pass, compute loss, zero gradients, backward pass, optimizer step.
    B. Backward pass, optimizer step, compute loss, forward pass.
    C. Compute loss, optimizer step, forward pass, zero gradients.
    D. Forward pass, `loss.backward()`, `optimizer.zero_grad()`, skip update.

17. Why call `optimizer.zero_grad()` during training?
    A. PyTorch accumulates gradients by default.
    B. It resets old gradients before computing new ones.
    C. It initializes model weights to zero.
    D. It prevents loss calculation.

18. Which statements about backpropagation are correct?
    A. It computes gradients of loss with respect to parameters.
    B. It relies on the chain rule.
    C. It updates weights directly without an optimizer.
    D. It propagates gradient information backward through the network.

19. In gradient descent, what does the learning rate control?
    A. Step size of parameter updates.
    B. Number of model layers.
    C. How strongly gradients affect updates.
    D. Whether the model is supervised or unsupervised.

20. If the learning rate is too high, what can happen?
    A. Training may diverge.
    B. Loss may oscillate.
    C. The model may jump over good minima.
    D. Gradients stop existing mathematically.

21. Which statements about mini-batch gradient descent are correct?
    A. It computes updates using small batches of examples.
    B. It is commonly used in deep learning.
    C. It is a compromise between batch GD and stochastic GD.
    D. It always uses the entire training dataset for each update.

22. Which optimizer combines ideas from momentum and RMSProp?
    A. Adam.
    B. AdaGrad.
    C. Plain batch gradient descent.
    D. Binary cross entropy.

23. Which statements about momentum are correct?
    A. It uses information from previous gradients.
    B. It can smooth noisy updates.
    C. It is a loss function.
    D. It can help move through shallow local regions.

24. Which statements about vanishing gradients are correct?
    A. Early layers may receive extremely small gradient updates.
    B. Sigmoid and tanh saturation can contribute to the problem.
    C. ReLU-like activations can help mitigate it.
    D. It only occurs in linear regression.

25. What is the dying ReLU problem?
    A. A ReLU neuron can output zero for many inputs and stop learning effectively.
    B. A sigmoid output exceeds 1.
    C. A model trains too quickly.
    D. Negative inputs can produce zero gradients through ReLU.

26. Which initialization is commonly associated with ReLU-based networks?
    A. Kaiming / He initialization.
    B. Xavier / Glorot initialization.
    C. Randomly setting all weights to exactly zero.
    D. Initializing every neuron identically.

27. Which statements about Xavier / Glorot initialization are correct?
    A. It considers input and output layer sizes.
    B. It is often associated with tanh-like activations.
    C. It sets all weights to one.
    D. It aims to keep signal variance stable.

28. Which signs indicate underfitting?
    A. High training error.
    B. High validation error.
    C. Training and validation performance both poor.
    D. Very low training error and much worse validation error.

29. Which signs indicate overfitting?
    A. Very low training error.
    B. High validation error.
    C. A growing gap between train and validation performance.
    D. Poor fit on the training set from the start.

30. Which actions can help reduce underfitting?
    A. Increase model complexity.
    B. Train for more epochs.
    C. Add useful features.
    D. Increase dropout aggressively.

31. Which actions can help reduce overfitting?
    A. Early stopping.
    B. Add regularization.
    C. Reduce model complexity.
    D. Use the test set repeatedly for tuning.

32. Which statements about bias and variance are correct?
    A. High bias is often linked to overly simple models.
    B. High variance is often linked to sensitivity to training data.
    C. Increasing complexity usually decreases bias and increases variance.
    D. Irreducible error can always be removed by a larger network.

33. Which regularization method randomly sets a fraction of neuron outputs to zero during training?
    A. Dropout.
    B. Batch normalization.
    C. L2 regularization.
    D. Softmax.

34. Which statements about L1 and L2 regularization are correct?
    A. L1 can encourage sparsity.
    B. L2 penalizes large weights.
    C. Both can add a penalty term to the loss.
    D. Both are activation functions.

35. What does early stopping monitor?
    A. Usually validation loss or validation metric.
    B. Only the number of input features.
    C. Whether validation performance has stopped improving.
    D. Whether the training loss is exactly zero.

36. Which statements about batch normalization are correct?
    A. It normalizes activations across a mini-batch.
    B. It can stabilize training.
    C. It can help with gradient flow.
    D. It replaces the need for a loss function.

37. Which are hyperparameters?
    A. Learning rate.
    B. Batch size.
    C. Number of hidden layers.
    D. Learned weight values after training.

38. Which hyperparameter tuning approaches were covered?
    A. Grid search.
    B. Random search.
    C. Bayesian optimization.
    D. Manual deletion of the validation set.

39. In K-fold cross-validation, what happens?
    A. The model is trained/evaluated multiple times on different splits.
    B. Results are averaged across folds.
    C. It is used to estimate performance more robustly.
    D. The test set is used as training data in every fold.

40. Which PyTorch objects are commonly used to feed mini-batches?
    A. `TensorDataset`.
    B. `DataLoader`.
    C. `SummaryWriter`.
    D. `nn.MSELoss`.

41. Which statements about `model.train()` and `model.eval()` are correct?
    A. `model.train()` enables training behavior for layers like dropout.
    B. `model.eval()` disables training behavior for layers like dropout.
    C. `model.eval()` automatically prevents gradients unless used with `torch.no_grad()`.
    D. The mode can affect batch normalization behavior.

42. Why use `torch.no_grad()` during evaluation?
    A. It avoids tracking gradients.
    B. It reduces memory usage.
    C. It is needed for optimizer updates.
    D. It makes the model train faster by updating weights.

43. Which metrics or tools are useful for classification evaluation?
    A. Confusion matrix.
    B. Precision and recall.
    C. F1-score.
    D. RMSE only.

44. Which metrics are common for regression evaluation?
    A. MSE.
    B. RMSE.
    C. MAE.
    D. Confusion matrix.

45. What is TensorBoard used for in the labs?
    A. Monitoring losses and metrics during training.
    B. Visualizing training curves.
    C. Replacing the optimizer.
    D. Writing logs with `SummaryWriter`.

46. What is Optuna used for in the labs?
    A. Hyperparameter tuning.
    B. Trying candidate values across trials.
    C. Automatically computing gradients.
    D. Replacing train/validation/test splitting.

47. Which statements about deep learning are correct?
    A. It can learn features directly from raw data.
    B. It is powerful for images, audio, and text.
    C. It often needs large labeled datasets and compute.
    D. It is always easier to interpret than linear models.

48. Why go deeper in a neural network?
    A. Layers can learn progressively more abstract representations.
    B. Deep architectures can compose features hierarchically.
    C. More layers always guarantee better test performance.
    D. Deeper models can be harder to train.

49. Which problems become more important in deep networks?
    A. Vanishing/exploding gradients.
    B. Overfitting risk.
    C. Internal covariate shift.
    D. Need for careful initialization and optimization.

50. Under negative grading, what is a good MCQ tactic?
    A. Select only options you can justify.
    B. Treat each option independently in multi-answer questions.
    C. Guess every option to maximize coverage.
    D. Leave uncertain options unselected if blank/unselected options are not penalized.

## Answer Key

1. A, B, D
2. A, D
3. A, B
4. A, B
5. A, B
6. A, B, C
7. A, B
8. A, B, C
9. A
10. A, B, D
11. A, B, C
12. D
13. A, B
14. A, B, C
15. A, C
16. A
17. A, B
18. A, B, D
19. A, C
20. A, B, C
21. A, B, C
22. A
23. A, B, D
24. A, B, C
25. A, D
26. A
27. A, B, D
28. A, B, C
29. A, B, C
30. A, B, C
31. A, B, C
32. A, B, C
33. A
34. A, B, C
35. A, C
36. A, B, C
37. A, B, C
38. A, B, C
39. A, B, C
40. A, B
41. A, B, D
42. A, B
43. A, B, C
44. A, B, C
45. A, B, D
46. A, B
47. A, B, C
48. A, B, D
49. A, B, C, D
50. A, B, D

## Last-Day Drill

1. Redo the 50-question quiz once without looking at the answer key.
2. For every wrong answer, write the exact rule you missed in one sentence.
3. Memorize the task/loss table.
4. Review only these files if time is short:
   - `ANN Syllabus.pdf`
   - `day1/ANN_02_understanding_neural_networks.pdf`
   - `day2/ANN_03_How_neural_networks_learn.pdf`
   - `day3/ANN_04_Model_evaluation_and_improvement.pdf`
   - `day4/ANN_exercise_curves.pdf`
   - PyTorch labs from days 1-4

