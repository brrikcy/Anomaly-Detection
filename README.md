# Anomaly-Detection
Anomaly Detection in ATM withdrawals dataset using machine learning (Multiple Gaussian Distribution)

Aim
---
To detect anomalies in the total amount withdrawn in a day from different ATMs around the city using 
Multivariate Gaussian Disribution.


Procedure
---------
1. Import necessary libraries
2. Import the dataset
3. Preprocess the data
4. Train the model with data using GaussianMixture
5. Identify anomalies
6. Display anomalies


After importing necessary libraries and the dataset, data is preprocessed to ensure good machine interpretability of
data. The preprocessing steps include the following..
1. Parsing dates so that date and time is converted to pandas datetime object so that it can be easily manipulated.
2. Encoding categorical features by using pd.get_dummies which will create a new binary column for each categorical values.
3. Handling duplicate and missing values.
4. Scaling numerical features using standard scaler.

After preprocessing, data is used to train a model using multivariate gaussian algorithm which is done by using the help of GaussianMixture submodule present in sklearn.mixture. Gaussin Mixture Model assumes all the data points are generated from a mixture of several Gaussian distributions with unknown parameters hence it can analyze how data is spread out and can find instances that are very different from what it expects as normal which are the anomalies.

After training the models, anomaly data is identified by setting the threshold which is set with the help of score_samples method in the model which will give log-probabilities of each data point in the data under the Gaussian Mixture Model (GMM) that was previously fitted. Threshold is set to make the data in fifth percentile of probability an anomaly. 

After clearly identifying anomaly according to the threshold, anomaly data is displayed and a scatter plot visualization of whole data differentiating normal and anomaly data is also displayed.


   
