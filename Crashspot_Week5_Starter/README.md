# Crashspot – Week 5 Starter

**Focus:** Model Preparation + Baseline ML Models

## Objectives
- Engineer numeric + categorical features from crash data  
- Define binary target (`target_multiveh`) = multi-vehicle crash  
- Train/test split of dataset  
- Evaluate baseline models (Logistic Regression, Random Forest)  
- Inspect feature importances  

## Workflow
1. Load cleaned crash dataset (`fars_monroe_2022_2023_clean.geojson`)  
2. Engineer features (`hour, month, weekday, is_weekend, is_night, ve_total, persons, peds`)  
3. Define target variable (`target_multiveh`)  
4. Train/test split (80/20)  
5. Train Logistic Regression + Random Forest models  
6. Generate evaluation plots and feature importances  
7. Save engineered dataset as `week5_features.csv`  

## Outputs
📓 Notebook: `Crashspot_Week5_Starter.ipynb`  
📊 Figures:  
- `docs/figures/week5_model_eval.png` → confusion matrices  
- `docs/figures/week5_rf_feature_importance.png` → feature importance plot  
📑 Dataset: `data_clean/week5_features.csv`  

## Insights
- Both baseline models achieve **100% accuracy** (likely due to small dataset → risk of overfitting).  
- Random Forest highlights **`ve_total`** and **`persons`** as most predictive features.  
- This engineered dataset will serve as input for Week 6 predictive modeling and dashboard development.  
