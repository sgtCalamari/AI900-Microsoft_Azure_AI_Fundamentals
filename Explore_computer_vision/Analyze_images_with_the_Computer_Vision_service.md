# Analyze images with the Computer Vision service

## Introduction

- *Computer vision* is one of the core areas of AI and focuses on creating solutions that enable AI applications to "see" the world and make sense of it
- Potential uses include:
    - **Content Organization**: identify people/objects in photos and organize them based on that identification
    - **Text Extraction**: analyze images/PDF documents that contain text and extract the text into a structured format
    - **Spatial Analysis**: identify people/objects in a space and map their movement within that space
- To AI models, images are arrays of pixel values. These numeric values can be used as *features* to train ML models to make predictions about images and their contents

## Get started with image analysis on Azure

- Computer Vision service is a cognitive service in Azure that provides pre-built computer vision capabilities

### Azure resources for computer vision

- To use the Computer Vision service, create one of the following resource types:
    - **Computer Vision**: use this resource type if you don't intend to use any other cognitive services, or if you want to track utilization and costs for your Computer Vision resource separately
    - **Cognitive Services**: use this resource type if you plan to use multiple cognitive services and want to simplify administration and development
- For these resources, two pieces of information will be provided and are required for usage:
    - **Key** used to authenticate client applications
    - **Endpoint** that provides the HTTP address to access the resource

### Analyzing images with the Computer Vision service

#### Describing an image

- Ability for Computer Vision to analyze an image, evaluate objects detected, and generate a human-readable phrase or sentence to describe what was detected
- May return multiple results depending on the image contents, each with its own confidence score

#### Tagging visual features

- Computer Vision service can suggest *tags* for the image analyzed based on its set of thousands of recognizable objects, that can be particularly useful for indexing

#### Detecting objects

- Similar to tagging, but provides additional bounding box coordinates to indicate the top, left, width and height of objects detected

#### Detecting brands

- Computer Vision service provides the ability to identify commercial brands, returning a response with the brand name, a confidence score (from 0 to 1) and bounding box coordinates for where the brand was found

#### Detecting faces

- Computer Vision service can detect and analyze human faces in an image, including the ability to determine age and a bounding box rectangle for the location of the face(s)
- Facial analysis capabilities are a subset of those provided by the dedicated **Face Service** and for more comprehensive needs, it should be used instead

#### Categorizing an image

- Similar to capabilities provided by tagging, categorization into a [limited set of categories](https://learn.microsoft.com/en-us/azure/cognitive-services/computer-vision/category-taxonomy) based on contents using a parent/child heirarchy

#### Detecting domain-specific content

- Two specialized models are available while categorizing images:
    - **Celebrities**: uses a model trained to identify thousands of well-known celebrities from the worlds of sports, entertainment and business
    - **Landmarks**: identify famous landmarks, such as the Taj Mahal and the Statue of Liberty

#### Optical character recognition

- Used to detect printed and handwritten text in images

#### Additional capabilities

- **Detect image types** i.e. identify clip art images or line drawings
- **Detect image color schemes** specifically, identifying the dominant foreground, background and overall colors in an image
- **Generate thumbnails** to create small versions of images
- **Moderate content** detecting images that contain adult content or depict violent, gory scenes