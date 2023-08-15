# Analyze receipts with the Form Recognizer service

## Introduction

- Processing invoice or receipt data is a common problem
- Extract data such as key-value pairs from common forms (i.e. receipts)
- Uses the *Form Recognizer* service

## Get started with receipt analysis on Azure

- **Recognizer** service supports document processing through:
    - Pre-built receipt model trained to recognize and extract data from sales receipts
    - Custom models to extract known key-value pairs and table data from forms
- Custom models are trained using your own data (as little as 5 samples) to tailor model to specific forms
- Refer to the [Form Recognizer documentation](https://learn.microsoft.com/en-us/azure/cognitive-services/form-recognizer/) for quickstarts to train a custom model

### Azure resources to access Form Recognizer services

- Either a *Form Recognizer* resource (specific to forms, separate key/endpoint if using multiple services) or *Cognitive Services* resource (to combine multiple services with one key/endpoint)

### Using the pre-built receipt model

- Currently supports receipts in English that are common to the United States (i.e. restaurants, retail locations, gas stations)
- Extracts key information such as:
    - time of transaction
    - date of transaction
    - merchant information
    - taxes paid
    - receipt totals
    - other pertinent information that may be present on the receipt
    - all text on the receipt is recognized and returned
- Follow these guildelines:
    - Images must be JPEG, PNG, BMP, PDF or TIFF format
    - File size less than 50 MB
    - Image size between 50 x 50 and 10,000 x 10,000 pixels
    - For PDF documents, no larger than 17" x 17"
- Free tier subscription plan for receipt model only supoprts the first two pages of PDF/TIFF documents