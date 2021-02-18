---
layout: post
title: NLP without annotated data - teaching notes
categories: Teaching, Notes
---

I taught an online guest course at my almamater, [Eberhard Karls University of Tuebingen](https://uni-tuebingen.de/en/) last month (January 2021). It is called **"NLP without a readymade annotated dataset"**. This post is a reflection on how it went, along with some comments from student feedback.

**Why this course?**  
When I was asked to teach a guest NLP course for [ISCL](https://uni-tuebingen.de/en/faculties/faculty-of-humanities/departments/modern-languages/department-of-linguistics/courses-of-study/courses-of-study-at-the-sfs/international-studies-in-computational-linguistics/) students, I was both excited at the prospect and worried. Excitement is because my first non-TA teaching experience was for these students in [2011-12](http://www.sfs.uni-tuebingen.de/~dm/11/ws/complexity/). Worry was because I did not want to teach the standard NLP course for a few reasons:   
a) I don't teach fulltime. So, I don't have the incentive to spend all that time in prep.   
b) Timeframe is too short (1 month) to cover topics for a full NLP course.  
c) I wanted to bring in some value as an external lecturer. Regular coursework can happen in regular courses.   

Since I had the freedom to choose my topic, I chose something that has been bothering me for sometime - dataset creation for NLP tasks. This very question of where do you get your data? is a completely ignored problem in a typical NLP course in my opinion. It was also a recurring question during out discussions in a previous online course I taught in October. So, I thought this course would be a good opportunity to explore this space.

This is my second online course ([reflections on first one here](https://nishkalavallabhi.github.io/EconNLP/)) and here too I had some of the challenges that I faced earlier. Here are the two main challenges: 

1. This is a month long course, with 2.5 hour sessions on 3 days a week for 3 weeks. Again, how much can you "pack" into a course that is intense, yet, short in terms of time frame? 
I wanted students to get some skills they can apply immediately, but also wanted at least those who have research interests to explore more. 

2. The class has a mix of students with primarily linguistics background, and with varying levels of experience with CS and programming.  So, I don't want to get into mathematical details and endlessly discuss "methods". This should also be kept in mind in choosing the topics and assignments (term papers are more flexible, and students can choose topics suiting their interests).

**Syllabus:**  
We met for 10 days (2.5 hours each session) and here is what I covered, with an attempt to address these challenges and aims I had.

- **NLP Overview** introduced NLP, with an overview of the various challenges, tasks, methods used in NLP research, and of how NLP is used in real world, and by other fields of research.

- **NLP Pipeline** outlined how a system development pipeline looks like for NLP software from data collection to deployment, and we had some discussions with real world NLP pipelines. I also covered text representation for NLP in detail during this session.

- **Corpus collection, extraction and exploration** gave an overview of the different ways of collecting annotated data for NLP, from elaborate annotations and web crawling to automatic data labeling, and discussed briefly how to extract text from various file formats, and how to do an exploratory analysis of the dataset to understand its structure. We also covered issues related to ethics, and had some exercises related to creating toy ["datasheets for datasets"](https://arxiv.org/abs/1803.09010). There was an extended discussion about how to anonymize textual data, based on student interest on the topic in the discussion forum.

- **Automatically Labeling Data and Data Augmentation** - This topic gave an overview of how to use [Snorkel](https://www.snorkel.org/) for creating labeled data from raw data using labeling functions, and how to use data augmentation techniques to increase the size of training data. I took the tutorials on their website, and adapted them a bit to highlight some practical issues to keep in mind while dealing with such problems. I spent 2 sessions on this.

- **Working with small datasets and transfer learning** - In this, I gave a quick overview of neural text embeddings, and the idea of "fine-tuning" a pre-trained model, and showed an example of using BERT for fine-tuning in a text classification setup. I also used some visuals from a blogpost illustrating how to visualize the attention heads during fine tuning, via bertviz. 

- **Group Discussions** - I compiled a bunch of research articles from NLP conferences over the past 5 years, covering the topics listed in the syllabus. Students formed into groups of 2-4 people, chose a paper from this list, and presented on it for our class. This went on for 3 sessions, with some [NACLO group exercises](https://nacloweb.org/) in the time left after student groups are done for that day. I have been using NACLO exercises for in-class group activities ever since the days I used to teach at Iowa State University. They have always been fun and students also liked them a lot. It was no different this time too. 

- **Wishlist topics** - There were student requests for three topics - NLP in language learning, NLP for endangered languages, and NLP careers. So, I spent roughly the equivalent of 1 session attempting to give an overview of these topics and reviewing the course in general. The first and last one came relatively easy to me, as I spent quite a lot of time thinking about these topics in the past decade. The second topic needed some prep, and I learnt about several interesting projects in the process.

As mentioned in an earlier post too, I don't like to give too challenging assignments in courses with non-CS students, since that may deter them from the content altogether. So, I focused on letting them figure out how to use some existing NLP tools, and in addition, write their observations on where they work and where they fail. Term paper was left more open, and I suggested a bunch of NLP problems using existing datasets, as well as exploring tools such as Snorkel to create a labeled dataset for a new problem. Submission deadline has not passed yet. I am looking forward to read their work!

I plan to upload the slides (although they are not made for a public appearance) at some point of time, in case someone finds it useful. 

**Format:** This was a live class, and I recorded the lectures. I was somewhat uncomfortable with recording as the slides are **clean** and I wasn't exactly prepared to expose myself for eternity after the class :-) I decided to record nevertheless, as I heard from students last time that recordings are useful. Several students wrote to me thanking for that - someone wanted to revisit the lectures, someone couldn't attend a class, someone was ill, someone was in a different country with a huge time zone difference etc. We also had some regular breakout room exercises in most of the sessions - the recording was just left on with muted screen and I did not edit out anything.  In the end, I am glad I recorded, and I hope the recordings stay with the class, not circulate outside! 

**What I liked:** I just loved the questions that came from students during our classes and in the group discussions. Some of these gave me a few new ideas to pursue further in near future. Student population and interests also seemed to be very different from when I was a student there. I felt there is much more interest in the topic now than before. Overall, I felt I had a good time teaching this class!  

**What I missed:** I missed seeing the faces of students in an actual classroom more than anything else!  

**What can be done better in the course:**:  
I had a few observations on how to teach better online based on my previous teaching experience. I implemented some of those this time (e.g., more group activities during the class, prompting more discussion during student presentations etc) and it seems to have worked. After teaching this course once, and seeing the student feedback, here are my thoughts on how to modify this next time (if there is a next time, that is:   

* There was a general call for making it a full semester course and have more handson coding activity. If I was a full time faculty, I would love this one, but I don't know if it is practical for me or the students to do this in a crash course. I am yet to figure out what can be improved on this front.  

* Try for more discussion. I am yet to figure out a way to encourage active participation in an online course. The breakout room exercises definitely helped, but it seemed like a bunch of students always are more responsive. This happens in physical courses too, though.  

* I felt I should probably have more coding examples. I tried to have them for the Snorkel and BERT part, and less for the other topics. But, perhaps I need to spend more time on thinking about easy to access code examples next time!! 

Overall, I think I very much enjoyed teaching this course despite the hectic schedule. I already had experience with one more online course by this time and that definitely helped. Zoom breakout rooms are the best part of online teaching for me. I am also thankful everything went smoothly in the family and work front, helping me fully focus on teaching the course without distractions! Now, there are a lot of ideas to explore further, based on things I learnt during my readings, and I look forward to see what the students did for their term papers!  
