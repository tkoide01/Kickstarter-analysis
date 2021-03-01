# An Analysis of Kickstarter Campaigns
Performing analysis on Kickstarter data to uncover trends

# Kickstarting with Excel

## Overview of Project

### Purpose:   
   The purpose of this analysis is to review the results of campaigns created through Kickstarter to provide visualized data and drive conclusions of how some variables impacts campaign outcomes.
   As the client Louise is especially interested in the trend of theatre category campaigns, we will analyze how the outcomes of theatre campaigns raising fund above their goal change depend on their **Launch Date** and **Goal amount**.

## Analysis and Challenges
  
Before we begin to analyse the dataset based on Launch Date and Goals, we needed resolve challenges as dataset were utilizing Unix Timestamps rather than Readable Format and also displaying Category and Subcategory in the same column. The followings steps are taken in order to analyze data with readable Launch Date and filter based on the theatre category;
1. The Column J displays the launching timing of campaigns in Unix Timestamps format. In order to visualize the outcome based on readable Month unit, we added Column S with following function.

   `(S,i)=((((J,i)/60)/60)/24)+DATE(1970,1,1)`

   \*note that Ji and Si represent corresponding cells in J column and S column
  In addition, we utilized `=YEAR()` functions in Column U to enable filtering data by launched year.
  
2. As the Column P of the dataset displys both Category and Subcategory together, Text to Columns function in Data tab is utilized. The entries in Column P are split with "/" and added Column Q as Parent category and Column R as Sub Category.

### Analysis of Outcomes Based on Launch Date

Given the dataset can be filtered based on the Launch Date and Category, a pivot table and a line chart are utilized to visualize the correlation between the outcome of campaigns with their Launch Dates. Note that the outcomes are categorized in three states; successful, failed, and canceled. Successful campagin have raised fund above its goal and failed cmpaign have not. The followings steps were taken to visualize the date;

1. Insert Pivot Table in a new sheet "Theatre Outcomes by Launch Date."

2. The followings fields/variables are utilized for Filters, Columns, Rows, and Values as shown in below screen shot. This pivot table allows us to see the number of Successful, failed, and canceled campaigns by each month. 

   ![ScreenShot][1]

3. In addition, the pivot table filtered data to "theater" Category and removed the Column Label of "lived" to omit campaign without the result yet. Then sort function is utilized to display data in the order of months. Below is the Pivot table generated.

   ![Pivot Table]()"Theatre_Outcomes_vs_Launch_PivotTable"

4. Lastly, generate the line chart from the table using Pivot Chart function. The line chart "Theatre Outcomes Based on Launch Date" shows how "theatre" category campaigns' outcomes vary for each calender month as below image shows.

   ![Line_Chart1]()"Theatre_Outcomes_vs_Launch"

Now both the table and the line charts are available to draw analysis of how Launch Date impacts the outcomes.

### Analysis of Outcomes Based on Goals

Next, a new table is created on a separate sheet "Outcomes Based on Goals" in order to analyze the correlation bewteen goal of campaigns and their outcomes. Below steps are taken to create a table and generate another line chart;

1. On a new sheet, create a table with rows with certain range of goals. The Number of Successful, Number of Failed, Number of Canceled, Total Projects, Percentage Successful, Percentage Failed, and Percentage Failed are utilized as columns.
2. Then, input `COUNTIFS` functions as below to chart number of Successful, Failed and Canceled campaigns for each range of goals.

   `=COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"successful",Kickstarter!$R:$R,"plays")`

   \* Note that criteria for inequal sign values and "successful" varies based on the cell of the table

   The table will show result as below after plotting each cell value and then calculate each percentage by dividing with Total Projects value for each corresponding row. Below is the resulted table.

   ![Table1]()"Outcomes_vs_Goals_Table1"

3. Lastly, generate a line chart based on the created table to visualize the trend of campaigns' outcome based on the range of goal dollar-amount. Ensure to specify the Percentage of Success, Failed and Canceled for Y-axis. Below is the resulted line chart.

   ![Chart2]()"Outcomes_vs_Goals"
 

### Challenges and Difficulties Encountered
Throught the analysis taken above, the biggest obstacle was creating the Outcomes based on Goals table using `COUNTIFS` function. Since function needs to be modified by changing the inequal values criteria or the type of outcome criteria based on each column and row combination, it took time to carefully type each function. Utilizing $ sign to specify the columns of Kickstarter sheet did help, but the rest of change could not utilize a dragging function.

As countermeasures, utilizing conditional format based on the goal dollar amount then color filtering the original dataset could have been a quicker approach. We can also filter the dataset by outcome as well then copy and paste the resulted dataset for countring funtion. 

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
  
   Through conducting the analysis of both Outcomes based on Launch Date and Outcomes Based on Goals, I encountered several limitations in data available.
   + In the case of Outcomes based on Goals analysis, there are limited number of campaigns with its goal more than 1000. The sum of those campaigns is only 158 and equal to 15% of the total theatre projects recorded. Which means, while the percentage of success and fail is calculated with 85% of data for three segmentations (Less than 1000, 1000 to 4999, and 5000 to 9999), while only 15% of date is available to generate results of 9 different segmentations (1000 and above). In fact, the success rate for the campaign plotted under “45000 to 49999” is 0% because there is only one available data that failed. Since the dataset is limited with Theatre campaigns with goals higher than 1000, the current trend we see that success rate declines as campaign goal increases may easily change with more entry of data.

- What are some other possible tables and/or graphs that we could create?
    
    Note that Analysis of Outcomes Based on Goals **did not filter the campaigns based on the currency of funding goals**. This may cause some inaccuracy to the plotting of each data point as Y-axis is separating by dollar-based goal value. For examples GDP and NZD are different from USD by more than **30%** of its value. As below line chart shows, the most successful Dollar-based goal is the _“35000 to 3999”_ hitting 80%. 
  
  ![Chart3]() “Outcomes vs Goal with USD filtering”
  
  This result is different from the chart generated without filtering the dataset with USD, which mentioned earlier in the analysis.
  
  
  
[1]:
resources/PivotTable_Fields.png "PivotTable Fields"
