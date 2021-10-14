# Data 512 A2: Data Bias 

## Purpose of this project

The goal of this assignment is to explore the concept of bias through data on Wikipedia articles - specifically, articles on political figures from a variety of countries. THis project will combine a dataset of Wikipedia articles with a dataset of country populations, and use a machine learning service called ORES to estimate the quality of each article. In this project, I perform an analysis of how the coverage of politicians on Wikipedia and the quality of articles about politicians varies between countries. The analyses consists of:

    1. The countries with the greatest and least coverage of politicians on Wikipedia compared to their population.
    2. The countries with the highest and lowest proportion of high quality articles about politicians.
    3. A ranking of geographic regions by articles-per-person and proportion of high quality articles.


## Data Source and Used API

Data used:
The Wikipedia politicians by country dataset can be found on Figshare: https://figshare.com/articles/Untitled_Item/5513449, which is licensed under CC-BY-SA 4.0. For this project, I only used the "page_data.csv" file which is contained in the original dataset. 
The population data is available in https://docs.google.com/spreadsheets/d/1CFJO2zna2No5KqNm9rPK5PCACoXKzb-nycJFhV689Iw/edit#gid=283125346, which is extractd from the world population datasheet published by the Population Reference Bureau: https://www.prb.org/international/indicator/population/table/. The Population data is copyrighted by the Population Reference Bureau (PRB)

API used: 
This project uses the machine learning system Objective Revision Evaluation Service (ORES) API, which is licensed under CC-BY-SA 3.0 to generate the article scores and predict article quality estimates. Documentation for this API can be found at: https://www.mediawiki.org/wiki/ORES. This API returns one of the following ratings for each article ,from best to worst:

    FA: Featured article 
    GA: Good article 
    B: B-class article 
    C: C-class article 
    Start: Start-class article 
    Stub: Stub-class article 

## Descriptions of Data Files

Original Data Files: 
    WPDS_2018_data.csv: csv file containing world population data
    page_data.csv: csv file containing Wikipedia politician articles
    
Generated Data Files:
    error_log.csv: csv file containing a log of articles for which I was not able to retrieve an ORES score
    wp_wpds_countries-no_match.csv: csv file containing rows that do not have matching data when merging world population data and page data
    wp_wpds_politicians_by_country.csv: csv file containing final merged data with article scores from ORES API and world population data

## Results

The results embeded in the notebook consists of six tables as follows:

    1. Top 10 countries by coverage: 10 highest-ranked countries in terms of number of politician articles as a proportion of country population
    2. Bottom 10 countries by coverage: 10 lowest-ranked countries in terms of number of politician articles as a proportion of country population
    3. Top 10 countries by relative quality: 10 highest-ranked countries in terms of the relative proportion of politician articles that are of GA and FA-quality
    4. Bottom 10 countries by relative quality: 10 lowest-ranked countries in terms of the relative proportion of politician articles that are of GA and FA-quality
    5. Geographic regions by coverage: Ranking of geographic regions (in descending order) in terms of the total count of politician articles from countries in each region as a      proportion of total regional population
    6. Geographic regions by coverage: Ranking of geographic regions (in descending order) in terms of the relative proportion of politician articles from countries in each region that are of GA and FA-quality

    
## Reflections 

1. What biases did you expect to find in the data (before you started working with it), and why?


Before I started this project, I recognized several biases that might exist in this project. Firstly, education level across countries are differnet. Some countries may have a large population but an eduaction level under average. Second, when ranking the article qualities of each countries, we also need to consider how people in these countries can get access to the internet and Wikipedia. This is becuase some countries may have low access rate to the internet and people in some countries do not use wikipedia. 

2. What (potential) sources of bias did you discover in the course of your data processing and analysis?

Most countries in the list of 10 highest-ranked countries in terms of number of politician articles as a proportion of country population are English-speaking countries with small poopulation. In this project, we should also consider if the targeted countries are English-speaking countries becuase it seems to be a significant feature that affects the final results. 

3. How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?

As I mentioned above, a researcher should consider internet-access, wikipedia-access, and the native language of countries. Thus, joining this dataset with other world indicators could be helpful to  aviod biases. 

One thing that surprises me mostly is that North Korea has the most high quality politican article percentage but low total article percentage. I assume this phoenomenon could be a reflectoin of governance of NOrth Korea. In addition, I realize that Oceania is the reagion with highest total article percentage. I think this is because most countries from Oceanis speak English and have small populations, such as Tuvalu, the top 1 highest-ranked country in terms of number of politician articles as a proportion of country population. 

