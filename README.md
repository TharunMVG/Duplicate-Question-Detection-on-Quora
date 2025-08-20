# MiniLM + Self-Attention for Duplicate Question Detection (Quora)

This repository contains the implementation of my research project **"MiniLM model incorporated with a self-attention mechanism for duplicate question detection on the Quora Q&A platform"**, carried out as part of the **Centre for Data Science and Applied Machine Learning (CDSAML)** at PES University.

---

## Overview

Duplicate questions clutter Q&A platforms like Quora, making it harder to retrieve precise answers.  
This is addressed by enhancing the **MiniLM** transformer model with a **self-attention mechanism** to improve semantic understanding and context capture in question pairs.

Approach:
- **Multi-head self-attention**
- **Layer normalization**
- **Feedforward neural network layers**

This augmentation boosts MiniLM’s capacity to capture complex relationships between tokens, leading to significant performance gains in duplicate question detection.

**Final Result:**  
✅ **90.59% accuracy** on the Quora Duplicate Questions dataset  
---

## 🛠️ Key Features

- **MiniLM Backbone** – Lightweight transformer, 2.7× faster than BERT.
- **Custom Self-Attention Layer** – Captures long-range dependencies & nuanced semantic relations.
- **Fine-tuning on Quora Dataset** – Using Hugging Face Transformers.
- **Preprocessing Pipeline** – Lowercasing, special character removal, lemmatization, stopword removal.
- **Comprehensive Evaluation** – Accuracy, F1-score, Precision, Recall.

---

## 📊 Dataset

**Quora Question Pairs** dataset from [Kaggle](https://www.kaggle.com/datasets/quora/question-pairs-dataset) containing **404,351** labeled question pairs.

| Column       | Description                                          |
|--------------|------------------------------------------------------|
| `id`         | Row ID                                                |
| `qid1`       | Question 1 ID                                         |
| `qid2`       | Question 2 ID                                         |
| `question1`  | First question text                                   |
| `question2`  | Second question text                                  |
| `is_duplicate` | 1 if duplicate, 0 otherwise                         |

---

## ⚙️ Methodology

1. **Tokenization & Encoding** – Using `microsoft/MiniLM-L12-H384-uncased` from Hugging Face.
2. **Model Architecture**  
   - MiniLM as the base encoder.
   - Added custom **multi-head self-attention** block.
   - Residual connections, layer normalization, and feedforward network.
3. **Training**  
   - Optimizer: Adam
   - Learning rate scheduling & gradient clipping
   - Early stopping after convergence (~5 epochs)
4. **Evaluation**  
   - Metrics: Accuracy, F1, Precision, Recall
   - Compared against LSTM, BiLSTM, BERT, RoBERTa, CNN-LSTM hybrids.

---

## 📈 Results

| Model                          | Accuracy  |
|--------------------------------|-----------|
| LSTM                           | 69.92%    |
| BiLSTM                         | 71.98%    |
| BERT                           | 80.47%    |
| **MiniLM + Self-Attention**    | **90.54%**|


