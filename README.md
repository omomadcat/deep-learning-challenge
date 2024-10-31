# deep-learning-challenge
## Module 21 Challenge
## Predicting Funding Success for Alphabet Soup Nonprofit Applications Using Deep Learning

## Introduction
### Purpose of the Analysis
The goal of this analysis is to create a deep learning model that can predict whether an applicant for funding through Alphabet Soup will be successful. This prediction model aims to help the organization make better funding decisions by focusing on applicants with the highest chance of success.

## Data Preprocessing
### Target and Features Identification
- **Target Variable**: `IS_SUCCESSFUL`, indicating whether the application led to success.
- **Features**: All other columns except `EIN` and `NAME`, which were removed.

### Data Cleaning
- **Non-beneficial columns removed**: `EIN` and `NAME` to streamline the data.

### Handling Categorical Data
- Categorical columns with multiple values, such as `APPLICATION_TYPE` and `CLASSIFICATION`, were grouped to reduce rare categories and then encoded using `pd.get_dummies()`.

### Data Splitting and Scaling
- The data was split into training and testing sets to enable effective evaluation.
- Applied `StandardScaler` to standardize feature values for optimal model performance.

## Model Architecture and Attempts
### First Model Attempt
- **Model Design**: Simple neural network with two hidden layers (80 and 30 neurons, ReLU activation) and a sigmoid output layer for binary classification.
- **Training**: Model trained over 50 epochs.
- **Results**: Achieved an accuracy of around 72.7% on test data.

### Second Model Attempt
- **Changes Made**: Increased model complexity by adding an additional hidden layer and a dropout layer to prevent overfitting.
- **Training and Results**: Increased training epochs to 100, achieving a slight accuracy improvement to 72.99%.

### Third Model Attempt
- **Further Optimizations**: Added Batch Normalization, changed activation function to `tanh` in the first layer, and reduced dropout to 0.3.
- **Early Stopping**: Implemented early stopping to avoid overtraining and reduce computational costs.
- **Results**: Best achieved accuracy was around 73%, slightly below the target of 75% accuracy.

## Results Summary
### Key Insights
- **Target variable**: `IS_SUCCESSFUL`.
- **Columns removed**: `EIN`, `NAME` as they were deemed non-beneficial.
- **Changes across attempts**: Additional layers, batch normalization, and activation adjustments.

### Overall Model Performance
The model’s accuracy plateaued at around 73%, suggesting that either the data lacks clear distinguishing features for success prediction, or that a deep learning model may not be the most effective choice for this structured dataset.

## Alternative Model Recommendation
### Recommended Model: Random Forest or XGBoost
- **Reasoning**: These models are highly effective for structured/tabular data and handle categorical features well. They are also less sensitive to scaling and often outperform deep learning models on structured data.
- **Expected Outcome**: Improved interpretability and potentially higher accuracy, as Random Forest and XGBoost could better capture non-linear relationships in structured data.

## Resources
- **Tools & Libraries**: Pandas, TensorFlow, Scikit-learn
- **Assistance**: GitHub Copilot & ChatGPT for conceptual guidance and coding support