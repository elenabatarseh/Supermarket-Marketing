# Supermarket Marketing for a Mempership Offer

## Abstract
This exploratory data analysis focuses on understanding customer behavior in response to a marketing campaign and identifying factors influencing their decisions. The superstore is preparing a year-end sale offering a Gold Membership at a discounted rate of $499 (original price: $999). The membership provides a 20% discount on all purchases and is exclusively available to existing customers through a targeted phone call campaign.

The goal of this analysis is to identify the key drivers of offer acceptance, such as income, spending patterns across product categories, website visits, and total spending. By understanding these factors, the superstore can develop more effective marketing strategies and improve customer segmentation to maximize campaign success while minimizing costs. This approach will ensure resources are directed toward customers most likely to respond positively to the campaign.

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Exploratory Data Analysis ](#exploratory-data-analysis)
- [Results](#results)
- [Conclusions](#conclusions)
- [Marketing Focus](#marketing-focus)

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

2. Is there a difference in acceptance rates based on education levels?
A stacked bar chart was created in Power BI to visualize the proportion of customers who accepted (Response = 1) vs. did not accept (Response = 0) the membership offer across different education levels.

3. Is there a relationship between total spending and the likelihood of accepting the offer?
A scatter plot was created in R to visualize the relationship between Total Spending and Offer Response (Response = 1 for Accepted, Response = 0 for Not Accepted). Points were color-coded to differentiate between customers who accepted and those who did not.

4. Which purchase channel (Web, Store, Deal, or Catalog) shows the highest proportion of customers accepting the membership offer?
A series of pie charts was created to visualize the proportion of customers who accepted (Response = 1) vs. did not accept (Response = 0) the membership offer for each purchase channel: Web, Store, Deal, and Catalog.

5. Does the number of small children in a customer's household influence the likelihood of accepting the membership offer?
A stacked column chart was created to show the proportion of customers who accepted (Response = 1) vs. did not accept (Response = 0) the membership offer, categorized by the number of small children in their household (Kidhome).

6. How does spending across different product categories (e.g., Wines, Meat, Gold, etc.) vary between customers who accepted the membership offer and those who did not?
A series of pie charts was created in Power BI to visualize the proportion of spending in different product categories (Fish, Meat, Fruits, Sweets, Gold, and Wines) by membership offer response (Response = 1 for Accepted, Response = 0 for Not Accepted).

### Data Analysis

##### Data Cleaning
``` R
# Handle missing values (replace with median)
store$Income[is.na(store$Income)] <- median(store$Income, na.rm = TRUE)
```

##### Scatterplot of Total Spending vs Offer Acceptance
``` R
# Create a new variable for total spending
store$TotalSpending <- store$MntFishProducts + store$MntMeatProducts + store$MntFruits + store$MntSweetProducts + store$MntWines + store$MntGoldProds

# Scatter plot of total spending vs offer response
ggplot(store, aes(x = TotalSpending, y = Response, color = as.factor(Response))) +
  geom_jitter(alpha = 0.4) +
  scale_color_manual(values = c("red", "green"), labels = c("Did Not Accept", "Accepted")) +
  labs(title = "Total Spending vs Offer Acceptance", x = "Total Spending", y = "Offer Response (0 = No, 1 = Yes)")
```


### Results
The analysis results are summarized as follows:

#### 1. How does income impact offer acceptance?  
Customers with higher income are slightly more likely to accept the offer.   

##### 2. Is there a difference in acceptance rates based on education levels?  
Customers with higher education levels (e.g., PhD) tend to have higher acceptance rates, with 20.78% of PhD holders accepting the offer compared to only 3.7% of those with Basic education. Acceptance rates decrease for lower education levels, suggesting education level is positively correlated with the likelihood of accepting the membership offer.  

#### 3. Is there a relationship between total spending and the likelihood of accepting the offer?  
Customers with higher total spending are more likely to accept the offer (Response = 1), as indicated by the concentration of green dots at higher spending values.
Conversely, customers with lower total spending tend to decline the offer (Response = 0), as shown by the dense cluster of red dots at lower spending values.
This suggests a strong positive relationship between total spending and the likelihood of accepting the offer.  

#### 4. Which purchase channel (Web, Store, Deal, or Catalog) shows the highest proportion of customers accepting the membership offer?  
Catalog purchases have the highest proportion of acceptance at 23.55%, suggesting customers who use catalogs are more likely to accept the membership offer.
Web purchases follow with an acceptance rate of 18.51%, while Store and Deal purchases have lower acceptance rates of 15.7% and 14.98%, respectively.
This indicates Catalog purchases could be a key channel to focus on for targeted marketing campaigns.

#### 5. Does the number of small children in a customer's household influence the likelihood of accepting the membership offer?  
Customers with no children (Kidhome = 0) have the highest acceptance rate at 17.17%, compared to 12.24% for households with 1 child and only 4.17% for households with 2 children.
Acceptance rates decrease as the number of small children increases, suggesting that households with more children are less likely to accept the membership offer.

#### 6. How does spending across different product categories (e.g., Wines, Meat, Gold, etc.) vary between customers who accepted the membership offer and those who did not?  
Wines have the highest proportion of spending by customers who accepted the offer, with 24.66% of total spending coming from customers who accepted (Response = 1).
Spending on Meat Products also shows a relatively higher proportion of acceptance at 26.29%, compared to other categories like Fruits (21.66%) and Fish (20.68%).
Gold Products have one of the lowest proportions of spending by customers who accepted (20.81%), suggesting it may not strongly influence membership acceptance.


### Conclusions

Based on the analysis, the following conclusions can be drawn to guide targeted marketing efforts for the membership offer:

1. **Target Higher-Income Customers**:
   - Customers with higher income levels are more likely to accept the offer, indicating that focusing marketing efforts on higher-income demographics may yield better results.

2. **Prioritize Customers with Higher Education Levels**:
   - Acceptance rates are significantly higher among customers with advanced education (e.g., PhDs). Marketing campaigns could emphasize the value and exclusivity of the membership to appeal to these highly educated groups.

3. **Focus on High-Spending Customers**:
   - Customers with higher total spending are strongly associated with membership acceptance. Targeting these high-spending customers is likely to maximize the success of the campaign.

4. **Leverage the Catalog Channel**:
   - Catalog purchases show the highest acceptance rates (23.55%), followed by web purchases (18.51%). Investing in marketing campaigns focused on catalog users, such as personalized offers or follow-up calls, could improve acceptance rates.

5. **Households Without Small Children**:
   - Customers with no small children in the household (Kidhome = 0) are more likely to accept the offer (17.17%) compared to households with one or more children. Marketing efforts should prioritize households without children, who may have fewer financial constraints or more discretionary spending power.

6. **Highlight Spending on Wines and Meat Products**:
   - Customers with higher spending on Wines (24.66%) and Meat Products (26.29%) show greater likelihood of accepting the membership offer. Promotions tailored toward these categories, such as exclusive discounts or premium offerings, could be an effective way to boost membership acceptance.

### Marketing Focus
To maximize the effectiveness of the membership campaign, the supermarket should focus on:
- **High-income, highly educated customers**.
- **Frequent catalog and web purchasers**.
- **Customers with high spending on Wines and Meat Products**.
- **Households without small children**, as they are more likely to accept the offer.

By targeting these groups with tailored messaging and personalized offers, the campaign can reduce costs and increase membership acceptance rates.










