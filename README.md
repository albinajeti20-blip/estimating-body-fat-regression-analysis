# Regression Analysis: Estimating Body Fat

This project predicts **body fat percentage** using regression techniques on body measurement data.  
The dataset included 252 samples with features like weight, abdomen, chest, wrist, etc.

## Tools & Libraries
- Python, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
- Models: Multiple Linear Regression, Support Vector Regression, Random Forest

## Methodology
1. Preprocessed dataset (cleaning, scaling, feature selection).  
2. Trained regression models on different feature sets.  
3. Evaluated with R², MSE, and MAE.  

## Results
- **Random Forest Regression** performed best with **R² = 0.655**.  
- Abdomen circumference was the strongest predictor of body fat.  

## Key Takeaway
Random Forest outperformed linear and SVR models. Abdomen, weight, and chest measurements are key predictors.
