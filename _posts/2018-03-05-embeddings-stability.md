---
layout: post
title: Reading Notes - Evaluating the stability of embedding based similarities
categories: Readings
tags: [Embeddings]
---

This post is a short summary of the following research paper

> Title: Evaluating the Stability of Embedding-based Word Similarities  
> Authors: Maria Antoniak, David Mimno  
> Year: 2018  
> Journal: Transactions of the Association for Computational Linguistics (TACL), Vol. 6
> [URL](https://www.transacl.org/ojs/index.php/tacl/article/view/1202)

Word embeddings have become very popular as one of the initial steps for various NLP tasks (parsing, language modeling, translation, classification etc) in the past 5 years. On the other hand, they are also used as a way of studying the language, how it is being used in some sample (say twitter), how language changes over time ([here](http://viveksck.github.io/langchangetrack/), [here](https://aclweb.org/anthology/P/P16/P16-1141.pdf), and [here](http://www.aclweb.org/anthology/W17-2624), for example)etc. While most of this comes from computer science researchers who work in NLP (even though the authors of this paper call it digital humanities), there are some researchers coming from a humanities background, who use embeddings as a tool to answer questions originating from their discipline (e.g., [this](https://dh2017.adho.org/abstracts/582/582.pdf) and the [associated website](http://ryanheuser.org/word-vectors/)). 

Most people who have ever trained such embeddings themselves would have perhaps noticed how sensitive the similar words and similarities are to minor parameter changes, and also to training data changes. So, how do we address this issue? How do we decide on the "stability" of embedding based similarities? This paper addresses that question. While there is some related work on tuning the hyper-parameters, and on how to harness large, generic corpora to use embeddings as features for other NLP tasks, this paper tackles small, specific corpora and studies the effect of corpus variation in embedding based similarities.

So, they built embeddings using 3 corpora sources (reddit posts, NYTimes, US Federal courts of appeals), which have different topics (history and science in reddit, sports and music in NYT) and produced in different locations (east vs west cost in the courts data - may be attitudes of courts are different - that can be tested). With these and different popular approaches for dense vector representations of text (LSA, skip-gram negative sampling, GloVe, PPMI (how they chose these is explained in the paper), they looked at how:
- order of the documents in the training corpus
- size of the data
- length of documents
affected the quality of embeddings. 

**Main conclusions:**
- "the presence of specific documents in the corpus can significantly affect the cosine similarities between embedding vectors"  
- longer documents result in greater variation in the cosine similarties between embeddings across runs of the experiments.
- however, variance stabilizes after 25 bootstrap runs  
So, here is the final recommendation:
> "If the intention of a study is to learn about a specific corpus, we recommend that practitioners test the statistical confidence of similarities based on word embeddings by training on multiple bootstrap samples."

Overall, I found it to be well-written, and thoroughly analysed paper. I haven't been reading much in terms of research articles these days, partly because of busy work days and partly because of boredom of seeing some neural network tweak followed by some potentially statistically insignificant improvement, without any insights about neither the problem at question nor the network architecture. This paper was a breathe of fresh air, and I feel like reading again!


