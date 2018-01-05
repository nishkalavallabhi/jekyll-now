---
layout: post
title: Reading Notes - Deep Learning: A Critical Appraisal 
categories: Readings
tags: [DeepLearning]
---

This are some notes I am making about the following article I came across on ArXiv.org:

> Deep Learning: A Critical Appraisal 
> Author: Gary Marcus
> [article url](https://arxiv.org/pdf/1801.00631.pdf)
> [author's webpage](http://www.psych.nyu.edu/gary/)

**So, what is the article about?**
In this article, the author reviews the progress made with deep learning in different areas such as speech recognition, image recognition, machine translation etc. and discusses 10 concerns he has about the current directions of research and development in deep learning.

**What are the main points?**
He starts with a question "Is deep learning approaching a wall?" and gives a rough outline of what deep learning is, what it does well, where it showed good results so far, and talks about the potential limits, where he lists the challenges with current approaches:

- *Deeplearning needs a lot of data*, whereas a human can learn with perhaps one or two examples in some cases, or by explicit definitions. Deep learning currently lacks a way to learn from such abstract definitions or representations without an accompaniment of millions of examples.

- *Deeplearning does not transfer much*, i.e., it does well with recognising "cats" does not mean it will automatically do well with recognising "dogs" without seeing millions of dog images. "Deep" part of deep learning is about architecture, and not about and not about conceptual learning. There are challenges in terms generalizing well beyond what is seen in the training examples despite all the developments.

- *Deep learning does not handle hierarchical structures*. Consider language as an example - If I say: "The teenager who previously crossed the atlantic set a record for flying around the world", "who previously..." is a relative clause embedded in the main clause. 

- *Deep language struggles with open-ended inference* i.e., drawing inferences that are not explicitly mentioned/specified (e.g., in a piece of text)

- *Deep learning is not sufficiently transparent* - being able to interpret the predictions is important in certain fields to adapt it.

- *Deep learning is not well-integrated with prior knowledge* - There is no straight forward way to integrate what is already known about the problem. General idea is that: machine figures everything out by itself, so this is not given much attention.

- *Deep learning cannot distinguish correlation and causation* - Causal inference is not possible.

- *Deep learning cannot handle constantly changing systems* such as politics, economics etc as it presumes a largely stable world
(I did not understand what he meant here)

- *Deep learning predictions are approximations, and cannot be fully trusted*. Here, there are a few examples of recent work on defaced stop signs mistakenly recognised as "speed limit" images (ouch!) etc. There is also a lot of recent work on *spoofability* of deep learning systems.

- *Robust engineering of deep learning systems is difficult* - quote from the paper: " As Google’s Peter Norvig (2016) has noted, machine learning as yet lacks the incrementality, transparency and debuggability of classical programming, trading off a kind of simplicity for deep challenges in achieving robustness.". There seems to be some interest in this direction in recent research.

After this general listing of challenges, the important conclusions are:
- There could be a potential fall in enthusiasm around AI and Deep learning in the coming few years, and some projects may be abandoned, or ideas may not get funding.
- There might be too much focus on "low hanging fruit" ideas, neglecting riskier ones that may actually lead to more important developments.

So, he suggests looking at four other things apart from current focus (i.e., supervised machine learning).
- Unsupervised Learning
- "integrate deep learning, which excels at perceptual classification, with symbolic systems, which excel at inference and abstraction." -this part reminded me of the last chapter of [Pedro Domingos' book](https://www.amazon.com/Master-Algorithm-Ultimate-Learning-Machine/dp/0465065708). 
- Look for more insights from cognitive and developmental psychology 

To push the research further, he proposes bolder challenge problems that would push system development: video comprehension, scientific reasoning, general game playing (not specific), Physical AI robot that can build IKEA shelves based on instructions etc. 

**My conclusions**:
I think this is a great piece. One of the several end-of-the-year pieces I enjoyed reading. Good thing about this is it comes from someone who has a background not primarily in engineering, but in the study of human brain. So, this gives a different perspective. Further, it is written in a way that most non-research folks can understand with some effort. I enjoyed reading it!
