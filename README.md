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
- `price`, `view_count`, `cart_count`, `session_duration_seconds`, `total_events_in_session`, `unique_categories_viewed`, `event_hour`, `is_weekend`
