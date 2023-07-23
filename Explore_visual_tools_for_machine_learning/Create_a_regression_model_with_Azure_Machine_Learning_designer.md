# Create a regression model with Azure Machine Learning designer

## Introduction

- Microsoft Azure Machine Learning designer can be used to create regression models by using a drag-and-drop GUI

## Identify regression machine learning scenarios

- **Regression** is used to understand the relationships between variables to predict a desired outcome
    - Predicts a numeric *label* or outcome based on *features* (variables)
    - Example of *supervised* machine learning technique in which you train a model using data that includes both the features and known values for the label
- Some examples of regression machine learning models:
    - Using features of houses (square footgae, number of rooms) to predict home prices
    - Using features of farm conditions (weather, soil quality) to predict crop yield
    - Using features of a past campaign (advertising logs) to predict future advertising clicks

## What is Azure Machine Learning designer?

- GUI used to train, test and deploy machine learning models
- Designer projects are known as *pipelines*
- To use the designer, identify the components (building blocks) needed and connect them on the canvas, then run a machine learning job

### Pipelines

- Let you organize, manage and reuse complex ML workflows across projects and users
- Starts with the dataset to train the model
- Each run's configuration and results are stored in workspace as pipeline jobs

### Components

- Encapsulates one step in a ML pipeline
- In a pipeline project, you can access data assets and components from the left panel's *Asset Library* tab

### Datasets

- Can create data assets on the *Data* page from local files, datastore, web files and Open Datasets

### Azure Machine Learning Jobs

- Azure ML job executes a task against a specified compute target
- Jobs enable systematic tracking for ML experimentation and workflows. All jobs' run records can be viewed in Azure ML studio

## Understand steps for regression

### 1. Prepare data

- Azure ML designer has several pre-built components to prepare data for training
- Enable you to clean data, normalize features, join tables, etc.

### 2. Train model

- To train a regression model, need a dataset that includes historical *features* and known *label* values
- Common practice to train using a subset of data and remaining subset to test trained model
- Azure ML designer's **Score Model** component is used to generate the predicted class label value

### 3. Evaluate performance

- Many performance metrics and methodologies for evaluating how well a model makes predictions
    - **Mean Absolute Error (MAE)**: average difference between predicted values and true values. Lower values indicate better predictions
    - **Root Mean Squared Error (RMSE)**: square root of the mean squared difference between predicted and true values. When compared with MAE, larger difference indicates greater variance in the individual errors
    - **Relative Squared Error (RSE)**: relative metric between 0 and 1 based on the square of the differences between predicted and true values. The closer to 0, the better the model is performing.
        - Can be used to compare models where the labels are in different units since the measure is relative
    - **Relative Absolute Error (RAE)**: relative metric between 0 and 1 based on the absolute differences between predicted and true values. Closer to 0 means better performing
        - Can be used to compare models where the labels are in different units since the measure is relative
    - **Coefficient of Determination (R<sup>2</sup>)**: summarizes how much of the variance between predicted and true values is explained by the model. Closer to 1 means better performing
        - More commonly referred to as *R-Squared*
- Can review evaluation metrics on the completed job page by right-clicking on the **Evaluate model** component

### 4. Deploy a predictive service

- In order to automate model into a service that makes continuous predictions, need to create and deploy an inference pipeline

#### Inference Pipeline

- Converting training pipeline into real-time inference pipeline removes training components and adds web service inputs and outputs to handle requests
- Performs the same data transformations as the first pipeline for *new* data, then uses the trained model to *infer* label values based on its features to form the basis for a predictive service that can be published for applications to use

#### Deployment

- Endpoints page can be used to view deployment details, test pipeline service with sample data, and find credentials to connect pipeline service to a client application
- **Details** tab shows the deployment state and will indicate *Healthy* when deployment is successful, but can take a long time to be deployed
- **Test** tab can be used to provide sample JSON for testing deployed service
- **Consume** tab will provide credentials used to connect trained ML model as a service to a client app