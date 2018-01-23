---
layout: post
title: Telugu Treebank in Universal Dependencies
categories: Research
tags: [NLP]
---
Several months back, in July 2017, I wrote about [Universal Dependencies](http://universaldependencies.org) and wondered about not seeing anything for Telugu. Thanks to [@phylostar](http://phylostar.github.io), I ended up in successfully collaborating on a [UD-Telugu](http://universaldependencies.org/treebanks/te/index.html) project during July-October 2017 and we successfully released the first freely available dependency treebank for Telugu in November 2017. 

I sort of took treebanks "for granted" and never bothered much about questions like: how they were annotated?, how do people reach a consensus when they have disagreement?, how should they be stored and distributed?, are the annotations objective and consistent?, should the treebanks be updated? what does it even mean to annotate words with relations between them? what do those relations even mean, linguistically? etc.

Not having done such annotations myself before (although, I did error analysis of a parser for a computational linguistics course project in 2006), this was a herculean task. Many days, weeks and months went by when I woke up as early as possible to be able to "understand" and catch up with stuff. I learnt a lot about formally describing my own language in this process. It is still a long way to go for me, but, getting there. Endless hours of calls happened where we debated on different clauses, what is a subject/object in the sentence, what is the right case marker for a given case? Is a compound word one word or multiple words? etc. 

Discussions going on multiple UD project pages, [for different languages](https://github.com/UniversalDependencies) were extremely useful. I found [UDPipe](http://ufal.mff.cuni.cz/udpipe) very easy to use to quickly train and use parser models for multiple languages. [Brat](http://brat.nlplab.org/) was good as an annotation tool, but I felt there is no good tool for collaborative annotation projects that is a) easy to setup and b) straight forward to compare between different annotators. OCR for Roman transliteration was bad for scanning examples from Grammar book, and we ended up eventually typing everything in Telugu script (which turned out to be good, in the end). 

I think I now have:
- tremendous respect for all the annotation efforts, and for those who develop software to support annotation projects
- a healthy skepticism about parser outputs and treebank annotation inconsistencies
- confidence that my next NLP course teaching will be better than the previous one, with this experience. 

[The paper we wrote together](http://aclweb.org/anthology/W/W17/W17-7616.pdf) (from Treebanks and Linguistic Theories proceedings, 2018) discusses some of the annotation decisions, and other stuff. The treebank is available for download from the link given at the end of first paragraph. Overall, it diverged significantly from what I knew until then, and what I did until then. Additionally, it dramatically altered my perception of computational linguistics itself. Thus, although it is not perfect work, I am completely proud of it :-) I hope to continue working in this direction in future. 

