# Model Results

## Project Objective

The objective of this project is to predict whether a student is **stressed** or **not stressed** based on lifestyle and academic factors.

The primary business objective is to **minimize False Negatives**, ensuring that students experiencing stress are identified as accurately as possible.

Therefore, **Recall** was selected as the primary evaluation metric.

---

# Models Evaluated

The following machine learning models were implemented and compared:

* Logistic Regression
* Logistic Regression (`class_weight='balanced'`)
* K-Nearest Neighbors (KNN)
* Gaussian Naive Bayes
* Support Vector Machine (SVM)

Each model was evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

Training and testing performance were also compared to ensure that the models generalized well and did not overfit.

---

# Final Model

**Algorithm:** Logistic Regression

**Configuration:**

* `class_weight='balanced'`
* Threshold Tuning

The balanced class weights helped improve the model's ability to correctly identify stressed students by reducing False Negatives.

---

# Final Model Performance

| Metric    |      Score |
| --------- | ---------: |
| Accuracy  | **0.7808** |
| Precision | **0.6079** |
| Recall    | **0.7916** |
| F1 Score  | **0.6877** |

---

# Final Confusion Matrix

![Final Model Confusion Matrix](images/final_model_confusion_matrix.png)

### Confusion Matrix Values

```text
[[2751  794]
 [ 324 1231]]
```

Where:

| Metric              | Value |
| ------------------- | ----: |
| True Negative (TN)  |  2751 |
| False Positive (FP) |   794 |
| False Negative (FN) |   324 |
| True Positive (TP)  |  1231 |

### Interpretation

* Successfully identified **1231** stressed students.
* Missed **324** stressed students.
* Generated **794** false alarms.
* Correctly identified **2751** non-stressed students.

Although the number of False Positives increased after applying `class_weight='balanced'`, the number of False Negatives decreased significantly, resulting in a much higher Recall.

This behavior aligns with the project's objective of identifying as many stressed students as possible.

---

# Threshold Tuning

Different classification thresholds were evaluated to analyze the trade-off between Precision and Recall.

| Threshold |   Accuracy |  Precision |     Recall |   F1 Score |
| --------- | ---------: | ---------: | ---------: | ---------: |
| 0.30      |     0.6861 |     0.4921 | **0.9177** |     0.6406 |
| 0.35      |     0.7161 |     0.5200 |     0.8939 |     0.6575 |
| 0.40      |     0.7422 |     0.5494 |     0.8579 |     0.6698 |
| 0.45      |     0.7606 |     0.5750 |     0.8232 |     0.6771 |
| 0.50      | **0.7808** | **0.6079** |     0.7916 | **0.6877** |

### Observation

* Lower thresholds increased Recall by identifying more stressed students.
* However, Precision decreased due to an increase in False Positives.
* The threshold should therefore be selected based on the application's business requirements.

---

# Comparison with Other Models

| Model                  |                     Accuracy |  Precision |     Recall |   F1 Score |
| ---------------------- | ---------------------------: | ---------: | ---------: | ---------: |
| Logistic Regression    |                       0.7808 |     0.6079 | **0.7916** | **0.6877** |
| K-Nearest Neighbors    |                       0.7845 |     0.6932 |     0.5260 |     0.5981 |
| Gaussian Naive Bayes   |                       0.7896 |     0.6825 |     0.5794 |     0.6267 |
| Support Vector Machine |                       0.8127 | **0.7742** |     0.5447 |     0.6395 |

---

# Model Selection

Although Support Vector Machine achieved higher Accuracy and Precision, its Recall was considerably lower.

Since the primary objective of this project was to minimize False Negatives and identify as many stressed students as possible, Logistic Regression was selected as the final model.

---

# Conclusion

The final Logistic Regression model demonstrated good generalization between training and testing datasets while achieving the highest Recall among the evaluated models.

By incorporating class balancing and threshold tuning, the model became more effective at detecting stressed students, making it more suitable for real-world student mental health screening applications.
