---
title: Understanding Cosine Similarity
layout: portfolio
---

# Learn Stochastic Gradient Descent

It's safe to say that many ML programmers focus on learning PyTorch and similar tools without spending much time mastering the algorithms and math that make neural networks work. I believe it's important to understand the math as well.

In my computer school (which is free and has 95% Ukrainian students), I teach students how to do logistic and linear regression and neural networks. We start with spreadsheets before writing code in Python. The reason is to teach the math and the algorithm.

It's difficult to find the solution for a neural network when you have more than one independent variable, because in that case, you have to work with partial derivatives (that is, the gradient). To teach the concept, we use just one independent variable.

Then it's not hard to find the least mean squared error (MSE) by hand.

To do this, we use one independent variable, $x$, and set the y-intercept to 0. The array we have is something like $X = [x_1, x_2, ..., x_n]$.

By setting the intercept to 0, we make the problem simpler since we only have to find one number and not two. Of course, to find the y-intercept (also known as the bias), you could repeat the procedure described below twice, since it's just a matter of going up or down until you reach the optimal solution.

So, we search for the coefficient $m$ in the $y = mX + b$ model. The simplified model becomes $y = mX$. The linear algebra is easy, as this is just a scalar times a vector. You can do this with a spreadsheet.

Then we take our first guess as to what the coefficient $m$ might be. Call it $m_1$.

Next, we calculate the predicted values as $\hat{y} = m_1 X$, and then we calculate the MSE, which is the square root of the sum of $(\hat{y} - y)^2$.

We then apply the learning rate (lr) to the coefficient, that is, $m_1 + lr$, and try again.

If the error is positive, we go in the negative direction by subtracting $lr$ from $m_1$. If it's negative, we go in the positive direction by adding $lr$ to $m_1$. Keep going back and forth until the error is zero (actually, close to zero, as computers cannot handle real numbers—they are approximated using the floating point number system).

We repeat this process until we reach the minimum error. At this point, our model is said to have converged, meaning we have found a solution.

Here is a [Colab notebook](https://github.com/werowe/HypatiaAcademy/blob/master/class/calculate_linear_regression_manually.ipynb) where I illustrate this idea.
