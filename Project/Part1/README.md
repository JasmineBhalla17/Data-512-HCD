## DATA 512: Human-Centered Data Science


## Problem Statement:
During the last three years we all have been experiencing a global pandemic. This has been tragic and disruptive to many countries and has taken a deep personal toll on many individuals and their families. One aspect that has been hard to miss in the last three years is the datafication of the pandemic. That is, many aspects of the individual toll of the pandemic have been collected, aggregated and re-represented as data. This datafication gives us the privilege to examine the pandemic from potentially many different perspectives to understand how it has changed lives and how it has changed society. To be honest, we are actually at the very beginning of understanding and comprehending these impacts. During this Course Project you are going to begin taking a look at some of the social aspects of the pandemic by conducting a human centered data science analysis of some available COVID-19 data. In Part 1- Common Analysis, every student in the course will work from the same datasets. Students will be assigned to analyze data for one specific County of the United States.

** Assigned County:** Shelby, Tennesse

**Data Sources:**

- [John Hopkins University COVID-19 data] (https://www.kaggle.com/datasets/antgoldbloom/covid19-data-from-john-hopkins-university)
- [Masking Mandates by County] (https://data.cdc.gov/Policy-Surveillance/U-S-State-and-Territorial-Public-Mask-Mandates-Fro/62d6-pm5i)
- [Mask Compliance Survey] (https://github.com/nytimes/covid-19-data/tree/master/mask-use)

**Input Data Files:** 
- Data/RAW_us_confirmed_cases.csv
- Data/mask-mandate.csv
- Data/mask-use-by-county.csv


### Repo Walkthrough:
# Project tree
/Project/Part1
   * [README.md](./README.md) 
   * [Raw_Data](./Raw_Data)
     * [RAW_us_confirmed_cases.csv](./RAW_us_confirmed_cases.csv)
     * [mask-use-by-county.csv](./mask-use-by-county.csv)
   * [Code](./Part1/Code)
     * [Common Analysis - Part 1.ipynb](./Code/Common_Analysis.ipynb)
   * [Intermediate Results](./Intermediate_Results)
      * [Confirmed_cases_Shelby.csv](./Confirmed_cases_Shelby.csv)
      * [cdc_mask_Shelby.csv](./Intermediate_Results/cdc_mask_Shelby.csv)
      * [mask_survey_Shelby.csv](./Intermediate_Results/mask_survey_Shelby.csv)
   * [Visualizations](./Visualizations)
      * [Daily_cases_change_rate.png](./Visualizations/Daily_cases_change_rate.png)
      * [Daily_covid_cases_change_rate.png](./Visualizations/Daily_covid_cases_change_rate.png)
      * [Density_plot.png](./Visualizations/Density_plot.png)
      * [Mask_mandates_yes_no.png](./Visualizations/Mask_mandates_yes_no.png)
      * [Total_Confirmed_cases.png](./Visualizations/Total_Confirmed_cases.png)
      * [change_point_detection.png](./Visualizations/change_point_detection.png)
      
** Final Visualization **
 Since the Shelby county data for Tennessee did not have face mandates data points in regards to date-series, we used the national CDC mask mandate timelines to analyze whether having the mask mandates had any impact on the trend of covid-19 cases that the county saw:

![Final Visualization](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/Project/Part1/Visualizations/Daily_cases_change_rate.png)

** Inference:**
In this final visualization where we have included arbitrary dates from the government, I clearly see no link between masks being made mandatory and the number of cases. Here we have time on the x-axis while the case-rate changes on the y-axis and we have included the new time dimension with respect to the  national CDC mask guidelines. As the timelines do not confirm/align with the case rate pattern, we can clearly say that for our given county, there isn’t a very direct relationship between mask guidelines and the number of confirmed cases. 


