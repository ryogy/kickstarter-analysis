# Kickstarting with Excel

## Overview of Project
The purpose of this analysis was to help Louise, who is currently running a fundraising campaign for a play, attain a broader understanding of how certain factors impact the success or failure of a Kickstarter campaign.  Specifically, Louise wants to know how the launch date and the fundraising goal effect overall campaign success. Using the data on hand, which consists of over 4,000 campaigns across different categories, the particular data values were isolated and then graphically represented to best show how the launch date and the goal can make or break fundraising campaign of a play.


## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
This analysis was conducted using the pivot table function in excel.  First, an additional colum was added in the parent spreadsheet that used the YEAR() function in order to isolate just the year from the "Date Created Conversion" column.  This was very simple as it only involved copying and pasting the first "Date Created Conversion" value and putting it inside the YEAR() function, then expanding it to the entire column.  After the new "Years" column had been added, the pivot table was created and placed in a new spreadsheet.  In the pivot table fields, the following values were chosen as shown in the image below.  This creates all the necessary colums and rows.
<img src="https://github.com/ryogy/kickstarter-analysis/blob/main/Screen%20Shot%202021-08-21%20at%2011.37.02%20AM.png" alt="Screen Shot 2021-08-21 at 11.37.02 AM" style="zoom:45%;" />
The pivot table was then filtered and sorted so that the only the relevant data was displayed in a particular order.  Finally, a line chart was created in order to give the table a more robust visual representation. 

### Analysis of Outcomes Based on Goals
For this analysis, the data was organized in order to determine the number of successful, failed, and cancelled kickstarter campaigns in the subcategory plays.  The data was arranged according to the fundraising goal, and a range was created in order to further organize the data.  The COUNTIFS() function was used in order to target specific fields in the parent spreadsheet.

Below are three lines of code that were used in order to calculate the 20,000 to 24,999 fundraising goal category.
##### Succesful 
=COUNTIFS(Kickstarter!R:R,"plays",Kickstarter!F:F,"successful",Kickstarter!D:D,">=20000",Kickstarter!D:D,"<=24999")
##### Failed 
=COUNTIFS(Kickstarter!R:R,"plays",Kickstarter!F:F,"failed",Kickstarter!D:D,">=20000",Kickstarter!D:D,"<=24999")
##### Canceled
=COUNTIFS(Kickstarter!R:R,"plays",Kickstarter!F:F,"canceled",Kickstarter!D:D,">=20000",Kickstarter!D:D,"<=24999")

All of these lines use data from the parent spreadsheet and use the COUNTIFS() function to pull relevant data from a particular column.  After this code had been entered to account for all the different goal ranges,  the SUM() function was used in order to add the three columns together.  These sums were then used to calculate the percentage of the campaigns that were successful, failed, and/or cancelled for each goal range.  The final step was to create a line graph that plotted the goal ranges VS the percentage of successful, failed, and canceled campaigns.


### Challenges and Difficulties Encountered
There were no challenges or difficulties that were encountered.  Seeing that so much of excel analysis is performed on a UI interface it seems difficult to run into problems.  The one problem that could be encountered is not entering all of the necessary fields into the functions, as it could miss important pieces of data that are relevant to the analysis.  The syntax could also be an issue because it is not forgiving at all and even missing a quotation mark would return an error.

## Results

### Outcomes Based on Launch Date Conclusions
The clear conclusion that can be made is that if you want to fundraise for a theater project the time to do it is in late spring or early summer.  Both May and June had over 100 successful outcomes over the 3 year span this data had been recorded.  This shows that there is a certain seasonality to fundraising especially for something within this category.  Summertime is the best time of year to go to the theater!  The other conclusion that can be made is that the number of failed campaigns remains stable throughout the year.  These failed campaigns could have unreasonably high goals or poor exposure, but it difficult to tell as the only filter is the months of the year. 

### Outcomes based on Goals Conclusion
The lower the goal the better the odds are of a particular campaign being successful.  The bulk of successful fundraising campaigns are all under $10,000 with the majority of the successfull campaigns falling between $1,000 and $5,000.  There are two successful campaigns that both had goals of over $50,000, but there is not enough information to conclude that this would be true for other campaigns if there goals were that high.

### Limitations
There are a couple limitations to the dataset, but the main one is that the length of time that the campaign was active could be a very useful metric in determining why a campaign was successful or unsuccessful.  The timeframe in which a company succeeded could also be used to make broader conclusions around donor interest.  At the moment, the dataset only allows us to make very distinct statistical conclusions, and with additional data there could be more discussion on the broader socialogical factors that impact these fundraising campaigns.

### Additional Tables or Graphs
There could be more graphs made that compare the outcomes from different categories.  Comparing and contrasting outcomes from a play or a technological product could give insight into something like the average donation cost.  Just looking at another industry category would help discern if the values from theater are normal or abnormal.  In terms of this particular project, a useful graph that could of been added was a histogram or bar graph.  It would of helped visualize the distribution skew better than that of a line graph.
