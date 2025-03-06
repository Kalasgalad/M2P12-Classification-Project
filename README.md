# M2P12-Classification-Project
--------

**The objective of the M2P12 Classification Project is to create a model that predicts whether or not a customer will cancel their membership causing churn.**

**The tools used for this project are the following:**
1. Feature Engineering and Data Preprocessing
2. Logistic Regression
3. K Nearest Neighbours (KNN)
4. Decision Trees and Random Forests

**M2P12 Classification Project has the following conditions:**
1. Project must include EDA section.
2. Project must include visualization.
3. Data must be cleaned and prepared.
4. Use Feature Engineering, if applicable.
5. Must compare at minimum 3 classification models.
6. Provide validation scheme (simple or cross-validation).
7. Explain which feature(s) are chosen for final model.
8. Use final model to make new predictions based on my provided input.

## Project Overview

1. EDA, Visualization, Data Cleaning, Encoding, Data Preparation (ex: Split to X and y).  <br>
2. Model #1: Logistic Regression. <br>
3. Model #2: K Nearest Neighbours (KNN). <br>
4. Model #3: Random Forest (Classifier). <br>
5. Determine which of the three models has the best performance, and will be selected as the prediction model.
The final prediction model will use chosen inputs in the Data Frame and produce conclusions.
   
  <u>Observations from Visualization:</u> 
- More occurrences of Churn at higher Monthly Charges.
- More occurrences of Churn with the 'Month-to-month' Contract Type.
- More occurrences of Churn (compared to No Churn) seen at lower Tenure (Months) and higher Monthly Charges.

  <u>Features Dropped:</u> <br>
- Dropped features with unique values for every row/customer ('CustomerID', 'Count', etc.)
- Dropped features related to location ('State', 'Lat Long', etc.): all customers are within the same country and state, there would have little to no variance, which would contribute little to predicting churn. <br> 
- Dropped Churn Value: This is already in Churn Label, which will be encoded. <br>
- Dropped Churn Score: This feature is likely derived or unnecessary, and is too closely related to Churn Label as target variable. <br>
- Dropped Churn Reason: This is a text-based column, not usable for training models as there could be too many catergories and sparse data. <br>

  <u>Encoders used, converting features to numerical data:</u> <br>
- 'Total Charges' feature has dtype "object" but they are strings of numerical values. This feature was converted to have numerical values.
- Label Encoding on features with binary choices/values.
- One Hot Encoding on features with multiple choices/values (greater than 2 choices).

## Model Comparison
   - The three classification models to be compared: Logistic Regression, K Nearest Neighbours (KNN) and Random Forest (Classifier).
   - Model #1: Logistic Regression (Scaled)
   - Model #2: K Nearest Neighbours (KNN) (Scaled)
   - Model #3: Random Forest (Classifier).
     
**Validation Scheme (simple or cross-validation).**
   - Cross-validation (with GridsearchCV) was used on all three models to evaluate and acquire the best parameters for each model.
   - Cross-validation was used to evaluate the holdout data, and has (somewhat) similar results/metrics with the test data.

**Features chosen for Final Model.**
   - Final model chosen is Logistic Regression.
   - Features which deal with demographics, performance, service, plans, offerings/benefits, payments and time duration were chosen as they could influence churn.
   - Features chosen: Gender, Senior Citizen, Partner, Dependents, Tenure Months, Phone Service, Multiple Lines, Online Security, Online Backup, Device Protection, Tech Support, Streaming TV, Streaming Movies, Paperless Billing, Monthly Charges, Total Charges, CLTV, Internet Service_Fiber optic, Internet Service_No, Contract_One year, Contract_Two year, Payment Method_Credit card (automatic), Payment Method_Electronic check, Payment Method_Mailed check    

**Final model predictions with chosen inputs from DataFrame**
   - As per prediction experimentation, with "new_data (data frame)" as input, the Logistic Regression Model was able to provide a prediction of No Churn (0) or Churn (1).

## Conclusion 
In conclusion, three models were tested: Logistic Regression, K Nearest Neighbours (KNN) and Random Forest (Classifier). <br>

*Of the three models, the Logistic Regression model had the best performance as it has the highest Churn F1-Score, as well as a good balance between Churn Precision, Churn Recall and Accuracy.* <br>

- For chosen features (applied to final model, Logistic Regression): features which deal with demographics, performance, service, plans, offerings/benefits, payments and time duration were chosen as they could influence churn. <br>
- Cross-validation (with GridSearchCV) was used for all three models. The reason is so we could evaluate the best parameters in a similar method before choosing final model. Cross-validation was used to evaluate the holdout data, and has (somewhat) similar results/metrics with the test data.<br>
- All three classification models required the data to be converted into numerical format hence the use of encoding. For features with binary values, LabelEncoder was used for encoding. For features with three or more values, OneHotEncoder was used. <br>   
- With what was stated above, the final model (Logistic Regression) had the encoding feature LabelEncoder for features with binary values and OneHotEncoder for features with three or more values. These encoders were applied as part of feature engineering for the final model (Logistic Regression). <br>  
- Continuing with feature engineering, scaling was applied on the data for the final model (Logistic Regression), as it makes it more efficient. <br>
- As per prediction experimentation, with "new_data (data frame)" as input, the Logistic Regression Model was able to provide a prediction of No Churn (0) or Churn (1). <br>
