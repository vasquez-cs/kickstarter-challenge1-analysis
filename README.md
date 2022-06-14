# Kickstarting with Excel

## Analyzing Kickstarter's data for Theater Launch Dates and Plays Funding Goals

### Louise’s play "Fever" came close to its fundraising goal in a short amount of time. Based on this experience, she wants to know how theater Kickstarter campaigns fared based on their launch dates, and how Kickstarter campaigns for plays fared based on their funding goals. To investigate this, analysis and visualizations were created to highlight the campaign outcomes based on their launch dates and their funding goals.

## Analysis and Challenges

### Analysis of Theater Outcomes Based on Launch Date

To best visualize the impact that the launch date had on the success of a theater Kickstarter, it was decided to create a pivot table and a corresponding line graph to visualize the relationship between outcomes and launch month. The pivot table showcased this relationship by tabulating the counts of each theater campaign outcome by their launch month. The line chart visually demonstrates the relationship through the rise and fall of each campaign outcome with a charted line through plotted data points representing total counts for each month.

<img src="https://user-images.githubusercontent.com/107224632/173497553-1c46e376-c3cf-4528-97f9-20b77585c9da.png" width=85% height=85%><br />
*Figure 1: Example of YEAR() function*

Before creating the visualizations, the Kickstarter datasheet was prepped to analyze the theater launch dates easier to group in the pivot table. As shown in Figure 1, the excel "YEAR()" function was utilized to fill a newly created column within the Kickstarter datasheet named "Years". The function isolated the year from the "Date Created Conversion" column representing the campaign launch date.

<img src="https://user-images.githubusercontent.com/107224632/173489232-1536249d-bbd2-485b-9d37-f4b60420ea2c.png" width=35% height=35%><br />
*Figure 2: Pivot Table*

Using this new "Years" column, a pivot table was created as shown in Figure 2. The pivot table was chosen to summarize the Kickstarter "Outcomes" counts for each campaign launch month. This was achieved by selecting three campaign "Outcomes" values for the pivot table columns: 'successful', 'failed', and 'canceled'. The rows of the pivot table had the 12 months selected from the theater Kickstarters "Years" column. The pivot table is filterable by the "Parent Category" and "Years" of campaign launches, however, is defaulted to "theater" and includes all available launch years. Once formatted, a line graph was created using the pivot table data to showcase the trends of each campaign outcome during different launch months as shown in Figure 3. This was achieved by making the x-axis the launch month and y access the number of campaigns. Three different colored lines, each representing a different campaign outcome value are present. Each line connects data points arranged by their total count at each month of launch.

<img src="https://user-images.githubusercontent.com/107224632/173492288-c83a5597-afbe-4051-9f32-1cec0c6db2b1.png" width=50% height=50%><br />
*Figure 3: "Theater Outcomes by Launch Date" Line Chart*

### Challenges and Difficulties Encountered

No real difficulties were encountered during this analysis, however, there are potential pitfalls that could affect the results. An excel function is needed to prep the Kickstarted dataset and populate a new column based on existing data. Incorrect use of this function or data it references could negatively impact the end line chart or pivot table. It is important to know the purpose of the excel function and correctly apply it to prevent getting a function error or creating junk data when selecting the column to reference.

In addition to potential pitfalls during the data prepping stage, selecting the correct data for the pivot table is critical, as is selecting the appropriate x and y-axis for the line chart. Having an understanding of the Kickstarter data set and the purpose of the analysis is crucial to avoiding these pitfalls in selecting the appropriate data for pivot tables or charts. This ensures that the final visualizations correctly demonstrate the relationship between outcomes and launch month.

### Analysis of Plays Outcomes Based on Goals

A second relationship was explored by showcasing the impact funding goals had on the Kickstarter outcomes for the subcategory "plays". This correlation was investigated by making heavy use of the excel COUNTIFS() function to create a new dataset "Outcomes Based on Goals". The dataset consists of campaign funding goals and the associated counts for each Kickstarter campaign outcome. The final visualization charts the relationship into a line chart.

<img src="https://user-images.githubusercontent.com/107224632/173492873-fae65609-2fb6-468c-a783-684574d45587.png" width=80% height=80%><br />
*Figure 4: "Outcomes Based on Goals" data table*

Before creating the line chart, the Kickstarter data was used to create the "Outcomes Based on Goals" data table shown in Figure 4. Column 'A', had its values created based on the Kickstarter "Goals" data. Data was separated into 12 tiers of funding starting with the first level that grouped campaign goals that were less than a 1,000 until the 12th tier which represents goal funding of "50000 or more" per campaign. Columns B, C, and D each contain the total counts at each funding tier for campaign outcomes: successful, failed, and canceled. The total count of campaigns per tier is captured in the "Total Projects" column. The three last columns display each Kickstarter outcome as a percentage.

<img src="https://user-images.githubusercontent.com/107224632/173507587-bc39b45d-e8aa-4905-8bb7-3ccc672336d9.png" width=80% height=80%><br />
*Figure 5: Example of COUNTIFS() function*

The table was filled using excel functions. Columns for the count of successful, failed, and canceled funding tiers had their values derived using the excel COUNTIFS() function. This function referenced the original Kickstarter data and used various criteria to pull the correct count for each column row. An example of the criteria used to produce the value in cell B13 is shown in Figure 5. The function counts campaigns that are "successful", with the subcategory "plays", and with a funding goal greater than or equal to 50,000. The function was altered slightly at each row to account for each of the 12 funding tiers and campaign outcome for columns B, C, and D. 

<img src="https://user-images.githubusercontent.com/107224632/173504864-ea7eaa2c-001d-493b-bc17-ca23e7e288f3.png" width=80% height=80%><br />
*Figure 6: Example of SUM() function*

The "Total Projects" column was populated by using the SUM() function to total columns B, C, and D at each funding tier as shown in Figure 6.

<img src="https://user-images.githubusercontent.com/107224632/173505339-1ea9580d-48dd-4193-badc-ee443613cec2.png" width=80% height=80%><br />
*Figure 7: Example of division formula nested within a ROUND() function*

Columns F, G, and H were populated by nesting a simple division formula within a ROUND() function. The division formula references the outcome count and divides it by the total number of projects, both only using the counts on the corresponding funding tier. The ROUND() formula was used to ensure that the resulting division value was rounded to two decimal places to produce a whole percentage. Finally, the three percentage columns were formatted to the percentage type with 0 decimal places. This formatting transformed the nested division result into a whole number with a percentage symbol.

A line chart named "Outcomes Based on Goal" was created to visually chart the newly created dataset. The goal-amount tiers were placed on the x-axis and the percentage of successful, failed, or canceled projects on the y-axis. The relationship between the two axes is demonstrated by three different colored lines, each representing a different campaign outcome as shown in Figure 8.

<img src="https://user-images.githubusercontent.com/107224632/173492496-61c87e8d-6458-4078-a20b-f8868b404889.png" width=80% height=80%><br />
*Figure 8: "Outcomes Based on Goal" Line Chart*

### Challenges and Difficulties Encountered

There were a few challenges that had to be overcome to produce this analysis. Numerous excel functions were used to create the "Outcomes Based on Goals" dataset. The COUNTSIF() function proved tricky to navigate as each of the outcome columns and various "Goal" tiers required slightly different criteria to pull the correct data. While the overall structure of the function is the same within columns B:D, the criteria needed to be altered for each funding tier. An error identified was not incorporating an "equals to" symbol when inputting the funding values. For example, as shown in B13 of Figure 5, the function is only counting campaigns on the original Kickstarter data that have a "successful" outcome and are greater or equal to 50,000. Originally, the function for that cell was entered as ">50000", leaving out campaigns with a funding goal of 50,000. Once corrected, all COUNTIFS() functions were reviewed with a handful requiring revision. This error would have affected our analysis since crucial data would have been erroneously left out. These types of pitfalls are crucial to identify following the execution of an excel function by checking that the correct value was outputted to prevent errors in the final line chart.


## Results

- Based on our analysis of the "Outcomes Based on the Launch Date" data and the corresponding chart in Figure 3, we can conclude that the most successful theater Kickstarters have a launch date within the month of May. In addition, we can conclude that successful theater Kickstarters have a higher count than Kickstarters with failed or canceled outcomes across all months. The gap between the counts of successful and failed Kickstarter counts was the closest in the month of December where there was only a 2 campaign count difference with successful Kickstarters recording 37 campaign counts in comparison to failed campaigns tally of 35. 

- Based on our analysis of the "Outcomes Based on Goals" data table and corresponding line chart in Figure 8, we can identify the "Less than 1,000" Goal as being the most successful, slightly outperforming the "1,000 to 4,999" funding goal. 

- A few limitations of the Theater Outcome dataset is that it only contains data from 2009 to 2017. It would be interesting to see data from the early 2000s to see how the financial crisis of 2008 or the recent COVID pandemic of 2020 affected campaign success. A limitation of the outcomes based on goals is that we cannot evaluate the number of contributors each campaign had within each of the outcome columns. In addition, we don't know the average or mean donation each donor gave for each of the outcome columns.

- To overcome our current analysis limitations for the Theather outcomes dataset is to increase our sample size. Based on our current analysis, we can see that there is a clear trend among the outcomes and dates. Due to this, additional theater data from the early 2000s as well as recent data would strengthen our current analysis and allow us to expand on it since we would be able to view the impact of major historical events, such as the 2008 financial crisis or 2020 COVID pandemic. To address our limitation of the outcomes based on goals data, we could incorporate into our new "Outcomes Based on Goals" dataset the available "Average Donation" data within the Kickstarter datasheet. Incorporating the counts of this average for every "Goal" level would allow us to have a different perspective on how donations are spread within each goal tier.
