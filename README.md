# Telecom Customer Churn Prediction

## Project Overview

This project analyzes customer churn in a telecom company using **Exploratory Data Analysis (EDA)** and **Machine Learning**. The objective is to identify the key factors influencing customer churn and build a predictive model that helps businesses proactively retain customers.

---

## Dataset

- **Source:** IBM Telecom Customer Churn Dataset
- **Records:** 7,043 customers
- **Features:** 21 customer attributes
- **Target Variable:** Churn (Yes / No)

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## Project Workflow

- Data Cleaning and Preprocessing
- Missing Value Handling
- Exploratory Data Analysis (EDA)
- Feature Engineering
- One-Hot Encoding
- Train-Test Split
- Feature Scaling using StandardScaler
- Logistic Regression Model
- Model Evaluation
- Business Insights and Recommendations

---

## Key Insights from EDA

- Overall customer churn rate is approximately **26.5%**.
- Customers with **Month-to-Month contracts** exhibit the highest churn.
- **Fiber Optic** internet users are more likely to churn.
- Customers without **Online Security** and **Tech Support** have significantly higher churn rates.
- **Senior Citizens** demonstrate a higher churn percentage.
- Longer customer tenure is associated with lower churn.

---

## Machine Learning Model

A **Logistic Regression** classifier was developed to predict customer churn.

### Preprocessing

- Converted categorical variables using One-Hot Encoding.
- Scaled numerical features using StandardScaler.
- Split the dataset into training and testing sets.

### Model Evaluation

The model was evaluated using:

- Accuracy
- Precision
- Recall
- Confusion Matrix
- Classification Report

Feature coefficients were analyzed to identify the strongest drivers of customer churn.

---

## Business Recommendations

- Encourage customers to switch to long-term contracts.
- Improve onboarding and retention strategies for new customers.
- Bundle Online Security and Tech Support services.
- Investigate service quality for Fiber Optic customers.
- Focus retention campaigns on high-risk customer segments identified by the model.

---

## Future Improvements

- Random Forest Classifier
- XGBoost
- Hyperparameter Tuning
- Cross Validation
- Streamlit Deployment
- Interactive Dashboard

---

## Author

**Suhani Malhotra**

GitHub: https://github.com/SuhaniMalhotra09

