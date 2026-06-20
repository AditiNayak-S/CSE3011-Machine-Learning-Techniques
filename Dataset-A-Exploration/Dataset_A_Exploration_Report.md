Dataset Exploration Report
Dataset A – Microsoft Cloud Monitoring Dataset
Course Information
Course Code: CSE3011
Course Title: Machine Learning Techniques
Purpose of Exploration
Before implementing machine learning algorithms for laboratory exercises, it is important to thoroughly understand the dataset being used. This exploration aims to analyze the structure, quality, characteristics, and suitability of Dataset A for the Machine Learning Techniques laboratory course.
The findings from this report will be used to determine whether the dataset can support various machine learning tasks such as classification, regression, clustering, dimensionality reduction, ensemble learning, and anomaly detection.
________________________________________
1. Dataset Overview
Dataset Name
Microsoft Cloud Monitoring Dataset
Dataset Description
The Cloud Monitoring Dataset is a collection of real-world cloud telemetry data obtained from Microsoft production services and client systems. The dataset was created for the development and evaluation of anomaly detection algorithms used in cloud monitoring environments.
The dataset contains manually labeled anomalies identified by domain experts. These anomalies represent unusual or abnormal behavior observed in cloud infrastructure and service monitoring metrics.
________________________________________
2. Dataset Domains
The dataset contains monitoring signals collected from multiple operational domains, including:
1.	Store purchase counts by client type
2.	Database query rates by individual machines
3.	Database query rates by application context
4.	Incoming service API query rates
5.	Outgoing service API latency
6.	Windows application crash rates
7.	Web application query rates
8.	Cloud infrastructure monitoring metrics
These domains represent different aspects of cloud service health and operational performance.
________________________________________
3. Dataset Structure
The dataset consists of multiple CSV files organized into different categories.
Total Number of CSV Files
60 CSV files
Example Categories
•	Application Crash Rate 1
•	Application Crash Rate 2
•	Consumer Purchase Rate
•	MongoDB Application Request Rate
•	MongoDB Machine Request Rate
•	Data Ingress Rate
•	Service Unavailable
•	API Request Rate
•	Outbound API Latency
________________________________________
4. File Format
Each CSV file follows the same structure and contains three columns.
Column Name	Description
TimeStamp	Date and time of observation
Value	Monitoring metric value
Label	Anomaly indicator
Label Description
Label Value	Meaning
0	Normal Observation
1	Anomalous Observation
________________________________________
5. Sample Dataset Inspection
A sample file (app2-01.csv) was analyzed.
Shape
Rows: 1114
Columns: 3
Column Names
•	TimeStamp
•	Value
•	Label
Missing Values
Column	Missing Values
TimeStamp	0
Value	0
Label	0
No missing values were found in the inspected sample file.
________________________________________
6. Statistical Analysis
Summary statistics for the Value column:
Statistic	Value
Count	1114
Mean	0.059358
Standard Deviation	0.091636
Minimum	0.000000
25th Percentile	0.018910
Median	0.031915
75th Percentile	0.061987
Maximum	1.174757
Observations
•	Most observations lie near zero.
•	Large spikes are occasionally observed.
•	Significant variability exists in the monitored metric.
•	Extreme values may correspond to anomalous system behavior.
________________________________________
7. Class Distribution Analysis
For the file app1-01.csv:
Class	Count
Normal (0)	318
Anomaly (1)	40
Percentage Distribution
Class	Percentage
Normal	88.83%
Anomaly	11.17%
Observation
The dataset exhibits moderate class imbalance, which is common in anomaly detection problems. However, the anomaly percentage is sufficient for supervised machine learning experiments.
________________________________________
8. Time Series Analysis
Visualization of the time series revealed the following characteristics:
•	Stable baseline values during normal operation.
•	Sudden spikes and bursts in monitored metrics.
•	Localized abnormal patterns.
•	Temporal behavior consistent with real-world monitoring systems.
The dataset clearly represents a time-series anomaly detection problem rather than a traditional tabular classification problem.
________________________________________
9. Anomaly Label Verification
Anomaly points were plotted alongside the original time series.
Findings
•	Most anomaly labels correspond to unusual spikes.
•	Anomalies are concentrated around abnormal system behavior.
•	Labels appear consistent and meaningful.
•	Expert annotations accurately identify suspicious activity.
This confirms the reliability of the labeling process described in the dataset documentation.
________________________________________
10. Anomaly Distribution Across Files
Several files contain substantial numbers of anomalies.
Examples
File	Number of Anomalies
ingress-01.csv	366
ingress-05.csv	353
ingress-04.csv	303
machine-01.csv	202
app2-05.csv	203
api-01.csv	120
Several files intentionally contain no anomalies.
Examples
File	Number of Anomalies
mongo-01.csv	0
mongo-04.csv	0
purchase-01.csv	0
outbound-16.csv	0
ingress-03.csv	0
unavail-01.csv	0
This behavior matches the dataset documentation, which states that some files are intentionally anomaly-free for evaluating false-positive behavior.
________________________________________
11. Suitability for Machine Learning Techniques Laboratory
Directly Suitable
•	Classification
•	Decision Trees
•	Logistic Regression
•	K-Nearest Neighbors
•	Support Vector Machines
•	Random Forest
•	AdaBoost
•	Naive Bayes
Suitable After Feature Engineering
•	Clustering
•	Principal Component Analysis (PCA)
•	Hierarchical Clustering
•	K-Means Clustering
Requires Further Investigation
•	Linear Regression
•	Multiple Linear Regression
Additional engineered features may be required to support regression-based experiments.
________________________________________
12. Planned Feature Engineering Strategy
Since each file contains only one primary metric value, additional features can be generated from the time series.
Potential features include:
•	Previous Value (Lag-1)
•	Lag-2 Value
•	Lag-3 Value
•	Rolling Mean
•	Rolling Standard Deviation
•	Rate of Change
•	Moving Average
•	Hour of Day
•	Day of Week
•	Trend Indicators
These engineered features will transform the dataset into a richer tabular format suitable for a wider range of machine learning algorithms.
________________________________________
13. Final Conclusion
The Microsoft Cloud Monitoring Dataset is a high-quality real-world anomaly detection dataset derived from Microsoft cloud telemetry.
Key strengths include:
•	Expert-labeled anomalies
•	Multiple monitoring domains
•	Real production cloud data
•	No missing values in examined files
•	Meaningful anomaly patterns
•	Sufficient anomaly representation
•	Support for both supervised and unsupervised learning
Based on the exploration conducted, Dataset A is approved for use in the CSE3011 Machine Learning Techniques laboratory exercises.
Future work will involve combining multiple time-series files and performing feature engineering to create a comprehensive machine learning dataset capable of supporting Labs 2–9.
