# hospital-readmission-risk-analysis

# 🏥 Hospital 30-Day Readmission Risk Analysis

## Overview
Analysis of 101,766 diabetic patient records from 130 US hospitals to identify 
key drivers of 30-day hospital readmission and build a predictive risk model.

## Business Question
Which diabetic patients are most likely to be readmitted within 30 days of 
discharge, and what clinical factors drive that risk?

## Tools & Technologies
- **Python** (pandas, matplotlib, seaborn, scikit-learn) — data cleaning, EDA, modeling
- **SQL** (SQLite) — business insight queries
- **Tableau Public** — interactive dashboard
- **Excel** — executive summary report

## Dataset
- **Source:** [Diabetes 130-US Hospitals Dataset](https://www.kaggle.com/datasets/brandao/diabetes)
- **Size:** 101,766 patient encounters, 23 features after cleaning
- **Target:** 30-day readmission (11.16% positive rate)

## Key Findings
1. **Prior inpatient visits** is the strongest predictor of readmission — 3x more important than any other feature
2. **High Risk patients** (3+ prior inpatient visits) have a 25.66% readmission rate vs 8.44% for Low Risk
3. **Patients aged 20-30** have the highest readmission rate at 14.24%
4. **Medication burden** correlates with readmission risk — patients on 15+ medications show consistently elevated rates
5. **Longer hospital stays** are associated with higher readmission risk

## Model Performance
| Model | ROC-AUC | Recall (Readmitted) |
|---|---|---|
| Logistic Regression | 0.64 | 0.51 |
| Random Forest v1 | 0.66 | 0.01 |
| Random Forest v2 | **0.67** | **0.56** |

Final model: Random Forest with manual 8:1 class weighting to address imbalance.

## Dashboard
🔗 https://public.tableau.com/app/profile/christopher.howard3423/viz/Hospital30-DayReadmissionRiskAnalysis/Hospital30-DayReadmissionRiskAnalysis?publish=yes

## Project Structure
- hospital_readmission_analysis.ipynb  ← Full analysis notebook
- Hospital_Readmission_Summary.xlsx    ← Executive summary report
-  feature_importance.csv               ← Model feature importance scores
- risk_summary.csv                     ← Risk tier breakdown
- age_summary.csv                      ← Readmission rates by age group
- README.md

## Recommendations
1. Flag patients with 2+ prior inpatient visits for care management upon discharge
2. Prioritize follow-up calls for patients aged 20-30
3. Review discharge planning for patients on 15+ medications
