---
layout: article
image: !(UMO)[https://img.discogs.com/Rm-Jhb3eqyBwBGYID4oDIkUHZCQ=/fit-in/300x300/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-4245199-1424373312-2117.jpeg.jpg]
title: Ontology driven Deep Learning for ABSA
excerpt: "My first experiments with Deep Learning and NLP. Automatic approaches to make sense of people's opinions."
last_modified_at: 2018-05-21
---

Due to Web popularity, nowadays, we experience a rapid growth of online reviews where people express their opinions on products or services. As manually processing these vast amounts of data is impossible, automatic approaches have been devised to provide summaries of people’s opinion, which benefit both customers and companies. One such solution is proposed by sentiment analysis (mining), where public sentiment in relation to products or services needs to be computed [1]. One can take this one step further and gauge the sentiment with respect to aspects (features) of products or services, this what is known as aspect-based sentiment analysis (ABSA) [2]. 
 
# Aspect-Based Sentiment Analysis

Following [Surver on ABSA Kim and Flavius]() here I would like to first introduce some basic terminology
Ortogonality
> Opinion: "Judgement or belief not founded on certainty or proof". In this sense, opinions are subjective and their oposite will be facts
> Sentiment: Its closely related to the attitude an emotion used to convey an evaluation of the topic under discussion

some  more pictures and examples

ABSA Task is concerned with finding:
* Target object for which the sentiment is expressed. 
* An aspect of the entity, which can be any characteristic or property of that entity
* Sentiment
* Holder, the one expressing the sentiment
* Time at which the sentiment was expressed

If large amounts of annotated data are available, machine learning approaches seem to give the best results [2]. For relatively small data sets (acquiring annotated data is a usually a very costly process), one can boost the performance of machine learning approaches by making use of domain knowledge formalized in domain ontologies [2]. Often such extensions are introduced by means of advanced ontology features that build on the semantics of the text reviews to provide high-quality signals to machine learning solutions. 

# Deep Learning and ABSA

In the last years, deep learning models were among the best performing machine learning algorithms in many fields including natural language processing. For ABSA, a DL model should look like this:

try1:

![cabasc](https://github.com/AlbertoPaz/albertopaz.github.io/blob/master/images/cabasc_framework.png)

try2:

![cabasc](https://github.com/AlbertoPaz/albertopaz.github.io/blob/master/_posts/NLP/cabasc_framework.png?raw=true)

The above image is the framework of the state of art algorithm for the ABSA task on the [SemEval dataset 2014](). One can play arround with the components of the Network architecture and make it as complex as possible using Embeddings, RNN, multiple hops, non-linearities, attention mechanisms are incorporated to enable the Network to handle complex sentences. Some best performing implementations:
- [4] proposes Long Short-Term Memory (LSTM) based on single-attention models which use aspect and word embeddings as input and LSTM hidden states for attention computation. 
- [5] determines the attention based on relative distance of the words with respect to the aspects present in a sentence. In order to consider also the words far from the current aspect, 
- [6] employs a recurrent attention mechanism based on a customized memory for each aspect. 

## Word Embeddings

## Recurrent Neural Networks

- [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)

## Long Short-Term Memory 

-[Understanding LSTM Networks](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)

## Attention modules

- [Attention and Augmented Recurrent Neural Networks](https://distill.pub/2016/augmented-rnns/#attentional-interfaces)
- [Attention and Memory in Deep Learning and NLP](http://www.wildml.com/2016/01/attention-and-memory-in-deep-learning-and-nlp/)

# The project()

The aim of this research is to implement several state of art deep learning models and explore extensions using information coming from domain ontologies to improve their working especially when small amounts of annotated data are available. Ontologies can play a role in the feature formation of deep learning solutions or can inject knowledge in the appropriate components of the used deep learning network architecture.
- [Link to the project](https://github.com/AlbertoPaz/ABSA-PyTorch/blob/master/README.md)
- [Link to the results]()


# Ontologies
- TO DO: check this [Sematch](https://github.com/gsi-upm/sematch)
- TO DO: also check the heroku app
Ontologies use specific knowledge-based semantic similarity metrics that rely on structural knowledge in taxonomy (e.g. depth, path length, least common subsumer), and statistical information contents (corpus-IC and graph-IC). 

Some of the Deep Learning approaches mentioned above [memenet, cabasc] use the absolute distances between context and aspect words to produce a weighted memory. 

![Ontologies](https://github.com/gsi-upm/sematch/raw/master/docs/sources/img/kg.png)


