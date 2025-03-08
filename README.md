# House Price Prediction Project

This repository contains our final project for **BUDT 758J**, completed in Spring 2024. The project focuses on predicting house prices using advanced regression techniques.

Data: https://www.kaggle.com/competitions/house-prices-advanced-regression-
techniques

---

## Methods used
- **Data preprocessing**: Set the threshold to filter out features and replace null values. with in and
using like or deletion.
- **Exploratory Data Analysis (data visualization)**: Creating histograms, box plots, scatter plots, heatmaps, ans pair plots to explore the distribution of data, identify outliers, and understand relationships between variables.
- **Feature Engineering**: Creating new Features from existing ones or transforming feature to better represent the inderlying data.
- **Correlation Analysis**: Calculating correlation coefficients between variables to identify potential linear or monotonic relationships. Visualizing correalations using heatmaps to provide insights into varable relationships.
- **Feature Importance**: Assessing the importance of features using techniques like correlation analysis, feature selection algorithms, or machine learning models.
- **Identifying Patterns**: Searching for patterns or trends in the data that may provide insights into underlying phenomena or relationships.
- **Building models** (Linear regression, Random Forest, XGboost, Keras, Torch)

---

## EDA and Feature Selection

### Correlation Heatmap Analysis
The heatmap reveals strong correlations between sale prices and factors like overall quality and living area size.

<img width="509" alt="heatmap" src="https://github.com/user-attachments/assets/964a7466-d697-4641-9b58-8ea20641a6a8">

### Boxplot of Sale price by Sale Type
Boxplot highlights a clear preference for newly built houses, leading to notably higher sale prices.

<img width="544" alt="boxplot1" src="https://github.com/user-attachments/assets/00994238-c1bc-4be7-aef3-f9fc595d50a6">

### Scatter Plot
Scatter plot showing the relationship between living area size and sale price.

<img width="484" alt="scatter plot 1" src="https://github.com/user-attachments/assets/6b20b764-093d-4425-981a-360a03e4b7eb" />

### Bar chart
The bar chart indicates that house with public utilities command higher sale prices. This can be attributed to the convenience, reliability, and regulatory compliance associated with such properties.

<img width="594" alt="barplot1" src="https://github.com/user-attachments/assets/311da32d-09ee-4a88-935d-deb847a39ac3" />

### Bar chart and Scatter plot
We uncover a strong correlation between overall quality and sales price. The bar chart highlights neighborhoods like NoRidge, NridgHt, and StoneBr with the highest quality ratings, suggesting that properties in these areas have the highest sale prices due to their superior quality.

<img width="1279" alt="subplot" src="https://github.com/user-attachments/assets/e822b892-a01f-40af-868d-713cb1a820a5" />

### Bar chart and Violin plot
From the bar chart above, it's evident that house equipped with Gas A heating boast the highest quality ratings. Moreover, there's a notable prevalence of homes ultilizing Gas A heating. Consequently, it can be inferred that properties featuring Gas A heating systems tend to command the highest sale prices.

<img width="1239" alt="violin subplot" src="https://github.com/user-attachments/assets/95e31de5-2ed0-4326-ae63-73bd9da40d20" />

### Box plot for Central air condition and Sale price
Houses equipped with central air conditioning systems consistently exhibit higher sale prices, suggesting a strong positive correlation between the presence of central air conditioning and the sale proce. This finding underscores the importance of central air conditioning as a desirable feature in the real estate market.

<img width="591" alt="boxplot2" src="https://github.com/user-attachments/assets/9f16ffbc-fed0-4290-967a-b7f74ea4586c" />

## Feature Engineering
### Create New Feature: "expensive_neighbor"
This represent the neighborhood having the average price is in top 13 neighbors

<img width="698" alt="boxplot3" src="https://github.com/user-attachments/assets/a6e1abb4-5c26-4533-84bb-1e27c96f9b9c" />

### Create New Feature: "YearGroup"
We grouped the houses depends on their salePrice

<img width="1309" alt="house price subplot" src="https://github.com/user-attachments/assets/1b82ca93-96de-496c-941e-885365f0af85" />

---

## Result and Reports

- We ultilized five model specification and submit the prediction, the scores from kaggle are as follows:

<img width="610" alt="kaggle score" src="https://github.com/user-attachments/assets/daee2963-1b7a-42ae-a2a5-37d41de5d03b" />

## Model Type:

1. Linear regression model
We employed linear regression, leveraging the feature set curated by the Lasso model. This strategic approach yield the most favorable performance on Kaggle, surpassing the efficacy of all other models we explored in our analysis.

2. Random Forest
Despite diligent optimization efforts, the resultant score yirld was 1.01025, indicating a notable performance gap compared to the top-performing model. This disparity underscores the importance of our meticulous model selection and parameter tuning processes in pursuit of optimal performance.

3. XGboost
The first XGBoost model we used only tuned the learning rate parameter. We attempted to find the optimal learning rate within the range of 0.0001 to 0.05.
However, even after finding the best one, the score on Kaggle remained very high (1.02). Consequently, we decided to tune more parameters, as found in this code sample. After adding additional parameter settings, we attempted to tune the learning rate once again, The following graph depicts the relationship between learning rate and MAE. We concluded that the optimal learning rate is 0.008199999999999999, and retrained the model achieved a better score than the previous attempt.

<img width="591" alt="learning rate" src="https://github.com/user-attachments/assets/8c2d785a-6233-4e92-b265-2821887fb333" />

4. Keras
Keras has the second-highest score among all the models we tried. We tuned parameters such as optimizer, loss function, units_layer, activation, batch size, and validation split to find the combination with the smallest MAE. The following table indicates the top 15 combinations out of 217, which have the least MAE.
According to these results, we observed some common settings, such as optimizer = SGD, loss function = mean_squared_error, and activation = sigmoid. With these findings, we retrained the Keras model using the optimal combination and achieved the second-highest score.

<img width="603" alt="Screenshot 2025-03-07 at 11 12 28 PM" src="https://github.com/user-attachments/assets/5dcb33a9-a146-4c66-9213-5cd6d960bf52" />

5. Torch
Our implementation of the Torch model employed Rectified Linear Unit (ReLU) activation functions across two layers, with the Adam optimizer and Mean Squared Error (MSE) as the loss function. Despite these strategic choices, the performance on Kaggle fell short of expectations.

---

## Learning and Takeaways

### Main Challenge
- Our team found data cleaning to be the most complex part of the project. It involves identifying useful data from a large dataset. We started with Exploratory Data Analysis (EDA), using charts to discover important insights. Then, in the feature engineering phase, we created new variables and used a Lasso model to help us select features. This was the most time-consuming part because improving model accuracy through parameter tuning cannot compare to the importance of starting with clean, well-prepared data.

### Second Challenge: Modeling
- We built several models, including Keras, Random Forest, and Linear Regression, but hit a bottleneck where no amount of parameter tuning significantly improved our accuracy. We identified a few potential reasons. One might be less than ideal feature selection. Even with Lasso helping us choose features, we might have missed some important ones or incorrectly excluded them. Additionally, our feature engineering might not have been very effective, missing key interactions or nonlinear relationships.

### Solutions for improvement
- To enhance our model's performance, we plan to reevaluate our feature selection strategy, possibly incorporating more advanced techniques like model-based feature selection (e.g., feature importance from Random Forests). We also plan to explore more feature engineering techniques, such as polynomial features and interaction features, to better capture complex patterns.
By implementing these steps, we hope to overcome current challenges, improve model accuracy, and successfully meet our project goals.
check spelling and anything that I can adjust to polish this project
