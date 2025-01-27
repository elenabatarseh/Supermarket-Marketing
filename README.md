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

2. Is there a difference in acceptance rates based on education levels?

3. Is there a relationship between total spending and the likelihood of accepting the offer?

4. Which purchase channel (Web, Store, Deal, or Catalog) shows the highest proportion of customers accepting the membership offer?

5. Does the number of small children in a customer's household influence the likelihood of accepting the membership offer?

6. How does spending across different product categories (e.g., Wines, Meat, Gold, etc.) vary between customers who accepted the membership offer and those who did not?

### Data Analysis
``` R
# Handle missing values (replace with median)
store$Income[is.na(store$Income)] <- median(store$Income, na.rm = TRUE)
```

### Results
The analysis results are summarized as follows:



   










