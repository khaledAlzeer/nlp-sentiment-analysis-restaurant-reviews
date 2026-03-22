# 🍽️ NLP – Restaurant Reviews Sentiment Analysis

A Natural Language Processing project that classifies restaurant reviews as **Positive** or **Negative**
using the Bag of Words model with multiple machine learning classifiers.

---

## 📌 Project Overview

This project is part of the **Machine Learning A-Z** course (Udemy) – Part 7: Natural Language Processing Homework Challenge.

The goals are to:
- Preprocess and clean raw text reviews
- Build a Bag of Words feature matrix
- Train and evaluate multiple classifiers
- Compare models using Accuracy, Precision, Recall, and F1 Score
- Predict the sentiment of new unseen reviews

---

## 📂 Dataset

| File | Description |
|------|-------------|
| `Restaurant_Reviews.tsv` | 1000 restaurant reviews labeled as Positive (1) or Negative (0) |

---

## 🔄 Project Pipeline
```
Raw Text Reviews
      ↓
Text Cleaning
  ├── Regex       → remove numbers, punctuation & special characters ([^a-zA-Z])
  ├── Lowercase   → convert all text to lowercase
  ├── Tokenization → split sentence into individual words
  ├── Stopwords   → remove common words (e.g. "the", "is") — keeping "not"
  └── Stemming    → reduce words to root form (e.g. "loved" → "love")
      ↓
Bag of Words (CountVectorizer, max_features=1500)
      ↓
Train/Test Split (80% / 20%, random_state=0)
      ↓
Model Training & Evaluation
      ↓
Performance Visualization
      ↓
Single Review Prediction
```

---

## 🤖 Models Compared

| Model | Accuracy | Precision | Recall | F1 Score |
|-------|----------|-----------|--------|----------|
| Gaussian Naive Bayes | 0.73 | 0.68 | 0.88 | 0.77 |
| Random Forest (n=300) | 0.76 | 0.88 | 0.62 | 0.73 |

> ✅ **Selected Model: Random Forest** — highest Precision (0.88), meaning fewer false
> positives compared to the Naive Bayes baseline (0.68).
> For a restaurant review context, predicting a bad review as good is more costly
> than missing a good one — making Precision the priority metric.

---

## 📊 Performance Visualization

Each model includes:
- **Confusion Matrix Heatmap** with TN / FP / FN / TP labels
- **Bar Chart** comparing Accuracy, Precision, Recall, and F1 Score

---

## 🔍 Single Review Prediction

Both models were tested on new unseen reviews:

| Review | Naive Bayes | Random Forest |
|--------|-------------|---------------|
| "I love this restaurant so much" | Positive ✅ | Positive ✅ |
| "I hate this restaurant so much" | Negative ❌ | Negative ❌ |

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Sklearn](https://img.shields.io/badge/Scikit--learn-ML-orange)
![NLTK](https://img.shields.io/badge/NLTK-NLP-green)
![Colab](https://img.shields.io/badge/Google-Colab-yellow)

- Python 3
- Pandas, NumPy
- NLTK (stopwords, PorterStemmer)
- Scikit-learn
- Matplotlib, Seaborn
- Google Colab

---

## 🚀 How to Run

1. Clone the repo
```bash
   git clone https://github.com/<your-username>/nlp-sentiment-analysis-restaurant-reviews.git
```

2. Upload `Restaurant_Reviews.tsv` to your Colab environment

3. Open and run `natural_language_processing.ipynb` cell by cell

---

## 📁 Repository Structure
```
nlp-sentiment-analysis-restaurant-reviews/
│
├── natural_language_processing.ipynb   # Main notebook
├── Restaurant_Reviews.tsv              # Dataset
└── README.md                           # Project documentation
```

---
