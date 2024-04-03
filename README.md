# Group - 31 Soen 6111 Project summary

# NYC Yellow Taxi Data – Recommender Systems



## Overview

New York Taxi and Limousine Commission provides dataset for its yellow taxis every month. This includes the datetime, fare amount, trip distance etc. We aim to leverage the dataset by recommending taxi drivers the optimal location and time for picking up passengers to maximize their profits. The goal is to develop a training model that can create clusters of high-density areas at each day in the week such that taxi drivers can optimize their pickup trips based on number of customers and maximize their profits. 

 


## Dataset

The Yellow Taxi dataset of 2023 consists of a set of columns but for this research question, we are mainly focussed on the following columns, 

tpep_pickup_datetime – The taxi’s pickup date and time<br>
Pickup_longitude – The pickup location’s longitute <br>
Pickup_latitude – The pickup location’s latitute <br>
Dropoff_longitude – The pickup location’s longitute <br>
Dropoff_latitude – The pickup location’s latitute <br>
Fare_amount – The total fare for the trip calculated by the meter <br>
Week_day– The day of the week <br>

This dataset is derived from the New York City TLC website,  
NYC Dataset :-  [https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page ](https://colab.research.google.com/corgiredirector?site=https%3A%2F%2Fs3.amazonaws.com%2Fnyc-tlc%2Ftrip%2Bdata%2Fyellow_tripdata_2013-01.csv)

## Research Question

Recommending New York city taxi drivers of optimal pickup locations of a particular day of week such that 
they can maximize their number of trips and increase their profits. 


## Model Classes
Based on the requirements we aim to use Supervised learning. We plan to use a set of features for training the model which is  pickup longitude, pickup_latitude,day of week, dropoff_latitude, dropoff_longitude, pickup time and spatial features (region clusters) for both linear regression and random forest regression. 


## Algorithms

1. **Random Forest:**
    Random Forest is an ensemble learning method that builds multiple decision trees during training and outputs the average prediction of these trees. In this scenario, it's used to predict optimal taxi pickup locations for each weekday in a given month. It involves clustering with K-means, and training based on cluster sizes and centers and then using these models to predict the optimal best location to maximize pickups. 

2. **XGB Classifier:**
    Similar to Random Forest, XGB Classifier is also an ensemble learning method which combines predictions from multiple weak learners (often decision trees) to create a stronger final model. This approach helps reduce the risk of overfitting and improves generalization performance. In our project, it's used to train our model and to predict the 'optimal' or 'not optimal' class labels. As stated above in Random Forest, XGBoost also uses 'pickup_latitude' and 'pickup_longitude' as features which are resampled and balanced to reduce class implanace.
 
## Notebook link
[https://colab.research.google.com/drive/1Oa4Jij4mOP0ugC3hBTAMXRdAkHtd65Mv?usp=sharing](https://colab.research.google.com/drive/1yDXrAuZqOuk6W3UVuvbRWt6YO8V_GqQx?usp=sharing#scrollTo=9cN4gnPYheqS)
 
