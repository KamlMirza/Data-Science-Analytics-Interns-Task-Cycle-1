# Credit Risk Prediction Project

## Task Objective

The primary goal of this project is to build a **classification model** that predicts whether a loan applicant is likely to **default** on their loan. This is a critical task for financial institutions to **minimize financial risk** and ensure that loans are granted to individuals with a **high probability of repayment**.

## Approach

The project followed a structured **machine learning pipeline**:

### Data Preparation
- The **Loan Prediction Dataset** was utilized, containing demographics, financials, and loan details.
- The dataset was found to be **clean with no missing values**.

### Feature Engineering
- Categorical variables, specifically the `purpose` column, were converted into numerical format using **One-Hot Encoding**.

### Exploratory Data Analysis (EDA)
- Visualized the **distribution of installments** and **loan purposes**.
- Analyzed the relationship between **FICO scores** and **interest rates** using joint plots.
- Examined **annual income** relative to loan status.

### Model Training
- The data was split into a **70% training** and **30% testing** set.
- **Feature Scaling** was applied using `StandardScaler` to ensure model convergence and handle varying data ranges.
- A **Logistic Regression** model was trained (with `max_iter=1000`) for the binary classification task.

## Results and Insights

### Model Performance
- **Accuracy**: The Logistic Regression model achieved an overall accuracy of **84.62%**.
- **Classification Metrics**:
  - The model showed a high recall for predicting **successful payments** (**0.99** for class 0) but struggled with identifying **defaults** (**0.04** for class 1).
  - This discrepancy is attributed to **class imbalance** within the dataset.

### Key Insights
- **FICO Scores**: Borrowers with higher FICO scores are significantly more likely to fully repay their loans.
- **Loan Purpose**: Debt consolidation is the most frequent reason for a loan but also shows a noticeable volume of defaults.
- **Installments**: Higher installment amounts do not always correlate directly with higher default rates, as income levels play a mediating role.

### Recommendations
- Implement techniques like **SMOTE** to handle class imbalance.
- Explore alternative models, such as a **Random Forest Classifier**, to improve sensitivity toward high-risk applicants.
