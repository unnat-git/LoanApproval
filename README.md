# Credit Loan Approval Prediction - ML

## Project Overview
This project focuses on predicting whether a loan application should be **approved or rejected** using machine learning. Financial institutions receive thousands of loan applications, and manually evaluating each one can be time-consuming and inconsistent. The goal of this project is to build a machine learning system that assists in **credit risk assessment** by analyzing applicant data.

## Problem Statement
Building a reliable model to predict loan approval based on features such as applicant income, credit score, debt-to-income ratio, and more.

## Project Structure
```
Credit-Loan-Approval-ML/
├── data/
│   └── loan_dataset.csv         # Raw dataset
├── notebooks/
│   └── CreditLoanProject.ipynb  # Main Jupyter notebook
├── models/
│   ├── logistic_regression_model.joblib  # Saved model
│   └── scaler.joblib                     # Saved scaler
├── requirements.txt             # Dependencies
└── README.md                    # Project documentation
```

## Dataset
The dataset `loan_dataset.csv` contains various features including:
- **Applicant Income**
- **Credit Score**
- **Loan Amount**
- **Existing Loans**
- **Loan Approved** (Target Variable)

## Machine Learning Models
Two models were trained and evaluated:
1. **Logistic Regression** (Primary focus for persistence)
2. **Gaussian Naive Bayes**

## Model Persistence
The trained Logistic Regression model and the preprocessing scaler are saved using `joblib` for future use:
- **Model:** `models/logistic_regression_model.joblib`
- **Scaler:** `models/scaler.joblib`

To load the model in Python:
```python
import joblib
model = joblib.load('models/logistic_regression_model.joblib')
scaler = joblib.load('models/scaler.joblib')
```

## Installation & Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/unnat-git/LoanApproval.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the notebook:
   ```bash
   jupyter notebook notebooks/CreditLoanProject.ipynb
   ```

## Understanding Errors in Loan Prediction
Before comparing the models, it is important to understand two types of mistakes:

### 1. Type I Error (False Positive / "False Alarm")
- **The Mistake:** The model predicts a loan should be **approved**, but it should have been **rejected**.
- **Business Impact:** This is the **most dangerous error** for a bank. It leads to lending money to a high-risk applicant who might default, resulting in financial loss.

### 2. Type II Error (False Negative / "Missed Opportunity")
- **The Mistake:** The model predicts a loan should be **rejected**, but the applicant was actually **creditworthy**.
- **Business Impact:** The bank loses a potential customer and interest income. While not as immediately damaging as a default, it affects growth and customer satisfaction.

---
Developed as part of an ML refactoring exercise.
