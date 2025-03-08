# House Price Prediction Project

This repository contains our final project for **BUDT 758J**, completed in Spring 2024. The project focuses on predicting house prices using advanced regression techniques.

**Dataset:** [House Prices - Advanced Regression Techniques (Kaggle)](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)

---

## Methods Used
- **Data Preprocessing**: Set thresholds to filter out features and replace null values using imputation or deletion.
- **Exploratory Data Analysis (EDA)**: Created histograms, box plots, scatter plots, heatmaps, and pair plots to explore the distribution of data, identify outliers, and understand relationships between variables.
- **Feature Engineering**: Created new features from existing ones or transformed features to better represent the underlying data.
- **Correlation Analysis**: Calculated correlation coefficients between variables to identify potential linear or monotonic relationships. Visualized correlations using heatmaps to provide insights into variable relationships.
- **Feature Importance**: Assessed the importance of features using techniques like correlation analysis, feature selection algorithms, and machine learning models.
- **Pattern Identification**: Identified patterns or trends in the data that provided insights into underlying phenomena or relationships.
- **Model Building**: Implemented Linear Regression, Random Forest, XGBoost, Keras, and PyTorch models.

---

## EDA and Feature Selection

### **Correlation Heatmap Analysis**
The heatmap reveals strong correlations between sale prices and factors like overall quality and living area size.

![heatmap](https://github.com/user-attachments/assets/964a7466-d697-4641-9b58-8ea20641a6a8)

### **Scatter Plot**
Scatter plot showing the relationship between living area size and sale price.

![scatterplot](https://github.com/user-attachments/assets/d9d5c00e-55f1-4ef7-b606-6f991c288afa)

### **Boxplot of Sale Price by Sale Type**
Boxplot highlights a clear preference for newly built houses, leading to notably higher sale prices.

![boxplot1](https://github.com/user-attachments/assets/00994238-c1bc-4be7-aef3-f9fc595d50a6)

### **Scatter Plot**
Demonstrating a strong relationship between above-grade living area square feet and sale price, as depicted in the heatmap. The points align closely along a discernible trend line, indicating a clear positive correlation between the variables.

![scatterplot](https://github.com/user-attachments/assets/4d7e71fa-7927-4012-b854-775e07053984)

### **Bar Chart**
The bar chart indicates that houses with public utilities command higher sale prices. This can be attributed to the convenience, reliability, and regulatory compliance associated with such properties.

![bar chart](https://github.com/user-attachments/assets/6c447d68-b0eb-4d2d-895c-2178f7dae3d4)

### **Bar Chart and Scatter Plot**
A strong correlation was uncovered between overall quality and sales price. The bar chart highlights neighborhoods like NoRidge, NridgHt, and StoneBr with the highest quality ratings, suggesting that properties in these areas have the highest sale prices due to their superior quality.

![bar chart and scatter plot](https://github.com/user-attachments/assets/0e5eab08-eb96-4b9f-a3f7-547acdb698c8)

### **Bar Chart and Violin Plot**
From the bar chart above, it's evident that houses equipped with Gas A heating boast the highest quality ratings. Moreover, there's a notable prevalence of homes utilizing Gas A heating. Consequently, it can be inferred that properties featuring Gas A heating systems tend to command the highest sale prices.

![violin](https://github.com/user-attachments/assets/44f30002-5d1f-46c3-8c5f-7a5db2b931f2)

### **Box Plot for Central Air Conditioning and Sale Price**
Houses equipped with central air conditioning systems consistently exhibit higher sale prices, suggesting a strong positive correlation between the presence of central air conditioning and sale price. This finding underscores the importance of central air conditioning as a desirable feature in the real estate market.

![boxplot2](https://github.com/user-attachments/assets/82910b91-98b3-402d-8696-78f71710bbab)

---

## Results and Reports

- We utilized five model specifications and submitted predictions. The scores from Kaggle are as follows:

![score](https://github.com/user-attachments/assets/d47b9bb9-3440-462d-87da-07d8af8f35b9)

## **Model Performance**

1. **Linear Regression**: Performed best (RMSE **0.16**) using Lasso-selected features.
2. **Random Forest**: RMSE **1.01**, showing a notable performance gap.
3. **XGBoost**: Initial RMSE **1.02**, optimized to **0.83** after hyperparameter tuning.
4. **Keras**: Achieved RMSE **0.45**, optimized via hyperparameter tuning.
5. **PyTorch**: RMSE **6.84**, likely due to suboptimal hyperparameters and feature engineering.

---

## Learnings and Takeaways

### **Challenges Faced**
1. **Data Cleaning Complexity**: Identifying useful data was time-consuming. Feature selection via Lasso was crucial.
2. **Model Optimization Bottlenecks**: Parameter tuning reached a limit in improving accuracy.
3. **Feature Engineering Limitations**: Some key interactions or nonlinear relationships may have been missed.

### **Future Improvements**
- **Advanced Feature Engineering**: Polynomial features, interaction terms.
- **Enhanced Model Stacking**: Combining multiple models for improved predictions.
- **Hyperparameter Optimization**: Exploring Bayesian optimization techniques.

This project provided valuable experience in **machine learning model development, feature engineering, and predictive analytics**. Through rigorous experimentation and tuning, we improved model performance while gaining deeper insights into real estate valuation trends.
