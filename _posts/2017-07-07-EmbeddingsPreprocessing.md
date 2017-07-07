---
layout: post
title: Reading Notes - Text Preprocessing in Neural Network Architectures
categories: Readings, Embeddings 
---
I came across this short paper today in the ArXiv digest. This post is a quick summary.

Title: *On the Role of Text Preprocessing in Neural Network Architectures: An Evaluation Study on Text Categorization and Sentiment Analysis*

Authors: Jose Camacho-Collados and Mohammad Taher Pilehvar

[Read online here](https://arxiv.org/pdf/1707.01780.pdf)

Word embeddings, and neural networks are being commonly used in various text processing tasks in the past 3-4 years (Read [Sebastian Ruder's article series]
(http://sebastianruder.com/word-embeddings-1/) to know more on embeddings). There is some discussion on how to do hyper-parameter tuning for embeddings, 
how to combine word level embedding representations to get document embeddings etc in literature. However, there is little analysis about
how pre-processing decisions can affect end results (e.g., in text classification) when using embedding representations. This article works 
on performing such an analysis.

They look at four pre-processing operations: tokenization, lowercasing, lemmatising and multi-word grouping, and how these affect a CNN's text
classification performance on 9 benchmark datasets (4 relate to topic classification, 5 are sentiment classification). 
Their main conclusions is as follows:

> "In general a simple tokenized corpus works equally or better than more complex
preprocessing techniques such as lemmatization or multiword grouping, except for a dataset corre-
sponding to a specialized domain, like health, in which sole tokenization performs poorly.  Addi-
tionally, word embeddings trained on multiword-grouped corpora perform surprisingly well when
applied to simple tokenized datasets."

I have been working on embedding representations with three different kinds of text datasets (one stylistic, one biomed literature, one forum postings) 
in the past few months and I have often thought on this issue of what is a better pre-processing? what is a better resource to train embeddings? etc.
Not as much about parameter tuning, as we have been relying on cross-validation to choose the best parameters. However, in my experience with using n-gram representations 
and any text classification in general, the performance of a learner is very sensitive to several pre-processing decisions and choice of tools (e.g., taggers, parsers etc).

So, I think this kind of empirical research into how such choices influence the eventual performance will perhaps make researchers in general think more
in the direction of whether their ultra-complex model is giving a marginally better performance because of engineering marvel or is there a simpler explanation such as
these simpler choices. I am very much looking forward to read more of this kind of work on analysing the models. 

One other recent work that I found useful in this context:

*An Empirical Evaluation of doc2vec with Practical Insights into Document Embedding Generation* by Lau and Baldwin.

[Read online here](http://www.aclweb.org/anthology/W16-1609)

