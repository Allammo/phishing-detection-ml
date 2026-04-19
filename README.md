# Phishing Website Detection using Machine Learning

*Cybersecurity · Binary Classification · NLP · Transformer · Feature Engineering*

---

## Overview

A large-scale machine learning pipeline for detecting phishing websites using URL and content-based features. Four model families are implemented and compared — from classical ML baselines to a Transformer-based classifier — on a dataset of 235,000+ samples with 56 engineered features.

Model generalization is validated on a held-out external dataset, confirming real-world robustness.

---

## Results

| Model | Accuracy | F1 Score |
|---|---|---|
| Logistic Regression | ~99% | ~0.99 |
| SVM | ~99% | ~0.99 |
| XGBoost | ~99–100% | ~0.99 |
| Transformer | 99% | 0.99 |
| **External dataset validation** | **~99%** | — |

---

## Methodology

1. **Feature engineering** — 56 features extracted from URL structure, domain properties, HTML content, and JavaScript behavior
2. **Preprocessing** — normalization, handling class imbalance
3. **Model training** — Logistic Regression, SVM, XGBoost, and a custom Transformer classifier
4. **Hyperparameter tuning** — grid search and cross-validation for each model
5. **Generalization test** — full pipeline re-evaluated on an independent external dataset

---


> **Dataset:** Based on the [UCI Phishing Websites Dataset](https://archive.ics.uci.edu/dataset/327/phishing+websites) and extended features. See notebook for full sourcing details.


## Tech stack

Python · Scikit-learn · XGBoost · PyTorch · Pandas · Matplotlib · Seaborn

---

## Key takeaways

- All four model families achieved near-identical accuracy, suggesting the features carry most of the predictive signal
- The Transformer's advantage shows on edge cases — low-confidence predictions where classical models struggle
- Feature importance analysis identifies URL length, HTTPS usage, and domain age as the strongest predictors
