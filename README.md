# Predicting-Purchasing-Behavior-Project

## Project Overview
In this project, I worked with a team to predict a customer purchase behavior. This was done using transactional and web session data from an online store. We then compared performance across multiple models to determine the most efficient approach.

## Key Objectives
1. **Predict Purchase Likelihood:** Build machine learning models to forecast whether a session ends in a purchase ($1 = \text{Yes}, 0 = \text{No}$).
2. **Identify Behavioral Drivers:** Determine which customer actions (e.g., cart adds, total events, view counts) most strongly indicate intent to buy.
3. **Model Optimization:** Compare performance across multiple algorithms (linear baselines, tree-based models, and neural networks) to balance accuracy and computational efficiency for targeted marketing.

## Dataset
- <a href="https://github.com/thowardIV/Predicting-Purchasing-Behavior-Project/blob/main/ecommerce_sample.zip">Dataset</a>

## Preprocessing
  * Group by product and session
  * Removed missing values
  * $60 / 40$ train-test split

# Key Predictors
`price`, `view_count`, `cart_count`, `session_duration_seconds`, `total_events_in_session`, `unique_categories_viewed`, `event_hour`, `is_weekend`

## Models & Performance Summary

We evaluated six different modeling approaches:

| Model | Accuracy | Insights & Findings |
| :--- | :---: | :--- |
| **Linear Regression** | $R^2 = 0.0043$[cite: 1] | Statistically significant ($p < 0.0001$)[cite: 1], but fails to capture non-linear relationships[cite: 1]. Serves as a baseline[cite: 1]. |
| **Decision Tree** | ~97.4%[cite: 1] | **Misleading:** High accuracy due to class imbalance[cite: 1]; predicted `0` (No Purchase) for all instances[cite: 1]. |
| **Logistic Regression** | 97.5%[cite: 1] | Strong performance ($\text{ROC AUC} = 0.9015$)[cite: 1]. Reveals that long sessions with high product views ("endless browsing") negatively correlate with purchase probability ($\beta = -4.6$)[cite: 1]. |
| **Random Forest** | High[cite: 1] | Resolved variance issue of single trees[cite: 1]. Top predictors: `session_duration_seconds` ($21.4\%$), `view_count` ($16.5\%$), and `cart_count` ($13.5\%$)[cite: 1]. |
| **Small Neural Net** | **98.62%**[cite: 1] | **Best performance/efficiency trade-off** (Execution time: ~89s)[cite: 1]. |
| **Medium Neural Net**| 98.63%[cite: 1] | Similar accuracy to Small NN, but execution time doubled (~194s)[cite: 1]. |
| **Large Neural Net** | 98.53%[cite: 1] | Accuracy slightly dropped due to overfitting and added noise (~500s runtime)[cite: 1]. |

---
