# UTSABootCampWeek1Challenge
Excel Kickstarter Challenge
Contains an Excel workbook conforming to these instructions:
## Instructions

![Crowdfunding Table]

Using the Excel [workbook] provided, modify and analyze the data of 1,000 example projects in an attempt to uncover market trends. 

* Dataset created by Trilogy Education Services, LLC.


* Use conditional formatting to fill each cell in the `outcome` column with a different color, depending on whether the associated campaign was successful, failed, canceled, or is currently live.
/* done: Successful is green, failed is red, canceled is orange, live is grey*/

  * Create a new column called `Percent Funded` that uses a formula to uncover how much money a campaign made relative to its initial goal.
/* done: Col O contains the percent funded*/

* Use conditional formatting to fill each cell in the `Percent Funded` column according to a three-color scale. The scale should start at 0 and be a dark shade of red, transitioning to green at 100, and blue at 200.
/* ? done: conditional formatting-->3-color scale-->first option=Number=0, second=number=1, third=number=2 ?*/

  * Create a new column called `Average Donation` that uses a formula to uncover how much each project backer paid on average.
/* done: col P formula E/G to get average each person donated*/

  * Create two new columns, one called `Parent Category` and another called `Sub-Category`, that use formulas to split the `Category and Sub-Category` column into the two new, separate columns.
/* done: Col Q formula =LEFT(N2,FIND("/",N2)-1) and Col R formula =MID(N2,FIND("/",N2)+1,256)*/

  ![Category Stats]
  * Create a new sheet with a pivot table that will analyze your initial worksheet to count how many campaigns were successful, failed, canceled, or are currently live per **category**.

  * Create a stacked column pivot chart that can be filtered by country based on the table you have created.
/* done 
Pivot table creation: insert-->pivot table-->new worksheet-->filters=country,columns=outcome,rows=parent category, values=count of outcome
Stacked Pivot Chart: Click inside pivot table-->PivotTableAnalyze ribbon-->PivotChart-->stacked Chart-->click each series and change color in attempt to match .png accompanying
*/
  ![Subcategory Stats]

  * Create a new sheet with a pivot table that will analyze your initial sheet to count how many campaigns were successful, failed, or canceled, or are currently live per **sub-category**.

  * Create a stacked column pivot chart that can be filtered by country and parent-category based on the table you have created.
/* done 
Pivot table creation: insert-->pivot table-->new worksheet-->filters=country, Parent Category,columns=outcome,rows=Sub-Category, values=count of outcome
Stacked Pivot Chart: Click inside pivot table-->PivotTableAnalyze ribbon-->PivotChart-->stacked Chart-->click each series and change color in attempt to match .png accompanying
*/

* The dates stored within the `deadline` and `launched_at` columns use Unix timestamps. Fortunately for us, [there is a formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) that can be used to convert these timestamps to a normal date.

  * Create a new column named `Date Created Conversion` that will use [this formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) to convert the data contained within `launched_at` into Excel's date format.

  * Create a new column named `Date Ended Conversion` that will use [this formula](https://www.extendoffice.com/documents/excel/2473-excel-timestamp-to-date.html) to convert the data contained within `deadline` into Excel's date format.
/*
done: col S and T formulas 
=(((J2/60)/60)/24)+DATE(1970,1,1)
=(((K2/60)/60)/24)+DATE(1970,1,1)
*/
  ![Outcomes Based on Launch Date]

  * Create a new sheet with a pivot table with a column of `state`, rows of `Date Created Conversion`, values based on the count of `state`, and filters based on `parent category` and `Years`.

  * Now create a pivot chart line graph that visualizes this new table.
/*
done follow previous steps to create pivot and chart, look at provided png for details, click the dots on the line, right click, format data series, fill, marker, solid line, color, change color
*/ 
* Create a report in Microsoft Word and answer the following questions.

1. Given the provided data, what are three conclusions we can draw about crowdfunding campaigns?
Only about half are successful
Theater/Plays are more often successful than the other categories
The month of September appears to be the least likely to succeed month

2. What are some limitations of this dataset?
limited to 7 countries
Jan 2020 most recent
limited to 9 parent categories

3. What are some other possible tables and/or graphs that we could create, and what additional value would they provide?
graphs on fail and success by staff picks--additional value--does staff-pick increase success?
graphs on fail and success by spotlight--additional value--does spotlighting help increase success?
/* 
done: see "Kickstarter Challenge Week 1.docx" for report
*/

## Bonus

* Create a new sheet with 8 columns:

  * `Goal`
  * `Number Successful`
  * `Number Failed`
  * `Number Canceled`
  * `Total Projects`
  * `Percentage Successful`
  * `Percentage Failed`
  * `Percentage Canceled`

* In the `Goal` column, create 12 rows with the following headers:

  * Less than 1000
  * 1000 to 4999
  * 5000 to 9999
  * 10000 to 14999
  * 15000 to 19999
  * 20000 to 24999
  * 25000 to 29999
  * 30000 to 34999
  * 35000 to 39999
  * 40000 to 44999
  * 45000 to 49999
  * Greater than or equal to 50000

  ![Goal Outcomes]
/*
done- see formulas used section of github readme
*/
* Using the `COUNTIFS()` formula, count how many successful, failed, and canceled projects were created with goals within the ranges listed above. Populate the `Number Successful`, `Number Failed`, and `Number Canceled` columns with this data.

* Add up each of the values in the `Number Successful`, `Number Failed`, and `Number Canceled` columns to populate the `Total Projects` column. Then, using a mathematical formula, find the percentage of projects that were successful, failed, or canceled per goal range.
/*
done
*/
* Create a line chart that graphs the relationship between a goal amount and its chances of success, failure, or cancellation.
/*done*/
## Bonus Statistical Analysis

Most people would use the number of campaign backers to assess the success of a crowdfunding campaign. Creating a summary statistics table is one of the most efficient ways that data scientists can characterize quantitative metrics, such as the number of campaign backers.

For those of you looking for an additional challenge, evaluate the number of backers of successful and unsuccessful campaigns by creating **your own** summary statistics table.

* Create a new worksheet in your workbook, and create one column for the number of backers of successful campaigns and one column for unsuccessful campaigns.

  ![Images/backers01.png]

* Use Excel to evaluate the following for successful campaigns, and then do the same for unsuccessful campaigns:

  * The mean number of backers

  * The median number of backers

  * The minimum number of backers

  * The maximum number of backers

  * The variance of the number of backers

  * The standard deviation of the number of backers
  /*
  done
  */

* Use your data to determine whether the mean or the median summarizes the data more meaningfully.
Median summarizes more meaningfully
* Use your data to determine if there is more variability with successful or unsuccessful campaigns. Does this make sense? Why or why not?
/*
done
see Kickstarter Challenge Week 1.docx for report
*/
