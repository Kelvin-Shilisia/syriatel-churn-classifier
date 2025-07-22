# SyriaTel Churn Prediction - Binary Classification Project

## Project Overview

This project aims to build a **machine learning classifier** that predicts whether a customer will churn (stop doing business) from SyriaTel, a telecommunications company. Customer churn is a critical business problem in the telecom industry, as retaining existing customers is more cost-effective than acquiring new ones.

By analyzing historical customer data, this project provides actionable insights to help SyriaTel identify customers at risk of churning and take proactive measures to retain them.

---

## Problem Statement

**Objective:**  
Develop a binary classification model to **predict churn** (Yes/No) based on various features such as customer usage patterns, service plans, and customer service interactions.

**Target Variable:**  
`churn` — A boolean variable indicating whether a customer churned (`True`) or not (`False`).

---

## Dataset Description

The dataset contains 3,333 customer records with the following key features:

| Column                    | Description                                      |
|---------------------------|--------------------------------------------------|
| `state`                  | Customer's state of residence                    |
| `account length`         | Number of days the account has been active       |
| `area code`              | Regional telephone area code                     |
| `international plan`     | Whether customer has an international plan       |
| `voice mail plan`        | Whether customer has a voicemail plan            |
| `number vmail messages`  | Number of voicemail messages                     |
| `total day/eve/night minutes` | Total call minutes in various periods      |
| `total intl minutes`     | Total international call minutes                 |
| `customer service calls` | Number of calls made to customer service         |
| `churn`                  | Target variable (True = churned, False = retained) |

---

## Exploratory Data Analysis (EDA)

- **Data Cleaning**: Verified missing values, consistent data types.
- **Class Imbalance**: 90% of customers are retained, only 10% churned.
- **Correlation Analysis**: Notable features include `international plan`, `customer service calls`, and `total day charge`.
- **Visualizations**: 
  - Bar charts for churn distribution
  - Boxplots for numeric features
  - Heatmap for feature correlation

---

## Model Building Process

1. **Preprocessing**:
   - Label encoding for categorical variables (`international plan`, `voice mail plan`)
   - Dropped non-informative columns (`phone number`, `state`)
   - Standardized numerical features

2. **Handling Class Imbalance**:
   - Applied **SMOTE (Synthetic Minority Oversampling Technique)** to balance the dataset

3. **Train-Test Split**:
   - 80% training, 20% testing

4. **Model Training**:
   - Tried multiple models: Logistic Regression, Decision Tree, Random Forest, Gradient Boosting
   - Final model: **Random Forest Classifier**

5. **Model Evaluation**:
   - Accuracy: ~91%
   - ROC-AUC Score: **0.917**
   - Confusion Matrix: Low false positives, acceptable false negatives

---

## Results Interpretation

- The model is highly capable of distinguishing between churned and retained customers.
- A ROC-AUC score of **0.917** indicates **excellent classification performance**.
- Key predictors of churn include:
  - Having an **international plan**
  - High number of **customer service calls**
  - **Daytime call charges**

---

## Business Insights & Recommendations

### Insights
- Customers with international plans are more likely to churn.
- Increased customer service calls signal dissatisfaction.
- Higher charges during the day correlate with churn.

### Recommendations
- **Targeted Retention Campaigns**: Proactively engage at-risk customers.
- **Customer Service Quality**: Improve service experience and reduce complaint frequency.
- **Flexible Plans**: Offer incentives for heavy users, especially for international plans.

### Solutions
- Build a **real-time churn prediction tool**.
- Integrate with CRM to trigger alerts and offers for high-risk customers.
- Conduct **monthly churn risk reviews** using updated data.

---

## Technologies Used

- **Python 3.10+**
- **Pandas**, **NumPy**
- **Matplotlib**, **Seaborn** (EDA & visualizations)
- **Scikit-learn** (modeling & evaluation)
- **Imbalanced-learn (SMOTE)**
- **Jupyter Notebook**
- **PowerPoint** (Business Presentation)



## How to Run the Project

1. Clone the repo:

   ```bash
   git clone https://github.com/kelvin-shilisia/syriatel-churn-classifier.git
