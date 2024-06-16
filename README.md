# SALES ANALYSIS WITH KINGSLEY OSUNKWO


## TABLE OF CONTENT
- [Project Overview](#project-overview)
- [Tidyverse](#tidyverse)
- [Objectives](#objectives)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation) 
- [Expolartory Data Analysis](#expolartory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results and Findings](#results-and-findings)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)



### Project Overview
---

Sales analysis is the process of examining and evaluating sales data to gain insights into the performance of a company’s products or services. It involves analyzing various aspects of sales, such as
trends, patterns, customer behavior, and performance metrics, to make informed business decisions.
Sales analysis helps companies understand their sales performance, identify areas of strength and
weakness, pinpoint opportunities for growth, and develop strategies to improve sales effectiveness.
Key components of sales analysis typically include:

1. Sales Volume: Examining the quantity of products or services sold over a specific period.
2. Revenue Analysis: Assessing the revenue generated from sales, including total revenue,
revenue by product or service, revenue by customer segment, etc.
3. Sales Trends: Identifying patterns and trends in sales data over time, such as seasonal
fluctuations, cyclical trends, or changes in demand.
4. Customer Analysis: Understanding the demographics, preferences, buying behavior, and
purchasing patterns of customers to target marketing efforts more effectively and improve
customer satisfaction.
5. Product Performance: Evaluating the performance of individual products or product categories in terms of sales volume, revenue, profitability, and market share.
6. Sales Channels: Analyzing the effectiveness of different sales channels (e.g., direct sales,
online sales, distribution channels) and optimizing their performance.
7. Sales Forecasting: Using historical sales data and predictive analytics to forecast future
sales volumes and revenue.
8. Competitive Analysis: Comparing the company’s sales performance with that of competitors to identify strengths, weaknesses, and opportunities in the market.
9. Store sales and profit analysis help businesses identify areas for improvement and make datadriven decisions to optimize their operations, pricing, marketing, and inventory management
strategies to drive revenue and growth.


### Tidyverse

Hello readers! Today, I'm excited to share how the Tidyverse, a powerful collection of R packages, can be used for sales analysis. The Tidyverse is a game-changer for data manipulation and analysis, and here's how it can transform our sales data into actionable insights:

1. Data Cleaning and Preprocessing: Using `dplyr` and `tidyr`, we can handle missing data, remove duplicates, and transform our data. These tools help ensure that our sales data is accurate and consistent before diving into analysis. It’s like tidying up our workspace before getting to the fun part!
2. Data Manipulation: The Tidyverse offers robust tools for filtering, sorting, grouping, and aggregating data. With `dplyr`, we can perform calculations, compute summary statistics, and reshape data to extract meaningful insights from our sales data. Think of it as shaping raw clay into beautiful sculptures!
3. Time Series Analysis: Time series data is no challenge with the Tidyverse and the `lubridate` package. We can easily analyze sales data over time, resample it, calculate rolling statistics, and perform date/time-based operations to understand sales trends and patterns. It’s like having a time machine for our data!
4. Data Visualization Integration: Creating insightful visualizations is a breeze with `ggplot2`, part of the Tidyverse. This powerful package allows us to create stunning visualizations of our sales data, making complex data more accessible and understandable. It’s like turning numbers into a story!
5. Data Merging and Joining: Combining multiple datasets is seamless with `dplyr` functions like `left_join`, `inner_join`, `right_join`, and `full_join`. This capability allows us to merge sales data with customer or product data, providing a comprehensive view and deeper insights into our sales performance. It’s like putting together pieces of a puzzle!

By leveraging these tools, we can conduct a thorough and insightful sales analysis that drives business decisions and strategies. Now Let’s dive into the main event. Let's use Tidyverse and uncover the stories hidden within this our Superstore Sales data, but before we do that, let's understand the Objective behind this project.

### Objectives
- What is the overall sales trend?
- Sales by Category?
- Sales by Sub-Category?
- Profit Analysis
- Profit analysis by customer segments:
- Which are the Top 10 products by sales?
- Which are the Most Selling Products?
- Which is the most preferred Ship Mode?
- Which are the Most Profitable Category and Sub-Category?

With these Objectives clearly stated, we know what sucess would look like, we also know what our key performance indicators(KPIs) would be. 

### Let's get Started
0.1 Setting up integrated development environment (IDE) for R. In this case, I would be using RStudio.
```
# Install Tidyverse package
install.packages("tidyverse")

# Load Tidyverse package and all Required Libraries
library(tidyverse)

# The Tidyverse package encompasses neumerous packages, for the sake of this particular line, we need `ggplot2` and `gridExtra`,
 if you load the `tidyverse` package in R, it will automatically load ggplot2 and other related packages, making them available for use,
but it would not automatically load `gridExtra`, so I have to load it.
library(gridExtra)

# Install and load the plotly package
install.packages("plotly")
library(plotly)
layout_options(theme = "plotly_white")
```

### Data Sources
```
# Install and load the readxl package
install.packages("readxl")
library(readxl)
# Loading the Dataset, Read Excel file into a data frame
sales_data <- read_excel('cloud/project/superstore_sales.xlsx')

# View the first few rows of the data
head(sales_data)
```
![image](https://github.com/kingsleyosunkwo/Sales-Analysis/assets/171164581/1476954d-c8d2-4a03-b698-d3d607be7b0e)

```
# Shape of the dataset
dim(sales_data)
(5681, 11)
```
```
# Columns present in the dataset
colnames(sales_data)
[1] "Item_Identifier"           "Item_Weight"               "Item_Fat_Content"         
 [4] "Item_Visibility"           "Item_Type"                 "Item_MRP"                 
 [7] "Outlet_Identifier"         "Outlet_Establishment_Year" "Outlet_Size"              
[10] "Outlet_Location_Type"      "Outlet_Type"
```
```
# A concise summary of the dataset
str(sales_data)
```
![image](https://github.com/kingsleyosunkwo/Sales-Analysis/assets/171164581/03bffa28-bf71-4bdf-814f-442b95a58b3d)


The Primary dataset used for this analysis is the "superstore_sales.csv" file, containing detailed information about each sales made by the company















### Tools
- Spreadsheet - Data Cleaning [Download here](https://drive.google.com/file/d/1n-XjMPebQ0HtojYkmf8SHRiXL-IA1MzJ/view?usp=sharing)
- SQL Server (Data Analysis) 
- Tableau (Creating visualisation report)

### Data Cleaning and Preparation 


### Expolartory Data Analysis


### Data Analysis
```SQl
Select
Where
```

### Results and Findings


### Recommendations
- The company should look into creating jingles during these periods to further maximize profit.
- Focus the ad targeted audience on East and South Regions.
- Bellen and Quad sell most during these periods consider getting more of them
- The best months for sales are September, October and November.


### Limitations


### References 
[Stake Overflow](https://stackoverflow.com/nocaptcha?s=911714e9-88d1-4757-8a3b-a85af16c7524)

🔼

💻

|Heading1|Heading2|Heading3|
|--------|--------|--------|
|Content|Content2|Content3|
|R|SQL|Spreadsheet|


`colomn_1`

**bold**

*Italic*
