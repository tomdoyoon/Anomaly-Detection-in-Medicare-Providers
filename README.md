# Anomaly-Detection-in-Medicare-Providers

# Abstract
This study leverages the Medicare Physician and Other Practitioners by Provider dataset, obtained from the Centers for Medicare and Medicaid Services (CMS), to detect anomalies in Medicare payments to physicians and other practitioners for services rendered in 2022. The dataset provides detailed information on utilization, payments, submitted charges, and beneficiary demographics, organized by National Provider Identifier (NPI). Following data preparation and preprocessing, as outlined in the accompanying Data Preparation notebook, an Isolation Forest model was trained to identify anomalous patterns in the data. The results of this analysis offer insights into potential irregularities in Medicare payments, contributing to the ongoing efforts to monitor and improve the integrity of the Medicare program.

The data on Medicare Physician and Other Practitioners by Provider is from the Centers for Medicare and Medicaid Services (CMS) and can be accessed through their website at https://data.cms.gov/provider-summary-by-type-of-service/medicare-physician-other-practitioners/medicare-physician-other-practitioners-by-provider/data>. The dataset provides information on Medicare payments to physicians and other practitioners for services rendered in 2022. The data was downloaded on March 10, 2025.
- The dataset is prefiltered to remove Rndrng_Prvdr_Ent_Cd = 0 (only individual practitioners are included).

"The Medicare Physician & Other Practitioners by Provider dataset provides information on use, payments, submitted charges and beneficiary demographic and health characteristics organized by National Provider Identifier (NPI). This dataset is based on information gathered from CMS administrative claims data for Original Medicare Part B beneficiaries available from the CMS Chronic Conditions Data Warehouse" (data.cms.gov, 2024).

Please see the data dictionary: https://data.cms.gov/resources/medicare-physician-other-practitioners-by-provider-data-dictionary

# Conclusions
The Isolation Forest model was trained on a dataset of Medicare Providers to detect anomalies. The model achieved a Silhouette Coefficient of -0.60, a Calinski-Harabasz Index of 6.05, and a Davies-Bouldin Index of 7.17 on the validation set. The anomaly detection rates for the training and validation sets were .0044 and .0042, respectively. The results suggest that the model is able to identify anomalies in the data, but the quality of the clusters and the anomaly detection rates could be improved. Further tuning of the model's hyperparameters and exploration of other anomaly detection algorithms may be necessary to achieve better results.

![image](https://github.com/user-attachments/assets/4313dfba-8c61-48dc-b877-99e61bafbb98)

The scatter plot of the PCA-transformed data reveals a mixed picture, with some outliers (red dots) showing a degree of separation from the normal data points (blue dots), while others appear more intermingled.
This observation is consistent with the metrics calculated earlier, which indicated a moderate level of cluster separation and cohesion. Specifically, the Silhouette Coefficient, Calinski-Harabasz Index, and Davies-Bouldin Index values suggest that while the clusters are not extremely well-separated, they are not entirely random either.
The partial intermingling of outliers with normal data points may indicate that some outliers share similarities with the normal data points, making them harder to distinguish. This could be due to various factors, such as noise in the data, non-linear relationships between variables, or the presence of multiple underlying clusters.
Overall, while the results do not demonstrate extremely clear separation between outliers and normal data points, they do suggest that the Isolation Forest model has identified some patterns and relationships in the data that are worth further exploration.

# Table of Contents
Please refer to the following table of contents to navigate your exploration:

Data Preparation: Reproducible steps for processing raw data.

Machine Learning: Application of a non-tuned Isolation Forest model to predict outliers.
