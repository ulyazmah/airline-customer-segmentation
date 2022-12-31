# Airline Customer Segmentation Based on LRFMC Model


## Introduction
This is an unsupervised machine learning practice on customer segmentation.

## Objective
To identify the customer segmentation in aviation company, analyze characteristics of different clusters and suggest business strategy to customer categories of different values.

## Data Understanding
This dataset has 62988 rows dan 23 columns.
Column names themselves are self explanatory, however here I provide several columns explanation related to aviation industry:
1. **MEMBER_NO**: ID Member
2. **FFP_DATE**: Frequent Flyer Program Join Date
3. **FFP_TIER**: Frequent Flyer Program Tier
4. **LOAD_TIME**: Observed Time
5. **FLIGHT_COUNT**: Customer Flight Count
6. **BP_SUM**: Itinerary
7. **SUM_YR_1**: Fare Revenue
8. **SUM_YR_2**: Votes Prices
9. **SEG_KM_SUM**: Total flight kilometers in observation window
10. **LAST_FLIGHT_DATE**: Last Flight Date
11. **LAST_TO_END**: The last flight time to the end of the observation window
12. **AVG_INTERVAL**: Average flight interval
13. **MAX_INTERVAL**: Maximum flight interval
14. EXCHANGE_COUNT**: Exchange count
15. **avg_discount**: Average discount rate
16. **Points_Sum**: The number of points earned by the customer
17. **Points_NotFlight**: Point not used by customers

## Method
I used LRFMC Model that is commonly used in aviation dataset. LRMFC stands for Length, Recency, Frequency, Monetary and Discount Factor. The details of each parameter is elaborated below:
1. Length: the length of days between subscriber's first register day to observation time. A larger number means they have been a member for a longer time
2. Recency: the length of a passenger's last consumption to observation window. A smaller number means they flew more recently
3. Frequency: the passenger's consumption frequency within a certain period of time. A bigger number means they flew more frequently
4. Monetary the average amount spent over a certain period of time. A bigger number means they spent more money
5. Discount Factor: the average space discount factor for passengers traveling within a certain period of time A bigger number means they use discounts more
After looking at the data, we use the columns below that related to the LRFMC features:
- Length: LOAD_TIME - FFP_DATE
- Recency: LAST_TO_END
- Frequency: FLIGHT_COUNT
- Monetary: SEG_KM_FM
- Customer Cost: avg_discount 

K-means clustering method is used to classify the customer segmentation. 

## Conclusion
From elbow plot, there is a possibility that the optimum clusters are 4-6. After consider the business perspective,
we decide that the suitable number of clusters are 5. The clusters are:
1. Cluster 1 - The Hibernating Customers 
2. Cluster 2 - The Promising Customers 
3. Cluster 3 - The Loyal Customers 
4. Cluster 4 - The Old-Seasonal Customers 
5. Cluster 5 - The Cheap Customer 

To see details on what are the characteristics of each cluster and recommendation for the company, make sure to check the notebook and power point files above.