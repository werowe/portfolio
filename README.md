# First Program:  Manual Gradient Descent

This notebook demonstrates how to convert a manual, numpy-based gradient descent for logistic regression to use TensorFlow's `GradientTape`. Here’s how the TensorFlow version works:

---

### 1. Setup

- Imports TensorFlow and initializes feature vector `x`, target label `y`, weight vector `w` (random initialization), and bias `b`.
- All variables use TensorFlow types (`tf.constant`, `tf.Variable`) for auto-differentiation.

---

### 2. Training Loop with GradientTape

- Sets a learning rate (`lr = 0.1`) and number of epochs (`num_epochs = 100`).
- For each epoch:
  - Uses `tf.GradientTape` to record operations for automatic differentiation.
  - Computes linear output `z = w · x + b`.
  - Applies the sigmoid activation for prediction.
  - Calculates the loss using TensorFlow's built-in sigmoid cross-entropy function.
  - Uses `tape.gradient` to get gradients w.r.t weights and bias.
  - Updates weights and bias using gradient descent.
  - Loss is printed every 10 iterations.

---

### 3. Model Results

- After training, prints final weights and bias.
- Computes the test prediction (forward pass) using trained parameters.
- Prints both the predicted value and the actual label for evaluation.

---

### Summary

- **Purpose:** Show basic logistic regression training using TensorFlow and auto-differentiation rather than manual derivatives.
- **Features:** 
  - Replaces numpy math and hand-coded backpropagation with TensorFlow's computational graph and automatic gradient computation.
  - Uses `GradientTape` for recording and computing gradients.
  - Training loop updates variables in-place and prints progress.
- **Predictions:** Demonstrates accurate prediction using trained weights.
- **Use Case:** Template for implementing custom differentiable models or training loops in TensorFlow.

You can extend this approach for more features, larger datasets, mini-batch training, or deeper models—all benefitting from TensorFlow's gradient mechanics and optimization tools.
