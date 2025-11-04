Bank Term Deposit Subscription Prediction Assignment

1. Project Objective

The goal of this project is to develop and compare machine learning classifiers to predict whether a bank client will subscribe to a term deposit. Due to class imbalance, the model is optimized using ROC AUC and evaluated heavily on Recall for the 'Yes' subscription class.

2. Data Preparation and Baseline
Dataset: Bank Marketing Dataset.
Target: Term Deposit Subscription (y).
Initial Baseline Accuracy: 88.73% (The simple prediction of the majority class, 'No').

Preprocessing Steps:

The predictive feature duration was removed to prevent data leakage.
Categorical features were converted using One-Hot Encoding.
Numerical features were scaled using the StandardScaler.

3. Model Comparison (Default Settings)

Four common classifiers were trained and compared on the full, preprocessed dataset. The comparison highlighted the Decision Tree as being severely overfit.

Model                         Train Time (s)               Test Accuracy     
Logistic Regression           ~0.15                        ~0.9085
K Nearest Neighbors           ~0.00                        ~0.9001
Decision Tree                 ~0.02                        ~0.8399
Support Vector Machine (SVC)  ~5.00                        ~0.9023

4. Hyperparameter Tuning and Final Result

The Decision Tree model was selected for tuning using GridSearchCV to improve its overall performance and generalization. 
Optimization Metric: ROC AUC.
Parameters Tuned: max_depth, min_samples_leaf, and min_samples_split.
Example of Best Parameters:
{'max_depth': 7, 'min_samples_leaf': 30, 'min_samples_split': 10}
Conclusion: The final tuned model is evaluated using a Classification Report and Confusion Matrix to ensure the best balance between Recall (identifying subscribers) and Precision (ensuring high-quality leads).
