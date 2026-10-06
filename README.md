# Behavioral-Indicators-of-AI-Generated-Phishing-Content
NLP analysis of 4,000 emails using behavioral indicators and machine learning to distinguish AI-generated from human-written content and phishing from legitimate emails.

## Overview

This research project was completed during a Data Intern / Research Assistant position at the University at Albany. It explores how behavioral indicators in email language can help distinguish AI-generated from human-written emails and phishing from legitimate emails.

## Methods

- Automatically labeled 4,000 emails using a rule-based NLP lexicon covering urgency, authority, emotion, targeting, and action.
- Trained and evaluated Random Forest, Logistic Regression, and SVM classifiers.
- Examined classification performance using accuracy, F1 score, ROC-AUC, and confusion matrices.
- Analyzed feature importance to identify influential behavioral indicators.
- Developed a Streamlit application displaying predictions and matched keywords.

## Results

- **AI vs. human:** 90.4% held-out accuracy.
- **Phishing vs. legitimate:** 76.5% held-out accuracy.
- Targeting was the most influential feature for AI-generated content classification; action requests were the most influential for phishing classification.

## Technologies

Python, Pandas, scikit-learn, NLP, Streamlit

## Contributors

Bella Kinch, David Jimenez, and Franklin Araujo
