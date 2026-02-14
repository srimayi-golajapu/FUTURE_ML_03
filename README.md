# FUTURE_ML_03
## Support Ticket Classification and Prioritization System

# Overview

This project builds an automated support ticket classification and prioritization system for IT service environments. The goal is to reduce manual ticket triaging and improve response efficiency using machine learning and rule-based decision logic.

The system reads raw support ticket text, assigns it to the correct support category, and determines an operational priority level.

# Problem Statement

Support teams receive thousands of tickets daily. Manual sorting causes:
Delays in response
Incorrect routing to teams
Increased backlog
Wasted operational time
This project solves that by automatically categorizing and prioritizing incoming tickets.

# Dataset

Dataset: IT Service Ticket Classification Dataset
Source: Kaggle
Total samples: 47,837
# Features:

Document: Ticket text
Topic_group: Support category label

# Classes:

Access
Administrative rights
HR Support
Hardware
Internal Project
Miscellaneous
Purchase
Storage
Methodology
Data Preparation
Used raw ticket text
Removed stopwords using TF-IDF built-in preprocessing
Converted text into numerical features using TF-IDF with bi-grams

# Feature Extraction

TfidfVectorizer
max_features=20000
ngram_range=(1,2)
min_df=2
max_df=0.95
stop_words="english"

# Model

Linear Support Vector Machine (LinearSVC)
80/20 train-test split
No data leakage via sklearn Pipeline
Evaluation Metrics
Accuracy
Precision
Recall
F1-score
Confusion Matrix
Results
Overall Accuracy: 85.14%

# Key Observations:

Strong performance for Purchase, Access, and Storage categories
Logical confusion between Administrative rights and Access
Balanced macro and weighted F1 scores
The confusion matrix shows dominant diagonal values, indicating strong category separation.
Priority Assignment
Since the dataset does not include priority labels, a hybrid scoring mechanism was implemented.
Priority is determined using:
Urgency keywords such as urgent, asap, system down, error
Critical topic groups such as Hardware and Access

# Priority Levels:

High
Medium
Low
This simulates real enterprise ticket routing systems where ML-based routing is combined with rule-based urgency detection.
Business Impact
Reduces manual ticket sorting effort
Improves routing accuracy
Decreases first response time
Scales support operations without increasing headcount
Enables faster handling of critical system failures

# Project Structure

support_ticket_classification_system.ipynb
README.md
.gitignore

# Future Improvements:

Add probability-based confidence scoring
Train a separate ML model for priority prediction
Deploy as REST API using Flask or FastAPI
Integrate with ticket management platforms

# How to Run

Install dependencies:
pip install pandas scikit-learn matplotlib seaborn

Open the Jupyter Notebook:
support_ticket_classification_system.ipynb

Run all cells sequentially.
