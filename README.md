# DS605: Fundamentals of Machine Learning

Lab Assignment - 3

Scikit-learn: Data Preprocessing and Model Performance Evaluation

Name: KUMARI SHREYA Student ID: 202618041

Dataset

The dataset used for this assignment is the Kaggle Hotel Booking Demand
dataset (hotel_bookings.csv).

The target variable used for prediction is is_canceled.

0 represents bookings that were not cancelled. 1 represents bookings
that were cancelled.

Data Preprocessing

The dataset was first loaded and explored using head(), shape, info(),
describe(), and dtypes.

The class distribution of the target variable is_canceled was checked
before model training.

The dataset was separated into features (X) and target (y).

Missing values were analyzed by calculating the count of missing values
for each column.

The company column was removed because it had a very high percentage of
missing values and did not provide enough useful information for
prediction.

The columns reservation_status and reservation_status_date were removed
because they directly reveal the final booking outcome and could cause
data leakage.

Outliers were checked using boxplots and the IQR method. No extreme
outliers were removed, so the number of rows removed was 0.

Preprocessing Pipelines

Two different preprocessing pipelines were created using Scikit-learn.

Pipeline A: - Numerical features: KNNImputer with StandardScaler -
Categorical features: SimpleImputer with most_frequent strategy and
OneHotEncoder

Pipeline B: - Numerical features: KNNImputer with MinMaxScaler -
Categorical features: SimpleImputer with most_frequent strategy and
OneHotEncoder

Train Test Split

The dataset was divided using train_test_split with:

test_size = 0.2 stratify = y random_state = 42

Machine Learning Models

Two classification models were trained:

1.  Logistic Regression with max_iter=1000

2.  Decision Tree Classifier with random_state=42

Model Performance Comparison

Model Training Accuracy Testing Accuracy Precision Recall F1 Score

Logistic Regression + StandardScaler 81.86% 81.71% 80.50% 66.81% 73.02%

Logistic Regression + MinMaxScaler 81.41% 81.27% 80.28% 65.53% 72.16%

Decision Tree + StandardScaler 99.62% 85.88% 80.84% 81.12% 80.98%

Decision Tree + MinMaxScaler 99.62% 85.88% 80.85% 81.10% 80.97%

Final Observations

1.  The Decision Tree models performed better than Logistic Regression
    models based on testing accuracy and F1-score.

2.  Decision Tree with StandardScaler gave the best overall performance
    with the highest F1-score of approximately 0.81.

3.  StandardScaler performed slightly better than MinMaxScaler for
    Logistic Regression because Logistic Regression is affected by
    feature scaling.

4.  Scaling did not create a major difference for Decision Tree because
    tree-based models are not sensitive to feature scaling.

5.  Logistic Regression showed very little overfitting because training
    and testing accuracy were almost similar. Decision Tree showed
    possible overfitting because the training accuracy was much higher
    than testing accuracy.

Files Included

-   Lab_3_Hotel_Booking_ML.ipynb
-   cleaned_hotel_bookings.csv
-   model_comparison.csv
-   logistic_confusion_matrix.png
-   decision_tree_confusion_matrix.png
