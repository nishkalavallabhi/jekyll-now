---
layout: post
title: Notes on Kaggle competitions
categories: Data Science
---
I participated in my first Kaggle competition in this month ([Sberbank Russian Housing Market](https://www.kaggle.com/c/sberbank-russian-housing-market)) along with [@embedsri](https://github.com/embedsri), and this post is a reflection on that.

The competition: The problem described in this competition is a typical regression problem, one that is often used as classroom example - housing price prediction. However, the data is much larger than a typical classroom example and comes from real life. There are close to 300 attributes in the dataset provided by Sberbank and about 30K training instances. The test file had about 7.5K instances (for exact numbers, check the competition website). About 3500 teams participated, and there was a public leaderboard that showed the performance of the teams' models on 35% of the test data. The final results were based on the other 65% and we had no clue on how the 35% was sampled from full test set. 

What I learnt:

* I haven't thought about housing price prediction before. I always kind of accepted it as a standard regression problem, with some typical kind of attributes (e.g., house size, num. rooms etc, and some information about neighborhood etc). However, I started thinking more about why such a modeling may be pointless as it cannot account for unprecedented social, political and economic factors that can control the housing market. I have read about why predicting future from past in such kinds of data is not a good idea in some cases, but never really actually experienced it myself until now :-)

* I used to work on applied machine learning in Java (and for a brief while in C-sharp), and additionally, accessing either terminal based interfaces (e.g., SVMRank, RankLib etc) or GUI based interfaces (WEKA, LightSide). This has been the case for almost a decade now. I started seeing Python as a more suitable language for data science projects early last year, when I taught a Python 101 course, and its follow-up course using Python-NLTK at ISU. I later started learning to work with Tensor Flow earlier this year and an RA I worked with was using sklearn. I realized I need to be more comfortable with NumPy and sklearn moving forward. This competition finally made me do that and I got comfortable exploring multiple models and using sklearn. 

* The kernels, and the discussion board had a lot of insightful discussions and code sharing. I did not spend much time, but if I had a lot of time just to explore such things, that is where I would perhaps be. If someone turns to Kaggle to learn to explore data, this is the most useful part of the website, IMHO.

These three, for me, are the major gains from this participation. I think I will participate in some other Kaggle competition too in near future. For now, I see Kaggle as something that can make me do something beyond academia and research. I see it as some kind of "no expectations" hobby, which I hope will allow me to freely explore stuff, and not bother much if things do not work.

Now for the pointlessness part:

* I think the training and test data have very different characteristics. My model predictions always seemed considerably better on the test set than on my development set (which was carved out of training set from different time frames). This made it difficult to judge what approach that worked for my testing will work on the actual data. This difficulty was also evident on the final leaderboard postings, where some teams saw almost 900 ranks drop or rise between public and private leaderboards. 

* I started feeling the whole effort is pointless as most of what was posted on leaderboard could possibly be overfitting the public leaderboard data anyway. Further, the increased model complexity sometimes resulted in very minor improvement (evaluation scores differed even in the 5th digit after decimal and I had no idea how to quantify this in real life price terms) which is perhaps statistically insignificant. So, at some point, I began feeling that the whole effort is pointless beyond providing some hobby for hands that itch to do some data engineering and make them squeeze false confessions (overfitting) er...predictions from data. For all practical purposes, like it happened with the [Netflix competition](https://www.wired.com/2012/04/netflix-prize-costs/) years ago, Sberbank will perhaps not find any of these solutions useful. Actually, I am very curious to know what happens after these competitions within the organizations that sponsor them, how they use the insights from the competition etc. I don't know if they write about that somewhere.

Difference from reality:
* You are given data that is already collected and properly organized, which is not the case in real life. Perhaps the "organized" part is slightly different for other kind of datasets such as images or text, instead of numeric datasets like this though. You may end of doing a lot of pre-processing work in such cases. But, even over there, collection and categorization of the data is not your problem in Kaggle. So, Kaggle is most useful for you to learn to work with data in the final stage, assuming that all the previous stages (collection, pre-processing, feature extraction, creating a neat csv) are all done. 

***************
Our github project related to this competition is [here](https://github.com/nishkalavallabhi/Skerbank). It has the basic code, but does not have all the different feature tweaking and model parameter tuning (aka black magic) we kept doing regularly with the hopes that there may be some magical performance spike (in to the 3rd or 4th or 5th digit after decimal that is!). The tweaking was mostly done without version control.

Our final performance was at 1900s on private leaderboard, about 1500 on public one. The highest rank we got on public leaderboard was around 1315 or something, which we got in the first week. We spent about 10 min per day (may be an hour a week) for about 3 weeks. (add an hour or two more for initial setup, random discussions while walking or driving etc). So, all in all, less than 10 hours of total effort.
