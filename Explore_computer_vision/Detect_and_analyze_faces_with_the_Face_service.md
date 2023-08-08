# Detect and analyze faces with the Face service

## Introduction

- Use AI to locate and analyze human faces in images or video content

### Face detection

- Identifying regions of an image that contain a human face, typically by returning *bounding box* coordinates that form a rectangle around the face

### Facial analysis

- Some algorithms can return other facial information, such as facial landmarks (i.e. nose, eyes, eyebrows, lips and others)
    - Can use facial features to train a ML model

![facial landmarks](./landmarks-1.png)

### Uses of face detection and analysis

- **Security**: such as building security applications
- **Social media**: automatically tag known friends in photographs
- **Intelligent monitoring**: automobile can monitor if a driver is looking at the road, looking at a mobile device or showing signs of tiredness
- **Advertising**: help direct advertisements to an appropriate demographic audience
- **Missing persons**: using public camera systems, identify if a missing person is in the image frame
- **Identity validation**: useful at ports of entry kiosks where a person holds a special entry permit

## Get started with Face analysis on Azure

- Multiple services available for detecting and analyzing faces:
    - **Computer Vision** offers face detection and some basic face analysis, such as returning the bounding box coordinates around an image
    - **Video Indexer** can be used to detect and identify faces in a video
    - **Face** offers pre-built algorithms that can detect, recognize and analyze faces

### Face

- Can return the rectangle coordinates for any human faces that are found in an image, in addition to attributes related to faces such as:
    - **Blur**: how blurred the face is (can be an indication of how likely the face is to be the main focus of the image)
    - **Exposure**: aspects such as underexposed or over exposed and applies to the face in the image and not the overall image exposure
    - **Glasses**: whether or not the person is wearing glasses
    - **Head pose**: face orientation in a 3D space
    - **Noise**: refers to visual noise in the image (grainy or full of tiny dots that make the image less clear)
    - **Occlusion**: determines if there may be images blocking the face in the image

### Responsible AI use

- Anyone can use the Face service, however the Limited Access policy requires customers to [submit an intake form](https://aka.ms/facerecognition) to access certain capabilities:
    - Ability to compare faces for similarity
    - Ability to identify named individuals in an image

### Azure resources for Face

- To use Face, create one of the following resources:
    - **Face** can be used if you don't intend to use any other cognitive services or if you want to track utilization/costs for Face separately
    - **Cognitive Services** combines multiple services and tracks usage/costs together
- Two pieces of information will be needed to use it:
    - **Key** used to authenticate client applications
    - **Endpoint** provides the HTTP address where the resource can be accessed

### Tips for more accurate results

- Considerations that can help improve accuracy:
    - *Image format*: supported formats are JPEG, PNG, GIF and BMP
    - *File size*: 6 MB or smaller
    - *Face size range*: from 36x36 up to 4096x4096. Smaller or larger faces will not be detected
    - *Other issues*: detection can be impaired by extreme face angles and/or occlusion. Best results are obtained when faces are full-frontal or as near as possible to it
