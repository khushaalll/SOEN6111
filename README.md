# Group - 31 Soen 6111 Project summary

# NYC Yellow Taxi Data – Recommender Systems



## Overview

New York Taxi and Limousine Commission provides dataset for its yellow taxis every month. This includes the datetime, fare amount, trip distance etc. We aim to leverage the dataset by recommending taxi drivers the optimal location and time for picking up passengers to maximize their profits. The goal is to develop a training model that can create clusters of high-density areas at each hour of the day for each day in the week such that taxi drivers can optimize their pickup trips and maximize their profits. 

 


## Dataset

The Yellow Taxi dataset of 2023 consists of a set of columns but for this research question, we are mainly focussed on the following columns, 

tpep_pickup_datetime – The taxi’s pickup date and time<br>
tpep_dropoff_datetime – The taxi’s dropoff date and time <br>
Trip_distance – The total trip distance covered by the taxi <br>
PULocationID – The Pickup location ID of the taxi. ID can be referenced by another document  which has the location for each ID <br>
Pickup_longitude – The pickup location’s longitute <br>
Pickup_latitude – The pickup location’s latitute <br>
Dropoff_longitude – The pickup location’s longitute <br>
Dropoff_latitude – The pickup location’s latitute <br>
Fare_amount – The total fare for the trip calculated by the meter <br>
Tip_amount – Tip amount provided by the passenger <br>
Total_amount – The combined amount of fare and tips amount which excludes other data like toll amount, mta_tax, extra fee and airport charge.  

This dataset is derived from the New York City TLC website,  
NYC Dataset :-  https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page 

## Research Question

Recommending New York city taxi drivers of optimal pickup locations along with the time of the day such that 
they can maximize their number of trips and increase their profits. 


## Model Classes
Based on the requirements we aim to use Supervised learning and Recommendation System. We plan to use a set of features for training the model which is tip amount, trip distance, pickup location, pickup time and spatial features (region clusters) for Random Forest regression with target variable being tip amount.   

Similarly, for content-based recommendations, hour of day, day of week and fare amount along with pickup and drop locations. And for collaborative filtering the features would be tip amount, fare amount and tip distance. 


## Algorithms

1. **Random Forest:** 
   Random Forest is an ensemble learning method that operates by constructing multiple independent decision trees during training and giving the mean prediction of the individual trees for regression tasks. For this project, Random Forest can accommodate features like tip amount, trip distance, pickup location, pickup time and spatial features like clustering of regions.

   This can be achieved by using K-means clustering to create those spatial features. Model will be trained on the given features with tip amount being the target variable. The trained model can make predictions on new data with which it can suggest optimal areas for taxi drivers.

3. **Content Based Recommendation:**
   Content-based filtering algorithm generates personalized recommendations for taxi drivers based on time, day, and spatial attributes extracted from historical trip data. In addition to features such as hour of the day, day of the week, rate code, and fare amount, we incorporate trip start and end locations represented by latitude and longitude coordinates.  

    Utilizing these spatial features, we calculate the similarity between trips using metrics like cosine similarity or Euclidean distance, considering both temporal and spatial aspects. Trips that closely match the time, day, and location characteristics of the driver's current position are identified and ranked based on their similarity scores. The top-ranked trips are then recommended to the driver as optimal routes for maximizing earnings in similar time, day, and location contexts. By leveraging both temporal and spatial features, our algorithm assists drivers in selecting trips and positioning themselves strategically to maximize profitability

3. **Collaborative Filtering:** 
 Using ALS - Alternating Least Squares (ALS) can be applied to decompose the user-item matrix of taxi trip data. Optimize the decomposition iteratively to minimize reconstruction error while factoring in attributes like tip amount, fare amount, and trip distance. Utilize the learned matrices to predict preferences for pickup locations, recommending those with higher estimated values for optimal trips. 


## Notebook link
https://colab.research.google.com/drive/1Oa4Jij4mOP0ugC3hBTAMXRdAkHtd65Mv?usp=sharing
 

   Using SVD: We can use Singular Value Decomposition (SVD) to break down the user-item matrix into meaningful components, capturing latent factors within the taxi trip data. Select a reduced rank approximation to retain essential patterns related to tip amount, fare amount, and trip distance. Recommend pickup locations based on reconstructed preferences, prioritizing areas associated with higher estimated values for a superior taxi trip experience. 
 
