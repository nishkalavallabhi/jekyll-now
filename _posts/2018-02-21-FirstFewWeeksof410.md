---
layout: post
title: Teaching Notes- First few weeks of text mining with R
categories: Teaching
tags: [R,410X]
---

This post is a continuation from my previous post on teaching a course "Language as Data" for introducing text processing and analysis methods to liberal arts majors. The posts in this series can be accessed [here](https://nishkalavallabhi.github.io/Tags/#410x).

We completed 6 weeks of classes and are in our second week now. I completed the first two topics:

- topic 1: different kinds of basic corpus analyses - ranging from getting word-frequency tables to searching for words in context)
- topic 2: working with different kinds of textual data (e.g., .txt, .docx, .pdf, .html, .xml, twitter, nytimes/guardian libraries etc)

We now entered what our [text book author](http://www.springer.com/us/book/9783319031637) calls "Macro Analysis", which is primarily text mining and modeling stuff such as text classification, clustering and topic modeling. Yesterday, I spent some time giving an overview of all three problems, discussing the similarities and differences between them, some real world examples etc. However, before we take a deep dive into these things, I decided to pause and do a quick summary of what we did so far (condense the main points into a couple of functions, basically!), and also make some notes for my self, about my observations and things to work on.

So, here are some observations about the class:

- Things like setting the right working directory, getting the correct file path, renaming a file from within R: I actually took these for granted. It did not occur to me this is not straight forward (especially if I show forward slashes and windows uses backward slashes, etc) for someone who is not coming from some technology background, especially humanities students. Next time, I should first make sure this part is clear before doing anything else. 
- The [swirl](http://swirlstats.com/) lessons from Coursera that I asked students to do initially - I got a feeling these are also not really geared towards the uninitiated. It seemed like something for people who are already familiar with some form of programming. They are good lessons though - doing some of them in the beginning surely familiarizes students with R environment. 
- The textbook is clearly not sufficient to handle this group of audience. My general perception is - while somethings are explained clearly, some things are either unnecessarily complex or just not explained at all and are assumed. In addition, as we progress, focus is exclusively on XMLs that follow a certain template/markup used with literary texts. I felt this last time too, but the students came from relatively technical backgrounds and they seemed to not feel it so much. A new [introductory book](http://www.springer.com/us/book/9783319645704) came up last month, but I quickly realized this book also may not meet my course requirements, as it focuses almost exclusively on basic statistical analysis with text data, and seemed very specific to corpus linguistics researchers. So, there seems to be a gap in terms of accessible teaching materials on the topic, which is going to be an important one to fill in the coming few years.
- The online help on R seems to both overwhelm and intimidate many students. Compared to Python's online help, I too generally find R related forums and blogs frustrating. I think this is primarily because there seems to be too many updates and too many of these things get too old too soon. This indeed can cause confusion for newbies. I need to work on ways to address this.
- Despite these major concerns for which I am slowly (and steadily) figuring out solutions and workarounds, I think students are motivated, and see the point of such a course, and why learning some data science basics will be useful for them as liberal arts and social science majors even if they don't stay in grad school. That is a start!

Coming to a quick summary of the course so far: 

My summary of descriptive analyses we discussed so far can be accessed online ([R Markdown](https://github.com/nishkalavallabhi/RTextNotes/blob/master/tutorials/CorpusAnalysesSummary.Rmd), [generated pdf](https://github.com/nishkalavallabhi/RTextNotes/blob/master/tutorials/22Feb2018-Tutorial.pdf)). It is for tomorrow's class, and I am still workign on it, but this is the basic outline. One thing I really really like about teaching with R is this quick way of preparing some tutorial documents. I hope to prepare another such summary for accessing different forms of textual data, but that has to wait for a few more weeks. Overall, so far, I learnt a lot of stuff about teaching across disciplines during these past 6 weeks, and there are about 8-9 more weeks to go!




