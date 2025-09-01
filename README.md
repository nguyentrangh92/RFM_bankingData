# Segmentation of Gate City Bank’s customer using RFM analysis (2016-2022)
## Purpose of the research
The purpose was to segment customers based on their spending behaviors and income which could give the financial institution more information about their clients to plan data-driven strategies for those who are using the debit card product. The key insights drawn from the analysis will help improve the bank promotion for maintaining their loyal customers, reactivating dormant customers based on their card usage.
## Data characteristics
There are 3 big tables given by the institution, the total of them is larger than 50GB and splited into multiple files to upload into Dropbox. Below is the diagram of the database structure. 

![image](https://github.com/user-attachments/assets/e91a21a5-f680-4c81-9b20-4852aa24b5aa)

Based on the defined scope of the research, we narrow it down to 2 main types of transactions which are external deposit and spending variables from 12/31/2022
## Coding language and approach method
Using Pyspark and Pandas to merge and extract data based on business need.
Utilizing Power BI to calculate and visualize data to get to know data's characteristics and have a general view of data
Using libraby in Python and R in modeling data, techniques used: RFM score for supervised data, Kmean for unsupervised one.

Create the model by using 2 different method of moneterizing: using NET (balance approach) and ABSOLUTE (fee approach) value of spending and income.
## Visualization

![image](https://github.com/user-attachments/assets/259c99aa-b631-4bcc-878a-6ee6272aaa58)

![image](https://github.com/user-attachments/assets/81abd6da-5d22-4109-aec9-3e70d26c4451)

Each year, the columns of March and December are higher than the others because it is tax season and the Christmas season. That trend is being followed by both spending and income.
We tried to look at what kind of merchants customers most spend at. We retail trade
receives the most amount of spend followed by services. Within retail trade Grocery Stores
are at the top followed by Gas Stations and then Restaurants or Eating places. We can use
this data to determine what sort of merchants should Gate City partner with in order to give
their customers promotions and/or discounts.

![image](https://github.com/user-attachments/assets/18c6d7ec-be9f-4b7a-b38d-7a0bac2bc6d0)

## Model
### RFM framework
![image](https://github.com/user-attachments/assets/22070efb-724f-4bf6-bb2a-41fd9a4435ee)

Recency value is calculated by the numbers of day from the last transaction until the current
date
Frequency value is the number of transactions during the time period
Monetary value is calculated by 2 different ways:
- Sum of absolute value of spending and income: This approach comes from a fee
perspective with an assumption that the bank will get benefit from both type of
transaction
- Sum of net value of spending and income: this approach comes from the interest
perspective. If customers spend all the money they receive. The monetary value of
that customer will be low.
#### RFM score by using absolute value

![image](https://github.com/user-attachments/assets/b1e47a01-d427-4006-b5f3-f7ffea331de1)

#### RFM score by using net value

![image](https://github.com/user-attachments/assets/9ef02b61-2575-4dbf-b66e-254316608889)

#### RFM K-mean - Unsupersived model for absolute value of spending and income:
We use 3 different method to calculate the optimal value of K value and test the result with
K = {3, 4, 5}:
- Elbow method
- Flattening three-dimensional graphs
- Snake plot
We come up with K = 5

![image](https://github.com/user-attachments/assets/ee761c65-3772-4374-97fe-d30c7786f025)


