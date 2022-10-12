## Homework- 2: Considering Bias in Data

#### Goals of the project:

The goal of this assignment is to explore the concept of bias in data by analyzing the Wikipedia articles on political figures from different countries. Ultimately, we assess how the coverage of politicians on Wikipedia and the quality of these articles varies among countries. To do so, we show a series of tables that show:
- The countries with the greatest and the least coverage of politicians of Wikipedia compared to their population.
- The countries with the highest and lowest proportion of high quality articles about politicians.
- A ranking of geographic regions by articles-per-person and proportion of high quality articles.


#### Overview of the Analysis Performed:

**A. Data Acquisition and Processing:**
- For this project, we combine a dataset of Wikipedia articles (on politicians) with dataset of country's population and use a Machine Learning service called [ORES](https://www.mediawiki.org/wiki/ORES) to estimate the **quality score** of each article as per the article's quality classes (from best to worst) below:
  - FA- Featured article
  - GA- Good article
  - B - B-class article
  - C - C- class article
  - Start- Start-class article
  - Stub- Stub-class article

2- We use the [API:Info](https://www.mediawiki.org/wiki/API:Info) request to get the article's most recent revisionID to make the label prediction using ORES.

- A final dataset 'wp_politicians_by_country.csv' is outputted with the following schema:

**Insert image here**


**B. Analysis*:**

- The entire analysis is on a country-by-country and regional basis with per capita values.


**C. Results:**

  










#### Reflection




