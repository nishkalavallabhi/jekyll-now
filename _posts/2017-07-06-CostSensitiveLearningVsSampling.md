---
layout: post
title: Reading Notes - Cost-Sensitive Learning vs. Sampling
categories: Readings, ML
---

This is a quick summary of this short paper:

> Weiss, G. M., McCarthy, K., & Zabar, B. (2007). Cost-sensitive learning vs. sampling: Which is best for handling unbalanced classes with unequal error costs?. DMIN, 7, 35-41.
[Read here](http://storm.cis.fordham.edu/~gweiss/papers/dmin07-weiss.pdf)

When you work with a classification problem in machine learning, it is common to see classifiers learn a skewed distribution towards the class with a majority representation if the class distribution is unbalanced. This is because the classifiers typically learn to optimise for accuracy. However, in several cases, the misclassification of those less frequent classes in the training data may be a more serious issue than the misclassification of the majority class i.e., not all misclassification are equally severe. 

In order for the classifier to not "not learn" minority class characteristics, typically, two procedures are followed:

* Cost-sensitive classification (telling the classifier to optimise for the costs instead of accuracy)
* Over-sampling the minority class, thereby bringing up a balanced class distribution artificially or 
* Under-sampling the majority class)

This short paper compares these approaches in an empirical evaluation using 14 datasets to study which of these three is actually useful for such scenarios. The datasets varied in size. "Small" in their datasets was 100-200 instances. Large was 5000+. There was one dataset with with around 1500 instances. Number of classes per dataset was not given (perhaps it is assumed to be 2?). Percentage of minority class was given. 

Overall, their main conclusion is this:

* For smaller datasets, sampling methods (especially oversampling) performed better.
* For larger datasets, cost-sensitive evaluation performed better.

My thoughts: I am trying to participate in this [CLPsych shared task](http://clpsych.org/shared-task-2017/) where the idea is to classify posts in a mental health forum based on degrees of severity. The class distribution in the training data is highly imbalanced, with what is perhaps the "important" class to get right being the minority class among the 4 classes (majority to minority ratio is some 35:1!). It is a moderately sized dataset, and I have been largely leaning towards oversampling (using [SMOTE](https://www.cs.cmu.edu/afs/cs/project/jair/pub/volume16/chawla02a-html/chawla2002.html)). However, I found over-sampling to be overfitting the training data and I suspect it still prefers majority class when used with the test set (I don't know the final predictions for test set yet). I came across [some research from 2013](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-14-106) that also concludes SMOTE overfits on high dimensional data (high dimensions for them is 1000 features - with text based features, you can easily go into several 1000s and more). However, I have no idea about the notion of "cost" for this particular problem. Further, I don't understand yet how to come up with a cost function for multi-class (as against binary) problems. So, looks like am stuck in that darkness for timebeing! 

While I am in these thoughts, [Data Science Weekly](https://www.datascienceweekly.org)'s newsletter today had this article on [handling imbalanced classes](https://elitedatascience.com/imbalanced-classes), with some examples. While this is not useful in the sense of getting a better theoretical picture, I think it still serves as a good summary of what one can do. 

