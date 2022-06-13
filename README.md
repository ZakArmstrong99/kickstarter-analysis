# Kickstarting with Excel

## Overview of Project

### Purpose

To summarize the reasoning of this project, Louise wanted to get a better idea of the relationship 
between different theater/play Kickstarter campaign launch dates and the campaign outcomes based on their goals.
The data used in the analysis consists of many different Kickstarter campaigns, 
including campaigns under the theater catergory. Using this anaylsis, Louis will better understand the performance
of her own play's Kickstarter campaign.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

My analysis began by creating a pivot table with the total amount of successful, failed, and canceled outcomes 
of kickstarter campaigns in relation to the dates they were launched. Using pivot table filters, I was able to 
filter this data by the parent catergory of theater. The filtered data was then used to make a pivot chart titled 
Theater Outcomes Based on Launch Date.

### Analysis of Outcomes Based on Goals

Next, I wanted to see how theater Kickstarter campaigns goals influenced their outcomes. This was done by making a new
table with including campaign goals, outcomes, and total projects in order to find the percentages of successful, failed,
and canceled projects. Finding the outcomes of play projects in relation to their set goals was possible with the
COUNTIFS() function. By spliting the goals up into intervals starting with  greater than 1000, then by $5000 up to $50000,
the countifs function was able to find the amount of the outcomes for these intervals while filtering by subcatergory "plays".
I also used the SUM() function in order to find the total projects, along with the IFERROR() function and ROUND() function for
the percentages. This data was then used to create the chart Outcomes Based on Goal.

### Challenges and Difficulties Encountered

The first challenge I encountered was that the data in launched_at and deadline columns were Unix tiemestamps and 
needed to be converted in order to get the month, day, and year for the Theater Outcomes Based on launch date to be possible. 
This was resolved by creating two new columns titled Date Created Conversion and Date Ended Conversion which included the
formula =(((J2/60)/60)/24)+DATE(1970,1,1). This formula converts Unix timestamps to readable timestamps making it possible
to create the Theater Outcomes by Launch Date chart. Other than that, there weren't any other challenges. A possible challenge
could be if one of the total projects on the Outcomes Based on Goals table were 0. This would lead to an error as there were 
no play Kickstarter campaigns canceled. This could be fixed with the with the IFERROR() function as it could turn all errors into 0s. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

When looking at the Outcomes based on Launch Date chart, it appears that the successful and failed campaigns follow a similar trend
throughout the year, even though there are more total successful outcomes than failures. From this we can conclude that the outcome 
of theater Kickstarter campaigns is related to the month the campaign was launched in, as the number of outcomes are almost proportional
for each month. Another conclusion is that creating theater Kickstarter campaign in the month of may has the highest success rate, 
while slowly decreasing every month until it picks back up after March. This could mean that launching a campaign in May gives a higher
chance of a successful outcome.

- What can you conclude about the Outcomes based on Goals?

When looking at the Outcomes Based on Goals chart, it appears percentage of successful campaigns and percentage of failed campaigns
follow the opposite trend. While percentage of successful campaigns are high, percentage of failed campaigns are low and vice versa.  
What is interesting is that the percentages of both outcomes meet at three spots on the chart, which could conclude that some goals
have equal chance of succeeding or failing. We also can conclude that the lower the goal of a play Kickstarter campaign, 
the more likely it is to succeed with the exception of goals in the range of 35000 to 39999 and 40000 to 44999. 
It is worth mentioning these excpetions as there are only 9 total projects in the range of 35000 to 44999, 
compared to the 1021 total projects under the goal of 34999. 

- What are some limitations of this dataset?

Some limitations include the fact that there aren't as many theater Kickstarter campaigns past the goal of 25000, which makes harder
to compare outcomes because there isn't as much data to go off of, relative to the amount of campaigns below that goal. Another
limitation is that the data doesn't include a reason as to why a campaign failed or not. If this was included, more conclusions 
could be drawn for the relationships of outcomes with launch date and goals.

- What are some other possible tables and/or graphs that we could create?

A possible table and graph that could be made could include whether a campaign was a Kickstarter staff pick or not relative to the outcome.
This would give insight as to how much influence the staff pick has. We also could make a table that shows the difference between how much 
theater campaigns pledged and it's goal relative to the outcome. This could give insight as how many Kickstarter supporters are backing plays 
they want to exist.
