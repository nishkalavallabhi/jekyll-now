---
layout: post
title: Reading Notes: FastText embeddings and classification
categories: Readings
tags: NLP
---

After about 4 months of break, I feel compelled to write a blog post on some readings again! I was working with [fastText](https://github.com/facebookresearch/fastText) over the past few weeks, as a part of preparing some tutorials, and I ended up reading some of the original papers behind it. This post consists of some of my notes/comments on three papers (first one has the longest summary, as I consider the rest as in some way building on top of this).

> "Bojanowski, P., Grave, E., Joulin, A., & Mikolov, T. (2017). Enriching word vectors with subword information. Transactions of the Association for Computational Linguistics, 5, 135-146." [url](https://www.mitpressjournals.org/doi/abs/10.1162/tacl_a_00051)

**Idea:** This paper describes the approach to create character n-gram based embedding representation for words, extending the original [word2vec skipgram method](http://papers.nips.cc/paper/5021-distributed-representations-of-words-andphrases). So, the idea is to create word representations by first learning representations for character ngrams and summing them up to get the word representation. The advantage is that this will make it possible to get representations for hitherto unseen words in the training data.  

**Experiments:** They evaluate the embeddings learned from this approach using 9 languages (Wikipedia data for learning the representations) for word similarity judgement, word analogy and language modeling tasks. They also performed experiments comparing these representations with other approaches based on learning morphological representations and effect of training data size on the models. Finally, they also report some qualitative analyses addressing aspects such as nearest neighbors for selected words, how important ngrams correspond to morphemes, and how this approach works on word similarity judgements of out of vocabulary words.

**Results:**   
- On the word similarity judgements task, their approach achieves better results over SOTA for languages that have richer morphologies, and it also does well on a rare-words dataset for English, providing support for the approach. This approach also does better when compared with other methods of incorporating morphological information into such models (which need more linguistic information to train) on the same task.  
- In the word analogy task, their approach improves SOTA by a large margin for syntactic tasks, but not for semantic tasks.  
- Training data size did not seem to affect the results on word similarity task much, compared to what we would usually see in such experiments. They show that good word representations can be learnt with small data sizes, which is very useful in practice.  
- In experiments with character ngrams size, they suggest 3--6 as the optimum range, based on their experiments.  
- They used these embeddings as the input layer for a LSTM based language model, and showed that this approach reduced perplexity on standard datasets, especially for the morphologically rich languages, by a good amount. 
- Qualitative analysis showed some examples of nearest neighbors of rare words (e.g., english-born, and polish-born were close neighbors), important ngrams in a word based on which ngram when removed results in a very different representation (e.g., auto, fahr, fahrer were the most important for the German word autofahrer), and how the model builds representations for out of vocabulary words.

**Comments:** I felt the paper is quite well-written and largely clear. However, one can't help but wonder - word embedding being a sum of character ngram embeddings makes intuitive sense. But, is there any other theory behind it? Are there alternatives to summing up like that?  A couple of other things such as: why is a particular hashing function chosen for hashing character sequences (Fowler-Noll-Vo)? What is its special advantage? were not explained, making them feel more ad-hoc than they probably are.  


> "Joulin, A., Grave, E., Bojanowski, P., & Mikolov, T. (2017). Bag of Tricks for Efficient Text Classification. In Proceedings of the 15th Conference of the European Chapter of the Association for Computational Linguistics: Volume 2, Short Papers (Vol. 2, pp. 427-431)." [url](http://www.aclweb.org/anthology/E17-2068)

**Summary:** This short paper describes a simple and efficient text classification approach, using the fastText embeddings from the first paper. Taking several sentiment analysis and tag prediction datasets, they show that this approach achieves performance on par with deep learning based classifiers, while being super fast on large corpora, with several thousands of categories and a billion words in the vocabulary. 
 
**Comments:** I found the paper surprisingly vague and with occasional grammar errors. For example, let us take the model architecture. The input layer shows N ngram features as a way to represent the text. These features are embedded and averaged to form hidden variable, which is the text representation. From that description, I assumed, they use fastText pre-trained embeddings. Yet, the question of how do they use them for sentence or paragraph instead of words (learnt character n-gram embeddings did not have spaces or newlines in them, did they?) remained unresolved. However, in the experiments/results, they then write: "Unlike Tang et al. (2015), fastText does not use pre-trained word embeddings, which can be explained the 1% difference in accuracy." Keeping the sentence formation aside, I did not understand what exactly is the architecture made up of. 

Another aspect that struck me was: tag prediction is a multi-label problem (as against multi-class). Precision@1 was used to measure the efficiency of fastText on the datasets related to this problem. I wondered if there is a better way to use more measures along with this, as this only tells us whether the best predicted tag matches one of the actual tags. 

However, despite these gaps in my understanding and some questions, I noticed the approach is, indeed, blazingly fast, even on relatively large text classification datasets. What took forever both with Logisitc Regression and some kind of a deep neural network (CNN or LSTM, for example) took only a few minutes with fastText. I do wish **someone** works on making this more usable with clearer documentation, though!

> "Joulin, A., Grave, E., Bojanowski, P., Douze, M., Jégou, H., & Mikolov, T. (2016). Fasttext. zip: Compressing text classification models. arXiv preprint arXiv:1612.03651." [url](https://arxiv.org/abs/1612.03651)

**Summary:** This paper deals with the problem of compressing large text classification models. They propose fastText.zip, which requires 2 orders of magnitude less memory than fastText while only being slightly inferior in terms of accuracy. After some experiments, they conclude that this approach outperforms SOTA in terms of a compromise between memory and accuracy. 

One thing I noticed while working with fastText classifier is the size of the model it created. It was several giga bytes, and I wondered about the scenarios where it will pose problems in deploying in some applications. This statement in this paper naturally appealed to me in that context:
> "We show that a few key ingredients, namely feature pruning, quantization, hashing, and retraining,
allow us to produce text classification models with tiny size, often less than 100kB when
trained on several popular datasets, without noticeably sacrificing accuracy or speed."

This paper is a bit dense for me to quickly read through, so I am only summarizing what I think are the main steps in their "compression pipeline" based on a skim-through of the approach.
- Bottom up product quantization: Product quantization is a compression technique used for doing approximate nearest neighbor search. The idea behind this [explained in this paper](https://hal.inria.fr/inria-00514462/document) is based on decomposing the large space into the product of several low dimensional subspaces, and quantizing each sub-space seapartely. A vector is represented by a short code, made of its subspace quantization indices, and nearest neighbors to this vector can be efficiently calculated from these codes. In this paper, they follow a: "bottom-up learning strategy where we first quantize the input matrix, then retrain and quantize the output matrix (the input matrix being frozen)." and show that this approach gets a 10 factor compression, without noticeable loss of performance. 
- Heuristics for text specific tasks: In addition to the above step, they propose a few heuristics for reducing the space taken by the vocabulary dictionary. Vocabulary pruning is the process of reducing the size of stored vocabulary, similar to language model pruning. They describe an approach to do this, while avoiding scenarios where none of the pruned vocabulary words appear in a given text, followed by hashing. 

In the experiments, they show different small and large datasets how their compression reduces the size while not compromising on accuracy, for text classification task. 

**Comments:** I can't comment much on the content as I only skimmed through. I think the fact that the code is available, and fastText classification already has this implemented gives us enough scope to try this out and compare the paper's claims for some real world datasets. 




