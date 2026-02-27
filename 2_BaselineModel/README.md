# Baseline Model

**Notebook:** `baseline_model_CPH2.ipynb`  
**Dataset:** `final_dataset.csv`

## Baseline Model Results

### Dataset Summary
- **Rows / Columns:** 10,896 rows × 22 columns
- **Date range:** 2013-07-01 → 2018-07-31
- **Target variable:** `Revenue` (continuous)

### Model Selection
- **Baseline Model Type:** Multilinear Regression (Ordinary Least Squares / OLS)
- **Rationale:** A linear regression baseline is a standard “first-pass” model for continuous targets. It is easy to interpret (feature coefficients), quick to train, and provides a strong reference point before introducing non-linear models.

### Feature Selection
The baseline uses a small, intuitive feature set:
- **Calendar signal:** `Holiday`
- **Autoregressive signal:** `lag_1` (previous day’s revenue)
- **Product mix:** one-hot indicators `Product_2` … `Product_6`

**Final feature list (7 features):**
`Holiday`, `lag_1`, `Product_2`, `Product_3`, `Product_4`, `Product_5`, `Product_6`

### Model Performance
**Hold-out test set (80/20 split, random_state=42):**
- **MSE:** 5901.34
- **RMSE:** 76.82
- **R²:** 0.7544

**Cross-validation (5-fold, shuffled, random_state=42; scikit-learn `LinearRegression` on same features):**
- **CV MSE:** 5810.49 ± 790.55
- **CV R²:** 0.7502 ± 0.0197
- **CV RMSE (√mean MSE):** 76.23

### Evaluation Methodology
- **Split strategy:** random train/test split (80% train, 20% test)
- **Training:** statsmodels `OLS` with an intercept term
- **Metrics used:**
  - **MSE (Mean Squared Error)** and **RMSE (Root Mean Squared Error)** for error magnitude
  - **R²** for variance explained / goodness-of-fit

### Metric Practical Relevance
- **RMSE (~76.8):** Interpretable in the same units as `Revenue`. Roughly, predictions are off by ~77 revenue-units on a “typical” day (larger misses are possible because RMSE penalizes large errors).
- **MSE (~5901):** Useful for model optimization/comparison because many training objectives minimize squared error; less interpretable than RMSE due to squared units.
- **R² (~0.75):** About 75% of the variance in revenue is explained by this small feature set (holiday + lag-1 + product indicators). This sets a strong reference point for improvements from richer seasonality, promotions, weather, non-linearities, etc.

## Next Steps
This baseline model serves as a reference point for evaluating more sophisticated models in the [Model Definition and Evaluation](../3_Model/README.md) phase.

