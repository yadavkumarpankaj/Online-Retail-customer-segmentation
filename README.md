# Online Retail Customer Segmentation

### Problem Statement:

In this project, our task is to identify major customer segments on a transactional data set which contains all the transactions occurring between 01/12/2010 and 09/12/2011 for an UK based and registered non-store online retail. The company mainly sells unique all occasion gifts. Many customers of the company are wholesalers.

Customer segmentation is a way to split customers into groups based on certain characteristics that those customers share. Customer segmentation will allow marketers
to better tailor their marketing efforts to various audience subsets. The dataset contains 541909 records of transactions with 8 features.

---
### Data Description:

The dataset contains 541909 records and 8 features which consists of:

● InvoiceNo: Invoice number. Nominal, a 6 digit integral number uniquely assigned to each transaction. If this code starts with letter ‘c’, it indicates a cancellation.

● StockCode: Product code. Nominal, a 5 digit integral number uniquely assigned to each distinct product.

● Description: Product name. Nominal

● Quantity: The quantities of each product per transaction. Numeric.

● InvoiceDate: Invoice date and time. Numeric, the day and time when each transaction was generated.

● UnitPrice: Unit Price. Numeric, product price per unit in sterling.

● CustomerID: Customer number. Nominal, a 5 digit integral number uniquely assigned to each customer.

● Country: Country name. Nominal, the name of the country where each customer resides.

---
### Data Exploration:

Let us now summarize the insights generated from EDA:

● White hanging heart T-light holder was the most sold product and Green with metal bag charm was one of the least sold products.

● UK had the most number of customers which is pretty obvious because it is an UK based online retail company.

● Saudi Arabia followed by Bahrain had the least number of customers.

● There are 4338 unique customers and only 10 customers had an order share of approx 9% which implies that these customers could be wholesalers.

● The distribution of all the variables were heavily right skewed and log transformation was applied to bring them close to a normal distribution.

● Most of the customers had made a purchase on Thursday followed by Wednesday and the least number of purchases was made on Friday.

● The most purchases were made during the festive months of October to December and the least number of purchases was made during the initial months of January
and February.

● Most of the people had made their purchases during the afternoon period and very less number of purchases during evening.

---
### RFM Segmentation & Analysis:

Recency, frequency and monetary value is a marketing analysis tool used to identify a company’s or an organization’s best customers by measuring and analyzing spending
habits.

The RFM model is based on three quantitative factors:

    ● Recency: How recently a customer has made a purchase

    ● Frequency: How often a customer makes a purchase

    ● Monetary: How much money a customer spends on purchases

RFM analysis numerically ranks a customer in each of these three categories, generally on a scale of 1 to 5. The best customers would receive a top score in every category. These three RFM factors can be used to reasonably predict how likely or unlikely it is that a customer will do business again with a firm or company. RFM analysis allows a comparison between potential customers or clients. It gives organizations a sense of how much revenue comes from repeat customers vs new customers, and which levers they can pull to try to make customers happier so they become repeat purchasers. Despite the useful information that is acquired through RFM analysis, firms must take into consideration that even the best customers will not want to be over solicited, and the lower ranking customers may be cultivated with additional marketing efforts.

---
### Clustering Models:

Clustering can be considered the most important unsupervised learning problem, so as every other problem of this kind, it deals with finding a structure in a collection of unlabeled data. A loose definition of clustering could be “the process of organizing objects into groups whose members are similar in some way”. A cluster is therefore a collection of objects which are similar between them and are dissimilar to the objects belonging to other clusters.

In Addition to the K-means clustering model implemented on RFM data, we have implemented K-means separately on Recency, Monetary and Frequency, Monetary data
along with hierarchical clustering on RFM data to compare the performances of each clustering method.
We have again used the silhouette score method and the elbow method for determining the best ‘K’ value for K-means clustering and a dendrogram for hierarchical clustering. A dendrogram is a diagram that shows the hierarchical relationship between objects. It is most commonly created as an output from hierarchical clustering. The main use of a dendrogram is to work out the best way to allocate objects to clusters.

Model Name | Data | Optimal Number of Clusters
---------- | ---- | --------------------------
K-Means | RM | 4
K-Means | FM | 3
K-Means | RFM | 3
Hierarchical | RFM | 2

We can observe from the different clustering methods that the optimal number of clusters for each method is around 2 or 3. Thus, we can consider 3 as the optimal number of clusters in our final model of K-means on RFM data and identify the different customer segments.

***
