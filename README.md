# Canadian Anti-Fraud Centre (CAFC) Fraud Analytics Projects

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-FF6600?style=for-the-badge&logo=xgboost&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

</div>

---

## Overview

This repository contains **two end-to-end machine learning projects** built using the public Canadian Anti-Fraud Centre (CAFC) fraud dataset. The objective of these projects was to apply data science techniques to real-world fraud reporting data and generate predictive insights for fraud detection, risk prioritization, and financial severity analysis.

Both projects follow a **complete machine learning workflow**:

```
Data Collection → Data Cleaning → EDA → Feature Engineering 
→ Model Training → Evaluation → Business Insights
```

---

## Dataset Source

**[Government of Canada Open Data Portal](https://open.canada.ca/)**  
**[Canadian Anti-Fraud Centre (CAFC)](https://www.antifraudcentre-centreantifraude.ca/)**

The dataset contains fraud and cybercrime complaints submitted through:
- Website
- Phone
- Email

### Key Features:
- **Fraud Category** — Type of fraud reported
- **Solicitation Method** — How victim was contacted
- **Country / Province** — Geographic location
- **Complaint Date** — Timestamp of report
- **Gender** — Victim demographics
- **Age Range** — Victim age group
- **Number of Victims** — Count of affected individuals
- **Dollar Loss** — Financial impact

---

## Project 1: Victim Prediction Classification

### Objective
Predict whether a fraud complaint involved a **victim**.

### Business Problem
Fraud agencies receive many complaints daily. Automatically identifying complaints involving confirmed victims can improve **investigation prioritization** and **resource allocation**.

### Target Variable
**`is_Victim`**
- `1` = Complaint involved victim(s)
- `0` = No measurable victim impact

### Workflow

#### 1. Data Preparation
- Converted incorrect data types
- Standardized column names
- Removed duplicate columns
- Cleaned text inconsistencies
- Handled missing values

#### 2. Feature Engineering
- Extracted `Year`, `Month`, `DayOfWeek` from `Date Received`
- Ordinal Encoding for Age Groups
- One-Hot Encoding for categorical features

#### 3. Preprocessing
- Train/Test Split
- MinMaxScaler normalization

### Models Used
- **Logistic Regression**
- **Random Forest**
- **XGBoost**
- **MLP Neural Network**

### Results

| Model | Accuracy |
|-------|----------|
| Logistic Regression | 79% |
| Random Forest | 81% |
| **XGBoost** | **83%** |
| **MLP Neural Network** | **83%** |

### Best Models
- **XGBoost**
- **MLP Neural Network**

### Business Impact
- Faster victim complaint identification  
- Better fraud triage systems  
- Improved case prioritization  
- Enhanced trend monitoring  

---

## Project 2: Loss Severity Classification

### Objective
Predict the **severity of financial loss** caused by fraud incidents.

Instead of predicting exact dollar values, loss amounts were converted into **categories**.

### Target Variable
**`Loss_Category`**
- **Low**
- **Medium**
- **High**

*(Generated using percentile ranges of non-zero Dollar Loss values)*

### Business Problem
Exact loss prediction is difficult due to **privacy limitations** and **limited feature richness**. Severity classification provides a more **practical solution**.

### Workflow

#### 1. Data Preparation
- Removed all rows with `Dollar Loss = 0`
- Created target classes using percentiles
- Prevented data leakage by removing `Dollar Loss` from model inputs

#### 2. Feature Engineering
- Year / Month / DayOfWeek extraction
- Categorical encoding
- Missing value treatment
- Feature scaling

### Models Used
- **Logistic Regression**
- **SVC (Support Vector Classifier)**
- **Random Forest**
- **XGBoost**
- **MLP Neural Network**

### Results

| Model | Accuracy |
|-------|----------|
| **Random Forest** | **61%** |
| MLP Neural Network | 60% |
| Logistic Regression | 59% |
| XGBoost | 59% |
| SVC | 50% |

### Best Model
- **Random Forest** (61%)

### Business Impact
- Detect high-loss incidents  
- Prioritize severe fraud reports  
- Support fraud risk scoring  
- Improve operational workflows  

------

## Key Learnings

These projects demonstrate common **real-world fraud analytics challenges**:

- **Missing values**  
- **Weak feature correlation**  
- **Privacy-driven data limitations**  
- **Class imbalance**  
- **Noisy public reporting data**  

Despite these limitations, **strong preprocessing** and **model comparison** still produced meaningful business insights.

---

## Future Improvements

- Hyperparameter tuning (GridSearchCV, RandomizedSearchCV)
- Ensemble learning (stacking, blending)
- SHAP explainability for model interpretability
- NLP on fraud descriptions (if available)
- Fraud trend forecasting (time series analysis)
- External economic indicators integration
- Advanced class balancing techniques (SMOTE, ADASYN)
- Cost-sensitive learning for financial risk models
Made with care for the data science community

</div>
