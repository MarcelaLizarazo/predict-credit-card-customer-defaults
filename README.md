# Predict Credit Card Customer Defaults

## 1.	Project Overview

This project aimed to predict the likelihood of default on credit card payments by clients in Taiwan. Utilizing a dataset with 30,000 observations and 23 independent variables, we constructed and evaluated three predictive models: Logistic Regression, Random Forest, and Gradient Boosting Machines (GBM)/XGBoost.

## 2.	Data Summary 
The dataset comprised demographic details, credit data, history of payment, and bill statements from April to September 2005.

## 3.	Data Processing and Analysis
   
Data cleaning involved correcting headers, converting data types, and handling outliers.

- **Fixing Headers:** Aligning the dataset's headers to accurately reflect each variable.
- **Data Type Conversion:** Changing variables to numeric or categorical types as necessary.
- **Outlier Analysis:** Boxplot and histogram visualizations revealed significant outliers, especially in bill and payment amount variables, suggesting a wide range of financial behaviours among clients. Categorical data showed expected distributions across gender, education, and marital status, with anomalies in education and marriage categories addressed by categorizing unknown values as such.

## 4.	Variable Selection and Transformation
   
Correlation analysis indicated high inter-correlations among bill amount variables, prompting the removal of some to reduce multicollinearity. StandardScaler was applied to numerical variables, and One-Hot encoding was used for categorical variables, preparing the data for modeling.

## 5.	Model Development
   
Three predictive models were chosen for their distinct capabilities:

- **Logistic Regression:** Chosen for its simplicity and interpretability.
-	**Random Forest:** Selected for its robustness and ability to handle numerous input variables.
-	**XGBoost:** Favored for its efficiency and performance in handling imbalanced datasets.

## 6.	Model Validation and Evaluation
   
Each model underwent a rigorous validation process, including hyperparameter tuning and cross-validation, to ensure robustness and generalizability. Evaluation metrics such as Accuracy, AUC-ROC, and F1 Score were used to assess each model's performance.

- **Hyperparameter Tuning:** Optimization of model parameters to improve performance.
- **Cross-Validation:** Evaluation of model generalizability using 5-fold cross-validation.
- **Overfitting Assessment:** Analysis of model performance on training and test datasets to check for overfitting.

## 7.	Key Findings

- **Logistic Regression:** Both accuracy and AUC-ROC are relatively low. This suggests that while the model is better than random guessing, there is still a considerable margin for improvement, especially in detecting default cases (class 1).
- **Random Forest:** Similar to logistic regression in terms of accuracy and AUC-ROC, with a slight increase in F1 score. Since Random Forest is a tree-based model, it can capture non-linear interactions between variables that logistic regression might miss.
- **XGBoost:** Offers the best AUC-ROC among the models evaluated, indicating a superior ability to distinguish between positive and negative classes. While the accuracy isn't significantly higher than the other models, the improvement in AUC-ROC is important in contexts where the cost of false negatives (failing to detect a default) is high.

## 8.	Business Relevance
   
Early detection of defaults can enable financial institutions to take preemptive actions, making a good balance between precision and recall crucial.

The improvement in AUC-ROC suggests that XGBoost is better suited to handle the inherent imbalance in default data, where default cases are less frequent than non-default cases.

## 9.	Additional Considerations

- Models need to be capable of handling changing payment behavior dynamics over time, and XGBoost with its boosting approach may adapt better to these trends.
- Model interpretability is crucial for business implementation. While tree-based models like Random Forest and XGBoost may be less interpretable than logistic regression, they offer greater accuracy and the ability to handle complex, non-linear data.

## Conclusion

Based on the results, XGBoost is the preferred model due to its higher AUC-ROC and its ability to handle classification in an imbalanced dataset. However, it's important to highlight that the search for improved performance metrics should also consider the model's ability to be interpreted and applied in business decisions. Financial entities could benefit from delving deeper into the most significant variables identified by XGBoost and applying proactive credit risk management strategies based on these insights.

