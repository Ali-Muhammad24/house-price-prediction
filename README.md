🏠 House Price Prediction Using Machine Learning
This project aims to predict house prices using two popular regression algorithms: Linear Regression and Random Forest Regressor. The dataset includes various features related to properties, such as location, number of bedrooms, baths, etc.

The notebook walks through all stages of a typical machine learning workflow—data preprocessing, exploratory data analysis, feature engineering, model training, and evaluation.

🔍 Key Insights & Findings
⚠️ Critical Finding – Data Leakage
During model development, a major data leakage issue was discovered. Including the feature price_per_bedroom in the training data led to a seemingly perfect R² score of 1.00 with the Random Forest model. However, this feature was directly derived from the target variable price, creating a shortcut for the model.
Once price_per_bedroom was removed, the R² score dropped to 0.91, which more accurately reflects the model's true performance. This highlighted the importance of carefully inspecting derived features for potential leakage.

📏 RMSE Observations
Even after performing outlier removal, the Root Mean Squared Error (RMSE) remained notably high. This is primarily due to the large scale of house prices, which ranged from millions to billions. While the R² score remained a reliable metric, the magnitude of MSE and RMSE was inflated.

Although transformations like log-scaling the target variable could have improved these error metrics and reduced the influence of extreme values, they were intentionally avoided to preserve the interpretability of the predicted prices in their original scale.

🧠 Algorithms Used
Linear Regression

Random Forest Regressor

Both models were evaluated using:

R² Score

Root Mean Squared Error (RMSE)

📝 Conclusion
This project not only demonstrates practical machine learning but also highlights the importance of vigilant feature engineering and evaluation. Small oversights like data leakage can lead to overly optimistic results, while high error metrics require a deeper understanding of the data’s scale and distribution.
