# International Debt Statistics (IDS)

## Background/Motivation
Everyday hundreds of billions of dollars are traded on the bond market. Lower and middle-income countries must secure external debt to finance their operations. Countries must find a balance between debt and equity investments while still recognizing the amount of risk that they are willing to take. Bonds from foreign countries can be a more secure method of financing in comparison to stocks in the marketplace, however, having too much debt with an unbalanced portfolio can be detrimental.  

## Problem Statement
Middle-income and lower-income countries need to determine whether they can afford to take on more debt or not. To financially support an economy, it is essential to purchase foreign debt, however, purchasing too much foreign debt may lead to defaults on payments to its creditors, thereby resulting in the potential to disrupt a country’s economy in ways such as increased inflation rates, increased unemployment, and a decrease in the value of that country’s dollar.  

## Analysis Questions 
1.	Which 10 countries have the highest levels of foreign debt? 
2.	Do middle and lower-income countries follow the same overall trends in debt levels that their regions do? 
3.	What is the overall current state of each region’s economy in terms of debt levels? 
4.	What countries (if any) are at risk of taking on too much foreign debt? 
5.	What countries, (if any) have relied the most on the International Monetary Fund to assist with their levels of debt in the past ten years? 
6.	Which countries have the highest levels of reserves set aside for debt protection, if needed?

## Dataset Description
The dataset is the International Debt Statistics (IDS) dataset, from the World Bank. The dataset includes debt statistics between the years of 1970-2029 for lower-income and middle-income countries and has been gathered from multiple sources from international government institutions. The dataset contains over 1,500 indicators of external debt and related financial flows, such as debt stocks and flows, creditor composition, and currency composition. The data is organized by country and includes aggregates for regions and income groups. It is available in both Excel and CSV formats and includes data on external debt for 121 countries and territories. The additional workbooks in the dataset include metadata, a detailed description of each ‘series name’ variable, and the sources that the data was retrieved from. The International debt statistics dataset contains 66 variables. 6 of these variables are objects, and the remaining 60 variables are floats.

## Data Collection Process
The data has been combined from a collection of various online databases amalgamated by the World Bank and is listed in the datasheet labeled ‘FootNote’ in the XLSX file. Different segments and groups within this dataset were taken into consideration. The data is organized not only by country but also by region or continent, enabling an assessment of whether countries follow trends similar to their respective regions. Additionally, the dataset categorizes countries based on income levels, with cumulative values provided for all countries within each income group.

Determining which variables to include and exclude presented significant challenges. Inclusion criteria were established based on the series name and their respective codes for each country. Ultimately, the following variables were identified as the most suitable for the analysis:

<img width="926" alt="Screenshot 2024-12-06 at 6 55 01 PM" src="https://github.com/user-attachments/assets/89d2edfd-d8df-4281-b6c7-5e9990c020b0">


## Data Cleaning
The data cleaning process involved several steps to ensure the dataset's consistency and usability. Columns representing years 1970-2005 were removed due to inconsistencies in their statistics, and the years 2023-2029 were excluded because of insufficient data for extrapolation. This narrowed the dataset to cover the years from 2006 to 2021.

Rows for each country were filtered to retain only those with values for the 11 selected series names. Additionally, the columns labeled "Counterpart-Area Name" and "Counterpart-Area Code" were removed, as all observations in these columns contained identical values, which did not provide meaningful information.

Finally, the dataset was checked for duplicate and null values. No duplicate values were found, but some null values remained in the year columns. These null values were not removed to preserve the integrity of the dataset, as removing them would have resulted in the loss of the entire dataframe. Instead, the data was analyzed with the null values intact.

## Expected Transformation Steps
The following transformations are planned for the dataset:

Two new columns, labeled ‘Income_Group’ and ‘Region’, will be added to indicate each country’s respective income level and regional categorization.

Since the dataset lacks a primary key column, a unique identifier for each row will be created by combining the ‘Country code’ and ‘Series code’ columns. For instance, to locate the total amount of debt rescheduled in Afghanistan, the combined code "AFG.DX.TXR.DPPG.CD" can be used.

Variable names will be transformed by replacing underscores ("_") with spaces to address issues encountered while working with the existing labeling format.

## Data Analysis

### Top 10 Countries with the Highest Levels of Foreign Debt

![image](https://github.com/user-attachments/assets/7599c729-f857-42e1-909b-c2501ecb4f44)

The first visualization compares the top 10 countries with the highest levels of foreign debt. This graph depicts debt owed to public creditors (government bodies) over time, with the respective countries highlighted in the legend.

The analysis focuses on changes in debt levels owed to public creditors between 2011 and 2021, showing that most countries have experienced an upward trend in debt levels during this period. While many countries follow a similar pattern, a few stand out:

India has exhibited a relatively consistent increase in debt over the past decade. Starting with significantly higher debt levels than other countries, India has further widened the gap between itself and others.
Bangladesh has also shown a consistent upward trend but experienced a notable spike in 2015, which warrants further investigation.
Egypt experienced a similar spike in 2014 but has since steadily reduced its debt levels, signaling to creditors that it is effectively meeting its repayment obligations and remains an attractive investment destination.
Vietnam has consistently decreased its debt levels since 2011, further establishing itself as a safer investment option for creditors.

### Regional Analysis: Countries with the Highest Total Change in External Debt Stocks in 2021

![image](https://github.com/user-attachments/assets/2b1f78f0-7c28-44e0-85a9-f2a7c72689e3)

The analysis identifies the countries in each region with the highest total change in external debt stocks in 2021 and examines trends in these changes over the past 10 years. The total change in debt stocks represents the year-over-year variation in debt stock, measured in current U.S. dollars.

To visualize these trends, a facet line graph was created for each of the identified countries, resulting in six distinct line graphs showing trends between 2011 and 2021. The findings are as follows:

China recorded the highest variation in debt stock in 2021, while Egypt, Arab Rep had the lowest.
Across all six countries, there were periods of negative total change in debt stock between 2014 and 2018, though the exact years varied by country.
The total change in debt stock fluctuated for China, Brazil, and India over the decade. However, the changes in 2021 were relatively similar to those in 2011.
For the Russian Federation, the variation in debt stock showed a decreasing trend, indicating effective debt stock reduction policies. In contrast, Egypt, Arab Rep experienced an increasing trend in the variation of debt stock from 2011 to 2021.

### Regional Economic Overview: Debt Levels and Income Distribution

To assess the overall state of each region’s economy in terms of debt levels, an initial analysis was conducted using a geographical map to visualize debt levels across countries. This revealed that countries in the South Asia region exhibit the highest overall debt levels.

To further refine the analysis, the income groups of countries within each region were compared to evaluate their contributions to the region’s economic performance. The results highlight notable disparities:

The Sub-Saharan Africa region demonstrates the largest income disparity among its countries. Approximately 34% of countries are classified as lower-income, 62.4% as lower-middle income, and only 3.53% as upper-middle income.
In contrast, the Latin America and Caribbean region is in a more favorable position in terms of income distribution. Around 78.8% of its countries are categorized as upper-middle income, while the remaining 21.2% are lower-middle income.









