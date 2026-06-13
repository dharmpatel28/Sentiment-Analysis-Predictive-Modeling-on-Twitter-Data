# Election Sentiment Analysis Using CNN

## Overview

This project predicts public sentiment toward political candidates using Twitter data and a Convolutional Neural Network (CNN). The model analyzes tweet text along with engagement metrics (likes and retweets) to estimate sentiment scores and identify the candidate with the highest average predicted sentiment.

## Features

* Tweet text preprocessing and cleaning
* Engagement feature engineering (likes + retweets)
* Text vectorization using TensorFlow TextVectorization
* CNN-based sentiment prediction model
* Candidate-level sentiment aggregation
* Election winner prediction based on average sentiment

## Dataset

The dataset contains:

* Tweet text
* Candidate name
* Sentiment labels (positive, neutral, negative)
* Likes and retweets

Sentiment labels are converted to numerical scores:

* Positive → 1
* Neutral → 0
* Negative → -1

## Model Architecture

* TextVectorization Layer
* Embedding Layer
* Conv1D Layer
* Global Max Pooling
* Dense Layers
* Linear Output Layer

Additional numeric feature:

* Engagement = Likes + Retweets

## Results

The model predicts sentiment scores for unseen tweets and aggregates predictions by candidate. The candidate with the highest average predicted sentiment is identified as the predicted election winner.

## Technologies Used

* Python
* Pandas
* TensorFlow / Keras
* NumPy
* Matplotlib

## Future Improvements

* Use pretrained embeddings (Word2Vec, GloVe, BERT)
* Add more social engagement features
* Deploy as a web dashboard
* Incorporate real-time Twitter data streams


**Project Workflow**

                 ┌─────────────────────┐
                 │ Election Tweet Data │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Data Cleaning       │
                 │ Remove IDs, Users   │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Feature Engineering │
                 │ Engagement Score    │
                 │ Sentiment Mapping   │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Text Vectorization  │
                 │ (Keras TextVector.) │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ CNN Model           │
                 │ Embedding + Conv1D  │
                 │ + MaxPooling        │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Merge Text +        │
                 │ Engagement Features │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Dense Neural Layers │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Sentiment Prediction│
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Model Evaluation    │
                 │ Actual vs Predicted │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Candidate Sentiment │
                 │ Aggregation         │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Election Outcome    │
                 │ Analysis            │
                 └─────────────────────┘
