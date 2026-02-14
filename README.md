Credit Card Fraud Detection Analysis

a. Problem Statement
The objective of this project is to build and deploy a machine learning system capable of identifying fraudulent credit card transactions. Given the high volume of daily transactions, manual review is impossible. This system automates the detection process to protect customers from unauthorized charges and minimize financial loss.

b. Dataset Description 

Source: Kaggle (mlg-ulb/creditcardfraud).
Instance Size: 284,807 transactions.
Feature Size: 31 features (Time, Amount, Class, and 28 PCA-transformed features V1-V28).
Target Variable: Class (1 for fraudulent transactions, 0 for genuine).

Characteristics: The dataset is highly imbalanced, with frauds accounting for only 0.172% of all transactions.

c. Models Used
Six classification models were implemented and evaluated using the same dataset. The following table summarizes their performance across all mandatory metrics:

--- Model Comparison Table ---
| ML Model Name       |   Accuracy |      AUC |   Precision |   Recall |       F1 |      MCC |
|:--------------------|-----------:|---------:|------------:|---------:|---------:|---------:|
| Logistic Regression |   0.999122 | 0.975293 |   0.863636  | 0.581633 | 0.695122 | 0.708353 |
| Decision Tree       |   0.999087 | 0.902771 |   0.705357  | 0.806122 | 0.752381 | 0.753608 |
| KNN                 |   0.999526 | 0.93356  |   0.938272  | 0.77551  | 0.849162 | 0.852794 |
| Naive Bayes         |   0.977827 | 0.967106 |   0.0603774 | 0.816327 | 0.112439 | 0.218423 |
| Random Forest       |   0.999579 | 0.95244  |   0.974359  | 0.77551  | 0.863636 | 0.869075 |
| XGBoost             |   0.999579 | 0.94059  |   0.940476  | 0.806122 | 0.868132 | 0.87051  |

d. Performance Observations
Based on the results above, here are the observations regarding model performance:

Logistic Regression: Achieved the highest AUC (0.975), indicating excellent separability, but had the lowest Recall among the top performers, missing nearly 42% of fraud cases.

Decision Tree: Showed a strong Recall (0.806) but suffered from lower Precision compared to ensemble methods, leading to more false positives.

kNN: Provided a very balanced performance with high Precision (0.938) and a strong MCC (0.852), though it is computationally more expensive.

Naive Bayes: While it had a high Recall (0.816), its Precision was extremely low (0.060), making it impractical due to the massive number of false alarms.

Random Forest (Ensemble): Tied for the highest Accuracy and provided the highest Precision (0.974), making it very reliable for minimizing false fraud alerts.

XGBoost (Ensemble): Produced the best overall balance for fraud detection with the highest MCC (0.870) and F1 Score (0.868), effectively capturing 80.6% of frauds with high confidence.
