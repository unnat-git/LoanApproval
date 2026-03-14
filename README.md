# Credit Loan Approval Prediction

## Project Overview

This project focuses on predicting whether a loan application should be **approved or rejected** using machine learning.
Financial institutions receive thousands of loan applications, and manually evaluating each one can be time-consuming and inconsistent. The goal of this project is to build a simple ML system that can assist in **credit risk assessment** by analyzing applicant data and predicting loan approval.

Two machine learning models were trained and evaluated:

* Logistic Regression
* Gaussian Naive Bayes

The models were compared using common classification metrics and confusion matrices to understand how each one behaves in real-world lending scenarios.

---

# Understanding Errors in Loan Prediction

Before comparing the models, it is important to understand two types of mistakes that can happen in a loan approval system.

### Type 1 Error (False Positive)

Actual borrower: **Risky / Should not get loan (0)**
Model prediction: **Approved (1)**

This means the bank gives a loan to someone who is likely to default.
This is the **most dangerous error** because it leads to **direct financial loss**.

---

### Type 2 Error (False Negative)

Actual borrower: **Safe borrower (1)**
Model prediction: **Rejected (0)**

This means the bank rejects someone who could have repaid the loan.
While this does not cause direct financial loss, it means **losing a potential customer**.

---

# Model Performance Comparison

| Metric    | Logistic Regression | Gaussian Naive Bayes |
| --------- | ------------------- | -------------------- |
| Accuracy  | 0.88                | 0.86                 |
| Precision | 0.784               | 0.811                |
| Recall    | 0.836               | 0.705                |
| F1 Score  | 0.809               | 0.754                |

---

# Confusion Matrix Results

### Logistic Regression

```
[[125 14]
 [10 51]]
```

* False Positives (Type 1 Error): **14**
* False Negatives (Type 2 Error): **10**

---

### Gaussian Naive Bayes

```
[[129 10]
 [18 43]]
```

* False Positives (Type 1 Error): **10**
* False Negatives (Type 2 Error): **18**

---

# Observations

Some interesting patterns appeared during the comparison:

* **Gaussian Naive Bayes produced fewer false approvals**, which means it made fewer Type 1 errors.
* **Logistic Regression performed better overall** with higher accuracy, recall, and F1 score.
* Logistic Regression was better at identifying borrowers who actually deserve the loan.

In simple terms:

* Gaussian NB is slightly **safer** but **more conservative**.
* Logistic Regression is **more balanced and reliable overall**.

---

# Final Conclusion

Although Gaussian Naive Bayes had fewer Type 1 errors, **Logistic Regression provided better overall predictive performance**. It maintained a stronger balance between identifying good borrowers and avoiding incorrect approvals.

Because of this balance, **Logistic Regression was selected as the final model for this project**.

---

# Tech Stack

* Python
* Scikit-learn
* Pandas
* NumPy
* Matplotlib / Seaborn
