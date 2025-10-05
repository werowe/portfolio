# First Program:  Manual Gradient Descent

[This notebook](https://github.com/werowe/portfolio/blob/main/tensorflow_tape_gradient_descent.ipynb) demonstrates how to convert a manual, numpy-based gradient descent for logistic regression to use TensorFlow's `GradientTape`. Here’s how the TensorFlow version works:

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

# Second Program:  Generate Sample JSON Customer Data

[This notebook](https://github.com/werowe/portfolio/blob/main/generateCustomersJSON.ipynb) generates synthetic customer and sales order records, serializes them as JSON, and writes them to two output files. Here is how it works, step-by-step:

---

### 1. Imports and Utility Functions

- Imports modules for working with dates, UUIDs, random numbers, and JSON.
- Defines helper functions:
  - `getToday()`: Returns the current date as an ISO string.
  - `randomString(length)`: Generates a random lowercase ASCII string.
  - `commaCheck(field)`: Converts numeric fields to strings. Returns field as-is otherwise.

---

### 2. Entity Classes

#### Customer
- Represents a customer with fields including customernumber (UUID as string), name, phone, postal code, locale, date created, and email.
- Methods include `getColumns()`, `getValues()`, and `getSalesOrders()`.
- Initializes `salesOrders` as an empty list, but does not automatically create orders upon instantiation.

#### SalesOrder
- Represents a sales order with fields for customer, order, comments, dates, type, discount, quantity, and product UUID.
- Methods include `getColumns()` and `getValues()`.
- Each order links to a customer via the `customernumber` field.

---

### 3. JSON Generation

- `generateJSON(record)`: Constructs a dictionary from column names and values, prints it, and returns the dict.

---

### 4. Data Generation and Output

- `generateCustomers(c, o)`: For each of two customers:
  - Instantiates a `Customer`, prints and writes customer info as JSON to the output file.
  - Calls `generateOrders(customer, o)` to create a random 1–4 orders for that customer.
- `generateOrders(customer, o)`: For each order (random number per customer):
  - Creates a new `SalesOrder`, prints columns and values for the order.
  - Produces its JSON, writes to the orders output file.
  - Adds each order dictionary to the customer's `salesOrders` list for reference.

---

### 5. Main Execution

- Main function opens two output files (`customers.json`, `orders.json`), generates customer and order records, and writes them as JSON.
- Prints sample columns, values, and resulting JSONs for inspection.

---

### Example Output

- Sample data is printed for each customer and each order, along with the lists and dictionaries.
- The `customers.json` and `orders.json` files end up containing serialized representations of every generated customer and associated orders.

---

### Summary

- **Purpose:** Populates sample structured datasets for customers and their sales orders in JSON format.
- **Workflow:** Randomly generates fields, serializes into JSON, and writes output files suitable for batch import, testing, or data science prototyping.
- **Flexibility:** Can easily increase the number of records, alter schemas, or adapt to different file formats or storage backends.

