# Disaster Detection with Tweets

This repository contains the code and resources for the **"Disaster Detection with Tweets"** project, which predicts whether a tweet describes a real disaster or not. The solution leverages deep learning techniques with a focus on recurrent neural networks (RNNs) and Bidirectional LSTMs to extract temporal relationships in the text data.

---

## Project Overview

In this binary classification task, tweets are analyzed to predict whether they describe actual disaster events. The dataset comes from a Kaggle competition and consists of labeled tweets for training and unlabeled tweets for testing.

**Key Metrics:**
- **F1 Score**: Used as the primary metric for evaluation to balance precision and recall.
- **Final Kaggle Score**: 0.780 (Improved from the earlier 0.778).

---

## Dataset

https://www.kaggle.com/competitions/nlp-getting-started/data


The dataset consists of:
- **Train Data**: 7,488 labeled tweets (`0` for non-disaster and `1` for disaster).
- **Test Data**: 3,263 unlabeled tweets for predictions.

Data preprocessing includes:
- Lowercasing, removing URLs, mentions, hashtags, and special characters.
- Padding sequences to a uniform length of 50 tokens.

---

## Model Architecture

The final model employs a deep learning architecture using Bidirectional LSTMs for robust performance:
1. **Embedding Layer**: Converts text to dense numerical vectors (128 dimensions).
2. **Bidirectional LSTM (128 units)**: Captures temporal relationships in both forward and backward directions.
3. **Dropout Layers**: Adds regularization to prevent overfitting.
4. **Bidirectional LSTM (64 units)**: Further processes text with a reduced dimensionality.
5. **Dense Layer (1 unit)**: Outputs a sigmoid activation for binary classification.

**Model Summary:**
- Total Parameters: **1,707,649**
- Trainable Parameters: **1,707,649**
- Non-Trainable Parameters: **0**

---

## Training Details

**Key Features:**
- **Class Weights**: Balanced the dataset to account for the minority disaster class.
- **Early Stopping**: Monitored validation F1 score with a patience of 2 epochs to prevent overfitting.
- **Optimizer**: Adam with a learning rate of 0.0001.

**Training Results:**
- **Validation F1 Score**: 0.7490 (peak at epoch 3).
- Training stopped at epoch 5 due to no further improvement in F1 score.

---

## Evaluation Results

The model was evaluated on the test set, yielding the following metrics:
- **Test F1 Score**: 0.7384
- **Test Accuracy**: 78%
- **Classification Report**:
  - Class 0 (Non-Disaster): Precision: 0.79, Recall: 0.84, F1 Score: 0.81
  - Class 1 (Disaster): Precision: 0.77, Recall: 0.71, F1 Score: 0.74

The weighted F1 score across classes was **0.78**.

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/disaster-detection-tweets.git
   cd disaster-detection-tweets
