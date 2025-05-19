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
```


---

## 📂 Dataset

The dataset used is `mini_sparkify_event_data.json`, which includes user logs with events like:

- 🎵 Playing songs  
- 👍 Thumbs up / 👎 Thumbs down  
- 🔐 Logging in / out  
- 🔼 Submitting upgrade requests  
- 🔽 Submitting downgrade requests  
- ❌ Cancelling subscription  

---

## 🧪 Methodology

### 🔹 Data Cleaning
- Dropped rows with missing `userId` or `sessionId`
- Removed rows with empty or whitespace-only `userId`

### 🔹 Exploratory Data Analysis (EDA)
- Analyzed user behavior such as:
  - Listening time  
  - Types of events  
  - Number of songs played  
  - Session duration  
- Visualized churn distribution and correlations with user activity

### 🔹 Feature Engineering
- Created features like:
  - Number of thumbs up/down  
  - Total songs played  
  - Number of upgrade/downgrade events  
  - Total listening time  
  - Subscription level  
- Aggregated user-level metrics using Spark window functions

### 🔹 Modeling
Models trained using Spark MLlib:
- Logistic Regression  
- Random Forest  
- Gradient-Boosted Trees (GBT)  
- Naive Bayes  
- Support Vector Machines (SVM)  

Model performance evaluated using:
- **F1 Score** (primary metric due to class imbalance)  
- **Precision**  
- **Recall**

---

## 📊 Exploratory Data Analysis

Key insights from EDA:
- Churned users interacted with the app less frequently
- More downgrades observed among users who churned
- Less time spent listening correlated with higher churn probability

---

## 🛠️ Feature Engineering

Engineered user-level features include:
- 🎧 Number of sessions  
- 🎼 Number of songs played  
- 👍/👎 Thumb up/down counts  
- 🔼/🔽 Upgrade and downgrade counts  
- ⏱️ Total listening time  
- 💳 Subscription level  

All features were standardized prior to model training to ensure consistent scale and performance.

---

## 🤖 Modeling

Multiple classification models were trained:

| Model               | Description                                      |
|---------------------|--------------------------------------------------|
| Logistic Regression | Baseline binary classifier                       |
| Random Forest       | Handles nonlinear relationships well             |
| GBTClassifier       | Best F1 score, captures complex patterns         |
| SVM                 | Compared for completeness                        |
| Naive Bayes         | Simple probabilistic model, baseline comparison  |

---

## ✅ Results

- 🏆 **Best Performing Model**: Gradient-Boosted Trees (GBTClassifier)
- 📏 **Evaluation Metric**: F1 Score  
- 💡 **Reason**: GBT captured nonlinear patterns and performed best under class imbalance

---

## 📌 Conclusion

This end-to-end churn prediction pipeline demonstrates the power of Spark in handling large-scale event data, allowing:

- Efficient data cleaning and processing  
- Scalable feature engineering  
- Fast and distributed model training  

These insights can help businesses proactively reduce churn and improve user retention with targeted incentives.

---

## 🚀 Future Work

- 📈 Implement model interpretability (e.g., SHAP or LIME)  
- 🌐 Train on full 12GB dataset using a distributed Spark cluster  
- 🛠️ Deploy model as a REST API for real-time churn prediction  

---



