# Supermarket Marketing for a Mempership Offer

## Abstract
This exploratory data analysis (EDA) focuses on understanding customer behavior in response to a marketing campaign and identifying factors influencing their decisions. The superstore is preparing a year-end sale offering a Gold Membership at a discounted rate of $499 (original price: $999). The membership provides a 20% discount on all purchases and is exclusively available to existing customers through a targeted phone call campaign.

The goal of this analysis is to identify the key drivers of offer acceptance, such as income, spending patterns across product categories, website visits, and total spending. By understanding these factors, the superstore can develop more effective marketing strategies and improve customer segmentation to maximize campaign success while minimizing costs. This approach will ensure resources are directed toward customers most likely to respond positively to the campaign.

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
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
- R - Data cleaning  
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

2. Which product categories are most associated with offer acceptance?  
A bar chart in Power BI showed average spending in each category for both groups (accepted vs. not accepted).  
Insight: Spending on wines and meats showed the greatest differences between the two groups, with higher spenders being more likely to accept.  

3. Do customers who spend more in specific categories (e.g., Wine or Gold) tend to accept the offer more frequently?  
A box plot was created to visualize spending on Wines and Gold Products for customers who accepted vs. did not accept the offer.  
Insight: Customers with higher spending on wines and gold products were significantly more likely to accept the offer, indicating these categories are strong drivers of acceptance.  
   
4. Do website visits correlate with offer acceptance?  
A box plot was created to compare the distribution of website visits between the two groups.  
Insight: Customers who accepted the offer tend to visit the website more frequently.  

5. Does total spending influence offer acceptance?  
A scatter plot was used to visualize the relationship between total spending and offer response.  
Insight: Higher total spending correlates with a higher likelihood of accepting the offer.   


### Data Analysis
``` R
# Handle missing values (replace with median)
store$Income[is.na(store$Income)] <- median(store$Income, na.rm = TRUE)
```

### Results
The analysis results are summarized as follows:


   










