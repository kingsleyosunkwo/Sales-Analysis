# SALES ANALYSIS WITH KINGSLEY OSUNKWO


## TABLE OF CONTENT
- [Project Overview](#project-overview)
- [Tidyverse](#tidyverse)
- [Objectives](#objectives)
- [Lets get Started](#lets-get-started)
- [Data Sources](#data-sources)
- [EXPLORATORY DATA ANALYSIS](#exploratory-data-analysis)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation) 
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
3. Customer Analysis: Understanding the demographics, preferences, buying behavior, and
purchasing patterns of customers to target marketing efforts more effectively and improve
customer satisfaction.
4. Product Performance: Evaluating the performance of individual products or product categories in terms of sales volume, revenue, profitability, and market share.
5. Sales Channels: Analyzing the effectiveness of different sales channels (e.g., direct sales,
online sales, distribution channels) and optimizing their performance.
6. Sales Forecasting: Using historical sales data and predictive analytics to forecast future
sales volumes and revenue.
7. Competitive Analysis: Comparing the company’s sales performance with that of competitors to identify strengths, weaknesses, and opportunities in the market.
8. Store sales and profit analysis help businesses identify areas for improvement and make datadriven decisions to optimize their operations, pricing, marketing, and inventory management
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

### Lets get Started
0.1 Setting up integrated development environment (IDE) for R. In this case, I would be using RStudio.
```
# Install Tidyverse package
<install.packages("tidyverse")

# Load Tidyverse package and all Required Libraries
<library(tidyverse)

# The Tidyverse package encompasses neumerous packages, for the sake of this particular line, we need `ggplot2` and `gridExtra`,
 if you load the `tidyverse` package in R, it will automatically load ggplot2 and other related packages, making them available for use,
but it would not automatically load `gridExtra`, so I have to load it.
library(gridExtra)

# Install and load the plotly package
<install.packages("plotly")
library(plotly)
layout_options(theme = "plotly_white")
```

### Data Sources
```
# Install and load the readxl package
<install.packages("readxl")
<library(readxl)
# Loading the Dataset, Read Excel file into a data frame
<sales_data <- read_excel('cloud/project/superstore_sales.xlsx')

# View the first few rows of the data
<head(superstore_sales_xlsx)
# A tibble: 6 × 11
  Item_Identifier Item_Weight Item_Fat_Content Item_Visibility Item_Type         Item_MRP
  <chr>                 <dbl> <chr>                      <dbl> <chr>                <dbl>
1 FDW58                 20.8  Low Fat                  0.00756 Snack Foods          108. 
2 FDW14                  8.3  reg                      0.0384  Dairy                 87.3
3 NCN55                 14.6  Low Fat                  0.0996  Others               242. 
4 FDQ58                  7.32 Low Fat                  0.0154  Snack Foods          155. 
5 FDY38                 NA    Regular                  0.119   Dairy                234. 
6 FDH56                  9.8  Regular                  0.0638  Fruits and Veget…    117. 
# ℹ 5 more variables: Outlet_Identifier <chr>, Outlet_Establishment_Year <dbl>,
#   Outlet_Size <chr>, Outlet_Location_Type <chr>, Outlet_Type <chr>
```


```
# Shape of the dataset
<dim(superstore_sales_xlsx)
(5681, 11)
```
```
# Columns present in the dataset
<colnames(superstore_sales_xlsx)
[1] "Item_Identifier"           "Item_Weight"               "Item_Fat_Content"         
 [4] "Item_Visibility"           "Item_Type"                 "Item_MRP"                 
 [7] "Outlet_Identifier"         "Outlet_Establishment_Year" "Outlet_Size"              
[10] "Outlet_Location_Type"      "Outlet_Type"
```
```
# A concise summary of the dataset
<str(superstore_sales_xlsx)
spc_tbl_ [5,681 × 11] (S3: spec_tbl_df/tbl_df/tbl/data.frame)
 $ Item_Identifier          : chr [1:5681] "FDW58" "FDW14" "NCN55" "FDQ58" ...
 $ Item_Weight              : num [1:5681] 20.75 8.3 14.6 7.32 NA ...
 $ Item_Fat_Content         : chr [1:5681] "Low Fat" "reg" "Low Fat" "Low Fat" ...
 $ Item_Visibility          : num [1:5681] 0.00756 0.03843 0.09957 0.01539 0.1186 ...
 $ Item_Type                : chr [1:5681] "Snack Foods" "Dairy" "Others" "Snack Foods" ...
 $ Item_MRP                 : num [1:5681] 107.9 87.3 241.8 155 234.2 ...
 $ Outlet_Identifier        : chr [1:5681] "OUT049" "OUT017" "OUT010" "OUT017" ...
 $ Outlet_Establishment_Year: num [1:5681] 1999 2007 1998 2007 1985 ...
 $ Outlet_Size              : chr [1:5681] "Medium" NA NA NA ...
 $ Outlet_Location_Type     : chr [1:5681] "Tier 1" "Tier 2" "Tier 3" "Tier 2" ...
 $ Outlet_Type              : chr [1:5681] "Supermarket Type1" "Supermarket Type1" "Grocery Store" "Supermarket Type1" ...
 - attr(*, "spec")=
  .. cols(
  ..   Item_Identifier = col_character(),
  ..   Item_Weight = col_double(),
  ..   Item_Fat_Content = col_character(),
  ..   Item_Visibility = col_double(),
  ..   Item_Type = col_character(),
  ..   Item_MRP = col_double(),
  ..   Outlet_Identifier = col_character(),
  ..   Outlet_Establishment_Year = col_double(),
  ..   Outlet_Size = col_character(),
  ..   Outlet_Location_Type = col_character(),
  ..   Outlet_Type = col_character()
  .. )
 - attr(*, "problems")=<externalptr> 
```

```
# Checking missing values
<colSums(is.na(superstore_sales_xlsx))

          Item_Identifier               Item_Weight          Item_Fat_Content 
                        0                       976                         0 
          Item_Visibility                 Item_Type                  Item_MRP 
                        0                         0                         0 
        Outlet_Identifier Outlet_Establishment_Year               Outlet_Size 
                        0                         0                      1606 
     Outlet_Location_Type               Outlet_Type 
                        0                         0 
```

```
# Generating descriptive statistics summary
<install.packages("psych")
<library(psych)
<summary_stats <- psych::describe(superstore_sales_xlsx)
summary_stats_rounded <- round(summary_stats, 2) # Round to 2 decimal places
summary_stats_rounded

                          vars    n    mean     sd  median trimmed    mad     min
Item_Identifier*             1 5681  774.39 445.53  772.00  774.37 576.73    1.00
Item_Weight                  2 4705   12.70   4.66   12.50   12.61   5.95    4.56
Item_Fat_Content*            3 5681    3.61   1.08    3.00    3.62   0.00    1.00
Item_Visibility              4 5681    0.07   0.05    0.05    0.06   0.05    0.00
Item_Type*                   5 5681    8.23   4.22    7.00    8.27   4.45    1.00
Item_MRP                     6 5681  141.02  61.81  141.42  139.78  67.82   31.99
Outlet_Identifier*           7 5681    5.72   2.84    6.00    5.73   4.45    1.00
Outlet_Establishment_Year    8 5681 1997.83   8.37 1999.00 1998.04   7.41 1985.00
Outlet_Size*                 9 4075    2.24   0.70    2.00    2.30   1.48    1.00
Outlet_Location_Type*       10 5681    2.11   0.81    2.00    2.14   1.48    1.00
Outlet_Type*                11 5681    2.20   0.80    2.00    2.13   0.00    1.00
                              max   range  skew kurtosis   se
Item_Identifier*          1543.00 1542.00  0.00    -1.20 5.91
Item_Weight                 21.35   16.80  0.13    -1.23 0.07
Item_Fat_Content*            5.00    4.00  0.07    -0.68 0.01
Item_Visibility              0.32    0.32  1.24     2.04 0.00
Item_Type*                  16.00   15.00  0.10    -0.96 0.06
Item_MRP                   266.59  234.60  0.14    -0.90 0.82
Outlet_Identifier*          10.00    9.00 -0.06    -1.26 0.04
Outlet_Establishment_Year 2009.00   24.00 -0.40    -1.21 0.11
Outlet_Size*                 3.00    2.00 -0.36    -0.92 0.01
Outlet_Location_Type*        3.00    2.00 -0.21    -1.46 0.01
Outlet_Type*                 4.00    3.00  0.93     0.62 0.01
```
### EXPLORATORY DATA ANALYSIS
1. SALES BY Item_Type
```
<print(colnames(superstore_sales_xlsx))
[1] "Item_Identifier"           "Item_Weight"               "Item_Fat_Content"         
 [4] "Item_Visibility"           "Item_Type"                 "Item_MRP"                 
 [7] "Outlet_Identifier"         "Outlet_Establishment_Year" "Outlet_Size"              
[10] "Outlet_Location_Type"      "Outlet_Type"              
>

#Sales Proxy: In the absence of direct sales figures in this particular dataset, Item_MRP can act as a proxy to analyze pricing strategies, revenue potential, and profit margins.
#Group by 'Item_Type' and sum 'Item_MRP'

<sales_by_Item_Type <- superstore_sales_xlsx %>%
  group_by(Item_Type) %>%
  summarise(Item_MRP= sum(Item_MRP))
print(sales_by_Item_Type)

Item_Type             Item_MRP
   <chr>                    <dbl>
 1 Baking Goods            56525.
 2 Breads                  23439.
 3 Breakfast               10069.
 4 Canned                  59558.
 5 Dairy                   65978.
 6 Frozen Foods            76044.
 7 Fruits and Vegetables  112360.
 8 Hard Drinks             20366.
 9 Health and Hygiene      46181.
10 Household               94268.
11 Meat                    43804.
12 Others                  14997.
13 Seafood                  3497.
14 Snack Foods            115876.
15 Soft Drinks             39789.
16 Starchy Foods           18403.
```
- Item Type: Snack Foods
- Item MRP: 115,876 
Therefore, this is the highest Maximum Retail Price.

2. SALES BY Item_Fat_Content
```
 <sales_by_Item_Fat_Content <- superstore_sales_xlsx %>%
+   group_by(Item_Fat_Content) %>%
+   summarise(Item_MRP= sum(Item_MRP))
> print(sales_by_Item_Fat_Content)

# A tibble: 5 × 2
  Item_Fat_Content Item_MRP
  <chr>               <dbl>
1 LF                 28319.
2 Low Fat           482849.
3 Regular           270035.
4 low fat             9337.
5 reg                10613.

# Opps It appears like there are inconsistencies in how Item_Fat_Content is recorded, this needs cleaned up for better analysis. Notice how we have LF, Low Fat and low fat.
# Load necessary library
<library(dplyr)
# Create a sample dataframe
<superstore_sales_xlsx <- data.frame(
  Item_Fat_Content = c("LF", "Low Fat", "Regular", "low fat", "reg"),
  Item_MRP = c(28319, 482849, 270035, 9337, 10613)
)
# Clean up the Item_Fat_Content column
<superstore_sales_xlsx <- superstore_sales_xlsx %>%
  mutate(Item_Fat_Content = recode(Item_Fat_Content,
                                   'LF' = 'Low Fat',
                                   'low fat' = 'Low Fat',
                                   'reg' = 'Regular'))
# Verify the changes
<print(superstore_sales_xlsx)
Item_Fat_Content Item_MRP
1          Low Fat    28319
2          Low Fat   482849
3          Regular   270035
4          Low Fat     9337
5          Regular    10613

# Summarize the cleaned data
<sales_by_Item_Fat_Content <- superstore_sales_xlsx %>%
  group_by(Item_Fat_Content) %>%
  summarise(Item_MRP = sum(Item_MRP))

# Print the summarized data
<print(sales_by_Item_Fat_Content)
# A tibble: 2 × 2
  Item_Fat_Content Item_MRP
  <chr>               <dbl>
1 Low Fat            520505
2 Regular            280648
```
- Therefore, Low Fat is the highest Maximum Retail Price.


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
