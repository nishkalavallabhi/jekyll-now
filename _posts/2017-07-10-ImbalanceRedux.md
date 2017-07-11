---
layout: post
title: Reading Notes - Class Imbalance, Redux
categories: Readings, ML 
---
This post is a summary of the following paper

Wallace, B. C., Small, K., Brodley, C. E., & Trikalinos, T. A. (2011). 

Class imbalance, redux. 

In IEEE 11th International Conference on Data Mining (pp. 754-763). IEEE.

[Read online here](https://pdfs.semanticscholar.org/a8ef/5a810099178b70d1490a4e6fc4426b642cde.pdf)

In accordance with my recent interest (and need!) for a practical and theoretical understanding of ways to handle class imbalance problem, I ended up reading this paper today. I found this via a twitter discussion on Yoav Goldberg's feed.

Paper summary: This paper provides a theoretical understanding of class imbalance, and corroborates the theory by experiments with simulated and real datasets. 

**Main theoretical propositions:**

* *weighted  empirical cost  minimizing  learners* i.e., cost-sensitive learning and other such methods do not have any effect in some settings. 
  - > "In particular, if the instances comprising
the classes in the training dataset are separable, modifying
the cost of false negatives relative to that of false positives in
the objective function will not reduce bias. "

  - > "As the degree of imbalance increases (i.e., π decreases), the
probability that using weighted empirical cost minimization
to counter imbalance will be effective in reducing bias
decreases."

  - >  "as the size of the training set increases, such strategies will become more
effective, in general."

* *SMOTE* (which does synthetic over-sampling) performs similarly to weighted methods.

* Solution is *combination of Bootstrapped undersampling and bagging ensembles*

**Main experimental results:**

* > "To summarize our results over synthetic datasets, we have
shown that: 1) bagging/undersampling consistently outper-
formed other strategies in terms of predictive performance
on synthetically generated imbalanced data (bagging doing
so with lower variance than undersamping alone), and 2)
as expected per our discussion in Section II, undersam-
pling/bagging was particularly effective, relative to SMOTE
and weighted-SVM, in cases when the training dataset was
not separable"

* > "both SMOTE and weighted-SVM perform better (worse), w.r.t.
the undersampled bagging approach, as the prevalence (π)
and the training set size (D) increase (decrease). The reverse
holds for dimensionality and sparsity: as these decrease,
the effectiveness of the empirical weighted cost methods
decreases, too (relative to bagging)"

* > "In the low-dimensional case, the empirical cost weighting
strategies (SMOTE, weighted) are competetive with under-
sampling and bagging. In higher-dimensions, however, these
strategies regress to the baseline."

**My Thoughts:**
The results are very useful, but kind of contrary to what the previous paper I wrote about ([Weiss et.al., 2007](https://nishkalavallabhi.github.io/CostSensitiveLearningVsSampling/)) wrote about. They did not use bagging with undersampling though. 
For now, in terms of practical advice, the best advice is to try both sampling and cost-sensitve learning and pick the one that works best
for the dataset (very obvious, I know!) 

Overall,  I find it very surprising that there is so little analysis on such a common problem (class imbalance). Also, I am disappointed to see some qualitative analysis in both these class imbalance papers I read fully in the past few days. There is an experiments section, there are some "real world" (which is UCI repo for most cases) dataset being used, but that is hardly the representation of diverse classification problems in real world. Perhaps, a better way is to pick more of real life datasets than synthetic data or standard UCI benchmark datasets. 

Btw, just yesterday, I had reasonable success with doing weight balanced classification in a unbalanced 4-class dataset where majority class had over 700 examples, minority class had less than 50 examples, and it is a triage problem where the minority class is the most important one to get right! I did not understand why? though.

In my search after reading this, I came across [Tom Fawcett's tutorial on learning from imbalanced classes](https://svds.com/learning-imbalanced-classes/). This is a great piece!! Definitely worth a revisit, and a re-read. I will blog in detail soon.



