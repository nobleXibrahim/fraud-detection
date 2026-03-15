# Fraud Detection in Mobile Money Transactions Using Machine Learning

**TS Academy Capstone Project – Group 12**

## Project Overview

The growth of digital payment platforms and mobile money services has significantly increased the need for reliable fraud detection systems. Fraudulent transactions can lead to major financial losses for both financial institutions and users.

This project focuses on applying machine learning techniques to identify suspicious transactions within a large dataset of mobile money activities.

The study uses the **PaySim dataset**, a financial transaction simulator that reflects the behaviour of real mobile money systems. With over **5.4 million transaction records**, the dataset provides a realistic environment for analyzing fraud patterns and building predictive models.

The main objective of the project is to explore how machine learning algorithms can detect fraudulent transactions while addressing challenges such as:

* Large-scale data processing
* Highly imbalanced datasets

---

## Dataset Description

The dataset used in this project is the **PaySim fraud detection dataset**, which simulates mobile money transactions.

**Dataset Characteristics**

* **Total records:** 5,420,481
* **Number of features:** 27
* **Target variable:** `isFraud`

The dataset contains information about different types of financial transactions, including:

* Transaction type
* Transaction amount
* Sender account balance before and after the transaction
* Receiver account balance before and after the transaction

### Class Imbalance

A major challenge in this dataset is **class imbalance**:

* Fraudulent transactions represent **less than 1%** of the dataset.
* The majority of transactions are legitimate.

This imbalance makes fraud detection difficult because models may become biased toward predicting the majority class.

Despite this challenge, the dataset contains valuable patterns that can help identify fraudulent behaviour.

---

## Data Preparation and Analysis

Before model development, several preprocessing steps were performed.

### Data Cleaning

The dataset was checked for:

* Missing values
* Duplicate records

No missing values or duplicates were found.

### Memory Optimization

Due to the large dataset size, **memory optimization techniques** were applied by converting large numeric data types into smaller ones. This reduced memory usage and improved computational efficiency.

### Exploratory Data Analysis (EDA)

Exploratory analysis revealed several important patterns:

**1. Transaction Types**
Fraud occurred most frequently in:

* `TRANSFER`
* `CASH_OUT`

These transaction types allow funds to move quickly between accounts, making them more vulnerable to fraudulent activity.

**2. Transaction Amounts**
Fraudulent transactions often involved **unusually large amounts** compared to typical transactions.

**3. Account Balance Behavior**
In many fraud cases, the transaction amount was close to the sender’s total balance, indicating attempts to **drain accounts completely**.

These insights helped identify important features for training the fraud detection models.

---

## Machine Learning Models

Two classification models were implemented in this project.

### Logistic Regression

Logistic Regression was used as a **baseline model**.

It is commonly used for binary classification problems and estimates the probability that a transaction belongs to one of two classes:

* Fraudulent
* Legitimate

### Random Forest

Random Forest is an **ensemble learning algorithm** that combines multiple decision trees.

Advantages include:

* Ability to capture complex relationships
* Strong performance on large datasets
* Reduced risk of overfitting

---

## Model Evaluation

The models were evaluated using several performance metrics:

* **Accuracy**
* **Precision**
* **Recall**
* **F1-score**

### Why Recall Matters

In fraud detection, **recall is a critical metric** because it measures how many fraudulent transactions the model correctly identifies.

Missing fraudulent transactions could result in significant financial losses.

### Results

**Logistic Regression**

* Achieved very high recall
* Detected most fraud cases
* Produced more **false positives**

**Random Forest**

* Achieved approximately **97.5% recall**
* Maintained a better balance between **precision and recall**
* Reduced unnecessary fraud alerts

Overall, the **Random Forest model provided the best performance balance**.

---

## Conclusion

This project demonstrates how machine learning techniques can be applied to detect fraudulent transactions in mobile money systems.

By analyzing transaction behaviour and account activity, models can identify patterns associated with fraudulent behaviour.

Among the models tested, **Random Forest delivered the most balanced performance**, effectively detecting fraud while minimizing false alerts.

These results show that machine learning can play a significant role in improving fraud detection systems and helping financial institutions identify suspicious transactions more effectively.

---
