---
layout: post
title: Reading Notes - Baselines and Bigrams
categories: Readings
tags: [NLP]
---
Today, I came across a tweet by François Chollet:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">The ML research community has long been driven by the need to publish, which results in a stark, sometimes ridiculous bias towards complexity. Remember to ask: &quot;can we do this with k-means and logistic regression?&quot;</p>&mdash; François Chollet (@fchollet) <a href="https://twitter.com/fchollet/status/948970872802443264?ref_src=twsrc%5Etfw">January 4, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

I often wondered about the same question, and also tried to submit writeups with such simpler methods that work - but usually the reaction was "this is too simple". In conferences I attended, when someone from the audience raised a similar question, some speakers felt offended. One or two such people I know even privately commented - "why will I use Naive Bayes when state of the art is using Deep Learning?". As I followed this twitter thread, I came across the following reference: 

> Baselines and Bigrams: Simple, Good Sentiment and Topic Classification
> Sida Wang and Christopher D. Manning
> ACL 2012 short papers
> https://www.aclweb.org/anthology/P12-2018

Here is a quick summary of this paper:
- The primary goal of this paper is to study model selection issues between different variants of Naive Bayes (NB) and Support Vector Machines (SVM) for sentiment and topic classification problems in NLP. They take a look at datasets with short snippets as well as longer texts, and consider word bigrams as the means of deriving feature vectors
- They show that for short snippets, Multinomial NB does better than SVM and for longer texts, SVM does better than NB using 9 datasets (4 short texts, 5 long texts) with 2 classification tasks (6 sentiment classification tasks, 3 topic classification tasks). 
- Bigrams are better than bag-of-words in most of the cases (wonder why they did not consider further n-grams. What is the main point?)
- NBSVM, an SVM with NB log-count ratios as features, consistently performs well in all their experiments. So, they recommend this as a strong baseline. 

I think it would be interesting to see more papers on such empirical evaluation of word/document/character embeddings and neural network architectures for different NLP tasks. I did not read a lot of them, but one paper I remembered as I write this is [Lau & Baldwin (2016)](http://www.aclweb.org/anthology/W16-1609). Also, seriously, someone has to write on what those 0.0001 (percent/points/whichever) differences in accuracies, UAS/LAS, BLEU, ROUGE (whichever metric) mean in terms of real implications, or even interms of what "progress" was made in that problem by adding 151 hidden layers, or some other complex engineering feat. No offense - genuine curiosity. 
