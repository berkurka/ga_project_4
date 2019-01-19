# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Estimating Neighborhood Affluence With Yelp Data

## Project Authors
- Bernard Kurka | <u>[LinkedIn](https://www.linkedin.com/in/bernardkurka)</u> | <u>[Email](bkexcel2014@gmail.com)</u>
- Thomas Ludlow | <u>[LinkedIn](https://www.linkedin.com/in/thomas-w-ludlow-jr-4568a1b)</u> | <u>[Email](tludlow@gmail.com)</u>
- Brittany Allen | <u>[LinkedIn](https://www.linkedin.com/in/brittlallen)</u> | <u>[Email](thebrittallen@gmail.com)</u>

## Notebooks
- <u>[01 Data Collection](link)</u>
- <u>[02 Data Cleaning & Exploration](link)</u>
- <u>[03 Data Modeling](link)</u>

## Table of contents
- <u>[Executive Summary](#header)</u>
- <u>[The Data](#header)</u>
- <u>[Analysis](#header)</u>
- <u>[Conclusion](#header)</u>

### Executive Summary
[New Light Technologies (NLT)](https://www.linkedin.com/company/new-light-technologies) requested an economic analysis utilizing Yelp cost estimates ($, $$, $$$, $$$$) to estimate neighborhood affluence. In thinking about conventional sources of economic data like the U.S. Census Bureau or the IRS two major flaws we can identify are the reporting-lags in acquiring this data and the ability to slice and dice the data in varied ways. How can we develop a tool leveraging more agile data sources (like Yelp) that will help us measure local economic activity?

Our initial approach was to build a supervised learning, linear regression model, but we found that defining a proper affluence metric by using IRS zipcode-level AGI (adjusted gross income) was difficult to do. While traditional methods typically estimate wealth of a locality based on demographic characteristics like income, the novelty of our latter approach — conducting an unsupervised learning analysis with clustering algorithms — is in its use of big data related to commercial activity and cost of product and services as an indicator of affluency.


Counting the number of business in each price range ($, $$, $$$, $$$$) in Yelp´s result page, we where able to use K Means Model create 4 distinct clusters.
 - $ cluster: Limited activity across all price ranges ($, $$, $$$, $$$$)
 - $$ cluster: Moderate activity in $ and $$. Limited activity in $$$ and $$$$.
 - $$$ cluster: Highest activity in $$. Increased activity in $$$ and $$$$
 - $$$$ cluster: Highest activity in $$$ and $$$$. High activity in $$.

 
We developed a Python Class that given a list of NYC Zipcodes or neighborhood names will acess Acess the Api gather data for these neighborhoods and use a knn model to predict wich cluster it belongs. The Class also has plot functions to compare the given Zipcodes with the 4 static clusters and there is also a option to print results in NYC map.

### The Data
##### Data Dictionary
tk|tk|tk| 

- Include links to relevant notebooks
- Our data was acquired via Yelp's Fusion API `from yelpapi import YelpAPI`.We set our Yelp Fusion API Key and established an API connection. From there we stored the data we gathered into a `Pandas` DataFrame.
- The search criterias included all Yelp´s categories (shops, restaurants ..), filtered by Yelp´s "best mach" option.
- We gathered top 100 business prices and reviews from 278 NYC zipcodes. 

 


### Analysis
- include links to relevant notebooks]
- intro sentence about our software requirements (e.g., `Pandas`, `Scikit-learn`)
- Used a Grid search through 3 different clustering models (K Means, Agglomerative and Hierarchical) and changing hiper parameters (n_clusters, inits, linkage_method, affinity...).
- Analizing Silhouette Score, Inertia Score and number of observations in each cluster, K Means yielded best results.
- Using the Elbow method n_clusters = 4 was found to be a good balanced choice. 
- Final K means model used the default parameters except for init='random' and random_state=42.
  

### Conclusion
State our findings and introduce recommendations. tk

##### Recommendations
- tk
- tk
- tk
