# Sentiment Analysis of Tweets towards PT Esteh Indonesia Makmur
 
A comparison of Naïve Bayes and Support Vector Machine (SVM) for classifying public sentiment on Twitter (X) surrounding the Esteh Indonesia somasi controversy. This project was developed as part of an undergraduate thesis and is designed to run on Google Colab.
 
## Project Overview
 
This project analyzes tweets related to "es teh indonesia" and "somasi" collected between September 24–30, 2022. The goal is to compare how well Naïve Bayes and SVM perform at classifying tweets as positive or negative, with and without hyperparameter tuning.

## Pipeline
 
- **Data Collection:** Twitter scraping using snscrape and manual labeling
- **Preprocessing:** Cleansing, case folding, normalization, tokenizing, stopword removal, and stemming
- **Feature Extraction:** TF-IDF
- **Imbalance Handling:** SMOTE oversampling
- **Modeling:** Naïve Bayes and SVM, each tested with and without hyperparameter tuning
- **Evaluation:** Accuracy, precision, recall, F1-score, AUC-ROC, and AUC-PR

## Dataset
 
Tweets were collected from X (Twitter) using snscrape, filtered by the keywords "es teh indonesia" and "somasi" within the timeframe of September 24–30, 2022.

The dataset files are available in the `Dataset/Scraping/` folder.

## Results
 
| Model | Accuracy | Precision | Recall | F1-Score | AUC-ROC | AUC-PR |
| --- | --- | --- | --- | --- | --- | --- |
| NB Without Tuning | 80.26% | 62.80% | **73.92%** | 64.83% | 0.80 | **0.45** |
| NB With Tuning | 85.45% | 65.37% | 70.38% | **67.26%** | 0.77 | 0.37 |
| SVM Without Tuning | **90.39%** | 78.91% | 59.17% | 62.51% | **0.85** | 0.42 |
| SVM With Tuning | 90.39% | **82.86%** | 57.03% | 59.68% | 0.79 | 0.37 |
 
Overall, SVM without hyperparameter tuning performed best across the evaluated metrics.

## Repository Structure
 
```
sentiment-analysis/
├── Dataset/
│   └── Scraping/
│       ├── Es Teh Indonesia.csv
│       ├── Full Data.csv
│       ├── Somasi.csv
│       └── Kamus Normalisasi.csv
├── Sentiment Analysis Twitter.ipynb
└── README.md
```
 
## How to Run
 
1. Open the notebook in Google Colab.
2. Install the required libraries by running the first cell:
   ```
   !pip install demoji
   !pip install sastrawi
   !pip install imbalanced-learn
   !pip install scikit-learn
   ```
 
3. Upload your dataset or use the default one provided in the notebook.
4. Run cells step by step with Shift + Enter, or run all at once with Ctrl + F9.

## Libraries & Tools

Platform: Google Colab | Language: Python
 
Libraries: pandas, numpy, snscrape, Sastrawi, demoji, scikit-learn, imbalanced-learn, matplotlib, seaborn, WordCloud
