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

<img width="713" alt="Screenshot 2024-12-06 at 7 48 19 PM" src="https://github.com/user-attachments/assets/72a80190-f2ea-4050-849f-719208421896">


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

<img width="1296" alt="Screenshot 2024-12-06 at 7 38 14 PM" src="https://github.com/user-attachments/assets/517ca9c4-99f2-41cb-8769-ab00602ddb15">

To assess the overall state of each region’s economy in terms of debt levels, an initial analysis was conducted using a geographical map to visualize debt levels across countries. This revealed that countries in the South Asia region exhibit the highest overall debt levels.

To further refine the analysis, the income groups of countries within each region were compared to evaluate their contributions to the region’s economic performance. The results highlight notable disparities:

<img width="1237" alt="Screenshot 2024-12-06 at 7 51 03 PM" src="https://github.com/user-attachments/assets/8b3856b5-221e-42cf-949a-c0cd8db69979">

The Sub-Saharan Africa region demonstrates the largest income disparity among its countries. Approximately 34% of countries are classified as lower-income, 62.4% as lower-middle income, and only 3.53% as upper-middle income.
In contrast, the Latin America and Caribbean region is in a more favorable position in terms of income distribution. Around 78.8% of its countries are categorized as upper-middle income, while the remaining 21.2% are lower-middle income.

### Identifying Countries at Risk of Excessive Foreign Debt

During the analysis to determine countries at risk of taking on excessive foreign debt, a significant portion of the dataset contained NA values. These were not removed during the data cleaning process due to the structure of the dataset, which spans multiple years where each year is represented as a variable. Removing rows with missing data for a single year would have resulted in the unnecessary loss of valuable information from other years.

This limitation posed challenges for the original analysis. The intended variable, rescheduled debt (representing restructured contract terms to aid a country), could not be used due to insufficient data. Consequently, an alternative approach was adopted by shifting focus to IMF credits as a proxy for assessing risk.

IMF credits represent loans extended to countries in need of additional monetary assistance, often during economic crises. These credits serve as an indicator of financial distress or reliance on external support, providing insights into which countries may be at risk of overburdening themselves with foreign debt.

### Reliance on the International Monetary Fund Over the Past Decade

![image](https://github.com/user-attachments/assets/73a92328-b037-4b82-a59d-dc2f0c64137c)

The countries that have relied most heavily on the International Monetary Fund (IMF) for assistance over the past 10 years are China, India, and the Russian Federation. While this reliance suggests potential economic challenges, additional context provides a more nuanced understanding of each country's financial situation:

China has utilized IMF resources primarily to expand its infrastructure and strengthen its economy. Despite its reliance on the IMF, China is not among the top 10 countries with the highest levels of external debt owed to public creditors and possesses substantial reserves. This indicates that China's IMF borrowing may be strategic rather than indicative of financial instability.

India is one of the top three borrowers from the IMF and is also the leading country for external debt owed to public creditors. This suggests that India faces challenges in sustaining its economy solely through private and public creditors, necessitating additional support from the IMF. These funds could be directed toward fostering economic growth or mitigating the effects of financial downturns.

The Russian Federation relies on IMF assistance partly due to the numerous tariffs imposed on its economy by other nations. Despite this reliance, Russia maintains relatively low levels of external debt from public creditors, reflecting its economic independence and limited access to traditional debt financing sources.


### Countries with the Highest Levels of Reserves for Debt Protection

![image](https://github.com/user-attachments/assets/a5a8087f-5182-4c4a-acdf-048041d9ae84)

The final analysis compares the top 5 countries with the highest levels of reserves, including gold, to determine which countries have the most liquid assets set aside for emergencies or unique investment opportunities.

The analysis reveals that China holds the highest level of reserves, which supports the notion that its use of IMF funds is primarily for economic expansion and infrastructure development. This is significant because it suggests that, despite relying on IMF assistance, China has maintained a strong financial position. As an upper-middle-income country, China has managed to keep its debt levels relatively stable while benefiting its society between 2011 and 2021. However, there is a noticeable disparity between China and the other top countries in terms of reserve levels.

The other upper-middle-income countries, namely the Russian Federation and Brazil, have much smaller reserves. Although the size of the economy likely influences the amount of reserves a country can set aside, the differences in reserves between China, Brazil, and Russia are substantial.

Overall, this analysis indicates that reserve levels are closely aligned with each country’s economic performance, following a similar pattern to their IMF borrowing levels. Countries with higher reserves tend to have stronger economic stability and greater capacity to manage external financial challenges.

## Conclusion
Several key conclusions can be drawn from the analysis and visualizations presented:

India holds the highest levels of external debt, with Bangladesh closely following. The increasing debt levels in India are significant, as they may indicate either a potential default on payments or a strategic investment in foreign expenditure to foster economic growth.

In 2020, many middle-income and lower-income countries experienced a decline in GDP growth. As shown in the analysis of debt stocks, all but one country saw an increase in debt in 2020, suggesting that the global economy was weakening. The pandemic had a considerable impact, with several nations experiencing both a decline in GDP and a rise in debt levels. Higher-income countries adapted more effectively due to their established infrastructure and resources. However, the economic gap between higher-income and lower/middle-income countries continued to grow in the post-pandemic period. China was one of the few countries that achieved positive GDP growth in 2020, driven by its substantial contributions to global exports and manufacturing.

The analysis of regional debt levels and income disparities revealed that the Sub-Saharan Africa region has the highest income disparity, with 34% of its countries classified as “lower income” and over 62% as “lower-middle income.” This highlights the varying levels of support within regions and the significant economic disparity between them.

Over the past decade, China has maintained a steady rate of borrowing from the IMF, utilizing it for economic growth and stability. While China’s borrowing levels far exceed those of other countries, its borrowing rate has remained stable, indicating sustained economic growth.

While ideal data trends would suggest that all countries make similar investment decisions to minimize risk and maximize return, anomalies exist. For example, the Russian Federation has substantial reserves set aside. This may seem unusual, but it makes sense considering the economic sanctions placed on Russia. Maintaining higher reserves provides financial security in the face of external economic pressures.

Generally, countries with higher GDP growth tend to have lower foreign debt levels and higher reserve levels, while those with lower GDP growth often have higher foreign debt levels and lower reserves. Low-GDP countries use foreign investments to stimulate their economies, such as borrowing funds for infrastructure projects that can lead to long-term economic growth, like building hotels that boost employment and tourism.

## Recommendations
Based on the results of the analysis and visualizations, the following recommendations are proposed for lower-income and middle-income countries:

1. Investment in Infrastructure and Resources: A key recommendation for lower-income and middle-income countries is to invest in robust infrastructure, as this can significantly contribute to economic growth and increase GDP. While India has already made strides in this area, diversifying investments beyond infrastructure—such as in education and technology—would further enhance long-term economic stability and growth.

2. Building Liquid Reserves and Crisis Preparedness: In light of the global crisis in 2020, it is crucial for countries to maintain adequate liquid reserves for emergency situations. Governments should ensure that enough funds are set aside as an emergency response fund, particularly in times of global crises. Moreover, investments made during a crisis should be carefully monitored, as certain types of infrastructure investments carry different levels of risk. By following these recommendations, lower-income and middle-income countries would be better equipped to respond effectively to future global challenges.

3. Increasing IMF Borrowing for Economic Growth: For regions like Sub-Saharan Africa, where income disparity is a significant issue, increasing borrowing from the International Monetary Fund (IMF) could provide the financial stability needed to support economic growth. IMF loans are tailored to help lower-income countries during times of crisis and are a valuable tool for stimulating economic development.

4. Maximizing IMF Assistance for Economic Strengthening: China has successfully utilized the IMF to strengthen its economy, and while India is already benefiting from IMF loans, using these funds to focus on key areas such as technology, education, and infrastructure could further boost economic development. Additionally, China may benefit from investing in external debt through official creditors of other countries to expand its portfolio and maintain financial balance.

5. Maintaining Adequate Reserves: Maintaining an appropriate level of reserves is critical for a country’s economic growth and stability. A country should avoid taking on excessive debt that may lead to default risks. Moreover, insufficient cash reserves can limit the ability to make quick, profitable investments or respond to emergencies. Having substantial reserves, like those of the Russian Federation, provides greater flexibility in decision-making and ensures that funds are available for both investments and emergencies.

6. Comprehensive Data Analysis: Finally, it is essential to consider all relevant factors affecting economic data, not just the variables presented in the datasets. Anomalies, such as Saudi Arabia’s high debt levels despite low GDP growth, highlight the importance of further analyzing economic data beyond surface-level statistics to understand the broader context and potential implications.













