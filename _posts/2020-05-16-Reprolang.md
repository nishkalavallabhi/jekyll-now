---
layout: post
title: REPROLANG 2020 Language Proficiency Scoring Task -  A review 
categories: Notes
tags: [NLP, May2020Notes]
---

In 2018, [Taraka Rama](http://phylostar.github.io/) and I published a paper["Experiments with Universal CEFR Classification"](http://aclweb.org/anthology/W18-0515). At that time, we shared the paper's code, along with the result files we obtained during our experiments [on github](https://github.com/nishkalavallabhi/UniversalCEFRScoring/). When we learnt about REPROLANG 2020, aimed at "*Reproduction of Research Results in Science and Technology of Language*", we volunteered our paper, thinking this should be a easy job, as we shared everything and the dataset we used is public too (we shared processed version). When the time came for me to review the submissions of those who reproduced our paper, I learnt about how many possible roadblocks exist in replication and reproduction of NLP and ML work. 

If our paper, which explored a relatively simple idea, and which shared everything we can about the paper, still faced all these challenges, can we trust the results such as sota comparisons and number games, especially those of papers that don't share data or code at all? Even for those with released code - is it stable enough to replicate, reproduce, and expand? - these were some thoughts I had earlier, which got reinforced ever since I reviewed these reproduction papers. Considering that people don't write and publish with the goal of reproduction (we would expect that the general goal is *to know* something, or to establish *sota* on some task), I don't think the ideal scenario will come though. In this post, I am writing some notes on the papers related to our paper's replication from [REPROLANG 2020](http://wordpress.let.vupr.nl/lrec-reproduction/), which was supposed to have taken place at LREC 2020 a few days ago. 

Let me start with the shared task's description paper:  

**A Shared Task of a New, Collaborative Type to Foster Reproducibility: A First Exercise in the Area of Language Science and Technology with REPROLANG2020**  
António Branco, Nicoletta Calzolari, Piek Vossen, Gertjan Van Noord, Dieter van Uytvanck, João Silva, Luís Gomes, André Moreira and Willem Elbers   
[url](http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.680.pdf)  

This paper summarizes what the task is about, how they chose the papers, the general process etc. I was hoping to see some quick insights on how reproductions went and what one can learn from this exercise, so I was kind of disappointed to see no such section(s) in this report.

Reproduction 1: **Reproducing Monolingual, Multilingual and Cross-Lingual CEFR Predictions**  
Yves Bestgen   
[url](http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.687.pdf)  

In many experimental conditions, the results seem to be closer to what was originally reported. However, things that appear very minor changes on the surface (e.g., usage of cross validation settings in sklearn or not noticing what F1 score were we reporting) changed the conclusions in some experimental setups. There was a brief comparison between classification and regression, where what seemed like a poor baseline in one setup seemed formidable in another. It was amazing to see all the statistical analyses of the experimenal results - a regular NLP paper does not provide any scope for such rigor, I think. 


Reproduction 2: **Reproduction and Replication: A Case Study with Automatic Essay Scoring**   
Eva Huber and Çağrı Çöltekin  
[url](http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.688.pdf)  

This paper did both replication as well as reproduction experiments. Here too, the results were closer to original paper in many experimental conditions during replication. During reproduction, substantial amount of parameter optimization was performed, leading to somewhat different results. A second kind of reproduction was performed where the approach was applied on another dataset (in another language), which also lead to different conclusions from the original paper. I agree with the authors that reproduction, and not replication, will lead us in a better direction. I really liked the final discussion on these experiments, and it would be good if this could lead to some sort of best practices recommendations for replicable and reproducible research in future. 

Reproduction 3: **REPROLANG 2020: Automatic Proficiency Scoring of Czech, English, German, Italian, and Spanish Learner Essays**  
Andrew Caines and Paula Buttery   
[url](http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.689.pdf)  

This paper is different from the other two reproductions in the sense that they reimplemented the code in R (!), and reached an interesting conclusion that the R approach is computationally much more intensive for these experiments. This paper also replicated these experiments on two other languages, and the conclusions couldn't be replicated. There are other experiments - I focused on the ones that interested me. This clearly showed there is plenty of stuff to do in understanding the task and the initial results we reported.

Reproduction 4: **Language Proficiency Scoring**  
Cristina Arhiliuc, Jelena Mitrović and Michael Granitzer   
[url](http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.690.pdf)  

This paper has similar conclusions as the other papers - some of the results were comparable, for some, they got lower scores, and the approach did not work when a new language was introduced. Again, there is a lot of other stuff, I am just focusing on overall conclusions. There were a lot of interesting thoughts towards the end on the general outlook -stuff like what new experiments can be added etc. 

Here are my concluding thoughts on this exercise:
- I wish there was some consolidated set of recommendations for best practices somewhere at the end of the task, but there was nothing of that sort. Nevertheless, there is much to learn from this experiment for the research community in general, and for us (the authors of papers used in this task) in particular too.  
- Clearly, there are plenty of interesting challenges ahead if one choses to continue from the questions we asked ourselves in our paper.  
- Reproduction, not replication, should be the goal in future. However, replication is also important first to ensure reproduction is a worthwhile effort.  

I wish these kind of replication and reproduction tasks continue in future, and I hope to submit future work for reproduction too, learning from this experience and getting better. 
