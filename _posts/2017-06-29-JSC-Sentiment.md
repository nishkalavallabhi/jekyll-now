---
layout: post
title: Reading Notes - A Joint Segmentation and Classification Framework for Sentiment Analysis
categories: Readings
tags: [JointLearning]
---

This is a reading summary of the following paper:

title: A Joint Segmentation and Classification Framework for Sentiment Analysis

authors: Duyu Tang, Furu Wei, Bing Qin, Li Dong, Ting Liu, Ming Zhou

where: Proceedings of the 2014 Conference on Empirical Methods in Natural Language Processing (EMNLP)

pages: 477--487

url: http://aclweb.org/anthology/D/D14/D14-1054.pdf

summary: This paper proposes a method to jointly learn sentence segmentation and sentiment classification. They argue that this kind of joint learning, instead of directly using words as basic units of feature engineering or using chunkers to consider noun phrases or verb phrases or such specific syntactic units, it is better to "learn" to segment words in sentences such that sentiment relevant constructs (e.g., "not bad", "not so well written", "too good") will be grouped together. They use sentiment information in the training data to do the segmentation, and use the segmented units as features to do sentiment classification (hence they called it the Joint Segmentation Classification framework aka JSC).

They argue that in a regular n-gram based approach, if there is a sentence: "That is not bad", "bad" and "not bad" can both be considered as features which can confuse the model. One may argue that syntactic chunking can be used to capture such groups of words (phrases). However, the authors then say:

> "The segmentations based on syntac-
tic chunkers typically aim to identify noun group-
s, verb groups or named entities from a sentence.
However,  many  sentiment  indicators  are  phrases
constituted of adjectives, negations, adverbs or id-
ioms (Liu, 2012; Mohammad et al., 2013a), which
are splitted by syntactic chunkers. "

So, that is what they do. Instead of considering all n-grams as features, they learn to segment the text into useful n-gram chunks such that they can do specific feature engineering even within that n-gram space. I think this is a useful idea. Over the past few days, I have been thinking about a related issue - I want to reduce the dimensionality of an n-gram style feature extraction, but at the same time, capture stylistic variations which embedding based representations do not seem to capture (in my experience). I was considering a range of word/POS combination n-grams, skip grams etc, and was wondering if one should just extract phrases instead. This segmentation based feature engineering seems to be a nice idea to explore. 

There seems to be another article by the same set of authors on the same topic. I did not read it though:

A Joint Segmentation and Classification Framework for Sentence Level Sentiment Classification 

Duyu Tang, Bing Qin, Furu Wei, Li Dong, Ting Liu, Ming Zhou

IEEE/ACM Transactions on Audio, Speech, and Language Processing. Issue 23 (11). 

http://ieeexplore.ieee.org/document/7138591/?reload=true
