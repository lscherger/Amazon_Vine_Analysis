# Amazon_Vine_Analysis

## Overview of the analysis: Explain the purpose of this analysis.
The purpose of this analyis was to analyze data from a particular dataset, in this case Health Products, to understand whether Vine users have a potential bias to rate their products more favorably than regular non-Vine users. To do this, I had to perform the ETL process to extract the dataset from an S3 bucket, transform the data using PySpark, connect to an AWS RDS instance, and load the transformed data into pgAdmin. This project allowed me to practice using the ETL process on big data, with heavy involvement in Amazon Web Services to store and connect the data.


## Results: 
### Deliverable 1: Perform ETL on Amazon Product Reviews

A dataframe is extracted from the Amazon Health Products database, and transformed with PySpark into 4 dataframes that will be loaded into our RDS, Postgresql.

<img width="275" alt="Screen Shot 2021-10-10 at 9 11 25 PM" src="https://user-images.githubusercontent.com/85946042/136723661-c8468a66-426b-4841-8ed8-1cd258a47a00.png">

<img width="301" alt="Screen Shot 2021-10-10 at 9 11 35 PM" src="https://user-images.githubusercontent.com/85946042/136723671-aad681d7-91da-42d9-b947-398db28b9333.png">


<img width="571" alt="Screen Shot 2021-10-10 at 9 11 43 PM" src="https://user-images.githubusercontent.com/85946042/136723688-5a5b1750-ba58-4591-8b62-dc963adf58a0.png">


<img width="663" alt="Screen Shot 2021-10-10 at 9 11 55 PM" src="https://user-images.githubusercontent.com/85946042/136723706-b8b30aac-b42a-47f5-ae18-6802f46fcde3.png">


### Deliverable 2: Determine Bias of Vine Reviews
An analysis was performed on the vine table to analyze the extent to which there was a bias in Vine reviews. The following screenshots follow the dataframes that led to the calculations addressed below. 

<img width="667" alt="Screen Shot 2021-10-10 at 9 10 23 PM" src="https://user-images.githubusercontent.com/85946042/136723588-adc100fe-3537-4d55-9676-f2205a52c30e.png">

<img width="660" alt="Screen Shot 2021-10-10 at 9 10 36 PM" src="https://user-images.githubusercontent.com/85946042/136723597-ce7a4dda-3ffd-4e8b-b829-3ea2c1fca9d0.png">


<img width="664" alt="Screen Shot 2021-10-10 at 9 10 46 PM" src="https://user-images.githubusercontent.com/85946042/136723613-80078917-d69d-4797-88b3-7fd73b2f4b59.png">


<img width="675" alt="Screen Shot 2021-10-10 at 9 10 55 PM" src="https://user-images.githubusercontent.com/85946042/136723619-a20df248-f81b-4ec1-ae2d-bf3ebe96d9f5.png">



* There were 5,331,449 total number of reviews. 5,299,189 of these reviews came from non-Vine reviewers. There were 32,026 vine reviews.
* There were 13,127 5 star Vine reviews. There were 3,344,959 5 star non-Vine reviews.
* 40.988% of Vine reviews were 5 stars. 63.122% of non-Vine reviews were 5 stars.

<img width="664" alt="Screen Shot 2021-10-10 at 9 02 31 PM" src="https://user-images.githubusercontent.com/85946042/136723087-0dc4f51d-8d41-4510-8fd9-75fb7661fcf5.png">


## Summary: 
The percentage of Vine reviews that were 5 stars was about 41%, compared to the 63% percentage of regular, non-Vine reviews that were 5 stars. While we may have expected to see a potential positive bias in reviews from Vine users, we saw the opposite in the Health Products data: there was a smaller percentage of 5 star reviews coming from Vine users, so we do not see bias in the Vine reviews. The number of Vine users is much smaller than non-Vine users, so we do expect to see more variability in the Vine users' data, but it is unclear how much chance affected the smaller 5 star review counts.



It would be effective to conduct more research into this phenomenon by comparing these percentages with those from Vine users for other types of products. I would also suggest performing another analysis to see if this data could have been skewed by a certain product that Vine users were rating much lower than others. 

