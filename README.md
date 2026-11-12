<div align="center">

# 📏 Estimating Body Fat with Regression

**Can simple body measurements replace expensive tests for body-fat percentage?**
Exploratory analysis → feature selection → three regression models compared.

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0)

`252 people` · `13 measurements` · `3 models` · `best R² 0.655`

</div>

> This repository is a **project showcase**. Source code and the full report are private.
> Contact: albinajeti20@gmail.com

## Overview

Measuring body fat accurately usually needs specialised equipment such as hydrostatic weighing.
This project tests how well it can be predicted from age, weight, height and ten body circumferences (neck, chest, abdomen, hip, and so on).

| Stage | What I did |
|---|---|
| **1. Data preparation** | Cleaned the dataset (252 samples), removed an empty column and checked the distributions. |
| **2. Exploration** | Studied the correlations between the measurements and body fat. |
| **3. Modelling** | Trained Multiple Linear Regression, SVR (RBF kernel) and Random Forest on three feature sets: all features, the top 3 correlated features, and abdomen only. |
| **4. Evaluation** | Compared the models with R², MSE and MAE on a 20% test set. |

## Exploration

<p align="center"><img src="assets/correlation_matrix.png" width="680" alt="Correlation matrix"></p>

**Abdomen, chest and weight** are the measurements most correlated with body fat. Many measurements are also strongly correlated with each other (e.g. weight and chest), so several features carry overlapping information.

## Results

<p align="center"><img src="assets/model_r2.svg" width="660" alt="Best R² per model"></p>

| Model | All features | Top 3 features | Abdomen only |
|---|---|---|---|
| **Random Forest** | **0.655** | 0.626 | 0.313 |
| Linear Regression | 0.616 | 0.560 | 0.493 |
| SVR (tuned) | 0.552 | 0.576 | 0.523 |

<sub>R² on the test set. Higher is better.</sub>

- **Random Forest with all features** explains about **66% of the variation** in body fat (MSE 16.0).
- **Abdomen** is by far the most important single measurement:

<p align="center"><img src="assets/feature_importance.png" width="600" alt="Feature importance"></p>

- Abdomen alone is not enough, though. Every model does better when it also uses the other measurements.

## Next steps
- Cross-validation and hyperparameter search (e.g. `max_depth` for Random Forest)
- Ridge / Lasso regression to handle the overlapping features

<sub>© 2025 Albin Ajeti. All rights reserved. See [LICENSE](LICENSE).</sub>
