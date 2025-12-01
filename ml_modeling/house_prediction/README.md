# 🏠 House Price Prediction using Machine Learning

---

## Project Overview

This project implements a machine learning solution for **House Price Prediction**, a classic **regression** problem. The primary goal is to predict the continuous target variable, `SalePrice`, based on various house and lot characteristics. The notebook follows a structured workflow involving data preprocessing, exploratory analysis, and training multiple regression models.

---

## Dataset

The model utilizes the **House Price Prediction dataset** (read from `./dataset/HousePricePrediction.xlsx`). The dataset consists of **2,919 records** and **13 features**.

### Key Features and Descriptions

The dataset features include:

| Feature Name | Type | Description |
| :--- | :--- | :--- |
| `Id` | Integer | Record counter (dropped from prediction) |
| `MSSubClass` | Integer | Identifies the type of dwelling involved in the sale. |
| `MSZoning` | Categorical | General zoning classification of the sale. |
| `LotArea` | Integer | Lot size in square feet. |
| `LotConfig` | Categorical | Configuration of the lot. |
| `BldgType` | Categorical | Type of dwelling. |
| `OverallCond` | Integer | Rates the overall condition of the house. |
| `YearBuilt` | Integer | Original construction year. |
| `YearRemodAdd` | Integer | Remodel date (same as construction date if no remodeling). |
| `Exterior1st` | Categorical | Exterior covering on the house. |
| `BsmtFinSF2` | Float | Type 2 finished square feet. |
| `TotalBsmtSF` | Float | Total square feet of basement area. |
| **SalePrice (Target)** | Float | The price of the sale (the variable to be predicted). |

---

## Dependencies

The following Python libraries were imported for this project:

* **Pandas**: For data import and manipulation.
* **NumPy** (Inferred): For numerical operations.
* **Matplotlib & Seaborn**: For data visualization (including creating a correlation heatmap).
* **Scikit-learn (`sklearn`)**: Provides tools for preprocessing, model selection, and evaluation.
    * `OneHotEncoder`
    * `train_test_split`
    * `mean_absolute_percentage_error`, `r2_score`
* **Regression Models**: `SVR`, `RandomForestRegressor`, `LinearRegression`.
* **CatBoost**: Used optionally for the `CatBoostRegressor` model.

---

## Methodology and Approaches Used

The project followed a standard data science pipeline with a focus on preparing data for regression modeling:

### 1. Data Preprocessing

* **Data Dimension Check**: Confirmed the dataset shape as (2919, 13).
* **Feature Categorization**: Features were categorized based on data type for specific handling: **4 Categorical** (Object), **6 Integer** (`int64`), and **3 Float** (`float64`) variables.
* **Feature Removal**: The `Id` column was dropped from the dataset as it does not contribute to the prediction.
* **Missing Value Handling**: A plan was noted to impute missing slots with **mean, mode, 0, or NA** depending on the specific column requirement.
* **Feature Encoding**: Categorical features were planned to be converted into numerical format using **`OneHotEncoder`**.

### 2. Exploratory Data Analysis (EDA)

* **Correlation Analysis**: A **Heatmap** was generated using the `seaborn` library to visualize the correlations between all numerical features.
* **Categorical Analysis**: Bar plots were planned to be drawn to analyze the distributions within different categorical features.

### 3. Model Training and Evaluation

* **Data Splitting**: The data was split into features (`X`) and the target variable (`Y`, which is `SalePrice`). The data was then split into training (`x_train`, `y_train`) and testing (`x_test`, `y_test`) sets.
* **Models Trained**: The following regression models were trained and evaluated:
    * **Linear Regression**
    * **Support Vector Regressor (SVR)**
    * **Random Forest Regressor**
    * **CatBoost Regressor** (Trained optionally in the final steps)
* **Evaluation Metrics**: Model performance was assessed using the following metrics:
    * **R-squared Score (`r2_score`)**: Measures the proportion of the variance in the dependent variable that is predictable from the independent variables.
    * **Mean Absolute Percentage Error (MAPE)**: A measure of prediction accuracy of a forecasting method.