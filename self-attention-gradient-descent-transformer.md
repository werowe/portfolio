---

# Do You Understand Self-Attention, Gradient Descent, the Transformer Architecture?

What is the most interesting way to study AI? What are the most important concepts to master?

It seems most AI/ML programmers and engineers are only interested in learning LLM APIs and plug-and-play tools (LangChain, OpenAI API, etc.) because that is what practitioners use. It's what hiring managers want you to know.

But that's not the fun part, if you like math and algorithms. And it does not enhance your understanding of how AI works.

I agree with Andrew Ng that it's important to learn how to calculate AI algorithms by hand. This is his approach in the Deep Learning Specialization course at Coursera, and probably other courses taught by his organization, [DeepLearning.ai](http://deeplearning.ai/).

In other words, don't just learn how to use TensorFlow—learn the algorithms that TensorFlow is using.

So, I spend my time studying Andrew Ng's videos and reading academic papers by Geoffrey Hinton et al. I ask ChatGPT for help too, of course, as I try to understand every concept and code every algorithm myself.

I've taken apart code examples and broken them down into their component parts. Some of my work is shown below.

I take Andrew Ng's diagrams, load them into Perplexity, and then ask it to explain each item in the image. (Often this is necessary as some of his lectures, like on the Transformer Architecture, move so quickly that you need a way to slow them down and elaborate. Plus, he writes his formulas with a stylus, so you need to convert them to MathJax and markdown to make them easier to read than his handwriting.)

Anyway, I believe these are the key ideas one should try to master:

1. **Gradient descent:** This requires knowing linear algebra and partial derivatives.

2. **Word embeddings:** This is a fascinating topic where you see how you can extract words encoded along multiple dimensions by looking at a single dimension to figure out which are near each other.

3. **The attention mechanism and self-attention:** This is the real game changer that enabled ChatGPT to work (plus all that came before it). It's a clever way to determine what parts of a text are important when doing generative AI.

4. **RNNs:** This is key for reading and generating sequences. It's a neural network with the time element added along one dimension, suitable for time series and text translation. It's also the precursor to generative AI.

5. **ConvNets:** ConvNets let you pick out portions of an image to do things like facial recognition. It's also the neural network architecture used in Transformer Networks.
