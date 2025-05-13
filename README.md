# DATA102 Final Project: Modeling CO₂ Emissions Across eGRID Subregions

This repository contains the final project for the UC Berkeley DATA102 course. The project investigates the drivers of CO₂ emissions across U.S. electricity subregions using EPA eGRID data.

## 🔍 Project Overview

We used two complementary approaches:

- **Causal Inference (Synthetic Control Method)** – Used to evaluate the impact of potential energy policy interventions over time.
- **Predictive Modeling (GLMs)** – Applied both parametric (PCR) and non-parametric (Random Forest) models to predict CO₂ emissions and identify key drivers.

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `DATA102_Final_project.report.pdf` | Full written report, including EDA, methodology, results, and discussion |
| `Final_Project_Code.ipynb` | Master notebook combining code from both team members |
| `Final_Project_Code.GLM.ipynb` | Notebook containing GLM work (Random Forest + PCR) and model diagnostics |
| `README.md` | This file |

## 📈 Modeling Summary

### Nonparametric Model (Random Forest)
- Used for high-dimensional prediction without requiring feature selection
- Evaluated using MSE, MAE, and out-of-bag \( R^2 \)
- Identified top predictors using impurity-based feature importances

### Parametric Model (Principal Component Regression)
- Applied PCA to reduce dimensionality and eliminate multicollinearity
- Selected top PCs covering ~92% variance
- Refit the OLS model using only statistically significant PCs (PC1, PC3, PC5)
- Back-projected coefficients to interpret feature contributions

### Causal Model (Synthetic Control)
- Constructed synthetic control units to estimate counterfactual CO₂ emissions
- Focused on identifying policy impact using pre/post trends
