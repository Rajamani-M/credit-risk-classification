
# Credit Risk Classification

## Overview of the Analysis

The purpose of this analysis is to build a logistic regression model to predict the credit risk associated with loans. Using historical data from a peer-to-peer lending services company, we aim to classify loans as either `0` (healthy) or `1` (high-risk). This classification helps in assessing the creditworthiness of borrowers and aids in risk management.

The data includes various financial features related to the loan and borrower characteristics. The analysis involves separating the data into features and labels, training a logistic regression model, and evaluating its performance using metrics such as accuracy, precision, and recall.

### Data and Preprocessing

- **Data Source**: The data is read from the `lending_data.csv` file.
- **Target Variable (`y`)**: `loan_status`, where `0` indicates a healthy loan and `1` indicates a high-risk loan.
- **Feature Variables (`X`)**: Includes `loan_size`, `interest_rate`, `borrower_income`, `debt_to_income`, `num_of_accounts`, `derogatory_marks`, and `total_debt`.

## Instructions

### 1. Split the Data into Training and Testing Sets
   - Load the `lending_data.csv` data into a Pandas DataFrame.
   - Create labels (`y`) from the `loan_status` column and features (`X`) from the remaining columns.
   - Split the data into training and testing sets using `train_test_split`.

### 2. Create a Logistic Regression Model with the Original Data
   - Instantiate the logistic regression model with `random_state=1` and `max_iter=1000` to ensure convergence.
   - Fit the model on the training data (`X_train`, `y_train`).
   - Make predictions on the testing data (`X_test`).

### 3. Evaluate the Model’s Performance

#### Confusion Matrix
The confusion matrix provides insight into the model's prediction accuracy for each category:
- 18,655 true positives (correctly predicted healthy loans)
- 583 true negatives (correctly predicted high-risk loans)
- 110 false positives (healthy loans predicted as high-risk)
- 36 false negatives (high-risk loans predicted as healthy)

This indicates that the model has a high accuracy in identifying healthy loans (`0`) and a reasonably good performance for identifying high-risk loans (`1`).

#### Classification Report
- **For the `0` label (healthy loan)**:
  - Precision: 1.00, indicating nearly perfect accuracy in predicting healthy loans correctly.
  - Recall: 0.99, suggesting the model identified almost all actual healthy loans.
  - F1 Score: 1.00, showing a strong balance between precision and recall.

- **For the `1` label (high-risk loan)**:
  - Precision: 0.84, indicating a fair number of the predicted high-risk loans are correct.
  - Recall: 0.94, meaning the model captures most of the actual high-risk loans.
  - F1 Score: 0.89, reflecting a balanced performance in terms of precision and recall.

### 4. Write a Credit Risk Analysis Report
   Provide a clear summary of the model’s performance based on the classification report and confusion matrix.
   Highlight key metrics that demonstrate the model’s ability to accurately predict high-risk loans.

## Results Summary

Using the classification report and accuracy score, the model’s performance is as follows:

* **Accuracy Score**: 0.99, indicating that the model correctly classifies 99% of the loan statuses.

* **Logistic Regression Model**:
  - **For Healthy Loans (0)**:
    - Precision: 1.00, indicating perfect accuracy in predicting healthy loans.
    - Recall: 0.99, showing that almost all healthy loans are correctly classified.
    - F1 Score: 1.00, reflecting a strong balance between precision and recall.
  - **For High-Risk Loans (1)**:
    - Precision: 0.84, indicating good accuracy in predicting high-risk loans.
    - Recall: 0.94, suggesting the model effectively captures most high-risk loans.
    - F1 Score: 0.89, demonstrating a balanced performance in identifying high-risk loans.

## Conclusion

The logistic regression model demonstrates robust accuracy and reliable precision-recall scores for both healthy and high-risk loans. The model excels at predicting healthy loans, with a precision and recall of 1.00, minimizing any potential misclassification of safe loans as risky. While the precision for high-risk loans is slightly lower, the recall remains high, ensuring most high-risk cases are accurately flagged. This is essential for lenders who seek to minimize the risk of defaults.

Overall, the model is a powerful tool for credit risk assessment, enabling financial institutions to effectively distinguish between high and low-risk loans. Future work could involve exploring more complex algorithms like Random Forests or Gradient Boosting for potentially better performance, though the logistic regression model already provides a solid foundation.

## Bonus: Next Steps for Improvement

To further enhance the model, consider fine-tuning its settings or trying different approaches:
- Adjusting the model's parameters to see if it improves accuracy.
- Creating new features that might capture additional patterns in the data.
- Dealing with class imbalance by using techniques like resampling or adjusting weights, especially since high-risk loans are less frequent.
  
These steps could help improve the model's ability to accurately classify high-risk loans, offering even better support for credit risk management.
