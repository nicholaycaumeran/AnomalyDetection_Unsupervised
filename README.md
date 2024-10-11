# Unsupervised Isolation Forest Model for Anomaly Detection (Fraud or money laundering cases) in Banking Transaction Withdrawals 

## Project Overview
This project implements an unsupervised Isolation Forest model to detect anomalies in banking transaction withdrawals. The model identifies unusual patterns in withdrawal amounts and frequencies, which could indicate fraudulent or money laundering activities

## Data Information
The data was extracted from a Czech bank with real transactional data from 1993 to 1999. There are 1,056,320 rows in this dataset.
The variables/features used for the model are as follows and are crucial in spotting outliers that deviate from normal transaction behaviors:
- 5-day cumulative withdrawal amounts (sum_5days)
- 5-day withdrawal frequency (count_5days)

## Practical Insights and Usage
- Predict anomalous withdrawals that can alert the bank for their review whether it's legitimate
- For banks lacking historical data on anomalous or fraudulent or money-laundering transactions, deploying an unsupervised Isolation Forest model offers an effective solution for detecting and validating such anomalies. This approach allows institutions to accumulate labeled anomaly data, which can subsequently be utilized to train supervised models. These supervised techniques can then be rigorously evaluated through diagnostic measures and continuously monitored to ensure optimal model performance over time.

## Model Output
The output is an overlay of multiple plots that indicates the following:
Blue: Represent areas with LOW anomaly scores. These regions are considered normal or inliers.
Red Contour Line: This line acts as a THRESHOLD. It's like a boundary between normal and abnormal. Data points exactly on this line are right on the edge of becoming an anomaly.
Orange: Represent regions with HIGH anomaly scores. These are the outliers or anomalies.

Based on the output of the plot from this project, reviews can be done for the following cases within a rolling 5-day period:
- accounts with 1 withdrawals above 80k USD
- accounts with 4 withdrawals with cumulative 5-day withdrawal above 65k USD
- accounts with 5 or more withdrawals with cumulative 5-day withdrawal above 45k

## Model Assumptions
1) Data Independence: Assumes that the instances in your data are independently and identically distributed (i.i.d.). In cases where this isn’t true, such as time-series data, additional preprocessing may be required.
2) Anomaly Proportion: Requires a predefined proportion of outliers (contamination). The choice of this parameter can significantly influence the model’s performance. It should be carefully chosen based on domain knowledge and context.

## Future Work
Plans for future enhancements include:
- Incorporating additional features for more robust anomaly detection.
- Accumulate validated data (labelled data) to use as training data set for supervised techniques.
