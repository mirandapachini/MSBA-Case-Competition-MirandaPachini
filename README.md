# MSBA-Case-Competition-MirandaPachini
# TruSource Telecom Churn Prediction Project

## Overview
This repository contains my individual work for the MSBA Case Competition focused on predicting customer churn for TruSource, a subscription‑based telecom provider. The project integrates predictive modeling, exploratory data analysis, feature engineering, and customer segmentation to identify the drivers of churn and develop actionable retention strategies.

The goal is to help TruSource reduce its churn rate of **26.54%**, improve customer lifetime value, and support data‑driven decision‑making across marketing, customer success, and operations.

---

## Repository Structure

---

## Project Components

### **1. Exploratory Data Analysis (EDA)**
Key insights:
- Early‑tenure customers churn at significantly higher rates  
- Month‑to‑month contracts are the highest‑risk group  
- Customers without tech support churn more frequently  
- Fiber optic customers show elevated churn due to performance expectations  
- Higher service counts and higher service intensity correlate with lower churn  

These insights guided feature engineering and model selection.

---

### **2. Feature Engineering**
I engineered several new variables to capture customer behavior more effectively:
- **avg_monthly_bill**, **avg_monthly_extra_fees**, **avg_monthly_long_dist_fee**
- **count_of_reg_services**, **count_of_streaming_services**, **count_of_add_on_services**
- **total_services**
- Adjusted tenure to avoid division by zero
- Encoded missing categorical values meaningfully (e.g., “none”)

These features improved model interpretability and predictive power.

---

### **3. Predictive Modeling**
Four supervised learning models were evaluated:
- Decision Tree  
- Random Forest  
- XGBoost  
- CatBoost  

**CatBoost** achieved the highest performance with an ROC–AUC of **0.896**, outperforming all other models. It was selected as the final model due to its ability to handle categorical variables, capture nonlinear interactions, and generalize well.

Class imbalance was addressed using:
- Stratified train/test split  
- Class weighting in the modeling pipeline  

---

### **4. Clustering & Customer Segmentation**
Using PCA and K‑Means (k=3), we identified three meaningful customer segments:

- **Cluster 1:** New, low‑value, high‑risk customers (43% churn)  
- **Cluster 2:** Established, moderate‑value, low‑risk customers (12% churn)  
- **Cluster 0:** High‑value, long‑tenured, low‑risk customers (14% churn)  

These segments informed differentiated retention strategies.

---

### **5. Retention Strategy Recommendations**
Based on modeling + segmentation:

- **Cluster 1:** Onboarding, early‑tenure support, simple plans, proactive outreach  
- **Cluster 2:** Loyalty rewards, upsell opportunities, referral incentives  
- **Cluster 0:** VIP support, priority issue resolution, premium loyalty benefits  

These strategies align with the business value and churn risk of each segment.

---

### **6. Deployment & Monitoring (Track 3)**
A real telecom company would deploy the churn model using:
- **Overnight batch scoring**
- **Scheduled Python or SQL pipelines**
- **CRM integration (Salesforce, HubSpot, Dynamics, Zoho)**

Monitoring includes:
- Data quality checks  
- Feature drift detection  
- Model performance tracking (AUC, lift, calibration)  

---

## Files Included
- **Notebook:** Full modeling workflow (EDA → Feature Engineering → Models → Clustering → Recommendations)  
- **Holdout Set:** Predictions for the unseen dataset  
- **Track Files:** Required individual write‑ups for Tracks 1–3  
- **Contribution File:** Summary of my personal contributions  

---

## How to Run the Notebook
1. Install required Python packages (CatBoost, scikit‑learn, pandas, numpy, matplotlib, seaborn).  
2. Open the `.ipynb` notebook in Jupyter or VS Code.  
3. Run cells in order — the notebook includes preprocessing, modeling, evaluation, and segmentation.  

---

## Author
**Miranda Pachini**  
MSBA Candidate, University of Louisville  
Business Analytics & Predictive Modeling
