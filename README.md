# Employee Attrition Prediction

**ACC102 Mini Assignment - Track 2 (GitHub Data Analysis Project)**

---

## Product Link & Demo Video

- **GitHub Repository**:
- **Demo Video**:

---

## 1. How to Run
**Prerequisites**:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```
**Steps**:
1. Clone the repository: `git clone 
2. Download the dataset from Kaggle and place `HR-Employee-Attrition.csv` in the project folder
3. Run the Notebook: `notebook.ipynb`
---

## 2. Data

**Dataset**: IBM HR Analytics Employee Attrition & Performance

**Source**: Kaggle - https://www.kaggle.com/datasets/rishikeshkonapure/hr-analytics-prediction

**Access Date**: 19 April 2026

**Size**: 1,470 employees, 35 features

**Target Variable**: `Attrition` (Yes = Leave, No = Stay)

**Key Fields**:
- MonthlyIncome - Employee's monthly salary
- YearsAtCompany - Years worked at current company
- OverTime - Whether employee works overtime
- JobSatisfaction - Satisfaction level (1-4)
- Age - Employee age
- DistanceFromHome - Commute distance in miles

---

## 3. Problem & User
**Analytical Problem**: Can we predict whether an employee will leave the company based on their work patterns, job satisfaction, and demographic information?
**Target User**: HR departments, team managers, and business decision makers who want to identify flight risk early and take proactive retention actions.
**Business Value**: Employee turnover costs companies 50%–200% of annual salary per replaced employee. Predicting attrition enables proactive retention, reduces costs, and improves workplace satisfaction.

---

## 4. Methods
| Step | Methods Used |
|------|---------------|
| Data Loading & Exploration | pandas, numpy |
| EDA & Visualization | matplotlib, seaborn (boxplots, stacked bar charts) |
| Data Preprocessing | One-hot encoding, median imputation, StandardScaler |
| Feature Engineering | Created Commute_Burden, Overall_Satisfaction, Long_No_Promotion, Income_Per_Year |
| Model Training | Logistic Regression, Random Forest |
| Model Evaluation | Accuracy, Precision, Recall, F1-Score, ROC AUC, Confusion Matrix |
| Hyperparameter Tuning | GridSearchCV with `scoring='recall'` (C for LR; n_estimators, max_depth for RF) |
| Feature Importance | Logistic Regression coefficients, Random Forest importance scores |
| Primary Metric | **Recall** — missing a leaver (False Negative) incurs 50–200% salary replacement cost, outweighing false positives |
| Model Selection | Logistic Regression outperformed Random Forest (Recall: 0.4085 vs 0.1127; AUC: 0.8207 vs 0.7682) and offers better interpretability for HR |

---

## 5. Key Findings
1. **Overtime is the strongest positive driver** — Logistic Regression shows OverTime_Yes has the largest positive coefficient (1.78), meaning overtime employees are significantly more likely to leave
2. **Frequent business travel increases attrition risk** — BusinessTravel_Travel_Frequently shows strong positive coefficient (1.42)
3. **R&D roles have lower attrition** — Department_Research & Development has a negative coefficient (-0.51), indicating these employees are more likely to stay
4. **Single employees show higher turnover** — MaritalStatus_Single has a positive coefficient (0.75)
5. **Logistic Regression outperforms Random Forest** — Achieving higher Accuracy (0.8821 vs 0.8277) and Recall (0.4085 vs 0.1127), capturing nearly 4x more actual leavers

---

## 6. Model Performance Summary

| Model | Accuracy | Precision | Recall | F1-Score | ROC AUC |
|-------|----------|-----------|--------|----------|---------|
| Logistic Regression | 0.8821 | 0.7436 | 0.4085 | 0.5273 | 0.8207 |
| Random Forest | 0.8277 | 0.3810 | 0.1127 | 0.1739 | 0.7682 |

**Best Model**: Logistic Regression

---

## 7. Random Forest Feature Importance

| Feature | Importance |
|---------|------------|
| MonthlyIncome | 0.0690 |
| TotalWorkingYears | 0.0621 |
| Age | 0.0569 |
| Income_Per_Year | 0.0446 |
| DailyRate | 0.0442 |
| MonthlyRate | 0.0412 |
| HourlyRate | 0.0406 |
| YearsAtCompany | 0.0399 |
| OverTime_Yes | 0.0388 |
| Overall_Satisfaction | 0.0383 |

---

## 8. Limitations

1. **Missing external factors** — The dataset lacks information on job market conditions, competitor salaries, and team culture

2. **Small sample size** — Only 1,470 employees, which may limit the model's generalizability

3. **Static data** — No time-series information to track how satisfaction and turnover risk change over time

---

## 9. Future Work

1. Collect real-world HR data from actual companies to validate findings
2. Incorporate external economic indicators (unemployment rate, industry salary benchmarks)
3. Develop a time-series or survival analysis model to predict *when* an employee will leave
4. Deploy as an interactive Streamlit dashboard for real-time risk prediction
5. Conduct A/B testing to evaluate whether model-driven retention interventions actually reduce attrition

---

## 10. AI Disclosure

| Tool | Version | Access Date | Purpose |
|------|---------|-------------|---------|
| Deepseek | 19 April 2026 | Code debugging, analysis structuring, report drafting |

*All analytical logic, data interpretation, and final conclusions are my own work.*

---

**Author**: [Jiarui.Cao]
**Student ID**: [2473734]
**Course**: ACC102 - Python Data Product Mini Assignment
**Track**: Track 2 - GitHub Data Analysis Project
**Submission Date**: 27 April 2026
