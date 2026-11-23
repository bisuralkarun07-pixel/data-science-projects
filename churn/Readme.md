Telco Customer Churn Prediction
Project Overview

Customer churn refers to the situation where customers stop using a company's products or services. Predicting customer churn helps businesses identify customers who are likely to leave and take preventive actions to improve customer retention.

This project focuses on analyzing customer data and building machine learning models to predict whether a customer will churn or stay with a telecommunications company.

Two classification algorithms are implemented and compared:

Logistic Regression
Random Forest Classifier
Dataset

The project uses the Telco Customer Churn Dataset, which contains customer information and service-related details.

Initial records: 7,043
Initial features: 21
Records after preprocessing: 7,010
Features after preprocessing: 20 (including target variable)
Key Features
Feature	Description
Gender	Customer's gender
SeniorCitizen	Whether the customer is a senior citizen
Partner	Whether the customer has a partner
Dependents	Whether the customer has dependents
Tenure	Number of months the customer has stayed
InternetService	Type of internet service
Contract	Customer's contract type
PaymentMethod	Customer's payment method
MonthlyCharges	Monthly amount charged
TotalCharges	Total amount charged
Churn	Whether the customer left the company

Target Variable: Churn

Yes: Customer has churned
No: Customer has not churned
Technologies and Libraries

The project uses Python and the following libraries:

Pandas – Data manipulation and analysis
Matplotlib – Data visualization
Seaborn – Statistical data visualization
Scikit-learn – Machine learning and model evaluation
Project Workflow
1. Data Loading and Exploration
Loaded the dataset using Pandas.
Examined the first 10 records using head().
Checked dataset structure, column names, and data types using info().
Identified numerical and categorical variables.
2. Data Cleaning and Preprocessing

The following preprocessing steps were performed:

Converted TotalCharges from object to numeric using pd.to_numeric().
Used errors='coerce' to convert invalid values into missing values.
Converted SeniorCitizen from numerical values (0 and 1) into categorical values (No and Yes).
Removed the customerID column because it does not provide useful predictive information.
Identified 11 missing values in TotalCharges and removed those records.
Checked and removed duplicate records.

After preprocessing, the dataset contained 7,010 records and 20 columns.

3. Exploratory Data Analysis (EDA)

Exploratory Data Analysis was performed to understand customer behavior and identify patterns associated with churn.

Numerical Analysis:

Analyzed tenure, MonthlyCharges, and TotalCharges.
Used histograms to understand the distributions of numerical variables.
Compared numerical feature distributions based on churn status.

Categorical Analysis:

Examined unique values in categorical variables.
Used count plots to visualize customer distributions.
Compared categorical features with churn using the hue='Churn' parameter.
4. Feature Engineering and Preprocessing

A preprocessing pipeline was created using Scikit-learn.

Numerical Features:

Missing values were handled using SimpleImputer(strategy='median').

Categorical Features:

Missing values were handled using SimpleImputer(strategy='most_frequent').
Categorical variables were converted into numerical representations using OneHotEncoder(handle_unknown='ignore').

A ColumnTransformer was used to combine numerical and categorical preprocessing.

5. Train-Test Split

The dataset was divided into training and testing sets.

Training data: 80%
Testing data: 20%
Random state: 10

The target variable Churn was converted into binary values:

Yes = 1
No = 0
Machine Learning Models
Model 1: Logistic Regression

Logistic Regression was implemented as the first classification model.

Parameters:

Penalty: L2
C: 1.0
Solver: lbfgs
Random state: 10

The model was trained using a Scikit-learn pipeline that combines preprocessing and classification.

Model 2: Random Forest Classifier

Random Forest was implemented as the second classification model.

Parameters:

Number of estimators: 200
Maximum depth: 10
Minimum samples split: 2
Maximum features: sqrt
Random state: 10

Random Forest combines multiple decision trees to improve classification performance.

Model Evaluation

Both models were evaluated using the following metrics:

Accuracy: Measures the overall percentage of correct predictions.
Precision: Measures how many predicted churn customers actually churned.
Recall: Measures how many actual churn customers were correctly identified.
Confusion Matrix: Shows correct and incorrect predictions for each class.
Model Comparison

Both models produced the same evaluation results in the current experiment.

Evaluation Metric	Logistic Regression	Random Forest
Accuracy	79.74%	79.74%
Precision	63.58%	63.58%
Recall	55.38%	55.38%
Confusion Matrix

Both models produced the following confusion matrix:

text
[[912 118]
 [166 206]]

	Predicted No	Predicted Yes
Actual No	912	118
Actual Yes	166	206
Conclusion

In this project, Logistic Regression and Random Forest were implemented to predict customer churn.

Both models achieved:

Accuracy of approximately 79.74%.
Precision of approximately 63.58%.
Recall of approximately 55.38%.

The models correctly classified a significant proportion of customers but still missed some customers who actually churned.

Since identifying customers who are likely to leave is important for customer retention, improving recall could be a useful direction for future work.

Further improvements could include:

Hyperparameter tuning.
Feature selection.
Feature scaling for Logistic Regression.
Handling class imbalance using class weights or SMOTE.
Threshold tuning to improve churn detection.
Comparing additional classification algorithms.
Project Structure
text
Telco-Customer-Churn/
│
├── Telco churn.csv
├── Telco_Customer_Churn.ipynb
└── README.md

How to Run the Project
Clone or download this repository.
Install the required libraries:
bash
pip install pandas numpy matplotlib seaborn scikit-learn

Make sure the dataset is in the project directory.
Open the Jupyter Notebook:
bash
jupyter notebook

Run the notebook cells sequentially to perform data preprocessing, EDA, model training, and evaluation.

Project Goal: To use machine learning techniques to identify customers who are likely to churn and help telecommunications companies improve customer retention.
