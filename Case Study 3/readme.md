# Case Study 3: Predicting Diabetic Patient Encounter Outcomes
## 1. Decision Tree Model
### Data Pre-processing
- Dataset: `D3.csv` (similar to D2.csv with an additional "readmitted" column)
- Pre-processing: Reused from Case Study 2, with additional steps for handling "readmitted" as a target variable.
- Data Split: 70% training, 30% testing; stratified split.

### Default Decision Tree
- Accuracy: Training 100%, Test 56.85% (indicating overfitting).
- Tree Size: 19591 nodes, 9796 leaves; depth 47.
- First Split Variable: `number_inpatient`.
- Top 5 Variables: `num_lab_procedures`, `num_medications`, `time_in_hospital`, `number_inpatient`, `age`.
- Parameters: Default settings; criterion = gini, max_depth = None.

### Tuned Decision Tree
- Optimal Hyperparameters: criterion = gini, max_depth = 7, min_samples_leaf = 170.
- Accuracy: Training 64.17%, Test 63.81% (less overfitting than default).
- Tree Size: 103 nodes, 52 leaves; depth 7.
- Top 5 Variables: `number_inpatient`, `discharge_disposition_id_11`, `age`, `number_emergency`, `number_outpatient`.
- Performance: Improved test accuracy and reduced overfitting compared to the default model.

### Comparison
- Tree Size & Depth: Tuned model has significantly fewer nodes and a shallower depth.
- Performance: Tuned model has better generalization with improved test accuracy and ROC AUC score.

## 2. Regression Model
### Data Pre-processing
- Pre-processing: Similar to Decision Tree, with additional one-hot encoding for categorical variables.
- Data Split: 70% training, 30% testing; stratified split.
### Default & GridSearchCV Regression
- Model: Logistic Regression.
- Top 5 Variables: `discharge_disposition_id_11`, `number_inpatient`, `number_emergency`, `admission_type_id_7`, `discharge_disposition_id_1`.
- Accuracy: Default: Training 64.72%, Test 64.57%. GridSearchCV: Training 64.72%, Test 64.57%.
- Overfitting: Minimal difference between training and testing accuracies indicates no significant overfitting.
### RFE Regression
- Accuracy: Training 64.60%, Test 64.49%.
- Overfitting: Very slight difference between training and test accuracies.

## 3. Neural Network Model
### Data Pre-processing
- Pre-processing: Same as Regression, with feature scaling and one-hot encoding.
- Data Split: 70% training, 30% testing; stratified split.
### Default Neural Network
- Parameters: Hidden Layer Size = 100, Max Iterations = 200, Alpha = 0.0001, Activation = 'relu'.
- Accuracy: Training 76.06%, Test 60.85% (indicating overfitting).
### GridSearchCV Neural Network
- Optimal Parameters: Hidden Layer Size = 9, Alpha = 0.001.
- Accuracy: Training 67.11%, Test 64.86%.
- Overfitting: Small difference between training and test accuracies.
### Dimensionality Reduction
- Top 3 Variables: `discharge_disposition_id_11`, `number_inpatient`, `number_emergency`.
- Accuracy: Training 64.72%, Test 64.47%.
- Overfitting: Minimal difference between training and test accuracies.

## Final Remarks
### ROC and Accuracy
- Best Model: Neural Networks with GridSearchCV (ROC AUC 0.6967).
- Decision Making: Neural Networks show the highest performance but lack interpretability. Logistic Regression provides a balance of performance and interpretability.
### Model Comparison
- Decision Tree: Easy to implement and interpret but can overfit without tuning.
- Logistic Regression: Simple and interpretable but limited by linear assumptions.
- Neural Networks: High performance but complex and less interpretable.

