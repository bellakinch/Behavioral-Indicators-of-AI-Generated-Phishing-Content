# Behavioral-Indicators-of-AI-Generated-Phishing-Content
NLP analysis of 4,000 emails using behavioral indicators and machine learning to distinguish AI-generated from human-written content and phishing from legitimate emails.

## Overview

# Behavioral Indicators of AI-Generated Phishing Content

## Overview

This project developed and evaluated machine learning classifiers using behavioral indicators derived from a taxonomy-based framework. It addressed two classification tasks:

1. Distinguishing AI-generated emails from human-written emails.
2. Distinguishing phishing emails from legitimate emails.

The workflow combined behavioral taxonomy development, rule-based lexicon matching, automatic scoring, and machine learning evaluation.

## Dataset

The project used 4,000 emails containing both human-written and LLM-generated content, including phishing and legitimate messages.

According to the dataset description, human-written phishing emails were sourced from the Nazario and Nigerian Fraud datasets, while LLM-generated emails were produced using ChatGPT and WormGPT.

**Dataset source:** [Human & LLM-Generated Phishing and Legitimate Emails — Kaggle](https://www.kaggle.com/datasets/francescogreco97/human-llm-generated-phishing-legitimate-emails/data)

## Phase 1: Behavioral Taxonomy Development

The first phase established a behavioral taxonomy: a structured framework for organizing email characteristics into categories that could support automatic labeling and machine learning.

Five indicators were selected based on prior cybersecurity research:

| Indicator | Description |
|---|---|
| Urgency | Pressures the recipient to act quickly without careful consideration. |
| Authority framing | Invokes or impersonates trusted organizations or figures, such as banks, security teams, or government agencies. |
| Emotional manipulation | Uses fear, excitement, or other emotions to influence the recipient. |
| Targeted messaging | Uses personalized or context-specific language to appear authentic to a particular recipient. |
| Action requests | Directs the recipient to take a specific action, such as clicking a link, verifying an account, or making a payment. |

## Phase 2: Lexicon Matching and Automatic Labeling

A lexicon of keywords and phrases was developed for each behavioral indicator. For example, urgency terms included “act now” and “within 24 hours,” while authority terms referenced banks, security teams, and government agencies.

A rule-based labeling system scanned each email for matching terms and assigned a score from **0 to 3** for each indicator:

- **0:** No matching evidence detected.
- **1–3:** Increasing levels of the indicator detected by the scoring rules.

This process produced five behavioral features for each email, allowing thousands of messages to be scored without manually annotating every message. These scores represented lexicon-based indicators rather than independently verified judgments of intent.

## Phase 3: Machine Learning Classification and Reporting

The behavioral scores were used as inputs to machine learning classifiers, including **Logistic Regression** and **Random Forest**.

Separate models addressed AI-generated versus human-written content and phishing versus legitimate content. Performance was evaluated using:

- Accuracy
- F1 score
- ROC-AUC
- Confusion matrices
- Classification reports

Feature importance analysis examined which behavioral indicators contributed most strongly to the predictions.

## Results

| Classification Task | Held-Out Accuracy | F1 Score | ROC-AUC |
|---|---:|---:|---:|
| AI-generated vs. human-written | 90.4% | 0.900 | 0.961 |
| Phishing vs. legitimate | 76.5% | 0.758 | 0.834 |

Targeted messaging was the most influential feature for distinguishing AI-generated from human-written emails. Action requests were the most influential feature for distinguishing phishing from legitimate emails.

These findings describe performance on the evaluated dataset and do not establish equivalent performance on unseen real-world email sources.

## Streamlit Application

A Streamlit application was developed to analyze pasted email text and display classification predictions alongside the matched keywords associated with the behavioral indicators.

## Technologies

Python, Pandas, scikit-learn, Streamlit, rule-based NLP, and lexicon matching.

## Contributors

Bella Kinch, David Jimenez, and Franklin Araujo.
