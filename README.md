# 🏦 Loan Approval Prediction

Predict loan approval decisions using machine learning. This repo includes data prep, modeling, evaluation, and an optional API/UI for quick demos.

![python](https://img.shields.io/badge/Python-3.9%2B-blue)
![license](https://img.shields.io/badge/License-MIT-green)
![build](https://img.shields.io/badge/CI-GitHub%20Actions-success)

---

## 🔍 Overview
Banks receive thousands of applications; this project uses applicant features (income, credit history, loan amount, etc.) to predict approval while reducing bias and turnaround time.

**Key features**
- Reproducible pipeline (preprocess ➜ train ➜ evaluate)
- Multiple models: Logistic Regression, Random Forest, XGBoost
- Metrics: Accuracy, Precision, Recall, F1, ROC-AUC
- Exportable artifacts: encoders, scalers, trained model (`.pkl`)
- Optional Flask/Streamlit app for interactive prediction

---


---

## 🧮 Dataset (example schema)
| Column            | Type      | Notes                                  |
|-------------------|-----------|----------------------------------------|
| Gender            | cat       | Male/Female                            |
| Married           | cat       | Yes/No                                 |
| Dependents        | cat       | 0/1/2/3+                               |
| Education         | cat       | Graduate/Not Graduate                  |
| Self_Employed     | cat       | Yes/No                                 |
| ApplicantIncome   | numeric   | monthly                                |
| CoapplicantIncome | numeric   | monthly                                |
| LoanAmount        | numeric   | in thousands                           |
| Loan_Amount_Term  | numeric   | in days/months (standardize if needed) |
| Credit_History    | numeric   | 1.0 (good) / 0.0 (bad)                 |
| Property_Area     | cat       | Urban/Semiurban/Rural                  |
| Loan_Status       | target    | Y/N                                    |

> Put your CSV in `data/raw/loan.csv` (or update paths in `src/config.py`).

---

## ⚙️ Setup

### 1) Clone & create environment
```bash
git clone https://github.com/<your-username>/loan-approval-prediction.git
cd loan-approval-prediction

python -m venv .venv
# Windows: .venv\Scripts\activate
# Linux/Mac:
source .venv/bin/activate

pip install --upgrade pip
pip install -r requirements.txt
