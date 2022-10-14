## Homework- 2: Considering Bias in Data

#### Overview of the project:

The goal of this assignment is to explore the concept of bias in data by analyzing the Wikipedia articles on political figures from different countries. Ultimately, we assess how the coverage of politicians on Wikipedia and the quality of these articles varies among countries. To do so, we show a series of tables that show:
- The countries with the greatest and the least coverage of politicians of Wikipedia compared to their population.
- The countries with the highest and lowest proportion of high quality articles about politicians.
- A ranking of geographic regions by articles-per-person and proportion of high quality articles.


#### Python Packages Used
General Purpose: json, time, urllib.parse, requests
Data Manipulation: pandas

#### Repo Walkthrough:
# Project tree
/homework_2
   * [README.md](./README.md) 
   * [LICENSE](./LICENSE)
   * [src](./src)
      * [politicians_by_country_2022.csv](./src/politicians_by_country_2022.csv)
      * [population_by_country_2022.csv](./src/population_by_country_2022.csv)
   * [Codes](./Codes)
     * [data_processing.ipynb](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/homework_2/Code/data_processing.ipynb)
     * [Analysis (1).ipynb](https://github.com/JasmineBhalla17/Data-512-HCD/blob/main/homework_2/Code/Analysis%20(1).ipynb)
   * [Results](./Results)
      * [wp_countries-no_match.txt](./Results/wp_countries-no_match.txt)
      * [wp_politicians_by_country.csv](./wp_politicians_by_country.csv)
 

#### Overview of the Steps Involved:

**A. Data Acquisition and Processing:**
- For this project, we combine a dataset of Wikipedia articles (on politicians) with dataset of country's population and use a Machine Learning service called [ORES](https://www.mediawiki.org/wiki/ORES) to estimate the **quality score** of each article as per the article's quality classes (from best to worst) below:
  - FA:Featured article
  - GA: Good article
  - B: B-class article
  - C: C- class article
  - Start: Start-class article
  - Stub: Stub-class article

- We use the [API:Info](https://www.mediawiki.org/wiki/API:Info) request to get the article's most recent revisionID to make the label prediction using ORES. This gives us article quality scores for each article. Along with this, we also manipulate the populations.csv and finally merge these datasets together to contain article information, article quality scores and population data in the final dataset 'wp_politicians_by_country.csv' that is saved under [Results](https://github.com/JasmineBhalla17/Data-512-HCD/tree/main/homework_2/Results) folder.


**B. Analysis and Results:**

- The entire analysis is on a country-by-country and regional basis with per capita values.
- For analysis variables being calculated are total-articles-per-population (a ratio representing the number of articles per person) and high-quality-articles-per-population (a ratio representing the number of high quality articles per person) on a country-by-country and regional basis. All of these values are “per capita”.

**C. Results:**
Results are in tabular form in the python notebook found here: code/Analysis.ipynb

1. Top 10 countries by coverage
2. Bottom 10 countries by coverage
3. Top 10 countries by high quality
4. Bottom 10 countries by high quality
5. Geographic regions by total coverage
6. Geographic regions by high quality coverage
 
#### Reflection/Research Implications
This project has helped me with how to make API calls by the implementation of API calls such as the WIkimedia and ORES. I have also gained the much needed practical experience in terms of data processing, manipulation, analysis and drawing conclusions. This project has also helped me in easily identifying anything out of order that might exist in the dataset.

In Table 1, we see that the result is highly skewed towards countries that have very low population which makes total sense as it is per-capita. On the other hand, in table 2, it is interesting to note that some countries actually do have large populations, but most have very few articles. We observe these top 10 countries are poor. An interesting observation was that the final dataset did not contain United States of America neither the region Northern America. I also found out that the article list doesn't contain articles from nations of the likes of Canada, United Kingdom, Australia, and many other popular or bigger nations.

Because of the lack of information on many countries, especially the entire of Northern America, performing a realistic data science research where using this data (to train a model, perform a hypothesis-driven research, or make business decisions) might create biased or misleading results.

However, the metric High-quality-articles-per-population (a ratio representing the number of high quality articles per population) seems like a good measure to analyse the goodness of the articles per country/region. Higher the ratio, higher the quality of articles generated from that country. One would assume that non-native English speaking countries would have lower quality articles, but that is not always the case. Countries such as Andorra, Slovenia, Lithuania, and many more come under top 10 countries with High-quality-articles-per-population.

On the other hand, I also think that the calculation of the metric ratio of no of articles by the population of that country is not a good measure, as it brings in the bias of population that skew the result significanlty. For instance, countries like India and China has a very huge population so the coverage ratio will be very low for articles produced in these countries, and it might not be true. Similarly for smaller countries like Barbados and Bhutan, the coverage will be very high considering very small population size and non-english speaking country.


**Further Analysis Questions:**
What biases did you expect to find in the data (before you started working with it), and why? <br>
I had thought that developed countries would have the highest ratios in High-quality-articles-per-population. However, countries like Northern America was not even a part of the final dataset due to lack of its presence from the articles list.

What (potential) sources of bias did you discover in the course of your data processing and analysis? <br>
The number of articles from Southern, Eastern and Western Europe are 876, 725 and 697 respectively. The data shows bias in having high number of articles from politions of the former 3 regions. The Wikipedia articles show a particular high bias towards European regions.

Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might still be appropriate and useful, despite its inherent limitations and biases? <br>
As mentioned above, the metric High-quality-articles-per-population (a ratio representing the number of high quality articles per population) seems like a good measure to analyse the goodness of the articles per country/region.



