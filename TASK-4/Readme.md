# Task 4: Predicting Insurance Claim Amounts

## Objective

The primary goal of this task is to develop a predictive model that estimates individual medical costs billed by health insurance. Accurate predictions serve two main purposes:

- **For Insurance Companies:** Enhances effective risk assessment.
- **For Individuals:** Facilitates better financial planning for healthcare expenses.

## Approach

The development process followed a standard data science workflow:

### 1. Dataset Understanding

The project utilized the **Medical Cost Personal Dataset**, which includes 1,338 entries. The features analyzed include:

- **Numerical:** Age, BMI, and number of children.
- **Categorical:** Gender (female/male), Smoking status (yes/no), and US Residential Region.
- **Target Variable:** Charges (medical costs).

### 2. Data Cleaning and Preparation

- **Missing Values:** The dataset was verified to have no missing values across any columns.
- **Categorical Encoding:** To make the data compatible with a Linear Regression model, categorical variables (`sex`, `smoker`, and `region`) were converted into numerical values using **Label Encoding**.

### 3. Exploratory Data Analysis (EDA)

Visualizations were created to identify key drivers of insurance costs:

- **Scatter Plots:** Used to visualize the impact of age and BMI on charges, specifically highlighting the influence of smoking status.
- **Correlation Heatmap:** Generated to quantify the relationships between features, identifying which variables had the strongest impact on the target variable.

### 4. Model Training

- **Algorithm:** A **Linear Regression** model was selected as the baseline for cost estimation.
- **Data Splitting:** The dataset was split into a **training set (80%)** and a **testing set (20%)** to evaluate performance on unseen data.

## Results and Insights

### Model Performance

The model's accuracy was evaluated using standard regression metrics:

- **Mean Absolute Error (MAE):** 4,186.51
- **Root Mean Squared Error (RMSE):** 5,799.59

### Key Insights

- **Primary Predictor:** **Smoking** was identified as the strongest predictor of high medical insurance charges.
- **Secondary Factors:** Both **age** and **BMI** contribute positively to costs.
- **Interaction Effects:** High BMI is particularly expensive for individuals who smoke.
- **Future Improvements:** While Linear Regression provides a solid baseline, using non-linear models like **Random Forest** or **Gradient Boosting** could better capture the complex interactions between BMI and smoking status.
