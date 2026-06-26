# Student Stress Prediction using Machine Learning

## Overview

This project aims to predict whether a student is **stressed** or **not stressed** using machine learning techniques. The objective is to build a classification model that can identify stressed students as accurately as possible, helping educational institutions detect students who may require timely support.

---

## Problem Statement

Student stress has become a significant concern due to academic pressure, social media usage, sleep patterns, and family support. Early identification of stressed students can help institutions provide counseling and improve student well-being.

The primary objective of this project is to minimize **False Negatives**, ensuring that as many stressed students as possible are correctly identified.

---

## Dataset

**Dataset:** Student Lifestyle and Stress Dataset

### Features

* Student_Type
* Sleep_Hours
* Study_Hours
* Social_Media_Hours
* Attendance
* Exam_Pressure
* Family_Support
* Month

**Target Variable**

* Stress_Level (Binary Classification)

---

## Project Workflow

### 1. Data Cleaning

* Checked missing values
* Handled missing categorical values using **Mode Imputation**
* Handled missing numerical values using:

  * Mean (for approximately symmetric distributions)
  * Median (for skewed distributions)
* Removed duplicate records
* Verified data types

---

### 2. Exploratory Data Analysis (EDA)

Performed analysis to understand:

* Class distribution
* Feature distributions
* Missing values
* Correlation between numerical features
* Feature relationships

---

### 3. Data Preprocessing

* One-Hot Encoding for categorical variables
* Standard Scaling for numerical features
* Train-Test Split
* Feature preprocessing using training data to prevent data leakage

---

### 4. Models Implemented

* Logistic Regression
* Logistic Regression (`class_weight='balanced'`)
* K-Nearest Neighbors (KNN)
* Gaussian Naive Bayes
* Support Vector Machine (SVM)

---

### 5. Model Evaluation

The following evaluation metrics were used:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

Training and testing performance were compared to detect overfitting.

---

### 6. Threshold Tuning

Since the primary objective was to identify stressed students, threshold tuning was performed on Logistic Regression.

Different thresholds (0.30–0.50) were evaluated to study the trade-off between Precision and Recall.

Lower thresholds increased Recall while reducing Precision.

---

## Final Model

**Selected Model:** Logistic Regression with `class_weight='balanced'`

### Why Logistic Regression?

Among all the implemented models, Logistic Regression achieved the highest Recall while maintaining good generalization between training and testing datasets.

This aligned well with the business objective of minimizing False Negatives.

---

## Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

## Project Structure

```
Student-Stress-Prediction/
│
├── Student_Stress_Prediction.ipynb
├── README.md
├── requirements.txt
├── images/
│   ├── confusion_matrix.png
│   ├── class_distribution.png
│   ├── correlation_heatmap.png
│
└── dataset/
```

---

## Installation

Clone the repository:

```bash
git clone <repository-url>
```

Install the required packages:

```bash
pip install -r requirements.txt
```

Run the Jupyter Notebook.

---

## Future Improvements

* Hyperparameter tuning using GridSearchCV
* Cross-validation
* Ensemble learning methods (Random Forest, XGBoost)
* Feature engineering
* Model deployment using Flask/Django

---

## Key Learning Outcomes

* Data Cleaning
* Exploratory Data Analysis
* Feature Engineering
* Handling Missing Values
* Handling Imbalanced Data
* Threshold Tuning
* Model Evaluation
* Overfitting Analysis
* Business-Oriented Machine Learning Decision Making

---

## Author

**Anit Paul**

If you found this project useful, feel free to ⭐ the repository.
