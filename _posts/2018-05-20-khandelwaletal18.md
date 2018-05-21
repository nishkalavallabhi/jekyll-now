---
layout: post
title: Reading on how neural language models use context
categories: Talks
---

This post is my comments/notes about the following paper:

*Title: Sharp Nearby, Fuzzy Far Away: How Neural Language Models Use Context  
Authors: Urvashi Khandelwal, He He, Peng Qi, Dan Jurafsky  
[ArXiv Link](https://arxiv.org/pdf/1805.04623.pdf)*

Over the past few years, neural language models (NLMs) were shown to outperform traditional ngram language models for various tasks. The reason for this is discussed as the ability of the neural models to model longer range contexts for words. However, how is this done is not explained. This paper addresses that issue.

Using a range of empirical experiments which involve manipulating prior context words while predicting the current word in NLMs trained using two popular language modeling datasets, their main conclusions show that:
- NLMs consider a context history of about 200 words, and this is not affected by changes in hyper-parameters.
- Infrequent words need more context than frequent words, and content words need more context than function words.
- Word-order is important in near-range context, but not in far-range context (beyond 50 words).

The paper is generally clearly written, and I really liked the main theme of the paper. However, what surprised me is the following: the experiments were conducted with 2 English datasets. The conclusions no where mention anything about a possibility of these conclusions being similar or different for a different language. Okay, there are several languages in the world, it is not possible to work with all of them. But, considering that there are a couple of non-English languages for which we can train NLMs, it would have been nice if 
- atleast one more language was included in the experiments or
- working with more languages was mentioned as a future direction, but I felt it was written as a secondary issue ("An interesting extension to further study this
separation would lie in experimenting with differeent model classes and even different languages") whereas, for a NLP community, that should be of primary interest (IMHO). 

This made me wonder about how much do NLM research literature mention about the differences between different languages. For example, word n-gram models typically did not do well for morphologically rich languages, and other approaches were proposed (e.g., factored language models). Are there any studies on NLMs performance across languages? Do NLMs learn different aspects for different languages? I have to find out answers to these questions. 

One other question that I wondered was: how many of these conclusions still generally hold, if character models were considered instead of words? 

Overall, this is a good read, which gave raise to a lot of questions that need further exploration. 
