# 🏠 House Price Prediction Using Machine Learning

This project aims to predict house prices using two popular regression algorithms: **Linear Regression** and **Random Forest Regressor**.  
The dataset includes various features related to properties, such as location, number of bedrooms, baths, etc.

The notebook walks through all stages of a typical machine learning workflow:

- Data Preprocessing  
- Exploratory Data Analysis  
- Feature Engineering  
- Model Training  
- Model Evaluation

---

## 🔍 Key Insights & Findings

### ⚠️ Critical Finding – Data Leakage

During model development, a major **data leakage** issue was discovered.  
Including the feature `price_per_bedroom` in the training data led to a seemingly perfect **R² score of 1.00** with the Random Forest model.  

However, this feature was **directly derived from the target variable `price`**, essentially giving the model access to the answer.  
Once `price_per_bedroom` was removed, the R² score dropped to **0.91**, more accurately reflecting the model’s true performance.

> This emphasized the importance of carefully inspecting derived features to avoid unintentional leakage.

---

### 📏 RMSE Observations

Even **after removing outliers**, the **Root Mean Squared Error (RMSE)** remained **notably high**.  
This is mainly due to the **large scale of house prices**, ranging from millions to billions.  
While **R²** remained an interpretable metric, the **MSE and RMSE** values were inflated due to the wide price range and presence of extreme values.

Although techniques like **log transformation** of the target variable could have minimized this effect,  
they were **intentionally avoided** to keep the predicted prices **interpretable in real-world terms**.

---

## 🧠 Algorithms Used

- Linear Regression  
- Random Forest Regressor  

Both models were evaluated using the following metrics:

- ✅ **R² Score**  
- 📉 **Root Mean Squared Error (RMSE)**  

---

## 📝 Conclusion

This project not only demonstrates the application of **practical machine learning techniques**,  
but also highlights the importance of **vigilant feature engineering** and **thoughtful evaluation**.  

Small oversights like **data leakage** can result in misleadingly high performance,  
and inflated error values require **deeper insight into data distribution and scale**.

---
