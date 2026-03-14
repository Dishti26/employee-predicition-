# Employee Attrition Prediction System

An end-to-end Machine Learning and HR Analytics project that predicts whether an employee is likely to leave the company and identifies the key factors driving attrition.

This project combines **data preprocessing, exploratory data analysis, feature engineering, machine learning modeling, explainability, and interactive prediction tools** to help HR teams understand and mitigate employee turnover.

Dataset used:
IBM HR Analytics Employee Attrition & Performance
https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset

---

# Project Overview

Employee attrition is a major challenge for organizations because it impacts:

* recruitment costs
* productivity
* project continuity
* team morale
* knowledge retention

This project builds a complete **HR analytics pipeline** that:

* predicts employee attrition as a binary classification problem
* compares multiple machine learning models
* identifies the strongest drivers of attrition
* generates visual insights for business decision-making
* provides an interactive prediction tool for scenario analysis

---

# Dataset

The dataset contains **1470 employee records** with multiple HR attributes.

Target variable:

Attrition
Values: Yes / No

After preprocessing and feature engineering, the dataset contains approximately **31 usable features**.

---

# Feature Categories

### Demographics

* Age
* Gender
* MaritalStatus
* Education
* EducationField

### Compensation

* MonthlyIncome
* DailyRate
* HourlyRate
* PercentSalaryHike
* StockOptionLevel

### Job and Work Environment

* Department
* JobRole
* JobLevel
* BusinessTravel
* OverTime
* WorkLifeBalance
* EnvironmentSatisfaction
* JobSatisfaction

### Experience and Tenure

* TotalWorkingYears
* YearsAtCompany
* YearsInCurrentRole
* YearsWithCurrManager
* YearsSinceLastPromotion
* NumCompaniesWorked

### Engagement and Performance

* JobInvolvement
* RelationshipSatisfaction
* PerformanceRating

---

# Project Workflow

## 1 Data Preprocessing

The preprocessing pipeline includes:

* removing duplicate records
* dropping identifier and constant columns
* handling missing values using SimpleImputer
* encoding categorical variables using OneHotEncoder
* scaling numerical features using StandardScaler

---

## 2 Exploratory Data Analysis (EDA)

Several visual analyses were created to understand workforce patterns.

Examples include:

* attrition distribution
* numerical feature histograms
* attrition vs overtime
* attrition vs job satisfaction
* attrition vs business travel
* correlation heatmap of numerical features

These visualizations provide insight into workforce behavior and potential attrition risks.

---

# Feature Engineering

Several new features were created to capture complex workforce dynamics.

PromotionDelay
YearsAtCompany − YearsSinceLastPromotion
Measures how long employees have been waiting for promotion.

WorkloadScore
JobInvolvement × OverTime
Detects potential employee burnout.

IncomeExperienceRatio
MonthlyIncome ÷ (TotalWorkingYears + 1)
Helps identify potentially underpaid employees.

WorkStability
YearsAtCompany ÷ (TotalWorkingYears + 1)
Represents employee job stability.

SatisfactionScore
JobSatisfaction + EnvironmentSatisfaction + RelationshipSatisfaction
Represents overall employee satisfaction.

These engineered features significantly improve model interpretability and predictive performance.

---

# Machine Learning Models

The following models were trained and evaluated.

Logistic Regression
Decision Tree
Random Forest

Models were trained using a pipeline combining preprocessing and classification.

---

# Model Evaluation

Models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix

Example model comparison:

| Model               | Accuracy | Precision | Recall | F1 Score |
| ------------------- | -------- | --------- | ------ | -------- |
| Logistic Regression | 0.7517   | 0.3488    | 0.6383 | 0.4511   |
| Random Forest       | 0.8469   | 0.5312    | 0.3617 | 0.4304   |
| Decision Tree       | 0.7279   | 0.3103    | 0.5745 | 0.4030   |

Best model by F1 score: Logistic Regression

---

# Explainability and Feature Importance

To understand the drivers of employee attrition, several explainability methods were used.

Logistic Regression coefficients
Random Forest feature importance
Permutation importance

Key drivers identified include:

* overtime
* monthly income
* job satisfaction
* stock option level
* business travel
* distance from home
* job level
* total working years
* marital status

These insights help HR departments focus on targeted retention strategies.

---

# Interactive Prediction Tool

The notebook includes an interactive prediction interface built with ipywidgets.

Users can input employee attributes such as:

* age
* monthly income
* job satisfaction
* overtime
* years at company

The system then predicts whether the employee is likely to leave.

This tool enables HR teams to perform simple **what-if analysis**.

---

# Generated Outputs

The pipeline generates several outputs including:

model comparison metrics
dataset summary reports
missing value analysis
classification reports
confusion matrices
EDA visualizations
feature importance plots
business summary insights

The outputs folder may include files such as:

* model_comparison.png
* attrition_distribution.png
* correlation_heatmap.png
* overtime_vs_attrition.png
* job_satisfaction_vs_attrition.png
* random_forest_permutation_importance.png

---

# Repository Structure

.
├── employee_attrition_prediction.py
├── employee_attrition_colab.ipynb
├── requirements.txt
├── outputs/
└── README.md

---

# Tools and Libraries

Python
pandas
numpy
scikit-learn
matplotlib
seaborn
ipywidgets


