# Phase 3: Feature Engineering and Modeling

#Objective

To engineer new predictive variables from the cleaned transaction dataset, address the lack of a fraud label by constructing a rule-based target, and build baseline classification models to detect fraudulent transactions.

#Tasks Performed

Engineered new features: account transaction frequency, time gap from previous account activity, amount-to-balance ratio, and unique device/location count per account
Built a rule-based synthetic fraud label using thresholds on transaction amount, amount-to-balance ratio, login attempts, and online channel usage (since the dataset has no ground-truth fraud column)
One-hot encoded categorical variables (Transaction Type, Channel, Customer Occupation)
Split data into training and testing sets using stratified sampling to preserve class balance
Trained a Logistic Regression model as an interpretable baseline
Trained a Random Forest model to capture non-linear patterns and extract feature importance
Evaluated both models using Precision, Recall, F1-Score, and ROC-AUC instead of plain accuracy, due to class imbalance
Compared model performance using ROC curves
Identified the top predictors of fraud using Random Forest feature importance


#Deliverables

Feature Engineering and Model Building Notebook
Engineered dataset with new features and synthetic fraud label (transactions_with_features_and_label.csv)
Model comparison results (phase3_model_results.csv)
Confusion matrices and ROC curve visualizations
Feature importance ranking


#Key Findings

The dataset contained no fraud label, requiring a rule-based synthetic label built from patterns identified during Phase 2 EDA (high amount, high amount-to-balance ratio, multiple login attempts, high-value online transactions).
All transactions in the dataset occur between 4 PM and 6 PM, so time-of-day could not be used as a fraud indicator despite being a common signal in real fraud detection.
TransactionAmount and AmountToBalanceRatio emerged as the strongest predictors of the synthetic fraud label.
Both models achieved very high ROC-AUC scores; this is expected since the label itself was derived from these same features, and should not be interpreted as real-world fraud detection performance.
A production-grade model would require a genuine fraud label sourced from confirmed chargebacks or fraud investigations rather than rule-based thresholds.


#Limitations

Because the fraud label was synthetically generated from the same features used for prediction, the high model performance reflects the model learning the labeling rule rather than validated real-world fraud patterns. This notebook demonstrates the complete feature engineering and modeling workflow as a baseline, to be revisited if a genuine labeled dataset becomes available.

