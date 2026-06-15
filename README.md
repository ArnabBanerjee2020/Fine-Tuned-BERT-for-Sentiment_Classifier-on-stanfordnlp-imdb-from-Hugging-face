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

## What is DistilBERT?

DistilBERT is a lightweight version of BERT developed through a process called knowledge distillation, where a smaller model learns from a larger pre-trained BERT model. DistilBERT retains most of BERT's language understanding capabilities while reducing the number of parameters and computational requirements.

## Why is it used for Sentiment Classification?

DistilBERT is particularly effective for sentiment analysis because it uses contextual embeddings, meaning it understands the meaning of a word based on its surrounding words. Unlike traditional approaches that treat words independently, DistilBERT captures semantic relationships and contextual information within a sentence. This enables it to better understand complex expressions, negations, and sentiment-bearing phrases such as "not bad" or "hardly disappointing".

## LSTM-Based Traditional Deep Learning Model
## What is LSTM?

Long Short-Term Memory (LSTM) is a type of Recurrent Neural Network (RNN) specifically designed to learn long-term dependencies in sequential data such as text. In this project, the model consisted of an Embedding layer, Spatial Dropout, LSTM layer, Dropout layer, and a Dense output layer for binary sentiment classification.

## Why is it used for Sentiment Classification?

Sentiment in text often depends on word order and contextual relationships. Unlike bag-of-words approaches, LSTM processes text sequentially and maintains information from previous words through its memory cells. This allows the model to capture patterns such as negations and contextual dependencies, making it suitable for sentiment analysis tasks where sentence structure influences meaning.

________________________________________________________________________________________________________________

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

____________________________________________________________________________________________________________________

In code 2.1 and 2.2 i have did a compation between Fine tune BERT and (Tf-IDS + Logistic Regression) Model, where i obtained that on custome dataset 

<img width="737" height="157" alt="image" src="https://github.com/user-attachments/assets/1095f9db-08bc-45e0-831a-0c0fb28892f2" />

and by comparing both the models it is evaluated that 


<img width="846" height="654" alt="image" src="https://github.com/user-attachments/assets/f87743df-95a6-44f8-a2fd-f088ff4a9db8" />


Hence, use of BERT is more effective in Sentiment analysis for IMDB dataset by StanfordNLP in comparison with the traditional Machine Learning model

_________________________________________________________________________________________________________________

In the third Code 3.0, used DistilBERT method for Sentiment Classification

## How did it perform?

In this project, DistilBERT achieved superior performance compared to traditional machine learning and deep learning approaches. The model demonstrated high accuracy and F1-score because it leverages knowledge acquired during large-scale pre-training and adapts it to the sentiment classification task through fine-tuning. Although training required more computational resources than Logistic Regression and LSTM, DistilBERT provided the best overall classification performance and generalization capability.

Obtained Training Loss and accuracy of 90%

<img width="768" height="276" alt="image" src="https://github.com/user-attachments/assets/abfd5b83-f50b-48ef-9321-87c48bf1f038" />

<img width="1309" height="144" alt="image" src="https://github.com/user-attachments/assets/b276dbc6-6777-4ffc-a9c7-bf06bb07074c" />

<img width="472" height="170" alt="image" src="https://github.com/user-attachments/assets/91d05f24-9cc0-4e6b-a89c-ba65f5d3aa4f" />

_________________________________________________________________________________________________________________

In Forth Code 4.0, I show the performance of the LSTM-based traditional deep learning model

## How did it perform?

The LSTM model achieved competitive performance and significantly outperformed traditional machine learning methods such as TF-IDF with Logistic Regression. By learning word embeddings and sequential patterns directly from the training data, it was able to capture sentiment-related features effectively. However, because the model learns language patterns only from the available dataset and does not benefit from large-scale pre-training, its performance was generally lower than DistilBERT. Additionally, LSTMs may struggle with very long reviews compared to transformer-based architectures that can better capture global contextual information.

### Summative Architecture of LSTM and DistilBERT

<img width="729" height="536" alt="image" src="https://github.com/user-attachments/assets/89af3e54-09e1-496e-920f-e415f1e3cf88" />




