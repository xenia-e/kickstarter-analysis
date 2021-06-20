# Kickstarting with Excel

## Overview of Project
This project is focused on determining whether there are specific factors that helped similar crowdfunding projects' success. Performing data analysis on several thousand crowdfunding projects to uncover any hidden trends and help to set target company to success.

### Purpose
The purpose of the project is to know how different campaigns fared in relation to their launch dates and their funding goals.

## Analysis and Challenges

Using the Kickstarter dataset I have analyzed and visualized results similar to Louise's campaign outcomes based on their launch dates and their funding goals. 

### Analysis of Outcomes Based on Launch Date
Performing analysis of outcomes based on the launch date helped us to determine the best date to launch our campaign. 
To do so, I created a pivot table filtered by Parent category and Year with Date created (launched) in the Rows section, Outcomes in columns section, and Outcomes in the Values section. 
To better visualize data I created Pivot Chart. I chose the 'Line with dots' chart type as I think it suits best to represent the correlation of the data. 
The results of the performed analysis are shown in the Figure 1 - Theater Outcomes by Launch Date

![Theater Outcomes by Launch Date] (https://github.com/xenia-e/kickstarter-analysis/blob/main/Theater_Outcomes_vs_Launch.png) chart.

### Analysis of Outcomes Based on Goals
Analysis of outcomes based on funding goals amount helped us to decide whether our goal is too bold to be funded.
To distinguish the most successful funding goal amounts I used the percentage of success of different goals. I divided all funding goals into 12 groups with a step of $5000.  Then using the `COUNTIFS` function I counted all successful, failed and canceled plays.  An example of the formula used to count all successful plays with a funding goal amount between $10000 and $14999 which is our target range is:

```
=COUNTIFS(Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,">=10000",Kickstarter!$D:$D,"<15000",Kickstarter!$F:$F,"successful")
```
Where 
-`COUNTIFS` is Excell function, 
- `Kickstarter!$R:$R,"plays"` -criteria 1 range and criteria 1, which means 'search for field with the text 'plays' in the column R on the sheet named 'Kickstarter'
- `Kickstarter!$D:$D,">=10000"` criteria 2 range and criteria 2: a field with a value more than or equal to 1000 in column D on the 'Kickstarter' sheet 
- `Kickstarter!$D:$D,"<15000"` criteria 3 range and criteria 3: a field with a value less than 15000 (that will include 14999, but not 15000) in column D on the 'Kickstarter' sheet 
- `Kickstarter!$F:$F,"successful"` criteria 4 range and criteria 4: a file with text value "successful" in column F on the "Kickstarter" sheet
If all 4 criteria meet then the field will be counted.
I used the simple SUM function to count all the plays used for the analysis. After that, I changed the data type in the columns "Percentage Successful", "Percentage Failed", and "Percentage Canceled" to `Percentage` and used formula  `=Number of plays/Total plays` (e.g. `=B2/E2`) to find the percentages.
I used a 2D line chart to visualize data. The results of the analysis presented in Figure 2 - Outcomes Based on Goal

  ![Outcomes Based on Goal] (https://github.com/xenia-e/kickstarter-analysis/blob/main/Outcomes_vs_Goals.png) chart.

### Challenges and Difficulties Encountered


## Results

- Looking at the ![Theater Outcomes by Launch Date] (https://github.com/xenia-e/kickstarter-analysis/blob/main/Theater_Outcomes_vs_Launch.png) chart I can say that the best months to launch the campaign are May or June, to narrow it down even more we can find the percentage of successful crowdfunding campaigns launched. We can narrow the period to May based on calculations. Still, the period from February to July has over 60% of successful campaigns. So two conclusions drawn from this analysis are:
The most favorable month to launch a campaign is May.
Louise should avoid launching her project in December as it has the lowest percentage of successful campaigns.

- Looking at ![Outcomes Based on Goal] (https://github.com/xenia-e/kickstarter-analysis/blob/main/Outcomes_vs_Goals.png) we can say that projects with the funding goal amount as Louise's don't always succeed. Still, in 54% of cases, they meet the funding goal, so Louise must look deeper into those that end up reaching the goal.

- In my opinion, one of the major limitations of the dataset is that we cannot identify the target audience for successful campaigns and types of plays that were more successful than others. Who are potential backers for Louise? Were drama plays more successful than comedies? Answers to that questions will surely benefit Louise. 

- I would suggest analyzing the length of the campaigns as an extra factor for success. 
