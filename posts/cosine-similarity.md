---
title: Understanding Cosine Similarity
layout: portfolio
---

# Understanding Cosine Similarity

A vector database stores embeddings—vectors that represent words or texts—so it can find items with similar meanings. An embedding is just a list of numbers—for example, dog → 0.3, 0.01, 0.06, …—learned from lots of text so that words used in similar contexts end up near each other in the vector space.

Two classic examples are "king is to queen as man is to woman" (gender) and "Prague is to Berlin as Washington is to Paris" (capitals). These illustrate how these vectors can capture relationships. The model knows nothing about gender or capitals. It's basically a mathematical trick to extract meaning from numbers. Remember that a generative LLM model is just a predictive model that outputs one sequence of numbers given another sequence of numbers. Those numbers are then converted back to text when shown to the user.

To measure how close two embeddings are, we use cosine similarity:

$$\text{cos similarity} = \frac{a \cdot b}{\|a\| \|b\|}$$

where $$\cdot$$ is the dot product of vectors $a$ and $b$, and $\|a\|$ is the vector’s length (norm). This formula gives the angle between two vectors, ranging from $-1$ to $1$.

Values near $1$ indicate very similar meanings, values around $0$ indicate they are unrelated, and values near $-1$ indicate they are not at all related. For example, "chicken" might be at $[-3,-3]$ and "rock" at $[3,3]$, so that their vectors point in opposite directions. Except in actual practice, embeddings like "dog" and "chicken" will have much higher dimensions (like 100), and the coordinates are scaled between $0$ and $1$.

To understand this, consider the vectors ending at points $[0,1]$ and $[1,0]$. These are, of course, the y and x axes in the Cartesian plane. You can see that multiplying these two vectors, $[0,1]$ and $[1,0]$: $1 \times 0 + 0 \times 1 = 0$, gives $0$ in the numerator so that 
$0 / (\|[0,1]\| \|[1,0]\|)$ 
is $0$. (And there's a $90^\circ$ angle between the vectors.)

Two vectors in the opposite direction, $[-3,-3]$ and $[3,3]$, have cosine similarity $-1$, meaning "dissimilar." The calculation of this angle $\theta_2$ is shown in the image.

![](https://github.com/werowe/portfolio/blob/main/images/cosine-similarity.jpeg)

