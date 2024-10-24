# Geopolitical Risk Dataset: Predicting Geopolitical Threat Using Machine Learning

### Overview
This project aims to predict the `GPRD_THREAT` (Geopolitical Risk Threat) using various machine learning models. The dataset contains geopolitical risk metrics over time and other related factors. Three different machine learning models were applied, and their performances were compared: **Linear Regression**, **Random Forest Regressor**, and **XGBoost Regressor**.

### Objective
The goal is to develop a predictive model that accurately estimates geopolitical risk based on the available features, allowing for more informed decision-making and risk analysis.

### Dataset Description
The dataset includes the following columns:
- `DAY`: Day of the recorded risk.
- `N10D`: Risk-related numeric feature.
- `GPRD`: Categorical geopolitical risk descriptor.
- `GPRD_ACT`: Categorical descriptor related to risk action.
- `GPRD_THREAT`: Target variable (the geopolitical threat level).
- `date`: Date of the observation.
- `GPRD_MA30`: 30-day moving average of the risk metric.
- `GPRD_MA7`: 7-day moving average of the risk metric.
- `event`: Rare event flags (not used in modeling).
- `Unnamed: 9`, `Unnamed: 10`: Columns with no data.

### Data Preprocessing
Before building the models, the dataset underwent the following preprocessing steps:
1. **Dropping irrelevant columns**: Columns such as `event`, `Unnamed: 9`, and `Unnamed: 10` were dropped due to missing data or irrelevance to the analysis.
2. **Label Encoding**: Categorical variables `GPRD` and `GPRD_ACT` were encoded into numeric values.
3. **Handling missing values**: The dataset was checked for missing values and cleaned appropriately.

### Models and Results
Three regression models were applied to the dataset: **Linear Regression**, **Random Forest Regressor**, and **XGBoost Regressor**. Below is a summary of each model and its performance.

#### 1. Linear Regression
Linear Regression was used as a baseline model. It assumes a linear relationship between the input features and the target variable.

- **Mean Squared Error (MSE)**: 2107.098
- **R-squared (R²)**: 0.431

The Linear Regression model captured only a moderate portion of the variance in the dataset (R² = 0.431), indicating that the relationship between the features and `GPRD_THREAT` is likely non-linear.

#### 2. Random Forest Regressor
Random Forest Regressor is an ensemble learning method that combines multiple decision trees to improve predictive performance.

- **Mean Squared Error (MSE)**: 455.423
- **R-squared (R²)**: 0.877

The Random Forest model significantly outperformed Linear Regression, achieving an R² of 0.877. This indicates that the model can explain a large proportion of the variance in the target variable. Random Forest's ability to handle complex interactions between features likely contributed to this performance.

#### 3. XGBoost Regressor
XGBoost is a high-performance gradient boosting model known for its efficiency and speed.

- **Mean Squared Error (MSE)**: 439.189
- **R-squared (R²)**: 0.881

XGBoost provided the best performance among all models, achieving the lowest MSE and the highest R² (0.881). This indicates that XGBoost is the most effective model for predicting `GPRD_THREAT`, likely due to its robust optimization and ability to capture complex patterns in the data.

### Model Comparison
| Model                | MSE       | R-squared (R²) |
|----------------------|-----------|----------------|
| **Linear Regression** | 2107.098  | 0.431          |
| **Random Forest**     | 455.423   | 0.877          |
| **XGBoost**           | 439.189   | 0.881          |

XGBoost performed marginally better than Random Forest, with the lowest MSE and highest R² value. Both Random Forest and XGBoost are well-suited for this type of dataset, as they capture non-linear relationships and interactions between the features effectively.

### Conclusion
In this project, we demonstrated that **XGBoost** is the most suitable model for predicting geopolitical threat based on the available features, followed closely by **Random Forest**. Both models outperformed the baseline **Linear Regression** model by a large margin. The performance improvement is mainly due to the models’ ability to capture complex relationships in the data.

