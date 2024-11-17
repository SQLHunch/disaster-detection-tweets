# Disaster Detection with Tweets

This repository contains the code and deliverables for the "Disaster Detection with Tweets" project, a binary classification problem to identify whether tweets are about real disasters or not. The project uses natural language processing (NLP) techniques and machine learning models to achieve the goal.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Approach](#approach)
  - [Data Preprocessing](#data-preprocessing)
  - [Feature Engineering](#feature-engineering)
  - [Modeling](#modeling)
- [Results](#results)
- [Usage](#usage)
  - [Dependencies](#dependencies)
  - [How to Run](#how-to-run)
- [Future Work](#future-work)
- [Acknowledgements](#acknowledgements)

---

## Project Overview

The goal of this project is to classify tweets as either related to disasters (`1`) or not related to disasters (`0`). This is a Kaggle competition problem titled **"Natural Language Processing with Disaster Tweets"**.

Be sure you create a Data folder on the same folder where the ipynb is. The files can be downloaded from Kaggle.

https://www.kaggle.com/competitions/nlp-getting-started/data

## Dataset

The dataset contains:
- **Training Set:** 7,613 labeled tweets.
- **Test Set:** 3,263 tweets without labels.
- **Features:**
  - `text`: The tweet content.
  - `keyword`: Disaster-related keywords (if available).
  - `location`: User location (if available).
  
The target column indicates whether a tweet is disaster-related (`1`) or not (`0`).

## Approach

### Data Preprocessing

1. **Handling Missing Data:** Filled missing values in `keyword` and `location` with placeholders.
2. **Text Cleaning:** 
   - Removed URLs, mentions, hashtags, special characters, and numbers.
   - Converted all text to lowercase.
3. **Tokenization and Padding:** 
   - Tokenized tweets into sequences using Keras.
   - Padded sequences to ensure consistent input length for the model.

### Feature Engineering

- Extracted additional features:
  - Word count, character count, average word length, and presence of keywords.
- Utilized tokenized and padded sequences for embedding layers.

### Modeling

- Implemented a deep learning model using:
  - **Embedding Layer:** To represent words in a dense vector space.
  - **Bidirectional LSTM Layers:** To capture contextual information in tweets.
  - **Dropout Layers:** To prevent overfitting.
  - **Dense Layer with Sigmoid Activation:** For binary classification.

- **Early Stopping:** Monitored validation loss to stop training when the model no longer improved.

## Results

- **Validation Accuracy:** ~78%
- **Test Accuracy:** ~79%
- **Loss on Test Set:** ~0.58

Loss and accuracy plots show consistent learning, with room for hyperparameter optimization.

## Usage

### Dependencies

To run the code, ensure you have the following dependencies installed:
- Python 3.x (3.9.20)
- Pandas
- NumPy
- TensorFlow/Keras
- Scikit-learn
- Matplotlib
- Seaborn

### How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/disaster-detection-tweets.git
   cd disaster-detection-tweets

