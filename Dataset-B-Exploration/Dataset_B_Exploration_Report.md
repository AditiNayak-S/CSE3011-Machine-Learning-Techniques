# Dataset Exploration Report

## Dataset B – OpenStack Failure Dataset

### Course Information

**Course Code:** CSE3011
**Course Title:** Machine Learning Techniques

### Purpose of Exploration

The purpose of this exploration is to understand the structure, characteristics, quality, and machine learning suitability of Dataset B. The findings from this analysis will help determine how the dataset can be utilized for classification, clustering, dimensionality reduction, ensemble learning, and failure diagnosis tasks in subsequent laboratory exercises.

This dataset serves as a real-world cloud infrastructure failure analysis dataset and complements Dataset A by focusing on failure classification rather than anomaly detection.

---

# 1. Dataset Overview

### Dataset Name

OpenStack Failure Dataset

### Dataset Description

The OpenStack Failure Dataset contains information collected from fault-injection experiments performed on the OpenStack cloud computing platform.

The experiments were conducted under multiple workload conditions, and different faults were intentionally introduced into the cloud environment. The resulting system behavior was recorded and labeled according to the type of failure observed.

The dataset was developed to support research on software failure analysis and machine learning-based failure diagnosis in cloud computing systems.

---

# 2. Dataset Source

The dataset originates from the research work:

**Enhancing the Analysis of Software Failures in Cloud Computing Systems with Deep Learning**

Published in:

* Journal of Systems and Software
* Elsevier

The dataset contains event traces generated during controlled fault-injection experiments conducted on OpenStack cloud infrastructure.

---

# 3. Dataset Organization

The dataset is divided into three workload categories:

| Workload | Description         |
| -------- | ------------------- |
| DEPL     | Deployment Workload |
| NET      | Network Workload    |
| STO      | Storage Workload    |

Each workload folder contains:

| File               | Purpose                      |
| ------------------ | ---------------------------- |
| SEQ.tsv            | Event feature matrix         |
| LCS_with_VMM.tsv   | Anomaly-based feature matrix |
| Failure_Labels.txt | Target failure labels        |

---

# 4. Dataset Structure

Unlike Dataset A, this dataset is already organized in a tabular machine learning format.

### SEQ.tsv

Contains:

* Rows = Fault-injection experiments
* Columns = Event types
* Values = Frequency/count of event occurrences

Each row represents the behavior of the OpenStack system during a particular experiment.

---

# 5. Workload Dimensions

### DEPL Workload

| Property | Value |
| -------- | ----- |
| Rows     | 1076  |
| Features | 104   |

---

### NET Workload

| Property | Value |
| -------- | ----- |
| Rows     | 561   |
| Features | 59    |

---

### STO Workload

| Property | Value |
| -------- | ----- |
| Rows     | 901   |
| Features | 75    |

---

# 6. Feature Characteristics

The features correspond to OpenStack operational events and API interactions.

Examples include:

* cinderclient_DELETE_202
* cinderclient_GET_200
* cinderclient_POST_202
* q-plugin_get_ports
* scheduler_select_destinations
* scheduler_update_instance_info

These features capture cloud infrastructure behavior during fault-injection experiments.

---

# 7. Failure Classes

The dataset contains multiple failure categories depending on the workload.

---

## DEPL Failure Classes

| Label | Failure Type     |
| ----- | ---------------- |
| 1     | Instance Failure |
| 2     | Volume Failure   |
| 3     | SSH Failure      |
| 4     | Cleanup Failure  |
| 5     | Network Failure  |
| 6     | No Failure       |

---

## NET Failure Classes

| Label | Failure Type     |
| ----- | ---------------- |
| 1     | Instance Failure |
| 2     | Network Failure  |
| 3     | SSH Failure      |
| 4     | No Failure       |

---

## STO Failure Classes

| Label | Failure Type     |
| ----- | ---------------- |
| 1     | Volume Failure   |
| 2     | Instance Failure |
| 3     | Cleanup Failure  |
| 4     | No Failure       |

---

# 8. Class Distribution Analysis

## DEPL Workload

| Failure Type     | Count |
| ---------------- | ----: |
| Instance Failure |   224 |
| Volume Failure   |   151 |
| SSH Failure      |    41 |
| Cleanup Failure  |    69 |
| Network Failure  |    52 |
| No Failure       |   539 |

Total Experiments: 1076

---

## NET Workload

| Failure Type     | Count |
| ---------------- | ----: |
| Instance Failure |    56 |
| Network Failure  |   195 |
| SSH Failure      |    11 |
| No Failure       |   299 |

Total Experiments: 561

---

## STO Workload

| Failure Type     | Count |
| ---------------- | ----: |
| Volume Failure   |    38 |
| Instance Failure |   320 |
| Cleanup Failure  |   157 |
| No Failure       |   386 |

Total Experiments: 901

---

# 9. Missing Value Analysis

The DEPL workload was inspected for missing values.

Result:

| Property       | Value |
| -------------- | ----- |
| Missing Values | 0     |

No missing values were detected in the dataset.

This indicates high data quality and eliminates the need for missing-value imputation during preprocessing.

---

# 10. Machine Learning Suitability Analysis

The dataset is highly suitable for machine learning because:

* Data is already tabular.
* Feature vectors are pre-generated.
* Failure labels are available.
* Multiple classes exist.
* No missing values were observed.
* Real cloud infrastructure behavior is represented.

---

# 11. Suitability for CSE3011 Laboratory Exercises

### Directly Suitable

| Lab Topic                 | Suitability |
| ------------------------- | ----------- |
| Logistic Regression       | Excellent   |
| Decision Trees            | Excellent   |
| K-Nearest Neighbors       | Excellent   |
| Support Vector Machines   | Excellent   |
| Random Forest             | Excellent   |
| AdaBoost                  | Excellent   |
| Naive Bayes               | Excellent   |
| Classification Evaluation | Excellent   |

---

### Suitable with Additional Analysis

| Lab Topic                | Suitability     |
| ------------------------ | --------------- |
| K-Means Clustering       | Suitable        |
| Hierarchical Clustering  | Suitable        |
| PCA                      | Highly Suitable |
| Dimensionality Reduction | Highly Suitable |

The large number of features makes the dataset particularly useful for PCA and feature-selection experiments.

---

# 12. Comparison with Dataset A

| Property                 | Dataset A              | Dataset B              |
| ------------------------ | ---------------------- | ---------------------- |
| Domain                   | Cloud Monitoring       | Cloud Failure Analysis |
| Type                     | Time-Series            | Tabular                |
| Labels                   | Anomaly Labels         | Failure Classes        |
| Features                 | Single Metric per File | Multi-Feature          |
| Preprocessing Effort     | High                   | Low                    |
| Classification Readiness | Moderate               | High                   |

Dataset B complements Dataset A by providing a structured failure classification dataset while Dataset A focuses on anomaly detection and monitoring analytics.

---

# 13. Final Conclusion

The OpenStack Failure Dataset is a high-quality cloud infrastructure failure classification dataset generated from controlled fault-injection experiments on OpenStack environments.

Key strengths include:

* Real-world cloud infrastructure events
* Multiple failure categories
* High-dimensional feature space
* No missing values
* Multi-class classification capability
* Strong suitability for classical machine learning algorithms

Based on the exploration conducted, Dataset B is approved as the primary dataset for classification-based laboratory exercises in CSE3011 – Machine Learning Techniques.

The dataset is particularly well suited for Logistic Regression, Decision Trees, KNN, SVM, Random Forest, AdaBoost, Naive Bayes, PCA, and clustering-based experiments.
