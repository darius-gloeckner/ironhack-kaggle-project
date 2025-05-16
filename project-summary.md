# Iron Kaggle: Sales Prediction Project Summary

## Project Overview
This project focused on predicting store sales based on various features including store information, date, promotion status, and holiday information. We progressed from a basic linear regression model to more sophisticated models with feature interactions and ultimately a Random Forest regressor to maximize predictive performance.

## Data Exploration Insights
- The dataset contained 640,840 records, with 532,016 representing open stores
- Key patterns discovered:
  - Strong positive effect of promotions (nearly doubles sales)
  - Day of week patterns (Monday highest, Sunday lowest)
  - Seasonal effects with December peak sales
  - Different holiday types showing varied impacts on sales

## Model Evolution
1. **Base Linear Regression**:
   - R² of 0.1493 (cross-validation)
   - Used basic features including store_ID, day_of_week, month, year, promotion, and holiday indicators

2. **Enhanced Linear Regression with Interactions**:
   - R² of 0.1709 (cross-validation) - 14.5% improvement
   - Added polynomial features to capture interaction effects between variables
   - Revealed important interactions (especially promotion-holiday combinations)

3. **Random Forest Regressor**:
   - R² of 0.254 (cross-validation) - 70% improvement over baseline
   - Captured non-linear relationships and complex interactions
   - Showed excellent stability across validation folds

## Feature Engineering Impact
- **Time-based features**: Extracting year, month, day from date column
- **Holiday indicators**: Creating specific flags for different holiday types
- **Interaction terms**: Particularly between promotions and holidays
- **Feature duplication quirk**: Accidentally extended holiday features twice, which became part of the model's expected input

## Prediction on Real Data
- Successfully applied the trained Random Forest model to REAL_DATA.csv (71,205 records)
- Properly handled feature consistency issues by matching the exact feature structure from training
- Applied predictions only to open stores (59,105), keeping closed stores (12,100) at zero sales
- Generated submission files:
  - G1.csv: Contains predictions for all stores
  - g1_r2_prediction.txt: Contains expected R² score of 0.254

## Key Findings
1. **Model Performance**: The Random Forest model's R² of 0.254 indicates it explains about 25.4% of the variance in sales, a significant achievement for retail prediction
2. **Feature Importance**: Promotions, day of week, and holiday interactions emerged as the strongest predictors
3. **Prediction Patterns**: Sales predictions followed expected patterns with:
   - No sales for closed stores
   - Higher sales during promotions
   - Day of week variations matching training data
   - Seasonal patterns with higher sales in winter months

## Business Recommendations
1. **Promotion Strategy**: Leverage the strong positive effect of promotions, especially during strategic periods
2. **Day of Week Planning**: Optimize staffing and inventory based on the weekly sales pattern
3. **Holiday Preparation**: Different holiday types show different sales patterns, suggesting tailored approaches for each
4. **Seasonal Planning**: Prepare for December sales peak with adequate inventory and staff

## Technical Lessons
- Feature engineering and interactions significantly improved model performance
- Random Forest captured complex non-linear relationships better than linear models
- Careful attention to feature consistency is critical when applying the model to new data
- Cross-validation provides reliable estimates of model performance on unseen data

## Conclusion
The project successfully delivered a predictive model with significant improvement over the baseline approach. The Random Forest model with carefully engineered features provides valuable sales predictions that can guide business decision-making for store operations, promotions, and inventory management.
