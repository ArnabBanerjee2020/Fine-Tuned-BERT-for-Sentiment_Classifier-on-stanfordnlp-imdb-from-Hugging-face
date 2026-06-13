# Fine-Tuned-BERT-for-Sentiment_Classifier-on-stanfordnlp-imdb-from-Hugging-face
Using the Hugging Face IMDb dataset to make comparison between transformers.

## What is BERT?

BERT stands for Bidirectional Encoder Representations from Transformers.
It is a pre-trained Natural Language Processing (NLP) model developed by Google in 2018.
The main purpose of BERT is to understand the meaning and context of human language. Instead of processing words individually, BERT learns relationships between words in a sentence and generates contextual representations (embeddings) that can be used for tasks such as:
Sentiment Analysis
Text Classification
Question Answering
Named Entity Recognition (NER)
Text Summarization

## What Makes "Bidirectional" So Special?

Before BERT, many language models read text in only one direction.
Traditional Left-to-Right Processing
Consider:
The movie was not good.
A left-to-right model predicts each word using only previous words:
The → movie → was → not → good
When processing "good", it knows the word "not" came before it.
However, for many language understanding tasks, a word's meaning depends on both sides of the sentence.

## Why BERT?

Unlike LSTMs which process text sequentially (token by token), 
BERT reads the entire sentence at once using self-attention — 
every token can directly attend to every other token. This means 
"not good" is understood differently from "good", because BERT 
sees the negation in full context. For sentiment analysis on long 
movie reviews, this bidirectional context is crucial.

The first code (1.1 and 1.2) is on fine-tuning a BERT transformer for a sentiment classifier on the StanfordNLP-IMDb dataset from Hugging Face,
using T4 GPU from Google Colab to tune the BERT model on text datasets

in which the model training accuracy obtained is 

<img width="747" height="207" alt="image" src="https://github.com/user-attachments/assets/5ffec75e-7529-45e0-9f52-c963b09941e2" />

The prediction accuracy obtained is 

<img width="769" height="126" alt="image" src="https://github.com/user-attachments/assets/e9866653-2022-4e11-8b71-63b4f93f74e9" />

Classification report:-

<img width="485" height="161" alt="image" src="https://github.com/user-attachments/assets/d777e867-ebe7-4aa7-ae42-d9542dd0cddf" />

Custom test report 

<img width="390" height="296" alt="image" src="https://github.com/user-attachments/assets/6aa08164-e481-4f4c-adee-7adad2636808" />

IN code 2.1 and 2.2 i have did a compation between Fine tune BERT and (Tf-IDS + Logistic Regression) Model, where i obtained that on custome dataset 

<img width="737" height="157" alt="image" src="https://github.com/user-attachments/assets/1095f9db-08bc-45e0-831a-0c0fb28892f2" />

and by comparing both the models it is evaluated that 


<img width="846" height="654" alt="image" src="https://github.com/user-attachments/assets/f87743df-95a6-44f8-a2fd-f088ff4a9db8" />


Hence, use of BERT is more effective in Sentiment analysis for IMDB dataset by StanfordNLP in comparison with the traditional Machine Learning model
