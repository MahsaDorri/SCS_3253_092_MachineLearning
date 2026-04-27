# Canadian Anti-Fraud Centre (CAFC) Fraud Analytics Projects

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
