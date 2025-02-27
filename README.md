# Walmart Sales 2010 - 2012 Excel Project Write Up

## Introduction

My objective for this project was to analyze Walmart’s sales data from 2010-2012 and uncover sales trends, compare performance across store locations, and explore the relationships between sales and external variables like inflation, temperature, and unemployment. I believe this project demonstrates my ability to clean, analyze, and visualize data using Excel, culminating in a dynamic dashboard.

The dataset, titled Walmart_Sales, was sourced from Kaggle and can be downloaded via this [link](https://www.kaggle.com/datasets/9592bb3b3c89493fabab56b4317ae10dbd70e6b66d2d464fb7f08c6a5903556d). The data contains 6,434 rows and contains weekly sales data, from February 2010 to October 2012, for 45 Walmart store locations. 

The data contains the following columns:
- Store: Unique store identifier
- Date: Sales week start date
- Weekly_Sales: Sales in USD
- Holiday_Flag: Binary marker indicating the presence or absence of a holiday
- Temperature: Average air temperature in the region for that week
- Fuel_Price: Average per gallon fuel cost in the region for that week
- CPI: Consumer price index that week
- Unemployment: Unemployment rate that week


### Data Preparation

**Loading, initial examination and cleaning**

After loading the dataset into Excel, the first step was to check for any duplicate rows or missing values using filters, of which there were none. Next I needed to ensure the data’s integrity and prepare it for analysis by properly formatting the columns. 


I quickly noticed a discrepancy in the date column; date values were appearing in 2 different formats (“DD/MM/YY” and “DD-MM-YYYY”). So the first thing I did was clear all formatting from the sheet to start with a clean slate. Next I inserted a helper column and used the function ISNUMBER() to check which format was being properly read as a number by excel, which turned out to be the “DD/MM/YY” format. Finally, I used the “Text to Columns” tool under the Data tab to standardize the formatting in the date column to “DD/MM/YY”.

 
Now that the date column was properly formatted, the next step was to adjust the formatting of the rest of the data. I converted weekly_sales and fuel_price column to the accounting format. I also reduced the number of decimal places in the temperature, fuel price, CPI, and unemployment columns as it would make for cleaner visualizations later on. 


Finally I used a helper column to turn the unemployment rate column to percentages, by dividing the cell by 100 and then setting the column to the percentage format. This way the unemployment rate would be appropriately represented as percentages in later analysis and visualizations and eliminate the need for further interpretation.
 

**Exploratory Data Analysis (EDA)**

Next I wanted to get a high level idea of the data I’d be working with, so I calculated some summary statistics using the Analysis ToolPak, and Data Analysis tool within the Data tab.

The most relevant summary statistics were for weekly_sales, temperature, fuel_price, CPI, and unemployment, as it gave me a better idea of the values present in each column. Being able to see average sales, fuel price, CPI, and unemployment where helpful in establishing baseline performance, while seeing the maximums helped me identify and theorize about outliers in the data.


## Analysis and Visualizations

For this project I created 7 visualizations, leveraging Pivot tables, to analyze the relationship between sales performance and external factors like temperature, CPI, and unemployment.

1. Sales Time-Trend Analysis by Store:
- Objective: Track and compare sales across all 45 locations represented in the data set.
- Methodology: Created a pivot table that sums sales across a selected time frame, and a line chart with a slicer and a timeline for filtering, that allows me to compare all or selected stores’ sales over a given period of time.
- Insights: In the line chart I was able to observe seasonal fluctuations in sales. As expected, sales for virtually all locations peaked during December, but I also observed fairly consistent peaks in sales at the beginnings of Q2 and Q3.
 
2. Top 5 Stores by Sales:
- Objective: Highlight top-performing stores in a given period.
- Methodology: Used a new pivot table where date is now in the column field and stores are in the rows field, and a bar chart connected to dashboard timeline.
- Insights: Store 20 consistently outperformed all other stores, ranking in 2nd in every year but 1st overall. Store 4 was another consistent top 5 store, while store 14 only made the top 5 in 2010 and 2012, but overall still earned 3rd place.

3. Total Sales Bar Chart
- Objective: Compare total sales across all stores for a given time period.
- Methodology: Pivot table, with date in the rows field and sales in the values field, and a bar chart.
- Insights: 2011 was Walmarts best performing year out of the 3 in the data set, but we are missing sales data for Q4 2012 so this is likely skewed. I don’t doubt though that if we had a whole years worth of sales data for 2012 we’d see positive YoY growth, as the US consumers were beginning to recover from the 2008 financial crisis. Plus, Walmart has always been more resistant to periods of economic downturns because of its wide selection of more affordable daily goods. In 2010, Walmart actually generated $405Bn across all 8,400 of its retail units (our data set only represents ~0.5%), which then grew to $443Bn in 2012, before growing to become the biggest company by revenue in 2014 (a ranking it continues to hold 10 years later).
 
4. Sales on Holiday v. Non-Holiday Week:
- Objective: Compare average weekly sales on holiday vs non-holiday weeks.
- Methodology: Created a pivot table that categorized weeks based on the Holiday_Flag column and compared average sales figures.
- Insights:Sales were significantly higher during holiday weeks, particularly around Thanksgiving and Christmas, supporting the long-standing trend of increased consumer spending during major holidays.
 
5. Temperature and Sales Distribution
- Objective: Analyze how temperature fluctuations impact sales performance.
- Methodology: Used a scatter plot to compare weekly sales against temperature values.
- Insights: Sales were highest when temperatures ranged between 30-50°F, with a decline in both extreme cold and hot conditions, indicating that weather influences shopping behavior.

6. MoM Sales Growth v. MoM Inflation
- Objective: Examine the relationship between inflation rates and Walmart’s sales growth.
- Methodology: Created a pivot table tracking MoM sales growth alongside CPI changes, visualized using a dual-axis line chart.
- Insights: While some correlation existed between inflation increases and slowed sales growth, Walmart's business model appeared more resilient to inflation than other retailers, suggesting strong consumer reliance on cost-effective goods.

7. Unemployment Rate and Weekly Sales
- Objective: Determine how unemployment rates impact sales.
- Methodology: Used a line chart to compare weekly sales trends against unemployment rates.
- Insights: Higher unemployment rates generally coincided with lower sales figures, reinforcing the idea that consumer spending power is heavily influenced by job stability.


## Full Dashboard


### Key Insights
The analysis conducted in this project revealed four key insights about retail sales:

**1. Holidays significantly impact retail sales:** Sales tended to be higher during holiday weeks, particularly in December. This trend aligns with traditional consumer behavior, where holiday shopping boosts retail revenue. However, it is worth noting that this effect has diminished in recent years due to the rise of e-commerce and changing shopping habits.
   
**4. Unemployment rates strongly correlate with sales performance:** Periods of higher unemployment typically saw lower sales, highlighting the sensitivity of consumer spending to economic conditions. This finding reinforces the idea that job stability is a crucial driver of retail sales.

**5. Walmart's sales remain resilient against inflation:** Despite fluctuations in CPI, Walmart's sales demonstrated resilience. This could be attributed to Walmart's value-driven business model, which attracts budget-conscious consumers during periods of economic uncertainty.

**6. Optimal sales occur in moderate temperatures (30-50°F):** Analyzing temperature and sales data revealed that sales were highest when temperatures ranged between 30 and 50 degrees Fahrenheit. This may be due to seasonal shopping patterns, where consumers are more likely to shop in-store during cooler but not extreme weather conditions.

## Reflections and Next Steps 
This project helped me strengthen my data cleaning, analysis, and visualization skills in Excel while providing valuable insights into retail sales trends. Working with real-world data required me to address formatting inconsistencies and choose appropriate methods for analysis, reinforcing my problem-solving abilities. Additionally, designing interactive visualizations, such as pivot tables and slicers, improved my ability to create user-friendly dashboards.

For future improvements, I would:

1. Expand the analysis by incorporating additional external factors, such as consumer sentiment or gas prices, to gain deeper insights.
2. Use Python or SQL to handle larger datasets more efficiently and perform more advanced statistical analyses.
3. Develop predictive models to forecast future sales trends based on historical data and economic indicators.


## Conclusion
This project successfully demonstrateS my ability to clean, analyze, and visualize data using Excel. By examining Walmart's sales trends from 2010-2012, I uncovered key factors influencing sales performance, including holiday effects, unemployment, inflation resistance, and temperature patterns. The insights gained can help businesses optimize sales strategies based on economic conditions and seasonal trends. Moving forward, I aim to expand my data analysis capabilities using advanced tools and methodologies to extract even deeper insights from complex datasets.
