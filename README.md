# Dynamic Pricing Machine Learning Model

----

# Introduction

“Leaving money on the table” is an idiom that means not getting as much money as you could from a transaction (Lares, 2020).

Dynamic pricing strategies are employed by businesses to maximise opportunities for revenue, thereby avoiding "leaving money on the table". Based on a retail transaction dataset, this project seeks to segment customers, and subsequently capture more revenue from these different customer segments through the use of varying prices across these segments. 

The project can be organised into 3 stages : 

<u>*Stage 1 - Customer Segmentation*</u>

At the first stage, I apply an unsupervised learning algorithm to identify clusters among consumers, whereby each cluster displays a particular purchase behaviour or preference that is different from other clusters. Evaluation metric to decide on the optimal number of cluster is the silhouette score, which is the average distance between clusters. The silhouette score ranges from -1 to +1 and a higher score indicates better separation between clusters.


<u>*Stage 2 - Ideal Price Range for each Cluster*</u>

Once clusters are set, at the second stage, I perform a multivariate regression analysis to predict the ideal sales price for each cluster. Evaluation metric to select the best model is the accuracy score (ie. the R^2 score). R^2 score ranges from 0 to 1 with 1 being perfect accuracy. 


<u>*Stage 3 - Expected Revenue Generated*</u>

With the predicted ideal price for the respective clusters, I apply a binary classifier on the data such that data where unit price is less than the predicted unit price is classified as 0 where consumers will not buy. For data where unit price is more than the predicted price, data is classified as 1 where consumers will buy. I run a model to predict whether the customer will buy or not and based on the model prediction of buy (1) or not buy (0), I then compute the potential revenue generated from using the predicted prices. 

---

# Framework

Present in visual :
Data Cleaning > EDA > Clustering algorithm > regression analysis > binary classification


# Analysis and Findings

EDA 

Stage 1 : Clustering 
- KMeans
- DBSCAN
- Agglomerative Clustering 

Conclusion - eg. 4 clusters found in the dataset 

Stage 2 : Regression 
- random forent regression 
- lasso/ridge/enet regression 

Conclusion - ideal price range for each cluster 

Stage 3 : Binary classification 
- RF classification 
- log reg classification 
- decission tree
- bagged tree classifier 

once classified, compare net revenue generated and extra profit earned from the new price only for those transactions that are 


Conclusion - more profitable for certain clusters, so dynamic pricing works. 


# Conclusion and Recommendations



# Further Development


# Limitations and Challenges 
finding good clusters is a pain, there is  aneed to do very detailed eda. clusters may change iwth new data, there may be new customer profiles, and need to consistently update. computing power needed to run each cluster of cusomters. May not be practical in a fast-changing environment like e-commerce. unless, there is very close monitoring, which is labour intensive. 


# References

"Is Your Sales Team Leaving Money On The Table?"(Lares, 2020)
https://salesandmarketing.com/content/your-sales-team-leaving-money-table

"Clustering Evaluation strategies" (Manimaran, 2019)
https://towardsdatascience.com/clustering-evaluation-strategies-98a4006fcfc

----

# Data Dictionary

Below the description of Superstore data.

| Features | Data Type | Description |
| :-------: | :--: | :---- |
| Row ID | int | unique identifier for each item purchased |
| Order ID | str | unique identifier for orders placed by a consumer |
| Order Date | datetime | date order was made or transaction date |
| Ship Date | datetime | date order was shipped |
| Ship Mode  | str | categorical variable of shipment class (ie. first class, second class, standard class or same day) |
| Customer ID | str | unique identifier assigned to customer based on orders|             
| Customer Name  | str | name of consumer |       
| Segment  | str  | type of purchase (ie. consumer, corporate or home office) |
| Postal Code | float | zip code based on location of purchase |
| City | str | city where purchase was made |                 
| State | str| state where purchase was made |                     
| Country | str | country where purchase was made |                  
| Region  | str | region where purchase was made |                
| Market | str | market where purchase was made |                 
| Product ID  | str  |  unique identifier for type of product |          
| Category | str  | category for product purchased |              
| Sub-Category | str   | sub-category for product purchased |            
| Product Name  | str  | product name for product purchased |           
| Sales | float | total sales for the transaction |
| Quantity  | int | quantity ordered for transaction |
| Discount | float | percentage discount used for transaction |
| Profit  | float | sales less discount and cost of transaction |
| Shipping Cost | float | shipping cost for the transaction |
| Order Priority | str | categorical vairable indicating high, medium, low or critical priority for the transaction |          
