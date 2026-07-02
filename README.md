# Telecom Customer Churn Prediction

Predicting which telecom customers are likely to churn using exploratory data analysis and supervised machine learning, with the goal of helping the business identify at-risk customers before they leave.

## Problem Statement

Customer churn — customers discontinuing their service — directly impacts telecom revenue. Acquiring a new customer is significantly more expensive than retaining an existing one, so the ability to flag high-risk customers early enables targeted retention efforts. This project analyzes the Telecom Customer Churn dataset (7,043 customers, 21 features) to identify the key drivers of churn and build a classification model that predicts churn risk.

## Dataset

- **Source:** Telecom Customer Churn dataset (7,043 rows, 21 columns)
- **Target variable:** `Churn` (Yes/No)
- **Features:** Demographics (gender, senior citizen, partner, dependents), account information (tenure, contract type, payment method, billing), and subscribed services (phone, internet, online security, streaming, tech support, etc.)
- **Class distribution:** ~73.5% No Churn, ~26.5% Churn (moderately imbalanced)

## Project Workflow

1. **Data Cleaning** — handled non-numeric blanks in `TotalCharges`, verified no duplicate customer IDs, confirmed no missing values post-cleaning (notebook runs end-to-end without errors)
2. **Exploratory Data Analysis** — univariate and bivariate analysis of churn against demographics, contract type, tenure, services subscribed, and payment method
3. **Preprocessing** — categorical encoding via one-hot encoding (`drop_first=True`), numerical feature scaling via `StandardScaler`
4. **Train/Test Split** — 80/20 stratified split to preserve class distribution
5. **Model Training** — trained and evaluated five classification algorithms
6. **Model Comparison** — compared all models on Accuracy, Precision, Recall, F1-Score, and ROC-AUC
7. **Business Recommendations** — translated findings into actionable retention strategies

## Key EDA Findings

- **Contract type is the strongest churn signal:** month-to-month customers churn at a much higher rate than customers on 1- or 2-year contracts.
- **Tenure matters:** customers in their first 1–2 months are far more likely to churn than long-tenured customers.
- **Fiber optic internet customers churn more** than DSL customers.
- **Customers without add-on services** (Online Security, Online Backup, Device Protection, Tech Support) churn at higher rates than those who subscribe to them.
- **Electronic check payment method** is associated with higher churn compared to automatic payment methods.
- **Senior citizens churn at a higher rate** than non-senior customers.

## Models Trained

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|---|---|---|---|---|---|
| Gradient Boosting | 0.798 | 0.655 | 0.508 | 0.572 | **0.842** |
| Logistic Regression | 0.807 | 0.658 | **0.567** | **0.609** | 0.842 |
| Random Forest | 0.791 | 0.637 | 0.492 | 0.555 | 0.827 |
| KNN | 0.747 | 0.525 | 0.500 | 0.512 | 0.772 |
| Decision Tree | 0.742 | 0.515 | 0.489 | 0.502 | 0.661 |

Gradient Boosting and Logistic Regression are effectively tied on ROC-AUC, with Logistic Regression achieving noticeably higher recall — an important consideration for churn use cases, where failing to flag an at-risk customer (a false negative) is typically costlier than a false alarm.

## Tech Stack

- **Language:** Python
- **Data manipulation:** pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning:** scikit-learn (Logistic Regression, Decision Tree, Random Forest, KNN, Gradient Boosting)

## Repository Structure

```
├── TCA.ipynb              # Full notebook: EDA, preprocessing, modeling, evaluation (runs top-to-bottom cleanly)
├── customer_churn.csv     # Dataset
├── README.md               # Project overview (this file)
└── EXECUTIVE_SUMMARY.md    # Business-facing summary of findings and recommendations
```

## Business Recommendations

- Encourage month-to-month customers to switch to longer-term contracts through discounts and loyalty incentives.
- Prioritize retention efforts on customers within their first few months of tenure with personalized onboarding.
- Offer customized pricing or promotional benefits to customers with high monthly charges.
- Investigate and improve service reliability for fiber optic internet customers.
- Use the trained model to score the existing customer base and proactively target high-risk customers with retention campaigns.

## Limitations & Future Work

This project currently establishes a baseline comparison across five models. The following are natural next steps to improve model performance and rigor:

- **Class imbalance handling** (e.g., `class_weight='balanced'` or SMOTE) to improve recall on the minority (churn) class
- **Cross-validation** to produce more reliable performance estimates than a single train/test split
- **Hyperparameter tuning** (GridSearchCV / RandomizedSearchCV) for the top-performing models
- **Feature engineering** (e.g., tenure buckets, total services subscribed, charge-per-tenure ratio)
- **SHAP / feature importance analysis** to explain individual predictions and support business trust in the model
- **Threshold tuning** to optimize the precision-recall trade-off for the specific cost of missed churners vs. false alarms

## Author

Suhani 

