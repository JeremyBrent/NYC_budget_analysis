# New York City Budget Analysis

## Motivation

Much controversy has fallen upon city budgets for their perceived excessive funding to police departments. As a data scientist, I strive to formulate opinions through the data. Therefore, I decided to dive into New York Cities Expense Budget for fiscal year 2021. I was inspired to see if the rhetoric about police spending in NYC was based in reality or political ideology. There have been recent claims that the NYPD had a budget of "almost $6 billion for the fiscal year of 2020" (<a href="https://www.cnn.com/2020/07/01/us/new-york-budget-nypd-1-billion-cut-trnd/index.html"> article link </a>). With that, the majority of the analysis will be framed around police spending.  I do want to note that as this can be a controversial topic, the findings of this analysis do not convey my political ideologies or beliefs in any capacity. 

## Dataset
New York Cities’ expense budget can be found <a href="https://data.cityofnewyork.us/City-Government/Expense-Budget/mwzb-yiwb"> here </a>.

## Questions
I targeted to answer three questions in my analysis: (1)How much and what percentage of the budget is appriopriated for each agency? (2) Are budget appropriations increasing or decreasing over time for specific agencies/projects (i.e. education, police, etc.)? and (3) Within agencies/projects, where is money being appropriated?

## Data cleaning and assumptions
In order for a seamless analysis, I used Python and Pandas to manipulate the dataset in a jupyter notebook. The dataset's column dictionary can be found <a href="./Data/Expense_budget_dictionary.xlsx"> here </a>. Columns such as the Budget Code, Object class and object code, agency name, etc. had both a descriptive column and a quantitative, codified column. For the analysis I deleted the codified column as it would be easier to interpret findings with descriptive names. 

The dataset also contained three columns that measured the size of the appropriation: (1) "Adopted Budgeted Amount", (2) "Financial Plan Amount" and (3) "Current Modified Budget Amount." After analyzing the similarities in the descriptive statistics for each column, I determined that an average for each record would be best for each analysis. The data manipulation can be found <a href='./eda.ipynb'> here </a>.

Fiscal Year columns contains some data errors. The unique values in the column are 1, 4, 60, 70, 2017, 2018, 2019, 2020, 2021. Intuitevely the values preceeding 2017 seem to be errors. I decided to remove these records for the analysis but it is curious that the same errors are repeated more then a couple of times.

## Analysis 
### Question 1: Where is NYC appropriating its fund?

<img src='./Images/budget_spending_by_project.png' alt="budget spending by project type">

The dataset denotes the "Project Type Name" by agency. For example, Education, Housing & Development, Correction, Parks, etc. are considered Project Types. For the rest of the analysis I will refer to the “Project Type Name” as project or agency interchangeably. Based on the aggregated "Total Budget Amount," the top five most funded agencies are: (1) Education: $112,630,941,060 / (2) Housing & Development: $38,876,057,247 / (3) Highway Bridges: $34,740,067,684 / (4) Water Pollution Control: $34,699,038,138 / and (5) Highways: $30,484,289,218. Corrections has the 6th highest funding amount at $25,285,190,537 and Police has the 16th highest funding amount at $7,649,723,283.

There has recently been calls for defunding police departments. Again, I by no means am expressing my political opinion about 'defunding the police department' but based on the findings from the dataset I analyzed, it seems as though the claims for the excessiveness of the NYPD budget – "in 2020 the NYPD budget was $6 billion" -- were politically motivated and rhetorical in nature, not necessarily citing data for the claims. That being said, navigating the NYC Office of Management and Budget is not the most user friendly experience; the complexities of the city’s budget makes it difficult to understand exactly what is being expressed; It is possible that the article cited in “Motivation” above are citing a different data source then the one I analyzed. 

### Question 2: Are budget appropriations increasing or decreasing over time for specific agencies/projects?

<img src='./Images/budget_spending_over_time.png' alt="budget spending over time for police, education, correction">

The screenshot above shows four different graphs of budget appropriations for Police, Education, and Correction for the 4 fiscal years. Mass incarceration and police brutality have spurred the conversation of police budgets to the national level. I chose to incorporate the budget over time for Corrections because of the association between policing and jailing.

At first glance, the image is deceiving. Take note that the y-axis uses a different scale for each graph. That is, "Police spending over time" has a max value on the y-axis of $3 billion while "Education spending over time" has a max y-axis value of $30 billion. Because of this, a change of $1 billion dollars will look more significant on the "Police spending over time" graph then the "Education spending over time" graph. 


We can see that the police budget decreases from $2,184,169,000 to $759,420,000 from fiscal year 3 to fiscal year 4. It seems as though the BLM movement has made headway in terms of "defunding the police." That said, correlation does not equal causation and as a scientist I am cautious to make claims about cause and effect relationships. The budget for corrections does not tell the same story. That is, from fiscal year 2 to fiscal year 3, the budget jumps from $3,474,121,600 to $9,049,473,821. While the budget for policing decreases by over 50% from year 3 to year 4, the budget for corrections increases by just under 300% from year 2 to year 3. 

### Question 3: Within agencies/projects, where is money being appropriated?
<img src='./Images/police_budget.png' alt="Total budget appropriated to the police department and categorized by ">

The graph above shows the budget line titles and the amount appropriated for said title within the NYPD. The largest budget line is for "improvements to police department property, citywide" for $3,348,850,922. 
The national conversation has frequently talked about increasing de-escalation and implicit bias training for police officers to combat police brutality. That said, it does not appear that there is any police training appropriated in the capital budget. This could mean that the NYC government does not budget for police training or police training is accounted for in another budget. Like I said before, navigating the NYC Office of Management and Budget is not a simple task. 

## Conclusion
The analysis of the capital budget has allowed me to generate some unique insights. It seems as though the claims that the 2020 budget for the NYPD was upwards of $6 billion are not true. The claim also misconstrues the fact that the police are the 16th highest funded agency/project in the capital budget in New York City. Based on the data analyzed, the police are appropriated about $7.5 billion over the next four years. In addition, it appears as though the budget will decrease over time which may be due to a whole host of unknown reasons including political pressure. While the police budget is set to decrease over the next four fiscal years, the corrections budget expands by almost 300% in one fiscal year. In terms of the geopolitical conversation on police brutality, mass incarceration and a healthier public infrastructure, redistributing appropriations to public needs is critical and expanding the corrections budget is moving in the wrong direction. 

We can see that the police budget decreases from $2,184,169,000 to $759,420,000 from fiscal year 3 to fiscal year 4. It seems as though the BLM movement has made headway in terms of "defunding the police." That said, correlation does not equal causation and as a scientist I am cautious to make claims about cause and effect relationships. The budget for corrections does not tell the same story. That is, from fiscal year 2 to fiscal year 3, the budget jumps from $3,474,121,600 to $9,049,473,821. So while the budget for policing decreases by over 50% from year 3 to year 4, the budget for corrections increases by just under 300% from year 2 to year 3. 
