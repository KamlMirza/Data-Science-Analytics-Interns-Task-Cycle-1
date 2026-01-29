# Customer Churn Prediction: Bank Customers

## Task Objective

The primary goal of this project is to identify bank customers who are likely to leave (churn) by analyzing their demographic profiles and transaction histories. By predicting churn, the bank can implement proactive retention measures for high-risk customers, which is more cost-effective than acquiring new ones.

## Approach

The project follows a structured data science workflow:

- **Dataset Acquisition**  
  Utilized the *Churn Modelling Dataset* containing **10,000 customer records** with **14 original features**.

- **Data Cleaning**  
  Removed non-predictive columns such as `RowNumber`, `CustomerId`, and `Surname`. The dataset was also checked for missing values, and none were found.

- **Exploratory Data Analysis (EDA)**  
  Visualized churn distributions and correlations using **Seaborn** and **Matplotlib**. This included:
  - Analyzing churn rates by **Geography**
  - Creating a **correlation heatmap** for numerical features

- **Feature Engineering**
  - Encoded the `Gender` feature using **Label Encoding**
  - Applied **One-Hot Encoding** to the `Geography` feature

- **Model Training**  
  Split the dataset into **80% training** and **20% testing** sets. A **Random Forest Classifier** with **100 estimators** was trained to predict the target variable `Exited`.

- **Evaluation**  
  Model performance was assessed using:
  - Overall accuracy
  - Confusion matrix
  - Detailed classification report

## Results and Insights

### Model Performance

- **Overall Accuracy**  
  The model achieved an accuracy of **86.60%**.

- **Churn Detection**  
  The model demonstrates high precision for non-churners (**0.88**), while being more conservative in identifying churners (**recall of 0.46**).

### Key Insights

- **Top Influencers**  
  **Age**, **EstimatedSalary**, and **CreditScore** were identified as the most significant drivers of customer churn.

- **Demographic Trends**  
  Younger customers are generally more likely to remain with the bank.

- **Geographical Trends**  
  Customers located in **Germany** exhibit higher churn rates compared to those in France or Spain.

- **Business Recommendation**  
  The bank should focus targeted retention strategies on **older, high-balance customers** who show signs of inactivity.
