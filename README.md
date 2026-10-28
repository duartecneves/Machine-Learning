# Machine-Learning
# Cars 4 You: Car Price Prediction

Machine learning project that estimates a used car's fair market price from information given by the user,
replacing slow manual inspections on an online car resale platform.

## Approach
- **Data preparation:** iterative imputation of missing values, frequency and target encoding of categorical
  variables
- **Feature engineering:** efficiency score (mpg-to-engine ratio), mileage per year, tax per engine size,
  ownership intensity
- **Feature selection:** Recursive Feature Elimination, Lasso, mutual information and correlation analysis
- **Models:** Linear Regression, KNN, Decision Tree, Random Forest, Extra Trees, Gradient Boosting, MLP
- **Tuning:** Optuna random search with a penalty on the train/validation gap to limit overfitting
- **Final model:** weighted ensemble of Gradient Boosting and Random Forest

## Results
| Model | Validation MAE | Validation R² |
|---|---|---|
| Gradient Boosting (best single model) | 1,231 | 0.955 |
| **Ensemble (GBR + RF)** | **1,224** | **0.956** |

The ensemble also reduced the train/validation gap (MAE 980 on train).

## Interactive interface
A Python interface takes a car's details and returns a predicted price with a confidence interval.
