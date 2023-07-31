# Classify images with the Custom Vision service

## Introduction

- Use predictive power of ML to enable AI systems to identify real-world items based on images

### Uses of image classification

- **Product identification**: performing visual searches for specific products in online searches or even, in-store using a mobile device
- **Disaster investigation**: identifying key infrastructure for major disaster preparation efforts
- **Medical diagnosis**: evaluating images from X-ray or MRI devices could quickly classify specific issues found as cancerous tumors, or many other medical conditions related to medical imaging diagnosis

## Understand classification

- Predict which category (*class*) something belongs to
- Use a set of quantifiable inputs (*features*) to calculate probability for each possible class and predict a *label* that indicates the most likely class for the object
    - For images, you need an existing data set of images with their corresponding labels to use for training
    - Digital images are made up of an array of pixel values and these are used as *features* to train the model

### Azure's Custom Vision service

- Most modern image classification solutions are based on *deep learning* techniques that make use of *convolutional neural networks* (CNNs) to uncover patterns in the pixels that correspond to particular classes
- [Custom Vision service documentation can be found here.](https://learn.microsoft.com/en-us/azure/cognitive-services/custom-vision-service)

## Get started with image classification on Azure

- Image classification is available as part of Azure Cognitive Services

### Azure resources for Custom Vision

- Creating a solution consists of using existing images to train the model, then publishing the model so that client applications can use it to generate predictions
- Can separate training and prediction resources to track resource utilization for model training separately from client applications using the model to predict image classes, or can combine by using Cognitive Services so that only one *endpoint* and *key* are required

### Model training

- To train a classification model, you must upload images to your training resource and label them with the appropriate class labels. Then you must train the model and evaluate the training results
- Can use the *Custom Vision portal* or a programming language-specific SDK

### Model evaluation

- **Precision**: what percentage of the class predictions made by the model were correct? 
    - For example, if the model predicted that 10 images are orange, of which eight were actually oranges, then the precision is 0.8 (80%)
- **Recall**: what percentage of class predictions did the model correctly identify? 
    - For example, if there are 10 images of apples, and the model found 7 of them, then the recall is 0.7 (70%)
- **Average Precision (AP)**: overall metric that takes into account both precision and recall

### Using the model for prediction

- When you publish the model, you can assign it a name and access it using the following:
    - **Project ID**: unique ID of the Custom Vision project you created to train the model
    - **Model name**: name you assigned the model during publishing
    - **Prediction endpoint**: HTTP address of the endpoints for the *prediction* resource to which you published the model (***not*** the training resource)
    - **Prediction key**: authentication key for the *prediction* resource to which you published the model (***not*** the training resource)