# ❤️ Heart Disease Prediction using Logistic Regression

---

## Project Overview

This project implements a machine learning solution to predict the risk of **Coronary Heart Disease (CHD)** based on patient health and demographic data. This is a **binary classification** problem, utilizing the **Logistic Regression** model and its cross-validated variant (`LogisticRegressionCV`) to determine the predictive accuracy of various health factors.

---

## Dataset

The analysis uses the **`heart_disease.csv`** dataset, containing records of patients and various health indicators.

### Key Features and Descriptions

The dataset includes several features, with some preprocessing steps already applied:

| Feature Name | Description | Preprocessing Note |
| :--- | :--- | :--- |
| `sex_male` | Gender (Binary, formerly 'male') | The 'male' column was renamed to **`sex_male`**. |
| `age` | Patient's age (Inferred) | |
| `cigsPerDay` | Number of cigarettes smoked per day (Inferred) | |
| `BPMeds` | Whether the patient is on blood pressure medication (Inferred) | |
| `prevalentStroke` | Whether the patient previously had a stroke (Inferred) | |
| `prevalentHyp` | Whether the patient is hypertensive (Inferred) | |
| `diabetes` | Whether the patient has diabetes (Inferred) | |
| `totChol` | Total cholesterol level (Inferred) | |
| `sysBP` | Systolic blood pressure (Inferred) | |
| `diaBP` | Diastolic blood pressure (Inferred) | |
| `BMI` | Body Mass Index (Inferred) | |
| `heartRate` | Heart rate (Inferred) | |
| `glucose` | Glucose level (Inferred) | |
| **`TenYearCHD` (Target)** | **Target Variable**: Risk of Coronary Heart Disease in 10 years (Binary: 0 or 1) | |

**Removed Column**: The **`education`** column was explicitly **dropped** from the dataset.

---

## Dependencies

The project relies on the following Python libraries for statistical modeling and machine learning:

* **Pandas & NumPy**: For data manipulation and numerical operations.
* **Matplotlib & Seaborn**: For data visualization, especially for plotting **Confusion Matrices**.
* **Scikit-learn (`sklearn`)**: For preprocessing, model implementation, and evaluation.
    * `StandardScaler` (Feature scaling).
    * `LogisticRegression` and `LogisticRegressionCV` (The core models).
    * `train_test_split` (Data splitting).
    * `confusion_matrix`, `classification_report`, `accuracy_score` (Evaluation metrics).
* **Statsmodels (`sm`)**: Used for statistical analysis (e.g., initial model fitting).

---

## Methodology and Approaches Used

The project followed a standard classification pipeline tailored for medical risk prediction:

### 1. Data Cleaning and Preprocessing

* **Feature Dropping**: The `education` column was removed.
* **Feature Renaming**: The `male` column was renamed to `sex_male` for clarity.
* **Missing Value Handling**: A check for missing values (`df.isna().sum()`) was performed (inferred as a necessary step before scaling).
* **Feature Scaling**: The independent features (`X`) were scaled using **`StandardScaler`**. Scaling is critical for algorithms like Logistic Regression to ensure all features contribute equally to the distance calculation.

### 2. Model Training and Selection

* **Data Splitting**: The data was split into training (`x_train`, `y_train`) and testing (`x_test`, `y_test`) sets.
* **Models Trained**: Two Logistic Regression models were compared:
    * **Logistic Regression** (`LogisticRegression`)
    * **Logistic Regression with Cross-Validation** (`LogisticRegressionCV`)

### 3. Evaluation and Results

* **Accuracy Score**: The performance of each model was evaluated by calculating the **Accuracy Score** on both the **training set** and the **test set**.
* **Confusion Matrix**: A **Confusion Matrix** was generated and visualized using a `seaborn` heatmap for each model based on the predictions on the **test set**. This provides a detailed breakdown of True Positives, True Negatives, False Positives, and False Negatives.
* **Classification Report**: A comprehensive **Classification Report** was generated, which includes Precision, Recall, and F1-score for each class (0 and 1).