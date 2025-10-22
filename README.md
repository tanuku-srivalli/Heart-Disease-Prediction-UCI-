# Heart-Disease-Prediction-UCI-

### 1. Introduction and Objectives

* **Project Goal:** To analyze clinical data from the `heart.csv` dataset and build an accurate Machine Learning model to predict the presence of heart disease in patients.
* **Target Variable:** `target` (0 = No Disease, 1 = Disease).
* **Target Distribution**:The target variable is relatively balanced, which is ideal for classification modeling:$54\%$ of patients have heart disease ($1$).$46\%$ of patients do not have heart disease ($0$).
* **Key Deliverables:** Cleaned dataset, Exploratory Data Analysis (EDA) insights, and an optimized classification model.

***

### 2. Data Inspection and Cleaning (Task 1: Quality)

* **Data Loading:** Confirm the dataset was loaded correctly and state its shape (e.g., (303, 14)).
* **Data Quality Check:**
    * **Missing Values:** Report the result of `df.isnull().sum()` (e.g., "Zero missing values were found, indicating a clean initial dataset.").
    * **Duplicate Rows:** Report the number of duplicates found and action taken (e.g., "One duplicate row was identified and removed to maintain data integrity.").
* **Initial Statistics:** Summarize key numerical features (e.g., "Mean age is $\sim54$ years; Cholesterol (`chol`) shows a wide range, indicating a need for scaling.").

***

### 3. Exploratory Data Analysis (EDA)

* **Target Distribution:** State the class balance (e.g., "The target variable is relatively balanced, with $54\%$ of patients having heart disease (1) and $46\%$ not having it (0).").
* **Numerical Feature Insights:**
    * **Distribution:** Discuss the shape of key distributions (e.g., Age is near-normal; Cholesterol is skewed with a few high outliers).
    * **Box Plots:** Note any visible outliers (e.g., in `chol` and `trestbps`) and how the median of numerical features differs between the $0$ and $1$ target groups.
* **Correlation Analysis (Feature Importance):** Present the Correlation Heatmap and list the features most strongly correlated with the `target`:
    * **Strong Positive Predictors:** `cp` (Chest Pain Type), `thal` (Thalium Test Result), `oldpeak`.
    * **Strong Negative Predictor:** `thalach` (Maximum Heart Rate Achieved).

***

### 4. Data Preprocessing (Task 1: Format)

* **Categorical Encoding:** Explain the use of **One-Hot Encoding** (`pd.get_dummies()`) on non-numeric features (`sex`, `cp`, `thal`, etc.) to create binary columns suitable for modeling.
* **Feature Scaling:** Explain the use of **Standard Scaling** (`StandardScaler`) on numerical features (`age`, `chol`, `trestbps`, etc.) to standardize their range.
* **Train-Test Split:** State the final split ratio (e.g., $80\%$ Training, $20\%$ Testing) and the use of `stratify=y` to maintain the class balance in both sets.

***

### 5. Model Building and Optimization

* **Baseline Models:** Briefly state the initial performance of the models tested (Logistic Regression, KNN, SVM) and identify the best-performing one (Logistic Regression, in this case).
* **Hyperparameter Tuning (GridSearchCV):**
    * **Goal:** To optimize the best model using a grid search over parameters like `C` and `penalty`.
    * **Best Parameters Found:** `{'C': 10, 'penalty': 'l2', 'solver': 'liblinear'}`
    * **Best Cross-Validation Score:** $0.8474$.

***

### 6. Final Conclusion and Interpretation

* **Final Model Accuracy:** State the definitive performance metric: "The final, optimized **Logistic Regression** model achieved a test accuracy of **$0.8525$ (85.25%)** on the unseen test set."
* **Final Classification Report & Confusion Matrix:** Include the final report and image of the Confusion Matrix. Interpret the results (e.g., "The high Recall and Precision scores indicate the model is effective at identifying both positive and negative cases of heart disease.").
* **Impact:** Conclude by summarizing which clinical factors (based on EDA/correlation) are the most significant predictors, affirming the model's potential utility as a non-invasive screening tool in a healthcare setting. Final Conclusion and Interpretation

* **Final Model Accuracy:** State the definitive performance metric: "The final, optimized **Logistic Regression** model achieved a test accuracy of **$0.8525$ (85.25%)** on the unseen test set."
* **Final Classification Report & Confusion Matrix:** Include the final report and image of the Confusion Matrix. Interpret the results (e.g., "The high Recall and Precision scores indicate the model is effective at identifying both positive and negative cases of heart disease.").
* **Impact:** Conclude by summarizing which clinical factors (based on EDA/correlation) are the most significant predictors, affirming the model's potential utility as a non-invasive screening tool in a healthcare setting.
