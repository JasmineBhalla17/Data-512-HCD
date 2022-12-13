# Impact Analysis of COVID-19 on the Housing Market in Shelby County, Tennessee

# Abstract
For this project, I am analyzing the impact of covid-19 on the housing market of Shelby county, Tennessee. Housing market was one of the prime areas that faced the severe brunt of the pandemic combined with anxious buying, remote work, relocation to suburbs, piling up of recession, etc. Pandemic created uncertainty in the overall housing market by creating short periods of bumps and falls in the overall trend- in short, it was hard to understand and analyze where the housing market was going next!

This project is human-centered in two-fold ways- in terms of the causes, a sudden change in the lifestyle due to remote work combined with other factors like anxious buying from people, fluctuations in the mortgage interest rate, etc. created an environment of uncertainty that we all witnessed during the pandemic. And in terms of the effects, we still see how this has directly impacted us in all the aspects- be it emotionally, financially or even physically. With such fluctuations in the housing market, a vast majority of Americans who are/were looking to purchase homes are affected and with the housing prices just soaring up, it would also mean that a lot of people from lower-income brackets will suffer as they will not be able to afford a house, or will be pushed to the suburbs thus widening the wealth gaps between the rich and the poor. And as homeownership is an important tool for building long-term wealth and children of homeowners are likely to become homeowners, this trend can further exacerbate wealth inequality for future generations.
   
By performing this analysis I hope to learn if there was any correlation between the number of covid cases and housing prices. This analysis is of particular scientific interest as it will help others see trends between housing prices and a fluctuating economy during a pandemic.

# Research Question and Analysis
As the pandemic progressed, the cases started increasing nationwide. The state and national government issued several lockdowns to control the spread of the virus, a lot of the businesses were shut and there was a widespread fear of a major recession coming up. Tracking changes in the housing market will provide us insights into the economy of Shelby county of Tennessee state, as it will help us to contextualize growth and decline, thereby giving an insight into the market. 

As part of this project, I plan to explore the following questions to help understand the trend in the housing market since the start of the pandemic:
1. Did Covid-19 impact the housing market for Shelby county, TN with respect to housing inventory, sale price, number of listings from February 2020 to October, 2021? If yes, then how?
2. How did Covid-19 impact the mortgage interest rates and how did that in turn impact the housing market in terms of homes sold and median sale price?
3. How was the overall housing market trend impacted during the covid-19 from February 2020 to October, 2021? Did it move away from its original trend? 

# Data Sources
To perform the analysis I will use the following different datasets.

1. The RAW_us_confirmed_cases.csv file from the Kaggle repository of John Hopkins University COVID-19 data - https://www.kaggle.com/antgoldbloom/covid19-data-from-john-hopkins-university?select=RAW_us_confirmed_cases.csv

2. The weekly housing market data from Redfin - https://redfin-public-data.s3-us-west-2.amazonaws.com/redfin_covid19/weekly_housing_market_data_most_recent.tsv

The Redfin weekly housing market data has data for each county on a weekly basis. The data is broken down by property type (All Residential, Single Family, Condo, Multi-Family, Townhouse, etc). Redfin has published [this page](https://www.redfin.com/news/data-center-metrics-definitions/) to define each column in the dataset and how to interpret the column. This data set is licensed under [Redfin’s Terms of Use](https://www.redfin.com/about/terms-of-use). The guidelines for using the data states to cite the data source appropriately and provide a link to Redfin.

   | Column                      | Values                                 |
   |-----------------------------|----------------------------------------|
   | period_begin                | Start date                             |
   | period_end                  | End date                               |
   | inventory                   | Housing Inventory                      |
   | total_homes_sold            | Total Homes Sold                       |
   | median_sale_price           | Median Sale Price                      |
   | median_new_listing_price    | Median New Listing Price               |
   | total_new_listings          | Total New Listing                      |

3. The monthly housing market data from Redfin - https://redfin-public-data.s3.us-west-2.amazonaws.com/redfin_market_tracker/county_market_tracker.tsv000.gz

4. 30 year fixed Interest Rate - https://fred.stlouisfed.org/series/MORTGAGE30US

# Methodology

### Correlation between covid cases and housing prices 
Here I will perform exploratory data analysis by creating visualizations to see the correlation between housing market data and covid cases week over week.  

Here I will plot the following visualization from the redfin data set. 
Weekly confirmed covid cases and the number of new listings.
Weekly confirmed covid cases and the total number of homes sold.
Weekly confirmed covid cases and inventory.
Weekly confirmed covid cases and median sale price.

 ### Linear Regression
I will also perform linear regression to predict housing prices for 2020 and 2021 and compare it with actual housing prices to see if there is a difference between predicted and actual housing prices for 2020 and 2021. 

Linear regression suits best to find the relationship between a dependent continuous variable (Median Sale Price) and one or more explanatory independent variables (Month/Year). Linear regression suits best here because we can see a linear trend in the dataset for housing prices and housing prices are normally distributed. 

![plot4](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Linear_Regression/houses_SP_trend%20(1).jpeg)

I fit a univariate linear regression model using historical data from (2012- 2019) where the feature is the weekly dates and the target is the median housing price. To avoid the outlier years from the housing market crash in 2008, I have taken the data post that. I have split the data into 75:25 train-test split and fit a linear regression model using python scikit learn. I have also computed the RMSE (root mean square error) as a measure of model performance and used the model to predict housing prices for the years of analysis (2020 and 2021) to compare if the prediction is higher or similar to actual prices.

![plot4](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Linear_Regression/regression_line.jpeg)

The model's performance on the test set is evaluated using the common evaluation metrics for regression problems
MAE, MSE and RMSE on Test Data for Shelby County

![image](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Linear_Regression/Screen%20Shot%202022-12-12%20at%2011.45.20%20PM.png)

![plot4](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Linear_Regression/actual_vs_predicted_house_prices%20(1).jpeg)

# Summary Plots and Visualization

### Findings
 **Housing Inventory**: During the pandemic in 2020 and 2021, we can see a sharp decline in housing inventory (blue line) in the first quarter of the year 2021 where we also observe a peak in covid cases as seen on the red line. A decline in inventory was caused by multitude of reasons such as decline in new constructions due to supply chain disruptions, people not wanting to sell homes due to economic uncertainty, people not wanting to sell homes to avoid home visits by strangers to avoid contracting the virus, and also because of strict stay at home orders and lockdowns in place by the government.
 
![plot1](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Weekly_analysis/weekly_covid_vs_houses_Inventory%20(2).jpeg)

**Median Sale Price**:  We can see an overall upward trend in median housing prices of Shelby county, TN. However, this is still followed by a lot of quick falls and ups- this hints at the overall chaos in the housing market combined with other factors such as anxious buying among people, falling interest rates, limited inventory, etc. The housing price dipped briefly again in the first quarter of 2021 when the cases peaked, but it steadily increased after that.  

![plot3](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Weekly_analysis/weekly_covid_vs_median_SP%20(1).jpeg)

**Total Number of Homes Sold and Total Number of New Listings:**  TThe first graph shows the fluctuations in the total number of homes sold. Overall we see that the number of homes sold over the covid period fluctuates a lot. There are again short periods of increases and decreases in this number. With the covid cases peaking up in the first quarter of 2021, we observe that the number of homes sold also goes down but then continues to go up with the fall in the number of covid-19 cases.
Similarly, we can see a sharp drop in the number of new listings around January 2021 when the cases peak. From these two graphs, we can conclude that everytime the covid-19 cases increase, the number of homes sold and number of new listings in the market decrease. This could be caused by a number of factors like lockdown, fear among people of getting covid by doing home tours, sellers thinking they might not be able to sell at a high price if there are not enough buyers, real-estate agents not wanting to do in-person home tours etc.

![plot2](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Weekly_analysis/weekly_covid_vs_houses_sold%20(5).jpeg)

![plot4](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Weekly_analysis/weekly_covid_vs_new_listings%20(1).jpeg)

### Mortgage Interest Rates and Housing Trends
Another interesting aspect to look into was the 30-year mortgage interest rate. Overall we can see a declining interest rate trend in 2020 followed by interest rates dropping significantly to a record of less than 2.7% in January 2021. Although we cannot directly correlate interest rate to total homes sold, we can see that lower interest rates have fueled a higher demand for homes as people want to take advantage of lower mortgage rates. However due to a shortage in inventory, the total number of homes sold remained lower which caused the median home price to increase.


![plot4](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Weekly_analysis/interest_rates_vs_homes_sold.jpeg)


![plot4](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Weekly_analysis/interest_rates_vs_homes_sold_vs_covid%20(1).jpeg)

### Linear Regression

From the output of the linear regression model, we can see that there is a big difference between the actual housing and predicted housing price trends for 2020 and 2021. The model was trained with historic housing price data from (2012 to 2019) and based on that was asked to predict the housing price for 2020 and 2021. The model output shows that the housing price during the pandemic increased significantly more compared to previous years and that houses sold for a higher price than they should have been.


![plot4](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Final_Project/Visualizations/Final_Analysis_viz/Linear_Regression/actual_vs_predicted_house_prices%20(1).jpeg)

# Conclusion
Through my analysis, I can conclude that the COVID-19 pandemic had an impact on the housing market in Shelby County. We can see that COVID-19 pandemic has impacted both supply and demand in the housing market. People wanted to take advantage of lower mortgage rates which in turn caused the demand for housing to go up- we see a lot of high and low bumps in the median sale price that indicates the anxiety and uncertainty in the housing market.
 
However the pandemic also fueled a shortage in supply of homes - both newly built and those sold by existing owners. We can see a decline in housing inventory, number of new listings on the market as covid cases increased during the first quarter (Q1) of 2021. We see that with a sharp increase in the number of  covid cases, our KPIs except median sale price fall sharply. Thus we can conclude that an increased demand and a shortage in supply fueled the median sale price of the homes to go up throughout the pandemic.

In terms of mortgage interest rate, we see that they very closely follow the covid-19 trend, that is, the mortgage interest rates keep falling down and reach their lowest point during the Q1 of 2021. With the number of covid-19 cases going down, the mortgage interest rate starts coming up again.

To conclude, this study informs the reader of their understanding of human centered data science as it is important to pay attention to this trend and for the government to take action. It is important to fix this gap between supply and demand by building more homes where people need it, otherwise this inequality will continue to skyrocket and a growing number of Americans will be shut out of the housing market altogether.

# Limitations
There were certain limitations to my analysis which are listed as follows:

I limited my analysis to a fixed period of time which is from February 2020  to October 2021. If looked at longer periods of time, this analysis could infer different conclusions.

I limited my analysis to Single Family Homes (SFH), that is, I did not include other home types like townhomes, condos, etc. This could mean that there could be other patterns and trends for different property types and my results do not extend to those other residential properties.

In my interest rate analysis, I focus on the 30 year fixed interest rate. This could mean that other interest rates could have influenced the housing market differently which is not explored in my analysis. 

The Redfin weekly and monthly data is not seasonally adjusted. Doing so could yield slightly different results.

# Future Work
Future Work
1. It will be interesting to build on top of my analysis to see patterns in the housing market related to other factors such as work from home, commuting patterns, supply chain disruptions, wood prices, lockdown restrictions that have also had some impact on the housing market indirectly. 
2. Another interesting future work is to see how the housing market performed in different states and counties and if there was any commonality that can be extended from such an analysis to generalize the results with similar size states and counties. 
3. Another potential analysis involves how rental prices fluctuated throughout the pandemic and if there was any correlation between rental price and housing prices. 
4. Another analysis that can be built on top of this includes looking at the median household income of the people purchasing the homes to further analyze how the government can create schemes to help racial and generational inequality. 

# License
  My research would be released under an MIT License and the data is all public domain.

# Libraries Used:
1. pandas
2. numpy
3. json
4. requests
5. matplotlib
6. sklearn

# References
1. The impact of coronavirus on the U.S Housing Market - Redfin. (n.d.). Retrieved December 11, 2021, from https://www.redfin.com/guides/coronavirus-housing-market-impact.
2. Florida, R. (2022, September 8). Why did housing costs explode during the pandemic? Bloomberg.com. Retrieved December 11, 2022, from https://www.bloomberg.com/news/features/2022-09-08/why-did-housing-costs-explode-during-the-pandemic 
3. Federal Reserve Bank of St. Louis. (2021, December 9). The impact of covid-19 on the residential real estate market: St. Louis Fed. Saint Louis Fed Eagle. Retrieved December 10, 2022, from https://www.stlouisfed.org/publications/regional-economist/fourth-quarter-2020/impact-co vid-residential-real-estate-market.
4. Demsas, J. (2021, February 5). Covid-19 caused a recession. So why did the housing market boom? Vox. Retrieved December 11, 2022, from https://www.vox.com/22264268/covid-19-housing-insecurity-housing-prices-mortgage-rate s-pandemic-zoning-supply-demand.


# Human Centered Data Science Perspective
In my analysis, I have made an effort to address a variety of human-cenetered data science considerations including:

1. Licenses: I ensured that the research is licensed under a MIT license so others can use it.
2. Copyright: Appropriately citing sources of data, tools, and inspiration
3. Interpretability: Following a literate programming style to explain decisions made along the way that impact the final results of my analysis
4. Reproduciblity: Making my research reproducible by providing information about my environment, how I used the data, and where I received my data in addition to including my data in my repository so that anyone could run my notebooks to replicate my results
5. Interpretability: I hav used methods like Linear regression that are very transparent and easy to understand for the audience of the research. Also I have used visualisation to convey the informaion in a simple manner to promote this goal.

