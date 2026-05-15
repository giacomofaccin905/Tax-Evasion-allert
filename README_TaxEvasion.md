# 🔍 Tax Evasion Risk Assessment — From Expected Utility to Evasion Risk: A Machine Learning Approach

A machine learning project built on the Allingham & Sandmo (1972) theoretical framework to estimate individual tax evasion propensity using Italian household data (SHIW — Bank of Italy).

---

##  Project Overview

The project models the utility trade-off between tax evasion and compliance at the individual level. An agent evades if and only if EU(evasion) > EU(compliance). This utility differential is used as a latent decision criterion and estimated through a **Random Utility Model (RUM)** implemented via CatBoost.

---

##  Dataset

**SHIW (Survey on Household Income and Wealth)** — public panel data disseminated by the Italian Central Bank, containing individual-level information on income, consumption, wealth, and financial assets.

---

##  Methodology

- **Data Cleaning:** removal of missing values and negative observations; outlier treatment via 99th percentile quantile capping
- **Benford's Law Analysis:** digit frequency analysis on total income to detect statistical anomalies, segmented by geographic area and work sector
- **Feature Engineering:** construction of `MDA_score` (Mean Absolute Deviation from Benford's Law) and `ratio_consume` (consumption-to-income ratio) as evasion risk proxies
- **Clustering (K-Modes):** unsupervised segmentation into 4 risk groups — `low_risk`, `acceptable_risk`, `medium_risk`, `high_risk` — manually labelled based on feature relationships
- **CatBoost Classifier:** gradient boosting model estimating the individual probability of being classified as `high_risk`

---

##  Key Results

- Total income (`yt`) and first digit of income (`first_digit_yt`) emerged as the strongest predictors of evasion probability
- The `high_risk` cluster peaks distinctly near P=1, confirming strong model separation
- Results are consistent with A-S theoretical predictions: evasion probability increases with the utility surplus from concealment and decreases as audit probability or penalties rise

---

##  Dependencies

- Python 3.x
- `pandas`, `numpy`, `matplotlib`, `seaborn`
- `catboost`, `kmodes`, `scikit-learn`

---

##  Author

**Giacomo Faccin**  
Master's Degree in Data Analytics for Business and Society — Fintech & Bigtech track  
Ca' Foscari University of Venice  

---

##  License

This project is for academic purposes only.
