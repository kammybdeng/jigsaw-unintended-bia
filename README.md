# Jigsaw Unintended Bias in Toxicity Classification - Kaggle Competition

## Contents
- [Introduction](#Introduction)
- [Exploring Data Analysis and text cleaning](#EDA)
- [Challenges](#Challenges)
- [Model](#Model)
- [Score](#Score)
- [Reference](#Reference)

## Introduction

When the Conversation AI team first built toxicity models, they found that the models **incorrectly learned to associate the names of frequently attacked identities with toxicity.** Models predicted a high likelihood of toxicity for comments containing those identities (e.g. "gay"), even when those comments were not actually toxic (such as "I am a gay woman").
https://www.kaggle.com/c/jigsaw-unintended-bias-in-toxicity-classification


## Objective
### Detect toxic comments ― and minimize unintended model bias

## Metrics

This competition will use a newly developed metric that combines several submetrics to balance overall performance with various aspects of unintended bias.

- Overall AUC
  - This is the ROC-AUC for the full evaluation set.

- Bias AUCs
  - Subgroup AUC
  - BPSN (Background Positive, Subgroup Negative) AUC
  - BNSP (Background Negative, Subgroup Positive) AUC

[Final Metric](https://www.kaggle.com/c/jigsaw-unintended-bias-in-toxicity-classification/overview/evaluation)

The following word embeddings used in this challenge.
- [glove.840B.300d](https://nlp.stanford.edu/projects/glove/)
- [wiki-news-300d-1M](https://fasttext.cc/docs/en/english-vectors.html)


## EDA

Will update later on.

## Text cleaning

Will update later on.

## Challenges

Will update later on.


## Model
To begin, I started with a basic LSTM model.

  0. **LSTM** with **embeddings weights** (GloVe) [link to model_0](xxx)
    - 1st layer: embedding layer as pretrained weights
    - 2nd layer: spatial dropout
    - 3rd layer: bidirectional with LSTM
    - 4th layer: bidirectional with LSTM
    - 5th layer: global max pooling 1D
    - 6th layer: 2 dense layers (size 16 and 32)
    - 7th layer: output dense layers
  1. **LSTM** with **embeddings weights** (GloVe and FastText) [link to model_0_v2](xxx)
    - added more special punctuation in preprocessing step
    - added Fasttext embedding file
    - used semi-supervised learning
    - revised code to better format

## Reference

This project would not made possible without the help from the very supportive Kaggle community. Below are some of the Kagglers who provided great insights and codes for the challenge.

https://www.kaggle.com/thousandvoices/simple-lstm/
https://www.kaggle.com/gpreda/jigsaw-fast-compact-solution
