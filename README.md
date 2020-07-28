# New York City Budget Analysis

## Motivation

Much controversery has fallen upon city budgets for their perceived excessive funding to police departments. As a data scientist, I strive to formulate opinions through the  data. Therefore, I decided to dive into the data. I was inspired to see if the rhetoric about police spending in NYC was based in reality or political ideology. With that, the majority of the analysis will be framed around police spending.  I do want to note that as this can be a controversial topic, the findings of this analysis do not convey my political ideologies or beliefs in any capacity. 

## Data and questions
New York Cities capital budget can be found <a href="https://data.cityofnewyork.us/City-Government/Capital-Budget/46m8-77gv"> here </a>. I strived to answer a handfull of questions: (1) Where is NYC appropriating its fund? (2) Are budget appropriations increasing or decreasing over time for specific agencies(i.e. education, police, etc.)? and (3) What specific project is money being appropriated to in different departments?

## Assumptions
The data set has a column called "First Fiscal Year" that denotes when the specific project will begin recieiving funding. Funding started/starts for 33.86% projects in 2019, 33.17% in 2020 and 32.96% in 2021 (found <a href= "./eda.ipynb"> here </a>).  The following columns are "Fiscal Year 1 Amount," "Fiscal Year 2 Amount," and so on until "Fiscal Year 4 Amount." In order to aggregate the data, I created a "Total Budget Amount" column that reflects the sum of the four fiscal year amounts without regard to the "first fiscal year.'  

## Analysis 
### Question 1: Where is NYC appropriating its fund?
The dataset denotes the "Project Type Name" by agency. For example, Education, Housing & Development, Correction, Parks, etc. are considered Project Types. Based on the aggregated "Total Budget Amount," the top five most funded agencies or projects are: (1) Education: $112,630,941,060 / (2) Housing & Development: $38,876,057,247 / (3) Highway Bridges: $34,740,067,684 / (4) Water Pollution Control: $34,699,038,138 / and (5) Highways: $30,484,289,218. Corrections has the 6th highest funding amount at $25,285,190,537 and Police has the 16th higest funding amount at $7,649,723,283.

<img src="./Images/Total_budget_spending.mov" alt='total budget spending by project/department'> 

There has recently been calls for defunding the police department; that the NYPD had a budget of "almost 6 billion for the fiscal year of 2020" (<a href='https://www.cnn.com/2020/07/01/us/new-york-budget-nypd-1-billion-cut-trnd/index.html"> article link </a>). Again, I by no means am expressing my political opinion about 'defunding the police department' but based on the findings from the dataset I analyzed, it seems as though the cries for the excessiveness of NYPD were politically motivated and rhetorical in nature, not neccesarily citing data for the claims. That being said, navigating the NYC Office of Management and Budget is not the most user friendly experience; the complexities of the cities budget makes it difficult to understand exactly what is being expressed. With that said, it is possible that the article cited above and the many more are citing a different data source. 
