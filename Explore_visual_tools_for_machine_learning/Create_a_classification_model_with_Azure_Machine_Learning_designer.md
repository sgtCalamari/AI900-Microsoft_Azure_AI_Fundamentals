# Create a classification model with Azure Machine Learning designer

## Introduction

- Classification is an example of a *supervised* ML technique where model is trained using data that includes both features and known values for the label, so taht the model learns to *fit* the feature combinations to the label
- Trained model can be used to predict labels for new items where the label is unknown

## Identify classification machine learning scenarios

- Can be applied to binary (i.e. class applies or it doesn't) or multi-class (i.e. positive, neutral, negative) scenarios
- Examples:
    - Using clinical data to predict whether a patient will become sick or not (binary)
    - Using historical data to predict whether text sentiment is positive, negative or neutral (multi-class)
    - Using characteristics of small businesses to predict if a new venture will succeed or not

## Understand steps for classification

- Similar to training for regression models ([see notes](./Create_a_regression_model_with_Azure_Machine_Learning_designer.md#understand-steps-for-regression))

### 3. Evaluate performance

#### Confusion matrix

- Tool used to assess the quality of a classification model's predictions by comparing predicted labels against actual labels
- For binary classification, confusion matrix is a 2x2 grid showing the predicted and actual value counts for classes 1 and 0
    - *True Positive*: model correctly predicts that class applies
    - *False Positive*: model incorrectly predicts that class applies
    - *False Negative*: model incorrectly predicts that class should not apply
    - *True Negative*: model correctly predicts that class should not apply

![binary confusion matrix](./confusion-matrix-terms.png)

- For a multi-class model, same approach is used but matrix would be NxN where N is the number of classes, resulting in a diagonal line of cells where the predicted and actual labels match
- Metrics that can be derived from the confusion matrix include:
    - **Accuracy**: number of correct predictions divided by the total number of predictions
    - **Precision**: number of cases classified as positive that are actually positive; number of true positives divided by the sum of true and false positives
    - **Recall**: fraction of positive cases correctly identified; number of true positives divided by sum of true positives and false negatives
    - **F1 Score**: overall metric that essentially combines precision and recall

#### Choosing a threshold

- Classification models predict the probability for each possible class; indication of likelihood of predicted label
- By default, probability including or above 0.5 results in a class prediction of 1, while a prediction below this threshold means that there's a greater probability of a *negative* prediction (0)

#### ROC curve and AUC metric

- **True positive rate** is another term for recall, with corresponding metric **False positive rate** that measures the number of negative cases incorrectly identified as a positive compared between the number of actual negative cases
- **ROC curve** or *receiver oeprating characteristic curve* is derived by plotting these metrics against each other for every possible threshold value between 0 and 1
- The larger **A**rea **U**nder the ROC **C**urve (**AUC**), the better the model is performing