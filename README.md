# Supermarket Marketing for a Mempership Offer

## Abstract
This exploratory data analysis (EDA) focuses on understanding customer behavior in response to a marketing campaign and identifying factors influencing their decisions. The superstore is preparing a year-end sale offering a Gold Membership at a discounted rate of $499 (original price: $999). The membership provides a 20% discount on all purchases and is exclusively available to existing customers through a targeted phone call campaign.

The goal of this analysis is to identify the key drivers of offer acceptance, such as income, spending patterns across product categories, website visits, and total spending. By understanding these factors, the superstore can develop more effective marketing strategies and improve customer segmentation to maximize campaign success while minimizing costs. This approach will ensure resources are directed toward customers most likely to respond positively to the campaign.

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Exploratory Data Analysis ](#exploratory-data-analysis)
- [Results](#results)

### Project Overview
The purpose of this project is to analyze customer data and identify patterns in their response to marketing campaigns. The analysis focuses on:

Identifying how income influences campaign response.  
Exploring spending habits across product categories.  
Evaluating the impact of website visits and total spending on offer acceptance.  

#### Key Variables Analyzed:
Response: Whether the customer accepted the offer (1 = Accepted, 0 = Not Accepted).  
Income: Yearly household income.  
Spending Categories: Amount spent on wines, meats, sweets, fruits, fish, and gold products.  
Website Visits: Number of times a customer visited the company’s website in the last month.  
Total Spending: Combined spending across all product categories.  

### Data Sources
The dataset used for this analysis is superstore_data.csv, which contains:  

Demographic information (e.g., Income, Marital Status, Education).  
Household composition (e.g., number of children and teenagers).  
Purchase behaviors (e.g., spending on specific product categories).  

### Tools
- R - Data cleaning and Visualizations 
- Power BI - Analysis and Visualizations  

### Data Cleaning/ Preperation
Before analysis, the following steps were performed:  
 
Handled missing values:  
Filled missing Income values with the median income.  

Standardized columns:  
Ensured consistency in variable naming and data formats.  

Created calculated columns:  
Derived total spending as the sum of all product category spending.  

Filtered outliers:  
Removed extreme values in spending and income for cleaner analysis.  

### Exploratory Data Analysis

EDA was conducted to answer key business questions:  

1. How does income impact offer acceptance?  
A bar chart was created in Power BI to compare the average income of customers who accepted vs. did not accept the offer.   
Insight: Customers with higher income are slightly more likely to accept the offer.  

2. Is there a difference in acceptance rates based on education levels?
A stacked bar chart was created in Power BI to visualize the proportion of customers who accepted (Response = 1) vs. did not accept (Response = 0) the membership offer across different education levels.
Insight: Customers with higher education levels (e.g., PhD) tend to have higher acceptance rates, with 20.78% of PhD holders accepting the offer compared to only 3.7% of those with Basic education. Acceptance rates decrease for lower education levels, suggesting education level is positively correlated with the likelihood of accepting the membership offer.

3. Is there a relationship between total spending and the likelihood of accepting the offer?
A scatter plot was created in R to visualize the relationship between Total Spending and Offer Response (Response = 1 for Accepted, Response = 0 for Not Accepted). Points were color-coded to differentiate between customers who accepted and those who did not.
Insight: Customers with higher total spending are more likely to accept the offer (Response = 1), as indicated by the concentration of green dots at higher spending values.
Conversely, customers with lower total spending tend to decline the offer (Response = 0), as shown by the dense cluster of red dots at lower spending values.
This suggests a strong positive relationship between total spending and the likelihood of accepting the offer.

4. Which purchase channel (Web, Store, Deal, or Catalog) shows the highest proportion of customers accepting the membership offer?
A series of pie charts was created to visualize the proportion of customers who accepted (Response = 1) vs. did not accept (Response = 0) the membership offer for each purchase channel: Web, Store, Deal, and Catalog.
Insight: Catalog purchases have the highest proportion of acceptance at 23.55%, suggesting customers who use catalogs are more likely to accept the membership offer.
Web purchases follow with an acceptance rate of 18.51%, while Store and Deal purchases have lower acceptance rates of 15.7% and 14.98%, respectively.
This indicates Catalog purchases could be a key channel to focus on for targeted marketing campaigns.

5. Does the number of small children in a customer's household influence the likelihood of accepting the membership offer?
A stacked column chart was created to show the proportion of customers who accepted (Response = 1) vs. did not accept (Response = 0) the membership offer, categorized by the number of small children in their household (Kidhome).
Insight: Customers with no children (Kidhome = 0) have the highest acceptance rate at 17.17%, compared to 12.24% for households with 1 child and only 4.17% for households with 2 children.
Acceptance rates decrease as the number of small children increases, suggesting that households with more children are less likely to accept the membership offer.

6. How does spending across different product categories (e.g., Wines, Meat, Gold, etc.) vary between customers who accepted the membership offer and those who did not?
A series of pie charts was created in Power BI to visualize the proportion of spending in different product categories (Fish, Meat, Fruits, Sweets, Gold, and Wines) by membership offer response (Response = 1 for Accepted, Response = 0 for Not Accepted).
Insight:
Wines have the highest proportion of spending by customers who accepted the offer, with 24.66% of total spending coming from customers who accepted (Response = 1).
Spending on Meat Products also shows a relatively higher proportion of acceptance at 26.29%, compared to other categories like Fruits (21.66%) and Fish (20.68%).
Gold Products have one of the lowest proportions of spending by customers who accepted (20.81%), suggesting it may not strongly influence membership acceptance.

### Data Analysis
``` R
# Handle missing values (replace with median)
store$Income[is.na(store$Income)] <- median(store$Income, na.rm = TRUE)
```


### Results
The analysis results are summarized as follows:



   










