# PyTensor Workshop #1 | A Deep Dive into Computational Graphs
Youtube Video Link: https://www.youtube.com/watch?v=C1JJ33z9g00

Youtube Video Desc
-------------------
366 views  Sep 2, 2025 
In this workshop, we explore PyTensor – the computational graph library that powers PyMC! 🧠

We'll start from the basics: symbolic variables, operators, and directed acyclic graphs (DAGs). You'll see how PyTensor differs from NumPy and why its symbolic approach is so powerful.

✨ What you'll learn:
Graph Replacements - make precise edits to your computational graphs
Graph Rewrites - automatic optimizations for speed & stability
Graph Transformations - reshape graphs, with autodiff as the star example

To bring it all together, we'll build a logistic regression model from scratch using gradient descent and compile it into an efficient function that can run on backends like C, JAX, or Numba.

In the second half, Ricardo rewrites the core of PyTensor in plain Python - a "Lego-style" version that shows exactly how Variables, Ops, and Applies fit together.

Whether you're a PyMC user, curious about symbolic computation, or just looking to sharpen your skills, this workshop will help you understand and use PyTensor with confidence.

📌 Helpful Links:
📖 Docs: https://pytensor.readthedocs.io/en/la...
💻 GitHub Repo: https://github.com/pymc-devs/pytensor/
🌐 Website: https://pymc-labs.com/

00:00:00 What on Earth is PyTensor?
00:00:44 The Core Idea: Computational Graphs
00:03:09 Symbolic vs. Numerical: Why PyTensor Isn't NumPy
00:04:23 Peeking Inside: Debugging Your Graph with drint()
00:05:58 Making it Pretty: Visualizing Graphs
00:07:11 The Building Blocks: Variables, Applies & Ops
00:11:46 The Real Superpower: Graph Manipulation
00:13:20 Technique 1: Replacing Parts of Your Graph
00:19:39 Power Move: Automatic Vectorization
00:22:25 Technique 2: Automatic Optimizations with Rewrites
00:24:03 Example: The Numerical Stability Rewrite
00:25:11 Technique 3: Graph Transformations & Autodiff
00:26:29 Combining Powers: Simplifying Gradients
00:30:18 From Symbols to Speed: Compiling Your Graph
00:33:37 Full Example: Logistic Regression from Scratch
00:38:16 Why PyMC Really Uses PyTensor
00:44:13 Part 2: Let's Rebuild PyTensor From Scratch!
00:46:27 The "Lego" Bricks: Types, Ops, and Nodes
00:58:06 Bringing it to Life: The 'perform' Method
01:02:20 Adding Constants to Our Library
01:11:11 Our First Rewrite: x + x becomes 2 * x
01:15:06 How Rewrites Actually Work
01:21:30 Hands-On Exercises & Next Steps



# PyTensor Workshop#2 | Advanced Graph Transformations & Normalizing Flows
Youtube video link: https://www.youtube.com/watch?v=jorKDY9kZ6c

Youtube video desc
------------------
100 views  Sep 16, 2025 
In this session, we go deeper into PyTensor to explore one of its most powerful features: Graph Transformations. 🚀

First up, Ricardo breaks down how advanced operations like automatic differentiation actually work. You'll see the difference between:
Eager transformations - when you explicitly ask for a new graph (like a gradient).
Lazy transformations - when PyTensor optimizes things behind the scenes, like realizing you only need one row of a big matrix instead of the entire thing.

We'll even peek under the hood and watch step-by-step as PyTensor's rewrite engine takes a messy graph and simplifies it into something elegant and efficient.

Then, Jesse takes us into a modern ML application: Normalizing Flows.
Together, we'll build a model that learns to transform a simple bell curve into a complex, multi-modal distribution. You'll see how PyMC's logp function automatically handles the tricky math (change of variables formula), and how you can even build PyTorch-style neural networks inside PyTensor for flexible and powerful modeling.

This session is perfect if you want to move beyond the basics and see how the theory of computational graphs connects to real-world machine learning. After this, you'll not only understand what PyTensor is doing - you'll know how to make it work for you.

📌 Helpful Links:
📖 Docs: https://pytensor.readthedocs.io/en/la...
💻 GitHub Repo: https://github.com/pymc-devs/pytensor/
🌐 Website: https://pymc-labs.com/

00:00:00 - Welcome to Session 2!
00:01:46 - Part 1: Deeper Dive into Graph Transformations
00:02:12 - Flavor 1: Eager Transformations (Gradients)
00:04:58 - How Autodiff is Implemented (The L_op Method)
00:12:53 - Under the Hood: Watching Rewrites Happen Step-by-Step
00:16:57 - Flavor 2: Lazy Transformations (Automatic Optimization)
00:18:06 - Example: Optimizing Subgraph Computations
00:20:23 - Why Lazy Transformations are So Powerful
00:28:04 - Part 2: Applied Example - Normalizing Flows
00:31:05 - The Core Idea: The Change of Variables Formula
00:36:09 - The PyMC "Magic": Automatic logp Transformation
00:39:09 - Using PyTensor to Optimize and Find Parameters
00:50:53 - Advanced Flows: Building Neural Networks with Coupling Layers
00:55:50 - Training the Flow & Key Takeaways
01:05:41 - Let's Get Hacking: Workshop Exercises
01:12:19 - Live Workshop: SciPy Optimization Exercise
