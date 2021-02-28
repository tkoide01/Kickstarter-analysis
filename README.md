# An Analysis of Kickstarter Campaigns
Performing analysis on Kickstarter data to uncover trends

# Kickstarting with Excel

## Overview of Project

### Purpose: Based on the Kickstarter dataset provided, analyze the trend of the campaigns’ result based on their launch dates and their funding goals.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

### Analysis of Outcomes Based on Goals

### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
  
  Based on the line chart outputted from the analysis, we can draw two conclusions in regard to the outcomes of Theatre campaigns based on their launch dates;
 
   ![Chart1]() “Theatre Outcomes vs Launch”
  1.	The month of May and June are the successful month for Theatre campaigns to launch. Thus one should plan to launch campaigns during these two months to aim for successful result. 
  2.	On the other hand, the number of failed theatre campaigns are consistent throughout the year from 30 to 50 cases. Thus analyzing the trend of failing theatre campaigns may require variables other than launch dates.

- What can you conclude about the Outcomes based on Goals?
  
  Based on the line chart outputted from the analysis, we can reach to the below conclusion in regards to outcomes based on goals;
   + The most successful campaigns are the ones with goal “less than 1000” with the success rate of 76%. The success rate of the campaign declines as the campaign goal dollar amount increases with exception of campaigns that fall on “30000 to 39999” and “40000 to 44999” that resulted success rate of 67%. Therefore, it is less risky to keep your campaign goal to below $1,5000 as the Percentage Failed outnumbers the Percentage Successful from this point as shown on the below line chart.

  ![Chart2]() “Outcomes Based on Goal”

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
    
    Note that Analysis of Outcomes Based on Goals **did not filter the campaigns based on the currency of funding goals**. This may cause some inaccuracy to the plotting of each data point as Y-axis is separating by dollar-based goal value. For examples GDP and NZD are different from USD by more than **30%** of its value. As below line chart shows, the most successful Dollar-based goal is the _“35000 to 3999”_ hitting 80%. 
  
  ![Chart3]() “Outcomes vs Goal with USD filtering”
  
  This result is different from the chart generated without filtering the dataset with USD, which mentioned earlier in the analysis.
