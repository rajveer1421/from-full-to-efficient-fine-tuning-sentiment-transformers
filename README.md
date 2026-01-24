# GloVe-Based Sentiment Transfer Learning for Movie Recommendation

This project explores **cross-domain transfer learning in Natural Language Processing (NLP)** using **GloVe word embeddings**.  
The objective is to study how sentiment knowledge learned from a **news classification domain (AG News)** can improve performance on a **movie review sentiment analysis task (IMDB)** and enable basic **movie recommendation based on review sentiment**.

---

## 📌 Project Overview

The project is divided into three major stages:

1. **Baseline Sentiment Model on IMDB**
   - Train a sentiment classification model directly on the IMDB movie reviews dataset.
   - Use pretrained **GloVe embeddings** for word representation.

2. **Cross-Domain Training and Fine-Tuning**
   - Train a separate model on the **AG News dataset** using the same GloVe embeddings.
   - Fine-tune the pretrained model on the **IMDB dataset**.
   - Compare performance with the baseline IMDB-only model.

3. **Movie Recommendation Based on Reviews**
   - Use the trained sentiment model to analyze movie reviews.
   - Recommend movies based on aggregated positive sentiment scores.

---

## 🧠 Motivation

Transfer learning is widely used in NLP, but most implementations rely on large transformer models.  
This project focuses on **classic word embeddings (GloVe)** to understand:

- How much transferable sentiment knowledge exists across domains
- Whether pretraining on non-movie text (news articles) improves movie review sentiment analysis
- The effectiveness of lightweight NLP models compared to large transformer-based approaches

---

## 🧾 Datasets Used

- **IMDB Movie Reviews**
  - Binary sentiment classification (positive / negative)
  - 50,000 labeled reviews

- **AG News**
  - Multi-class news classification dataset
  - Used for pretraining textual representations

---

## 🛠️ Model Architecture

- Embedding Layer initialized with **pretrained GloVe vectors**
- Sequence model (LSTM / CNN-based text classifier)
- Fully connected classification head
- Padding and batching handled via custom DataLoader and collate functions

---

## ⚙️ Training Strategy

1. Train IMDB baseline model from scratch using GloVe
2. Train AG News model using the same embedding space
3. Transfer weights and fine-tune on IMDB
4. Evaluate and compare:
   - Accuracy
   - Loss convergence
   - Generalization behavior

---

## 📊 Evaluation

- Classification accuracy on IMDB test set
- Comparison between:
  - IMDB-only training
  - AG News pretraining + IMDB fine-tuning
- Qualitative review sentiment inspection

---

## 🎬 Movie Recommendation Logic

- Predict sentiment for multiple reviews of a movie
- Aggregate sentiment scores
- Recommend movies with consistently positive review sentiment

---

## 📁 Project Structure (planned)

