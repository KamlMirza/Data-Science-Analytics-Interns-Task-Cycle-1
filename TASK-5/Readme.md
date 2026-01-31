# Project: Personal Loan Acceptance Prediction

## Task Objective

The primary goal of this project is to develop a **classification model** that predicts which bank customers are most likely to accept a personal loan offer. By leveraging a bank marketing dataset containing customer demographics and past marketing interactions, the project aims to help the bank:

- Identify high-potential customer segments for targeted campaigns.  
- Improve overall marketing efficiency and reduce operational costs.  
- Increase loan conversion rates by focusing efforts on high-value customers.

## Approach

The project follows a structured data science workflow, from data preparation to model evaluation:

### 1. Dataset Understanding

The analysis utilizes the **Bank Marketing Dataset**, which includes records of 45,211 clients contacted via phone campaigns.

- **Key Features:** Includes age, job type, marital status, education, account balance, housing/personal loan status, and call duration.  
- **Target Variable (`y`):** Indicates if the client subscribed to the offer ("yes" or "no").

### 2. Data Cleaning and Preparation

- **Missing Values:** The dataset was verified to contain no null values.  
- **Encoding:**  
  - The target variable (`y`) and binary categories (default, housing, loan) were converted to 0/1 using `LabelEncoder`.  
  - Multi-class categorical variables (job, marital, education, etc.) were processed using **One-Hot Encoding**.  
- **Data Splitting:** The prepared data was split into an **80% training set** and a **20% testing set**.

### 3. Exploratory Data Analysis (EDA)

Visualizations were created to identify patterns in loan acceptance:

- **Age:** Distribution analyzed to see the density of customers across different age brackets.  
- **Job Type:** Management and blue-collar roles represent large contact groups, while certain roles like "retired" and "student" show specific acceptance trends.  
- **Marital Status:** Married individuals formed the largest portion of the dataset contacted.

### 4. Model Training

A **Decision Tree Classifier** was selected for its interpretability and ability to handle mixed data types.

- **Hyperparameters:** A `max_depth=5` was applied to prevent overfitting and ensure the model remains easy to interpret.

## Results and Insights

### Model Performance

The classification model achieved the following metrics:

- **Overall Accuracy:** 89.64%  
- **Confusion Matrix:** Successfully identified 7,777 "No" responses and 328 "Yes" responses in the test set.  
- **Class Imbalance:** While accuracy is high, the model showed a lower **recall for the "Accepted" class (0.30)** because the majority of customers in the dataset do not subscribe to loans.

### Key Predictors

| Predictor | Insight |
| --- | --- |
| **Duration** | The strongest predictor; longer phone conversations significantly increase acceptance. |
| **Poutcome (Success)** | Customers who accepted previous offers are highly likely to accept again. |
| **Demographics** | Factors like age and account balance play a measurable role in the prediction. |

### Business Recommendations

- **Prioritize Past Success:** Target customers with a "poutcome_success" status for the highest conversion potential.  
- **Improve Engagement:** Sales representatives should be trained to extend call durations and improve engagement quality to boost acceptance.  
- **Niche Targeting:** Tailor marketing strategies specifically toward **students** and **retired individuals**, as these groups exhibit higher relative acceptance rates.
