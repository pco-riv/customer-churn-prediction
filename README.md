# Customer Churn Prediction

## Project Overview

Customer churn is a major business challenge for subscription-based companies. Identifying customers who are more likely to leave can help organizations prioritize retention efforts and allocate resources more effectively.

This project develops an end-to-end machine learning workflow to predict customer churn using the **IBM Telco Customer Churn dataset**.

The objective is not only to build a predictive model, but also to understand the main factors associated with churn and translate the model results into actionable business recommendations.

---

## Business Problem

The company wants to identify customers who are at higher risk of churning so that targeted retention strategies can be implemented before customers leave.

The project addresses the following questions:

* Which customer characteristics are most strongly associated with churn?
* Can machine learning accurately identify customers at higher risk of leaving?
* Which classification threshold provides an appropriate balance between precision and recall?
* How can model predictions be translated into actionable retention strategies?

---

## Dataset

The project uses the **IBM Telco Customer Churn dataset**, which contains information about customer demographics, account information, subscribed services, contract characteristics, and churn status.

The dataset contains **7,043 customers and 21 original variables**.

The target variable is:

* `Churn` — whether the customer left the company (`Yes`) or remained (`No`).

---

## Project Workflow

The project follows an end-to-end Data Science workflow:

1. Data loading and initial inspection
2. Data cleaning and preprocessing
3. Exploratory Data Analysis (EDA)
4. Feature engineering and encoding
5. Baseline model development
6. Model comparison
7. Model evaluation
8. Classification threshold optimization
9. Model interpretation
10. Business insights and recommendations

---

## Key Findings

The exploratory analysis and model interpretation identified several important patterns associated with customer churn:

* **Month-to-month contracts** are strongly associated with higher churn.
* **Lower customer tenure** is associated with substantially higher churn risk.
* **Fiber optic customers** show higher churn rates than DSL customers.
* Customers without certain additional services, such as **Online Security and Tech Support**, tend to show higher predicted churn risk.
* Payment method is also associated with different levels of churn risk.

These findings represent **statistical associations rather than causal relationships**.

---

## Modeling

Logistic Regression was used as an interpretable baseline model, while a non-linear model was evaluated to determine whether more complex relationships could improve predictive performance.

Model evaluation considered multiple classification metrics:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC

Because the business objective is to identify customers who are likely to churn, **recall was given particular attention** during model evaluation.

The project also included **classification threshold optimization**, allowing the decision threshold to be adjusted according to the business objective rather than relying exclusively on the default 0.50 threshold.

## Model Performance

The final model was evaluated on the held-out test set using multiple classification metrics.

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 0.7736 |
| Precision | 0.5599 |
| Recall    | 0.6872 |
| F1 Score  | 0.6170 |
| ROC-AUC   | 0.8421 |

The model achieved a **ROC-AUC of 0.8421**, indicating good overall ability to distinguish between customers who churn and those who remain.

Recall was particularly relevant for this project because missing a customer who is likely to churn can represent a lost opportunity for retention.

### Threshold Optimization

The classification threshold was also optimized on the validation set rather than relying exclusively on the default threshold of 0.50.

A threshold of approximately **0.38** provided a better balance between precision and recall for the project's retention objective:

| Metric    | Validation Score |
| --------- | ---------------: |
| Precision |           0.6077 |
| Recall    |           0.6890 |
| F1 Score  |           0.6458 |

This optimization demonstrates that the appropriate classification threshold depends on the business objective and the relative importance of false positives and false negatives.


---

## Business Recommendations

Based on the analysis, several retention strategies could be considered:

### 1. Prioritize high-risk customers

Use churn predictions to identify customers with a high predicted probability of leaving and prioritize them for retention campaigns.

### 2. Focus on the early customer lifecycle

Customers with lower tenure represent an important retention opportunity. Proactive onboarding, satisfaction checks, technical support, and personalized offers could be evaluated during the first months of the customer relationship.

### 3. Encourage longer-term contracts

The company could test incentives designed to encourage customers to move from month-to-month contracts toward one-year or two-year contracts.

### 4. Investigate Fiber optic churn

The higher churn associated with Fiber optic service should be investigated further, considering factors such as pricing, service quality, technical issues, customer expectations, and competitive alternatives.

### 5. Use predictions as decision support

The model should support, rather than replace, business judgment. A potential retention process is:

**Predict → Prioritize → Intervene → Measure → Improve**

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* Jupyter Notebook
* Git & GitHub

---

## Project Structure

```text
customer-churn-prediction/
│
├── data/
│   └── raw/
│
├── models/
│
├── notebooks/
│
├── reports/
│
├── src/
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

## Limitations and Future Improvements

The results of this project should be interpreted as predictive associations rather than causal relationships.

Future improvements could include:

* Hyperparameter optimization for the selected models.
* Evaluation on new customer cohorts.
* Probability calibration.
* Cost-sensitive evaluation based on the financial impact of false positives and false negatives.
* A/B testing of retention interventions.
* Incorporating customer lifetime value into retention prioritization.
* Monitoring model performance over time.

---

## Conclusion

This project demonstrates how machine learning can be used not only to predict customer churn, but also to identify high-risk customer profiles and translate predictive results into actionable business strategies.

The main objective is therefore not simply to predict **who will churn**, but to use those predictions to help the business determine **who should be prioritized for retention efforts and how those interventions can be evaluated**.
