---
layout: post
title: Teaching Notes- Text Mining in R, for non-programmers
categories: Teaching
tags: [R,410X]
---

I teach a course "Language as Data" for introducing text processing and analysis methods to liberal arts majors. The course is a new experimental course first taught in Spring 2017, and now in its second round, in Spring 2018. I use R as the programming language, and this series of posts are my notes and observations about teaching in R for non-programmers.

Roughly, the topics discussed in the course are:
- corpus analysis (counting most frequent words, plotting them, knowing about relationships between words, searching for words in context, counting ngrams)
- reading different data formats (text, doc, pdf, tweets, html, xml etc)
- text classification (sentiment classification)
- topic modeling
- text clustering
- text visualization
Syllabus for the course is [online](http://sowmya.public.iastate.edu/Syllabi/410-Spring18-Syllabus.pdf) and I am trying to also upload some of the [tutorials I prepare for the class](https://github.com/nishkalavallabhi/RTextNotes/). 

**Purpose of the course**: When I wrote the course proposal last year, our idea was to introduce text analysis methods to students who are not coming from a technology/CS background, without expecting them to have strong programming foundation as a requirement. There are reasons for this. Many traditionally social science disciplines rely on a lot of technology tools to process data, and several of them work with textual data. For example, let us take news articles - students of journalism, sociology, political science (and several others) - all are interested in analysing news content for a variety of reasons. Social scientists interested in studying how language changes, what people are talking about (on twitter, let us say) increasingly rely on software for these analyses. So, the course was proposed in that background, with an aim to train social science and liberal art majors and prepare them to be able to perform some amount of text analysis and derive knowledge about patterns in collections of text data. 

**Why R?:** I chose to teach the course using R as the programming language. I considered opting for Python (which I use in a introductory programming class), which I think is generally a good first programming language, and has a quick learning curve initially. But, eventually, chose R for the following reasons:
- Many of the students we originally targeted have no background in programming, and presumably, learning to program is not particularly, directly, useful during their disciplinary education.
- Yet, with increasing amounts of data everywhere, they have to know some deal of programming to do simple tasks with textual data.
- It is possible that some of them will get exposed to R at some point, as a part of some statistics course.
- R has a lot of custom libraries and functions, so the students may be quickly able to work on small scale text processing projects in their disciplines, without requiring them to be full-fledged programmers. 
- Supposedly, there is a lot of online help for R (I will get to this below), so beginners will get support.

**Reflections after starting the second round:**
- I still think R is the best language for this course.
- However, it seems like there is hardly a beginner level text mining textbook in R. I know of two books that target textmining and R.
    * Text analysis with R for students of literature - Matthew Jockers (which I use as the textbook)
    * [Text Mining with R - A Tidy Approach](https://www.tidytextmining.com) by Julia Silge and David Robinson
  The first one is a good book, but seems too focused on literature, and does not talk about 2 major topics from what I want to discuss. The book primarily reads like a series of specifically focused tutorials directed towards some XML markup used in literature world. So, even though this is the only such beginning R book focusing on text mining, it is not ideal. The second one is not for beginners. It is for seasoned R programmers who are new to textual data
- While there is indeed a lot of online help, it is not in a way that is understandable by people who are both new to R and programming.

While I noticed these issues in the past, they seem more important now, as this year's students exclusively are undergraduates, and none come from the departments where they can potentially be exposed to technical topics (linguistics, mass communication, sociology etc). Last year, students came from school of business, and computer science (mainly) and almost 3/4ths of the class know some programming in some other language or statistical analysis in R. 

I plan to write as time permits on issues that I think the students faced difficulties with, and my thoughts on handling them. Let us see how this will go. Since there is no textbook for many of these issues, I also started preparing some tutorials and additional notes apart from classroom slides. I will try to put the notes up as much as possible.

