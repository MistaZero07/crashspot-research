# Week 7 — Model Tuning & Evaluation

## 📌 Focus
Hyperparameter tuning and robust evaluation of machine learning models for crash prediction.

## ⚙️ Methods
- Applied **RandomizedSearchCV** to tune **Random Forest**.  
- Applied **GridSearchCV** to tune **Gradient Boosting**.  
- Evaluated models using **classification reports**, **confusion matrices**, and **ROC/PR curves**.  
- Performed **Stratified 5-Fold Cross-Validation** and a **shuffle-label test** to check for overfitting and data leakage.  
- Saved best performing model (`week7_best_model.pkl`) for future deployment.

## 📊 Outputs
- Figures:
  - `docs/figures/week7_ROC_RF_tuned.png`  
  - `docs/figures/week7_PR_RF_tuned.png`  
  - `docs/figures/week7_ROC_GB_tuned.png`  
  - `docs/figures/week7_PR_GB_tuned.png`
- Data:
  - `data_clean/week7_results.csv` — model accuracy, precision, recall, F1  
- Model:
  - `models/week7_best_model.pkl`

## ✅ Results
- **Test set (12 samples)**  
  - Both RF and GB achieved **100% accuracy, precision, recall, and F1**.  
- **Cross-validation (5-fold)**  
  - RF tuned: F1 = 1.000 ± 0.000, ROC AUC = 1.000 ± 0.000  
  - GB tuned: F1 = 1.000 ± 0.000, ROC AUC = 1.000 ± 0.000  
- **Shuffle Test**  
  - Performance dropped to chance (~0.20–0.34 F1), confirming no leakage.  

## 📑 Notes
- Models show **perfect predictive performance** on this dataset.  
- However, given the **small dataset size (n=60)**, results may not generalize well to larger/unseen crash data.  
- Next steps: validate on an **expanded dataset** and explore model interpretability (feature importances, SHAP).  

## 📊 Figures

### Random Forest (Tuned)
![ROC Curve](docs/figures/week7_roc_RF_tuned.png)  
![PR Curve](docs/figures/week7_pr_RF_tuned.png)

### Gradient Boosting (Tuned)
![ROC Curve](docs/figures/week7_roc_GB_tuned.png)  
![PR Curve](docs/figures/week7_pr_GB_tuned.png)
