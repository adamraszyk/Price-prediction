This project focuses on predicting prices using various regression models. It includes data exploration, feature selection, model comparison, and hyperparameter tuning.

Dataset

- Contains 7 features and 1 target variable: `price`
- All features are numeric
- No missing values

Exploratory Data Analysis

- The target variable `price` is right-skewed
- Several features show strong correlation with `price`
- Outliers were detected using boxplots and IQR analysis

Feature Selection

- Correlated features were identified using Pearson correlation
- Random Forest feature importances helped prioritize inputs

Models Compared

Nine regression models were tested using 5-fold cross-validation:

| Model             | RMSE   | R²     |
|------------------|--------|--------|
| LightGBM         | 161.0  | 0.66   |
| Random Forest    | 164.7  | 0.64   |
| XGBoost          | 172.9  | 0.61   |
| Linear/Lasso/Ridge | ~186 | ~0.55  |
| Neural Net (MLP) | 189.7  | 0.53   |
| KNN, SVR         | Poor   | <0.45  |

Final Evaluation (Train vs Test)

| Model         | Train R² | Test R² | Train RMSE | Test RMSE |
|---------------|----------|---------|------------|------------|
| LightGBM      | 0.77     | 0.65    | 125.1      | 196.9      |
| Random Forest | 0.95     | 0.68    | 58.0       | 188.4      |
| XGBoost       | 0.88     | 0.65    | 91.6       | 195.4      |
