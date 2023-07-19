# Use Automated Machine Learning in Azure Machine Learning

## Introduction

- Machine Learning (ML) is the foundation for most artificial intelligence solutions
- Azure Machine Learning is a cloud service to train and manage ML models

## What is Machine Learning?

- *Supervised Machine Learning* requires that you start with known label values
    - **Regression**: used to predict a continuous value (i.e. price, sales total, etc.)
    - **Classification**: used to determine a class label (binary or multi-class labels)
- *Unsupervised Machine Learning* does not require starting with known label values
    - **Clustering**: used to determine labels by grouping similar information into label groups
 - Feature selection is an integral part of data processing

## What is Azure Machine Learning studio?

- Training and deploying a ML model involves resource-intensive work
- Azure ML helps automate many time-consuming tasks associated with training models
- Azure ML workspace is used to manage data, compute resources, code, models and other artifacts
- Azure ML studio is a web portal for ML solutions in Azure
    - To use it, you must assign the workspace created to Azure ML studio
- Azure ML compute targets are cloud-based resources to run model training and data exploration
    - **Compute Instances**: development workstations data scientists can use to work with data and models
    - **Compute Clusters**: scalable VM clusters for on-demand processing of experiment code
    - **Inference Clusters**: deployment targets for predictive services that use trained models
    - **Attached Compute**: links to existing Azure compute resources (i.e. VMs or Azure Databricks clusters)

## What is Azure Automated Machine Learning?

- Automatically tries multiple pre-processing techniques and model-training algorithms in parallel
- Operations run in Azure ML are called *jobs*
    - Job run configuration provides information needed to specify training script, compute target and Azure ML environment

## Understand the AutoML process

1. **Prepare data**: identify features and labels. Pre-process data as needed.
2. **Train model**: split data into training and validation data. Train model using training set, then test the model using validation set.
3. **Evaluate performance**: comapre how close model's predictions are to known labels
4. **Deploy a predictive service**: deploy model as an application on a server or device for others to use

- ML models must be trained with existing data, u sually encapsulated into a *data asset*
- Automated ML capabilities in AzureML support supervised models
- Difference betweeen predicted and actual value (residual) is used to indicate amount of error in model
    - Root mean squared error (RMSE) is calculated by squaring errors in model, finding its mean, then taking square root
    - Normalized RMSE (NRMSE) standardizes this metric for comparison usage
- Can deploy a service as an Azure Container Instances (ACI) or Azure Kubernetes Service (AKS) cluster
    - AKS is recommended for production but requires an inference cluster compute target
