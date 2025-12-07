# CardDefender: Credit Card Fraud Detection Pipeline
![Project Status](https://img.shields.io/badge/Project_Status-Completed-brightgreen.svg)
![Models](https://img.shields.io/badge/Models-Random_Forest_|_Logistic_Regression-orange.svg)
![Framework](https://img.shields.io/badge/Framework-Scikit_Learn-yellow.svg)
![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)

## **1. Problem Statement**

Credit card fraud is a major financial challenge. Millions of transactions occur daily, and fraudulent activity can cause significant monetary loss. Manual inspection of transactions is impossible due to data scale and speed requirements.

**Goal:**
Build a machine learning pipeline that identifies fraudulent transactions accurately, even when the dataset is extremely imbalanced.

<img width="1874" height="1012" alt="Image" src="https://github.com/user-attachments/assets/e1c357b5-9fe7-4fc4-b612-3a8d5ffe9162" />

<img width="1872" height="1011" alt="Image" src="https://github.com/user-attachments/assets/70d806a2-659e-4d8d-97ed-2f427fcdc3e0" />

---

## **2. Motivation**

* Fraudulent activities cause billions in financial loss annually.
* Transaction data streams are high volume and must be processed automatically.
* Fraud cases are rare, which makes traditional machine learning techniques perform poorly.
* Building a reliable fraud detection system is crucial for banks, fintech services, and e-commerce.

**Why this project matters:**
A strong fraud detection model improves financial security, protects customers, and enhances trust in digital payment systems.

---

## **3. Dataset Description**

* Total Rows: **284,807 transactions**
* Fraudulent Transactions: **492**
* Legitimate Transactions: **284,315**
* Fraud Ratio: **0.172 percent**

**Features:**

* Most features (`V1` to `V28`) are PCA-transformed to protect customer privacy.
* Includes `Amount` and `Time` features.
* `Class` column is the target:

  * **0 = Legitimate**
  * **1 = Fraudulent**

**Dataset Used:**
Kaggle – Credit Card Fraud Detection
Link: [https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

This dataset contains real credit card transactions made in Europe. It is highly imbalanced, with fraudulent transactions making up only **0.172 percent** of the data.

<img width="1871" height="1006" alt="Image" src="https://github.com/user-attachments/assets/cf882dea-22f6-46f0-b481-051edfbee441" />

---

## **4. Challenges**

1. **Severe Class Imbalance**
   Fraud cases are extremely rare, making it difficult for classifiers to learn meaningful patterns.

2. **Hidden Patterns**
   Features are PCA components, so fraud patterns are not directly interpretable.

3. **High Precision Required**
   False positives inconvenience customers, while false negatives allow fraud to pass undetected.

<img width="1876" height="1016" alt="Image" src="https://github.com/user-attachments/assets/2a9e9b43-1412-445e-8d88-6936ecf132aa" />
<img width="1874" height="1007" alt="Image" src="https://github.com/user-attachments/assets/669c41af-5ea7-48bf-a5de-bcb5f698c5e8" />

---

## **5. Project Pipeline**

1. Load and explore dataset
2. Handle imbalance (SMOTE, undersampling, oversampling or class weighting)
3. Preprocess features (scaling, splitting)
4. Train models (Random Forest, Logistic Regression or others)
5. Evaluate using metrics suitable for imbalanced data
6. Compare performance for balanced vs. imbalanced approaches
7. Generate confusion matrix and classification report
8. Final conclusions and improvements

---

## **6. Handling Imbalanced Data**

Your notebooks include two approaches:

### **A. Without Balancing**

* Train ML model directly on the original dataset
* Model tends to predict everything as non-fraud
* High accuracy, low recall

### **B. With Imbalance Handling (SMOTE / Undersampling / Oversampling)**

* Balances the dataset before training
* Helps model detect minority (fraud) cases
* Improves recall and F1-score for fraud class

---

## **7. Models Used**

The notebooks generally include:

### **Random Forest Classifier**

* Handles nonlinear patterns
* Robust and easy to tune
* Works well on fraud datasets

### **Logistic Regression (optional)**

* Baseline linear model
* Useful for comparison
  
---

## **8. Evaluation Metrics**

<img width="1874" height="1008" alt="Image" src="https://github.com/user-attachments/assets/2a819e26-3253-4a12-a3ce-a0ef133d822e" />

<img width="1872" height="1006" alt="Image" src="https://github.com/user-attachments/assets/1420e16b-7d08-4722-8f82-509596173570" />

<img width="1875" height="1012" alt="Image" src="https://github.com/user-attachments/assets/b909b4d6-8c3a-423a-a53c-3e3101ae9dfc" />

<img width="1881" height="1016" alt="Image" src="https://github.com/user-attachments/assets/1d057995-0012-499f-b2db-8702c938bb44" />

<img width="1875" height="998" alt="Image" src="https://github.com/user-attachments/assets/e7c302ed-08e8-4491-993a-af18d0d1962d" />

---

## **9. Confusion Matrix Interpretation**

A confusion matrix helps analyze:

* True Negatives (legitimate correctly identified)
* True Positives (frauds correctly caught)
* False Negatives (frauds missed — most dangerous)
* False Positives (legitimate flagged as fraud — customer inconvenience)

Balancing techniques usually reduce **False Negatives**, which is essential for fraud systems.

<img width="1877" height="1020" alt="Image" src="https://github.com/user-attachments/assets/de0dad12-adcd-4f82-9c70-7325e1a3b5a6" />

---

## **10. Insights & Discussion**

* Imbalance handling dramatically improves fraud detection.
* Random Forest generally performs better than Logistic Regression in nonlinear PCA-transformed space.
* Fraud patterns exist but require proper feature scaling and minority oversampling to be learned.

---

## **11. Limitations**

* PCA transformation hides interpretability
* Synthetic balancing (like SMOTE) may introduce noise
* Dataset lacks real-world contextual features such as location, merchant ID, or device type
* Models may not generalize perfectly to new fraud strategies

<img width="1869" height="1010" alt="Image" src="https://github.com/user-attachments/assets/87492194-79b9-49fa-adc9-7e8dac6d979c" />

---

## **12. Future Work**

* Use **XGBoost** or **LightGBM** for improved detection
* Add time-series modeling (fraud often shows patterns over time)
* Implement anomaly detection methods
* Deploy model in real-time detection pipeline
* Train transformer models for sequential fraud detection

<img width="1867" height="1016" alt="Image" src="https://github.com/user-attachments/assets/fc1c4a6d-0575-4c27-b3ac-81faf1f860db" />

---

## **13. Glossary**

* **SMOTE**: Synthetic Minority Oversampling Technique
* **Oversampling**: Duplicate or synthesize more minority samples
* **Undersampling**: Remove majority samples
* **PCA**: Dimensionality reduction technique used for anonymization
* **Precision**: Correct fraud predictions
* **Recall**: Ability to detect fraud cases
* **F1 Score**: Balanced metric for imbalanced datasets

---
