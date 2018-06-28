---
layout: post
title: Readings and Thoughts on deploying NLP/ML models
categories: Readings
tags: NLP
---

Over the past few weeks, I spent quite a bit of time reading and thinking about the difference between academic and industry R&D for NLP and Machine Learning systems.
This post is a quick summary of my thoughts, and readings. The disclaimer: this is from someone who switched very recently (2 months) from years in
academia, into industry. All views are my own, not my employer's.

A typical conference paper in NLP (in my view) is largely about engineering newer and newer models, resulting in incremental improvements in solving
various NLP problems (e.g., machine translation, information extraction, syntactic parsing etc) using standard datasets and evaluation procedures.
A typical scenario in industry R&D is largely about - what works in production? what approach scales up to production? how much does it
add to product functionality? what will a customer find useful? what amount of revenue increase will happen? etc. So, basically, a researcher in academia and a researcher in industry
have different goals.

Reading academic research papers is a good idea to draw inspiration, get some ideas about things to approach, but increasingly, I feel the results 
need to be taken with a grain of salt. The innumerable number of parameters to be set while tuning models, infrastructural differences, and many other factors make
exact reproducibility of results difficult to impossible. These are not my unique concerns. For example, WildML.com had a couple of posts on the same issue earlier this year (or was it last year?)
I cannot find the article I have in mind (was it not from this blog?), but here is one [which talks about these issues](http://www.wildml.com/2017/12/ai-and-deep-learning-in-2017-a-year-in-review/) -
search for "reproducibility" here. Elsewhere, similar concerns were expressed about how one parameter change can change the interpretation of results drastically.

- In [Reimers & Gurevych, 2017](http://aclweb.org/anthology/D17-1035), they write:  
* "We demonstrate for common sequence tagging tasks that the seed value for the random number generator can result in statistically
significant (p < 10−4) differences for state-of-the-art systems. For two recent systems for NER, we observe an absolute difference of one percentage point F1-score depending on the selected seed
value, making these systems perceived either as state-of-the-art or mediocre." *   
- In [Crane, 2018](https://www.transacl.org/ojs/index.php/tacl/article/view/1299/296) they write:  * "In this paper we present a number of controllable, yet unreported, effects
that can substantially change the effectiveness of a sample model, and thusly the reproducibility of those results. Through these
environmental effects we show that the commonly held belief that distribution of source code is all that is needed for reproducibility
is not enough. Source code without a reproducible environment does not mean anything at all. " *

So, my point is - research papers should be read to understand different approaches to solve a problem, but results need not be considered conclusive 
in many cases.

Back to real-world applications. A lot has been written about deploying NLP/ML (I use them interchangeably here, because there is very little 
NLP that does not involve machine learning nowadays) in production, and issues to consider in that.

[Citicariu et.al., 2013](http://www.aclweb.org/anthology/D13-1079)'s "Rule-based Information Extraction is Dead! Long Live 
Rule-based Information Extraction Systems!" became sort of my reading recommendation to all datascientists and engineers involved in NLP projects now.
It talks about how most of industry systems are either rule based or ML+Rule-based hybrids, compared to academic research which is largely
completely machine learning, little bit of Hybrid, and 1% of rule-based approaches (for information extraction tasks). It comments on how
"rule-based" systems are considered a "dead end" in academia (My perception from submitting and reviewing in the past 2 years has been that any 
non-neural approach is considered either old-fashioned, or pointless). This article highlights the need and significance of rules in
production systems, and calls for a research agenda that bridges academia-industry gap.

[Suganthan et.al., 2015](https://www.cs.helsinki.fi/u/jilu/paper/bigdataapplication01.pdf)'s "Why Big Data Industrial Systems Need Rules
and What We Can Do About It" from work done at Walmart Labs is also a case in this direction, which also highlights why rules make sense, and 
what can be done to support rule creation in AI systems.

Another article I liked, and which resonated with me is [Dahlmeier, 2017](http://www.aclweb.org/anthology/P17-2015)'s "On the Challenges of Translating NLP Research into Commercial
Products". This highlights the differences between academic and industry research interms of aspects such as - over emphasis on test scores with
benchmark datasets, lack of domain specific data in real world applications ([Prodigy](https://prodi.gy) is very useful for this, btw), academic vs industry timelines in terms of research/Proof of concept etc and finally
calls for a industry track in NLP conferences. This happened in NAACL 2018 this year - search for "industry track" in [NAACL program](http://naacl2018.org/program.html)

Dahlmeier's article, and a recent medium.com post I read on ["Minimum Viable (Data) Product"](https://medium.com/idealo-tech-blog/what-is-minimum-viable-data-product-49269e338d85),
both also discuss on how to approach a industry research problem, raising questions such as: Do we need NLP? Do we need ML? Can our problem
be solved with Rules? How should we build a simple model first and gradually increase complexity, comparing performance? etc. These are all very
useful stuff for industry practitioners, especially when there is a lot of hype about deep learning being a universal solution, even when there is
no data, or bad data, or when we need some interpretable insights etc. 

I will close this post with a link to an article on evaluation/testing of NLP/ML models in production. Google's [NIPS 2016 paper](https://ai.google/research/pubs/pub45742) "What’s your ML test score? A rubric for ML production systems" is a very useful article in this direction. 
This seems to be a very under-discussed topic - how do you do QA for ML systems? I will hopefully write more on this aspect in future, as I read more, and learn more from experiences at work.



