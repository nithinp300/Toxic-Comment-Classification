﻿# Toxic Comment Classification

## Introduction
This repository contains a Multilabel Text Classification model using pretrained BERT base-cased model for classifying toxic comments. The goal is to classify comments into six categories: toxic, severe_toxic, obscene, threat, insult, and identity_hate.

## Problem Statement
The task is to classify comments based on their context using the BERT contextual model. The dataset consists of comments labeled with the aforementioned categories, and the model is trained to predict these labels based on the content of the comments.

## BERT (Bidirectional Encoder Representations from Transformers)
BERT is a deeply bidirectional, unsupervised language representation model pretrained using a plain text corpus. It uses the Transformer architecture, which learns contextual relations between words in a text. Unlike directional models, the Transformer encoder reads the entire sequence of words at once, allowing it to learn the context of a word based on all its surroundings. This makes BERT well-suited for tasks requiring understanding of context in natural language.

## Dataset
The dataset contains a large number of comments, each associated with one or more of the six labels. The dataset has 8 fields including id, comment_text, and the 6 labels. Each instance is associated with a set of labels. The dataset can be downloaded from [here](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/data).

## Modelling
Google Research provides pre-trained BERT models. In this project, the cased-bert-base model is used, which has the following configuration:

    {
      "architectures": [
        "BertForMaskedLM"
      ],
      "attention_probs_dropout_prob": 0.1,
      "hidden_act": "gelu",
      "hidden_dropout_prob": 0.1,
      "hidden_size": 768,
      "initializer_range": 0.02,
      "intermediate_size": 3072,
      "layer_norm_eps": 1e-12,
      "max_position_embeddings": 512,
      "model_type": "bert",
      "num_attention_heads": 12,
      "num_hidden_layers": 12,
      "pad_token_id": 0,
      "type_vocab_size": 2,
      "vocab_size": 30522
    }


## Usage
To use the model, follow these steps:
1. Open the `toxic-comment-classification.ipynb` notebook in Google Colab.
2. Change the runtime to GPU for faster processing.
3. Mount Google Drive (check the left-hand side panel in Colab).
4. Download the dataset and upload the `test.csv`, `test_labels.csv`, and `train.csv` files to a new `dataset` folder in your Google Drive.
5. Execute each cell in the notebook to train and test the model.
