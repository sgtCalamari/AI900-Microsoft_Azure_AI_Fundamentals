# Introduction to Anomaly Detector

## Introduction

- Used to determine whether values in a series are within expected parameters

## What is Anomaly Detector?

![example of anomaly detection](./batch-anomaly.png)

- In the graphic, shaded area indicates boundary (or sensitivity range) with solid blue line indicating measured values
- Orange dots indicate anomalies, or data points outside the shaded boundary
- Sensitivity boundary is a parameter specified when calling the service

### Azure's Anomaly Detector service

- Part of the *Detection Services* category within Azure Cognitive Services
- Uses the concept of a "one parameter" strategy where only the *Sensitivity* (from 1 to 99) is needed to adjust the outcome to fit the scenario

## How Anomaly Detector works

- By default, upper and lower boundaries are calculated using concepts known as **expectedValue**, **upperMargin** and **lowerMargin**
- You can adjust the boundaries by applying a **marginScale** to the upper and lower margins:

*upperBoundary* = *expectedValue* + (100 - *marginScale*) * *upperMargin*

### Data format

- Accepts JSON data, such as:
```
{
    "granularity": "hourly",
    "series": [
      {
        "timestamp": "2021-03-02T01:00:00Z",
        "value": -10.56
      },
      {
        "timestamp": "2021-03-02T02:00:00Z",
        "value": -8.30
      },
      {
        "timestamp": "2021-03-02T03:00:00Z",
        "value": -10.30
      },
      {
        "timestamp": "2021-03-02T04:00:00Z",
        "value": 5.95
      },
    ]
}
```
- Supports maximum of 8640 data points (more data points can result in latency for response)
    - Chunking large data point sets (windowing) can improve performance

### Data consistency recommendations

- If your data may have missing values in the sequence, consider the following recommendations:
    - Sampling occurs every few minutes and has less than 10% of the expected number of poitns missing
        - Impact should be negligible on the detection results
    - If more than 10% is missing, options are available to help "fill" the gaps
        - Consider the linear interpolation method to fill in missing values and complete the data set to fill gaps with evenly distributed values

## When to use Anomaly Detector

### Batch detection

- Involves applying the algorithm to an entire data series at one time
- Best used when data contains:
    - Flat trend time series data with occasional spikes or dips
    - Seasonal time series data with occasional anomalies
        - Seasonality is considered to be a pattern in your data, occurring at regular intervals (i.e. hourly, daily, monthly)

### Real-time detection

- Uses streaming data by comparing previously seen data points to the last data point to determine if your last one in an anomaly
- By calling the service with each new data point, you can monitor your data as it's created

