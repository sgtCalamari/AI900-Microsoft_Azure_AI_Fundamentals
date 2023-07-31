# Detect objects in images with the Custom Vision service

## Introduction

- *Object detection* is a form of ML-based computer vision in which a model is trained to recognize individual types of objects in an image and to identify their location in the image

### Uses of object detection

- **Checking for building safety**: evaluating the safety of a building by analyzing footage of its interior for fire extinguishers or other emergency equipment
- **Driving assistance**: creating software for self-driving cars or vehicles with *lane assist* capabilities
- **Detecting tumors**: medical imaging such as an MRI or X-rays that can detect known objects for medical diagnosis

## What is object detection?

- Object detection models return the following information:
    - *Class* of each object identified in the image
    - *Confidence* of the predicted class being correct
    - *Bounding box* of each object's coordinates
- Object detection goes further than image classification by classifying individual objects within the image and returning the coordinates of a bounding box that indicates the object's location

## Get started with object detection on Azure

- [Similar to image classification](Classify_images_with_the_Custom_Vision_service.md#azure-resources-for-custom-vision) with regard to using Custom Vision or Cognitive Services

### Image tagging

- Before you can train an object detection model, you must tag the classes and bounding box coordinates in a set of training images
    - *Custom Vision portal* provides a GUI to make this process straightforward
- After tagging and training with an initial dataset, *smart tagging* can be used to suggest classes and bounding boxes for additional images
- Key considerations when tagging training images for object detection are:
    - Ensuring that you have sufficient images of the objects in question
    - Offering multiple angles for the object classes being trained
    - Making sure bounding boxes are defined tightly around each object

### Model training and evaluation

- [See considerations for image classification](./Classify_images_with_the_Custom_Vision_service.md#model-training)

### Using the model for prediction

- [See requirements for image classification](./Classify_images_with_the_Custom_Vision_service.md#using-the-model-for-prediction)