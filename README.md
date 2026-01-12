# Financial-anomalies-detection
Project Summary & Key Insights

Data Analysis Key Findings

GMM Model (Gaussian Mixture Model):

Configuration: 108 distinct models were evaluated. Optimal parameters: n_components=2, covariance_type='full', reg_covar=1e-06, threshold_percentile=0.5.
Detection: Identified 217 anomalies (approx. 0.5% of test data).
Characteristics: Top anomalies featured extremely low log-likelihood scores (lowest ~ -271.1) and included transactions with unusually high amounts (e.g., ~712k).
Structure: Anomalies appeared as local deviations within clusters rather than forming distinct sparse clusters.
Isolation Forest Model:

Configuration: Optimal parameters: n_estimators=200, contamination=0.01, max_features=1.0.
Detection: Identified 450 anomalies (approx. 1% of test data).
Characteristics: Top anomalies had very low scores (high isolation) and often involved specific AccountIDs (8, 9, 10), occurred in Los Angeles, and happened late at night during the latter months of the year.
Insights & Next Steps

Consolidated View: The models identified different sets of anomalies, suggesting they capture different types of irregularities (density-based vs. isolation-based). Combining these insights offers a more robust detection system.
Key Indicators: High transaction amounts, specific locations (e.g., Los Angeles), and time patterns (late night) are strong indicators of potential fraud in this dataset.
Feature Importance: The Isolation Forest model highlighted 'Merchant', 'AccountID', 'Day', and 'Location' as the most critical features for detecting anomalies.
Recommendation: Implement a hybrid monitoring system that uses both models to flag transactions. Investigate the specific user behaviors associated with the flagged AccountIDs and Merchants to refine detection rules.
