# BI_Analytics_with_Kmeans
A business analysis of two brands and understanding their health by looking at relavant KPIs and using Kmeans Clustering

## Brands Data Science Write Up
### Schuyler Blasy. January 3rd, 2022
#### Assignment Overview

A generic company has two brands represented in a spreadsheet to be analyzed containing store level data across two distinct brands. The analysis must include:
1) At a high level describe what you understand about the business based on the data.
2) Are there any issues/problems/ anomalies in the data? If yes, list them out.
3) How are the two brands present in the data set different from one another?
4) Create 3-4 calculated metrics/ KPIs from the data set which best help understand performance of a store
5) How do we understand the health of a store? Using the data can you flag out the most "Healthy" stores Vs the least "Healthy" stores. What are the key differences between them? How can we bridge the gap to improve the performance of unhealthy stores?

There is quite a bit of overlap in answering these questions, such as describing the data and what it says about the business, any anomalies found, and the differences between brands, but I have attempted to answer each question as succinctly as possible. 

All work was done in Python and in Jupyter Notebook. Included with this document are the notebook and an excel file with the top stores

#### High Level Description and Overview

The spreadsheet includes data on 649 stores across two brands. Describing the data shows a massive variance of store performance. This initial exploratory step was done on the entire data set, and needs to keep in mind that there are also two brands aggregated into that data description. Nonetheless, the initial look at the data shows a potential large range of stores either doing extremely well or struggling. 

#### Issues and Anomalies with the Data

A data quality check showed no missing values. However, from describing the data, multiple columns had zero values. What wasn’t clear is if this was a true zero value or a null value erroneously labeled as zero. 

The problem with the zero values is in calculating KPIs which usually include ratios. Having a zero in the denominator creates for an undefined -and nonsensical- output value, and this indeed happened to be the case which forced me to drop that observation.
Comparing the Two Brands

A better alternative to exploring the dataset as two distributions, subsetting on the brands, and showing comparisons between the two.  As examples of the differences between brand A and D, I visually compared them across Sales, Margin, Labor Hours, Wages, and Store Traffic. 

Brand A is smaller with 156 stores and Brand D has 491 stores, and this can be seen with Brand D’s distribution having a much larger mass. 
What’s more interesting is the rightward skewness of Brand D with respect to A, and this can be seen especially in the labor hours, wages, and foot traffic. The average higher wages of Brand D might indicate efficiency problems that could have a determining factor of its success or/and health of its stores. 

#### Creating KPIs to Better Understand Brand Health

Feature engineering is a fundamental task in data science, such as constructing KPIs to bring better understanding of a business question. Using the data I constructed three more KPIs.
* Sales Per Square Foot (Clothing Sales/Selling Square Foot Space)
* Sales Per Labor Hours (Clothing Sales/Labor Hours)
* Sales Per Total Wages (Clothing Sales/Total Wages)

#### Kmeans Clustering

I then used kmeans clustering to cluster each respective brand based on those KPIs to deterine store health respective to each brand. This methodology was able to create distinct cohorts per brand of stores which were clearly healthy and those which were not.
