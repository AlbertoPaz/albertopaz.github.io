---
layout: article
image: !(UMO)[https://img.discogs.com/Rm-Jhb3eqyBwBGYID4oDIkUHZCQ=/fit-in/300x300/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-4245199-1424373312-2117.jpeg.jpg]
title: Ontology based Deep Learning for ABSA
excerpt: "Experiments with automatic approaches to make sense of people's opinions."
last_modified_at: 2018-05-21
---

Due to Web popularity, nowadays, we experience a rapid growth of online reviews where people express their opinions on products or services. As manually processing these vast amounts of data is impossible, automatic approaches have been devised to provide summaries of people’s opinion, which benefit both customers and companies. One such solution is proposed by sentiment analysis (mining), where public sentiment in relation to products or services needs to be computed [1]. In the recent years a lot of attention has been given to a subfield of sentiment analysis called aspect-based sentiment analysis (ABSA), where the sentiment is gauged with respect to aspects (features) of products or services [2]. 
 
If large amounts of annotated data are available, machine learning approaches seem to give the best results [2]. For relatively small data sets (acquiring annotated data is a usually a very costly process), one can boost the performance of machine learning approaches by making use of domain knowledge formalized in domain ontologies [2]. Often such extensions are introduced by means of advanced ontology features that build on the semantics of the text reviews to provide high-quality signals to machine learning solutions. 

# Deep Learning 

In the last years, deep learning models were among the best performing machine learning algorithms in many fields including natural language processing. For ABSA, a DL model should look like this:

![Cabasc framework](https://github.com/AlbertoPaz/albertopaz.github.io/blob/master/images/cabasc_framework.png)

The above image is the framework of the state of art algorithm for the ABSA task on the SemEval dataset 2014. Recurrent NN, multiple hops, non-linearities, attention mechanisms are incorporated to enable the Network to handle complex sentences. Some best performing implementations:
- [4] proposes Long Short-Term Memory (LSTM) based on single-attention models which use aspect and word embeddings as input and LSTM hidden states for attention computation. 
- [5] determines the attention based on relative distance of the words with respect to the aspects present in a sentence. In order to consider also the words far from the current aspect, 
- [6] employs a recurrent attention mechanism based on a customized memory for each aspect. 
 
The aim of this research is to extend deep learning models with information coming from domain ontologies to improve their working especially when small amounts of annotated data are available. Ontologies can play a role in the feature formation of deep learning solutions or can inject knowledge in the appropriate components of the used deep learning network architecture. While we have previously devised ontologies for ABSA for two domains, there is also room to improve the quality of these ontologies, if needed. The evaluation is done using existing standard data sets. 

# Deep Learning and NLP
Some of the resources I have found more interesting in each of the topics
![Cabasc framework](https://github.com/AlbertoPaz/albertopaz.github.io/blob/master/images/cabasc_framework.png)

### Recurrent Neural Networks
- [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)

### Long Short-Term Memory 
-

### Attention modules
- [Attention and Augmented Recurrent Neural Networks](https://distill.pub/2016/augmented-rnns/#attentional-interfaces)
- [Attention and Memory in Deep Learning and NLP](http://www.wildml.com/2016/01/attention-and-memory-in-deep-learning-and-nlp/)


# Ontologies
- TO DO: check this [Sematch](https://github.com/gsi-upm/sematch)
- TO DO: also check the heroku app
Ontologies use specific knowledge-based semantic similarity metrics that rely on structural knowledge in taxonomy (e.g. depth, path length, least common subsumer), and statistical information contents (corpus-IC and graph-IC). 

Some of the Deep Learning approaches mentioned above [memenet, cabasc] use the absolute distances between context and aspect words to produce a weighted memory. 

![Ontologies](https://github.com/gsi-upm/sematch/raw/master/docs/sources/img/kg.png)

[Link to the project](https://github.com/AlbertoPaz/ABSA-PyTorch/blob/master/README.md)
