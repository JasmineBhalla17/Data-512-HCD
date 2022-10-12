# Professionalism and Reproducibility -- Wikipedia Pageviews Analysis

### Goal/Scope of the project:
The goal of this project is to analyze dinosaur article traffic from English Wikipedia from July 2015 through September 2022 while applying the ideas around 'reproducibility' and 'professionalism' in the field of Data Science as discussed in the assinged readings.

As this project falls under 'Data-512-HCD' repo that has been granted the Creative Commons (CC) licence, this project is open to public for further work and analysis.

### Overview:

1.  Data Acquisition 
  - The data has been collected from Pageviews API that provides access to desktop, mobile-web and mobile-app traffic data from July 2015 onwards. 
  - Here is more information on Pageviews API here: [documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews) and [endpoint](https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)
  - The data specifically is collected for a specific subset of dinosaur articles for three access-types: 1. desktop 2. Mobile (mobile-web + mobile-app) and 3. Cummulative (all access-types) with 'user' as the agent and is collected through July 2015 up to end of September 2022.
  - All of the resultant data sets from the API calls are time series of monthly activity with the specific dinosaur name as the key.
  - Three final JSON files are created by the end of the data processing.

2. Analysis
  - Analysis is done using the 3 JSON files created for the 3 specific access-types from above.
  - Analysis is done on the following:
      - **Maximum and Minimum average** of page requests/views of the article titles for desktop and mobile access types respectively.
      - **Top 10 Peak Page Views** for the top 10 article pages by largest page views over entire time by access type.
      - **Fewest Months of Data** showing the pages that have the fewest months of available data for desktop and mobile access types. 
      
### Repo Walkthrough:
# Project tree
/homework_1
   * [README.md](./README.md) 
   * [datafiles](./datafiles)
     * [dino_clean (1).csv](./datafiles/dino_clean%20(1).csv)
   * [Codes](./Codes)
     * [dataprocessing.ipynb](./Codes/dataprocessing.ipynb)
     * [Analysis.ipynb](./Codes/Analysis.ipynb)
   * [JSON_files](./JSON_files)
      * [dino_monthly_cumulative_201507-202209.json](./JSON_files/dino_monthly_cumulative_201507-202209.json)
      * [dino_monthly_desktop_201507-202209.json](./JSON_files/dino_monthly_desktop_201507-202209.json)
      * [dino_monthly_mobile_201507-202209.json](./JSON_files/dino_monthly_mobile_201507-202209.json)
   * [plots](./plots)
      * [Max_Min_Avg.png](./plots/Max_Min_Avg.png)
      * [Top10fewest_plot.png](./plots/Top10fewest_plot.png)
      * [Top_10_Peaks_Mobile_Desktop.png](./plots/Top_10_Peaks_Mobile_Desktop.png)
  




