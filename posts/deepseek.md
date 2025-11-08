---
title: DeepSeek AI Model
layout: portfolio
---

# China Rocks AI Marketplace with DeepSeek AI Model. NVIDIA Stock Price Tumbles

Today's newspapers and news programs are filled with news that China has created a Sputnik moment with the release of its ChatGPT competitor, DeepSeek.

As an AI developer, educator, and writer, I am here to quickly explain what this means.

First, no, China has not created anything truly new. Not even OpenAI has genuinely created something unprecedented. All of OpenAI, Google, Facebook, etc. are using the same basic technology, most of it developed by Geoffrey Hinton and others. The only differences between vendors are small changes at the edges. The training algorithms themselves remain the same.

All that DeepSeek has done is find a way to train its model faster. This has rocked the stock market because it challenges the idea that you need to invest billions of dollars in NVIDIA GPUs to train LLMs (large language models).

So, what does "train" mean?

In just two paragraphs, I can explain what this means. Look at the graphic below of the activation function by the artist Vizuara. It does a great job of laying out in one picture how model training works.

The idea is rather simple.

Recall from high school some basic algebra: $y = mx + b$ is the equation for a line. This is also the basic equation for a neural network. ChatGPT and the rest are all neural networks.

In high school, $m$ and $b$ are numbers. For AI, these are arrays of numbers. $x$ is the input. For LLMs, $x$ is the entirety of the data they have absorbed, which for ChatGPT is the entire internet plus offline material as well. 

The difficulty is that these arrays, and their operations, grow exponentially. Such explosive growth in data requires an immense array of computers and memory cards (NVIDIA GPUs), because everything must be held in memory at the same time while the computer churns through linear algebra on arrays of unfathomable size.

When you say that ChatGPT and other large language models are trained, that means they have finished calculating the values of $m$ (weights) and $b$ (bias).

They do this literally by guessing. First, you take a guess. Then you calculate the error—that is, how far off your guess was. Then you adjust the weights and bias and check again.

You repeat this until you find the point where this model $f(x)$ reaches its minimum error. The error means the difference between the guess $f(x)$ and the actual observed value, say $f^*(x)$.

What is not yet known—but will be revealed in the coming days—is how DeepSeek was able to achieve a performance boost of several orders of magnitude. The source code is free and online [right here](https://github.com/deepseek-ai/DeepSeek-V3). All over the world, thousands of developers are downloading it right now to figure that out.
