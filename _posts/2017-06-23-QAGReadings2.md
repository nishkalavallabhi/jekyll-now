---
layout: post
title: Reading Notes - A Joint Model for Question Answering and Question Generation
categories: Readings, QG/QA/RC
---

This post is my quick summary of what I understood an article I read, by a team from Microsoft Maluuba.

A Joint Model for Question Answering and Question Generation

Tong Wang, Xingdi Yuan and Adam Trischler

It can be read on [ArXiv](https://arxiv.org/pdf/1706.01450.pdf)
(that article was originally published on 5th June 2017)

**General Summary about the paper**: 
In this paper, they describe a sequence to sequence learning framework that can learn to do question and answer generation. They show that this approach shows benefits for question answering task on a standard dataset. 

Here is one of their motivation for going the joint learning route:
> "We  hypothesize that question generation can help models achieve better QA performance. This is motivated partly by observations made in
psychology that devising questions while reading can increase  scores  on  comprehension  tests  (Singer  &  Donlan, 1982)."

**My Thoughts**: 
This paper is in a way similar to the one in my previous post - it also talks about learning to generate and answer questions together. However, the difference lies in the way they operationalize the "joint"ness of the two tasks. The previous paper had an approach where both QA and QG models at run time had a "dual" regularization term during training. In this, the approach is different. They describe a sequence to sequence generation model "conditioned" on a word sequence. In a QG system, the "condition" is the answer word sequence. in a QA model, the condition is the answer word sequence. 

I think this paper is well-written. The related work was too crisp, but had good references to ponder over later. The evaluation was a bit more extensive for QG than the previous one, and the results for QA were comparable to some existing results. One thing I liked about this paper is the way they discussed the results - it was not a ground breaking result. They seemed to be fine with publishing and discussing that, accepting readily that it is not state-of-the-art, and then adding a BUT saying why it is still interesting. The other thing I liked is: they even had a "implementation details" section where they mentioned about their experimental settings, tools used etc. This is something I seriously miss in several papers I read and I never understand why they do not think it is important, considering how much variation can exist in outputs just because someone uses a different pre-processing. I have been thinking about joint learning in the context of a different problem (information extraction). Hence, this article gave me something to think about for that project too. To me, NER is also a joint learning problem (learning to segment Named Entity Boundaries AND classify them). But, surprisingly, these papers don't seem to mention that as an example. 

My reading list on this topic increased, but perhaps once I clear what I wanted to read this week, I will first start with the following from these new additions:

*Singer,  Harry  and  Donlan,  Dan. **Active  comprehension: Problem-solving  schema  with  question  generation  for comprehension of complex short stories**.Reading Research Quarterly, pp. 166–186, 1982.*
