# Predicting Bleeding Risk in ICU Patients Receiving Intravenous Heparin: A Machine Learning Approach for Early, Explainable, and Actionable Intervention


## Overview

This project presents a machine learning–based early warning system to predict the risk of clinically significant bleeding within 48 hours of intravenous (IV) heparin administration in ICU patients. The model leverages structured ICU data from the MIMIC-IV database and applies advanced predictive techniques to support early, explainable, and actionable intervention in anticoagulated patients.

---

## Type of Analysis

- **Machine Learning in Healthcare**
- **Predictive Modeling**
- **Explainable AI (SHAP)**
- **Model Calibration and Clinical Utility (DCA)**

---

## Objectives

- Predict bleeding events within 48 hours post-heparin infusion  
- Compare multiple ML models (XGBoost, LightGBM, GBM, RF, LogReg)  
- Provide SHAP-based explainability for clinical transparency  
- Optimize thresholds to balance early detection and alert burden

---

## Dataset

- **Source**: MIMIC-IV v3.1  
- **Cohort**: ICU patients receiving systemic IV heparin  
- **Sample**: 24,738 unique encounters  
- **Outcome**: Bleeding event within 48 hours (defined by lab-based thresholds)

---

## Methodology

- Feature engineering from labs, vitals, comorbidities, medications, procedures  
- Imputation via IterativeImputer  
- Model training with stratified 5-fold cross-validation  
- Hyperparameter tuning using GridSearchCV  
- Threshold optimization using Youden’s J statistic  
- Calibration via isotonic regression  
- Interpretability via SHAP (global + local)  
- Decision Curve Analysis (DCA) to assess clinical benefit

---

## Model Performance (Test Set)

| Model     | ROC-AUC | Sensitivity | Precision | F1 Score | Specificity |
|-----------|---------|-------------|-----------|----------|-------------|
| **LightGBM** | 0.905   | 0.815       | 0.657     | 0.719    | 0.823       |
| XGBoost   | 0.905   | 0.813       | 0.665     | 0.721    | 0.829       |
| GBM       | 0.904   | 0.823       | 0.648     | 0.720    | 0.814       |
| RF        | 0.891   | 0.812       | 0.639     | 0.693    | 0.809       |
| LogReg    | 0.888   | 0.805       | 0.660     | 0.686    | 0.827       |

---

## SHAP-Based Interpretability

- Top predictors included platelet variability, PT, aPTT, lactate, and INR  
- SHAP beeswarm and waterfall plots used for both global and patient-level explanation  
- Clinically aligned insights support real-world applicability

---

## Decision Curve Analysis (DCA)

- LGBM and GBM provided the highest net clinical benefit  
- Optimized threshold reduced false positives by 60–70%  
- DCA confirmed added value over “treat-all” or “treat-none” approaches

---

## Clinical Implications

- **High Sensitivity Mode (Safety-Focused)**: RF at fixed threshold  
- **Balanced Mode (CDS Integration)**: XGB/LGBM at optimized threshold  
- **Interpretable Mode (Auditability)**: Logistic Regression with SHAP explanations

---

## Tools & Technologies

- Python · Scikit-learn · XGBoost · LightGBM · SHAP  
- SQL (PostgreSQL) for MIMIC-IV extraction  
- Jupyter Notebooks · Matplotlib · Seaborn

---

## Skills Demonstrated

- AI for medication safety and risk stratification  
- Clinical machine learning using real-world ICU data  
- SHAP-based model explanation (global & local)  
- Threshold optimization and decision curve analysis  
- End-to-end ML pipeline development following MLI checklist  
- High-stakes model deployment planning

---

## Author

**Alanoud Abdulaziz Al Turki**  
Health Data Analyst | Health Informatics Specialist | Pharmacist  
MS in Health Informatics · MS in Health Data Analysis · PhD Student  
[LinkedIn](https://www.linkedin.com/in/alanoud-alturki-5601b2b5)

---

## License

This project is for research purposes only. Data is de-identified and derived from the publicly available MIMIC-IV database. 
