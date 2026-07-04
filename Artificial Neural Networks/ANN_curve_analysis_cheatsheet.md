# Day 4 Curve Analysis Cheat Sheet

Source: `day4/ANN_exercise_curves.pdf`

## First Rule

Do not diagnose underfitting or overfitting from the training curve alone.

- A high training loss can suggest underfitting, but you need validation loss to confirm.
- A very low training loss can suggest overfitting, but you need validation loss to confirm.
- The validation curve tells you whether the model generalizes.

## How To Analyse Training Curves

Use this sequence:

1. Identify the metric.
   - If it is loss, lower is better.
   - If it is accuracy, higher is better.
2. Compare training and validation curves.
3. Look at the final level: are both good or bad?
4. Look at the gap: is validation much worse than training?
5. Look at time: does validation improve first, then get worse?
6. Look for oscillation/noise: is the curve unstable rather than simply high or low?

## Main Curve Patterns

| Pattern | Diagnosis | Meaning | Fix |
|---|---|---|---|
| Training loss high, validation loss high | Underfitting | The model is not learning the training data well enough | Increase complexity, train longer, improve features/data, reduce excessive regularization |
| Training loss low, validation loss high | Overfitting | The model memorizes training data but generalizes poorly | Early stopping, add regularization, reduce complexity, add data, feature selection |
| Training loss decreases, validation loss decreases, small gap | Good fit | The model learns and generalizes | Keep model; evaluate once on test set |
| Training loss keeps decreasing, validation loss decreases then rises | Overfitting after some epochs | Training too long | Early stopping at minimum validation loss |
| Curves are very noisy or oscillating | Optimization instability | Learning rate too high, batch size too small, or mini-batch noise | Lower learning rate, increase batch size, smooth/average curves |
| Train and validation both decrease but validation remains consistently worse | Ambiguous | Could be mild underfitting or train/validation distribution mismatch | Check split/stratification, add or improve training data |
| Curves wiggle but trend downward together | Usually no problem | Normal mini-batch training noise | Continue if validation trend improves |

## Day 4 Exercise Mapping

| Slides | Instructor answer | Lesson |
|---|---|---|
| Pages 2-3 | Maybe underfitting, but cannot say | Training loss alone is insufficient |
| Pages 4-5 | Maybe overfitting, but cannot say | Need validation curve |
| Pages 6-7 | Overfitting | Validation loss worse than training loss |
| Pages 8-9 | Performing well | Both curves converge well |
| Pages 10-11 | Trains well, then overfits | Use early stopping |
| Pages 12-13 | Underfitting | Both train and validation remain too high |
| Pages 14-15 | Hard to say; maybe slight underfitting or distribution issue | Improve/add training data; check train/test distribution |
| Pages 16-17 | Oscillation problem | Lower learning rate; increase batch size |
| Pages 18-19 | No problem | Curves trend down normally |
| Pages 20-21 | Gradient functions | 1 = tanh, 2 = sigmoid, 3 = ReLU |

## Underfitting

Underfitting means the model is too weak, too constrained, or not trained enough to capture the pattern.

Signs:

- High training loss.
- High validation loss.
- Both curves plateau at a bad level.
- Training and validation are both poor.

Common causes:

- Model too simple.
- Too few epochs.
- Learning rate poorly chosen.
- Bad or missing features.
- Poor scaling/preprocessing.
- Too much regularization or dropout.

Fixes:

- Add neurons or layers.
- Train longer.
- Add useful features.
- Improve data quality.
- Normalize or standardize inputs.
- Reduce excessive regularization.

## Overfitting

Overfitting means the model learns training data too specifically, including noise and outliers.

Signs:

- Training loss very low.
- Validation loss high or increasing.
- Gap between training and validation grows.
- Validation curve gets worse after initially improving.

Common causes:

- Model too complex.
- Too many epochs.
- Too little data.
- Noisy data or irrelevant features.
- Weak regularization.

Fixes:

- Early stopping.
- Dropout.
- L1 or L2 regularization.
- Reduce model complexity.
- Add more data or data augmentation.
- Remove irrelevant features.

## Gradient Function Identification

In the Day 4 exercise, the plotted gradients are derivatives of activation functions.

| Gradient shape | Function | Formula | How to recognize it |
|---|---|---|---|
| Tall symmetric bell, peak 1 at 0, goes to 0 on both sides | tanh | `tanh'(z) = 1 - tanh(z)^2` | Highest peak; saturates quickly away from 0 |
| Lower wider bell, peak 0.25 at 0, goes to 0 on both sides | sigmoid | `sigmoid'(z) = sigmoid(z) * (1 - sigmoid(z))` | Same bell idea, but much lower maximum |
| Step shape: 0 for negative inputs, 1 for positive inputs | ReLU | `ReLU'(z) = 0 if z < 0; 1 if z > 0` | Flat zero left, flat one right |

Extra useful derivatives:

| Function | Gradient |
|---|---|
| Linear | Constant `1` |
| Binary step | `0` almost everywhere; not useful for gradient descent |
| Leaky ReLU | Small slope `alpha` for negative inputs, `1` for positive inputs |
| PReLU | Same as Leaky ReLU, but `alpha` is learned |

## Exam Traps

- A decreasing training loss alone does not prove the model is good.
- A low training loss alone does not prove the model generalizes.
- A high training loss alone suggests underfitting, but validation is still needed.
- Overfitting is about the gap between train and validation performance.
- Early stopping uses validation performance, not training loss alone.
- For loss curves, lower is better; for accuracy curves, higher is better.
- Sigmoid and tanh gradients go to zero in saturated regions, causing vanishing gradients.
- ReLU keeps gradient 1 for positive inputs but can die on negative inputs.

