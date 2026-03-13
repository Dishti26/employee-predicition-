# employee-predicition-
# Employee Attrition Prediction System

An end-to-end machine learning project that predicts whether an employee is likely to leave the company and highlights the main factors behind attrition.

This project uses the public Kaggle dataset: [IBM HR Analytics Employee Attrition & Performance](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

## Overview

Employee attrition is a major business problem because it affects hiring cost, productivity, delivery continuity, and team morale. This project builds a complete HR analytics pipeline to:

- predict attrition as a binary classification problem
- compare multiple machine learning models
- identify the strongest attrition drivers
- generate visual business insights for decision-making

## Dataset

The dataset contains employee-level HR records with `Attrition` as the target variable.

### Target

- `Attrition`: `Yes` or `No`

### Important feature groups

- Demographics: `Age`, `Gender`, `MaritalStatus`, `Education`, `EducationField`
- Compensation: `MonthlyIncome`, `DailyRate`, `HourlyRate`, `PercentSalaryHike`, `StockOptionLevel`
- Job and work environment: `Department`, `JobRole`, `JobLevel`, `BusinessTravel`, `OverTime`, `WorkLifeBalance`, `EnvironmentSatisfaction`, `JobSatisfaction`
- Experience and tenure: `TotalWorkingYears`, `YearsAtCompany`, `YearsInCurrentRole`, `YearsWithCurrManager`, `YearsSinceLastPromotion`, `NumCompaniesWorked`
- Performance and engagement: `PerformanceRating`, `JobInvolvement`, `RelationshipSatisfaction`

## Project workflow

### 1. Data preprocessing

- removes duplicates
- drops identifier and constant columns
- handles missing values using `SimpleImputer`
- encodes categorical variables using `OneHotEncoder`
- scales numerical features using `StandardScaler`

### 2. Exploratory Data Analysis

The project generates:

- attrition distribution plots
- numeric feature distributions
- attrition rate by overtime, work environment, job satisfaction, and business travel
- correlation heatmap

### 3. Models

- Logistic Regression
- Decision Tree
- Random Forest

### 4. Evaluation metrics

- Accuracy
- Precision
- Recall
- F1 Score

### 5. Explainability

Top attrition drivers are extracted using:

- logistic regression coefficients
- random forest feature importance
- permutation importance

## Repository structure

```text
.
├── employee_attrition_prediction.py
├── employee_attrition_colab.ipynb
├── requirements.txt
├── outputs/
└── README.md
```

## Results snapshot

Dataset used in the current run:

- Rows: `1470`
- Columns after cleaning: `31`
- Attrition rate: `16.12%`

### Model comparison

| Model | Accuracy | Precision | Recall | F1 Score |
|------|---------:|----------:|-------:|---------:|
| Logistic Regression | 0.7517 | 0.3488 | 0.6383 | 0.4511 |
| Random Forest | 0.8469 | 0.5312 | 0.3617 | 0.4304 |
| Decision Tree | 0.7279 | 0.3103 | 0.5745 | 0.4030 |

Best model in this run by F1 score: `Logistic Regression`

## Key attrition drivers

The strongest factors observed in this run included:

- overtime
- monthly income
- stock option level
- distance from home
- job satisfaction
- marital status
- total working years
- job level
- business travel

These insights help HR teams focus on retention strategies such as workload balancing, compensation review, role design, and employee experience improvements.

## Visual outputs

The `outputs/` folder contains generated charts and reports such as:

- `model_comparison.png`
- `attrition_distribution.png`
- `correlation_heatmap.png`
- `overtime_vs_attrition.png`
- `job_satisfaction_vs_attrition.png`
- `random_forest_permutation_importance.png`

## Run locally

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd <your-repo-folder>
```

### 2. Create and activate a virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Download the dataset

Download the Kaggle CSV and place it in the project root with this exact name:

```text
WA_Fn-UseC_-HR-Employee-Attrition.csv
```

### 5. Run the pipeline

```bash
python employee_attrition_prediction.py
```

If your file is stored elsewhere:

```bash
python employee_attrition_prediction.py --data /path/to/WA_Fn-UseC_-HR-Employee-Attrition.csv
```

## Run in Google Colab

If you prefer not to run locally:

1. Open [Google Colab](https://colab.research.google.com/)
2. Upload `employee_attrition_colab.ipynb`
3. Run the notebook cells in order
4. Upload the Kaggle CSV when prompted

## Generated outputs

After execution, the pipeline saves:

- `model_comparison_metrics.csv`
- `dataset_summary.csv`
- `missing_values_report.csv`
- classification reports for each model
- confusion matrices
- EDA visualizations
- feature importance plots
- `business_summary.txt`

## Tools and libraries

- Python
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
