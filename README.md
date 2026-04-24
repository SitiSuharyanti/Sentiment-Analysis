# Sentiment Analysis of Twitter Users towards PT Esteh Indonesia Makmur

### Comparison of Naïve Bayes and Support Vector Machine Algorithms

## Overview

This project is an undergraduate thesis that performs **sentiment analysis** on Twitter (X) data related to PT Esteh Indonesia Makmur, classifying tweets as **positive** or **negative**. The study compares two machine learning algorithms — **Naïve Bayes** and **Support Vector Machine** — with and without hyperparameter tuning, to determine which performs better on this dataset.

---

## Repository Structure

```
sentiment-analysis/
│
├── Dataset/
│   └── (Twitter dataset collected via snscrape)
│
├── Port_2_Analisis_Sentimen_Siti_Suharyanti_Skripsi.ipynb
│
└── README.md
```

---

## Dataset

- **Source:** Twitter (X) — scraped using the `snscrape` library
- **Keywords:** "es teh indonesia" and "somasi"
- **Timeframe:** September 24–30, 2022
- **Labels:** Positive, Negative
- **Labeling method:** Manual

---

## Methodology

### 1. Data Collection

- Scraping Twitter data using `snscrape`
- Manual labeling of tweets

### 2. Preprocessing

- **Cleansing** — removing URLs, mentions, hashtags, and special characters
- **Case Folding** — converting all text to lowercase
- **Normalization** — standardizing informal/slang words
- **Tokenizing** — splitting text into individual tokens
- **Stopword Removal** — removing common words with low information value
- **Stemming** — reducing words to their root form using Sastrawi

### 3. Feature Extraction

- **TF-IDF** (Term Frequency-Inverse Document Frequency)

### 4. Handling Class Imbalance

- **SMOTE** (Synthetic Minority Over-sampling Technique) using `imbalanced-learn`

### 5. Modelling

| Model       | Tuning                                    |
| ----------- | ----------------------------------------- |
| Naïve Bayes | Without Hyperparameter Tuning             |
| Naïve Bayes | With Hyperparameter Tuning (GridSearchCV) |
| SVM         | Without Hyperparameter Tuning             |
| SVM         | With Hyperparameter Tuning (GridSearchCV) |

### 6. Evaluation Metrics

- Accuracy, Precision, Recall, F1-Score, AUC-ROC, AUC-PR

---

## Results

| Model              | Accuracy   | Precision  | Recall | F1-Score | AUC-ROC  | AUC-PR |
| ------------------ | ---------- | ---------- | ------ | -------- | -------- | ------ |
| NB Without Tuning  | 80.26%     | 62.80%     | 73.92% | 64.83%   | 0.80     | 0.45   |
| NB With Tuning     | 85.45%     | 65.37%     | 70.38% | 67.26%   | 0.77     | 0.37   |
| SVM Without Tuning | **90.39%** | **78.91%** | 59.17% | 62.51%   | **0.85** | 0.42   |
| SVM With Tuning    | **90.39%** | **82.86%** | 57.03% | 59.68%   | 0.79     | 0.37   |

> **Conclusion:** SVM without hyperparameter tuning performs best overall, achieving the highest accuracy (90.39%) and AUC-ROC (0.85).

---

## How to Run

This project is designed to run on **Google Colab**.

1. Open the notebook in Google Colab
2. Install the required libraries by running the first cell:

```bash
!pip install demoji
!pip install sastrawi
!pip install imbalanced-learn
!pip install scikit-learn
```

3. Upload your dataset or use the default dataset provided
4. Run all cells with `Ctrl + F9` or step by step with `Shift + Enter`

---

## Libraries & Tools

| Library                 | Purpose                  |
| ----------------------- | ------------------------ |
| `pandas`, `numpy`       | Data manipulation        |
| `snscrape`              | Twitter data scraping    |
| `Sastrawi`              | Indonesian stemming      |
| `demoji`                | Emoji removal            |
| `scikit-learn`          | ML modeling & evaluation |
| `imbalanced-learn`      | SMOTE oversampling       |
| `matplotlib`, `seaborn` | Data visualization       |
| `WordCloud`             | Word cloud visualization |
