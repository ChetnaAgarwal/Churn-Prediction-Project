# Churn Prediction for a Music Streaming Service 🎵
Churn Prediction Project for a Music Streaming Service using PySpark

### Author: Chetna Agarwal

This project focuses on predicting customer churn for a music streaming service similar to Spotify. The goal is to identify users likely to cancel their subscription using user activity logs and behavioral features, enabling the business to proactively retain users through incentives.

---

## 🧠 Project Overview

Churn, in this context, refers to a user canceling their service. Identifying users at risk of churning allows businesses to take preemptive measures and reduce revenue loss. This project uses a **mini dataset (128MB)** derived from a larger 12GB dataset and processes it using **Apache Spark** to ensure scalable and efficient data handling.

---

## 📑 Table of Contents

- [Installation](#installation)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Feature Engineering](#feature-engineering)
- [Modeling](#modeling)
- [Results](#results)
- [Conclusion](#conclusion)

---

## ⚙️ Installation

To run this project, you need the following libraries installed:

- Python ≥ 3.7
- PySpark
- pandas
- numpy
- matplotlib
- seaborn

You can install them via:

```bash
pip install pyspark pandas numpy matplotlib seaborn



📂 Dataset
The dataset used is mini_sparkify_event_data.json, which includes user logs with events like:

Playing songs

Thumbs up/down

Logging in/out

Submitting upgrade/downgrade requests

Cancelling subscription

🧪 Methodology
Data Cleaning

Dropped rows with missing userId or sessionId

Removed rows with empty or whitespace-only userId

Exploratory Data Analysis (EDA)

Analyzed user behavior like listening time, event types, number of songs, session duration, etc.

Visualized churn distribution and its relationship to user activities

Feature Engineering

Created features like number of thumbs up, total songs played, downgrade/upgrade events, and more

Aggregated user-level features using Spark window functions

Modeling

Used MLlib models including:

Logistic Regression

Random Forest

Gradient-Boosted Trees

Naive Bayes

Support Vector Machines

Evaluated models using F1 score, precision, and recall

📊 Exploratory Data Analysis
EDA helped uncover trends such as:

Churned users often had fewer interactions

Downgrades were more frequent among churned users

Less time spent on the platform often indicated churn

🛠️ Feature Engineering
Engineered features include:

Number of sessions

Number of songs played

Thumb up/down counts

Downgrade and upgrade counts

Total listening time

User's subscription level

All features were standardized before modeling.

🤖 Modeling
Several classification models were trained and evaluated:

Model	Notes
Logistic Regression	Baseline binary classifier
Random Forest	Strong performance on nonlinear features
GBTClassifier	Achieved best F1 score
SVM & Naive Bayes	Compared for completeness

✅ Results
Best Model: Gradient-Boosted Trees

Evaluation Metric: F1 score to handle class imbalance

GBT achieved the highest predictive performance by capturing nonlinear relationships.

📌 Conclusion
The project demonstrates a full pipeline of handling large-scale event data using Spark, from data cleaning and feature engineering to predictive modeling. These insights can help businesses make informed decisions to reduce churn and improve customer retention.

🚀 Future Work
Implement model interpretability using SHAP

Train on full 12GB dataset using distributed Spark cluster

Deploy model as a REST API for real-time churn prediction




