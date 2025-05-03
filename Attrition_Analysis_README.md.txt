# Employee Attrition Analysis and Prediction

## 1. Objective

The primary goal of this project is to analyze historical employee data to understand the key factors driving employee attrition (resignation) and to build a predictive model to identify employees who may be at high risk of leaving in the future. The ultimate aim is to provide actionable insights for developing targeted retention strategies.

## 2. Dataset Used

*   **File:** `employee_attrition_dataset.csv`
*   **Description:** This dataset contains 1000 anonymized records of employees, including demographic information (Age, Gender, Marital Status), job details (Department, Job Role, Job Level, Monthly Income), work-related metrics (Years at Company, Years Since Last Promotion, Overtime), and satisfaction/engagement scores (Job Satisfaction, Work-Life Balance, Environment Satisfaction, etc.). The target variable is `Attrition` (Yes/No).

## 3. Methodology & Workflow

The project followed these key steps:

1.  **Data Loading & Initial Inspection:** Loaded the dataset using Python (Pandas) and performed initial checks for data types, missing values, and basic statistics.
2.  **Exploratory Data Analysis (EDA):**
    *   Analyzed the distribution of the target variable (`Attrition`).
    *   Investigated relationships between various features and attrition using visualizations (Seaborn, Matplotlib). Key areas explored included:
        *   Department-wise attrition rates.
        *   Impact of Overtime.
        *   Attrition across different Salary Bands (derived from Monthly Income).
        *   Relationship between Job Satisfaction/Engagement scores and attrition.
        *   Effect of Tenure and Time Since Last Promotion.
        *   Demographic factors (Age, Gender, Marital Status).
3.  **Data Preprocessing:**
    *   Converted binary categorical features ('Attrition', 'Overtime') to numerical (0/1).
    *   Applied One-Hot Encoding to nominal categorical features (e.g., Department, Job Role).
    *   Split the data into training (75%) and testing (25%) sets using Scikit-learn, stratifying by the Attrition variable.
    *   Applied StandardScaler to numerical features on the training data and transformed both training and testing sets.
4.  **Model Building:**
    *   Trained two classification models using Scikit-learn:
        *   **Logistic Regression** (with `class_weight='balanced'` to handle imbalance).
        *   **Decision Tree Classifier** (with `max_depth=5` and `class_weight='balanced'` to handle imbalance and prevent overfitting).
5.  **Model Evaluation:**
    *   Evaluated both models on the unseen test set using:
        *   Overall Accuracy.
        *   Confusion Matrix.
        *   Precision, Recall, and F1-Score (especially for the 'Attrition = Yes' class).
6.  **Model Interpretation (SHAP):**
    *   Utilized the SHAP (SHapley Additive exPlanations) library to understand feature importance and the impact of specific features on individual model predictions for the selected model (or both). Generated summary plots and dependence plots.
7.  **Visualization & Reporting:**
    *   Developed an interactive dashboard in Power BI to visualize key EDA findings and attrition trends.
    *   Compiled a Model Performance Report including evaluation metrics and confusion matrices.
    *   Created a PDF document outlining data-driven Attrition Prevention Suggestions based on the analysis.

## 4. Tools & Technologies Used

*   **Programming Language:** Python 3.x
*   **Core Libraries:**
    *   Pandas (Data manipulation and analysis)
    *   NumPy (Numerical operations)
    *   Matplotlib & Seaborn (Data visualization)
    *   Scikit-learn (Machine Learning: Preprocessing, Modeling, Evaluation)
    *   SHAP (Model interpretation)
*   **Business Intelligence:** Microsoft Power BI (Dashboard creation and visualization)
*   **Reporting:** PDF generation (via standard document editors)

## 5. Project Files Attached / Included

1.  **`employee_attrition_dataset.csv`**: The raw input dataset used for the analysis.
2.  **`employee_attrition_analysis.ipynb`**: Jupyter Notebook or Python script containing the full code for data loading, EDA, preprocessing, modeling, evaluation, and SHAP analysis.
3.  **`Project 3.png`**: Power BI Dashboard.
4.  **`Model_Performance_Report.pdf`**: Report detailing the performance metrics (Accuracy, Confusion Matrix, Precision, Recall, F1-Score) for the evaluated machine learning models. *(Note: This might be combined with the suggestions PDF).*
5.  **`Attrition_Prevention_Suggestions.pdf`**: A document outlining key findings from the analysis and providing actionable recommendations for HR and management to reduce employee attrition.
6.  **`README.md`**: This file, providing an overview of the project.

## 6. Summary of Results

The analysis identified several key drivers strongly associated with employee attrition, including working overtime, lower job satisfaction/engagement scores, longer time since last promotion, and lower income levels. While predictive models (Logistic Regression, Decision Tree) were built, their performance on the test set indicated low reliability (Accuracy ~51-52%, low F1-scores for attrition class), suggesting the need for further feature engineering, more advanced modeling techniques, or potentially more predictive data. The Power BI dashboard provides an interactive way to explore these trends, and the suggestions report offers concrete steps based on the identified drivers.

This project is licensed under the MIT License.
