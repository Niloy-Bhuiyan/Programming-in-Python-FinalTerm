# Seoul Bike Sharing Demand Data Analysis Project

## Project Title

**How Weather, Time, and Holidays Affect Public Bike Rental Demand in Seoul**

## Student Information

<table>
<tr>
<td><b>Student Name</b></td>
<td>Nurul Azam Bhuiyan</td>
</tr>
<tr>
<td><b>Student ID</b></td>
<td>23 50020 1</td>
</tr>
<tr>
<td><b>Course</b></td>
<td>Programming in Python</td>
</tr>
<tr>
<td><b>Section</b></td>
<td>C</td>
</tr>
<tr>
<td><b>Semester</b></td>
<td>Spring 2026</td>
</tr>
<tr>
<td><b>Course Instructor</b></td>
<td>MD. TANZEEM RAHAT</td>
</tr>
<tr>
<td><b>Project Type</b></td>
<td>Final Term Data Analysis Project</td>
</tr>
</table>

## Project Overview

This project is a complete data analysis investigation using **Pandas**, **NumPy**, and **Matplotlib**.

The main goal of this project is to understand how public bike rental demand changes based on time, season, weather, holiday status, and service availability in Seoul. The project follows a full data analysis workflow: dataset understanding, data cleaning, feature engineering, subgroup comparison, relationship analysis, outlier detection, visualization, findings, limitations, and conclusion.

Bike sharing systems are important for modern city transportation. They help people travel short distances, reduce pressure on public transport, and support cleaner urban mobility. However, bike sharing operators need to understand when demand becomes high and when demand becomes low. This project uses real data to explain those demand patterns.

## Dataset Information

<table>
<tr>
<td><b>Dataset Name</b></td>
<td>Seoul Bike Sharing Demand</td>
</tr>
<tr>
<td><b>Dataset Source</b></td>
<td>UCI Machine Learning Repository</td>
</tr>
<tr>
<td><b>Dataset Link</b></td>
<td>https://archive.ics.uci.edu/dataset/560/seoul+bike+sharing+demand</td>
</tr>
<tr>
<td><b>Original Rows</b></td>
<td>8,760</td>
</tr>
<tr>
<td><b>Original Columns</b></td>
<td>14</td>
</tr>
<tr>
<td><b>Main Analysis Rows</b></td>
<td>8,465 service open records</td>
</tr>
<tr>
<td><b>Key Variable</b></td>
<td>Rented Bike Count</td>
</tr>
<tr>
<td><b>Data Types</b></td>
<td>Numerical, categorical, and date time data</td>
</tr>
</table>

## Dataset Columns

<table>
<tr>
<td><b>Category</b></td>
<td><b>Columns</b></td>
</tr>
<tr>
<td>Time Information</td>
<td>Date, Hour</td>
</tr>
<tr>
<td>Demand Information</td>
<td>Rented Bike Count</td>
</tr>
<tr>
<td>Weather Information</td>
<td>Temperature, Humidity, Wind Speed, Visibility, Dew Point Temperature, Solar Radiation, Rainfall, Snowfall</td>
</tr>
<tr>
<td>Calendar Information</td>
<td>Season, Holiday</td>
</tr>
<tr>
<td>Service Information</td>
<td>Functioning Day</td>
</tr>
</table>

## Research Questions

1. Which time related factors, such as hour, month, season, and weekend status, have the highest bike rental demand?

2. How do weather factors such as temperature, humidity, rainfall, snowfall, and solar radiation relate to bike rental demand?

3. Are there unusual high demand or low demand hours, and what do those patterns tell us?

## Tools and Libraries Used

<table>
<tr>
<td><b>Tool</b></td>
<td><b>Purpose</b></td>
</tr>
<tr>
<td>Python</td>
<td>Main programming language</td>
</tr>
<tr>
<td>Pandas</td>
<td>Data loading, cleaning, filtering, grouping, aggregation, and summary tables</td>
</tr>
<tr>
<td>NumPy</td>
<td>Percentiles, mean, standard deviation, z score, IQR, and custom numerical calculations</td>
</tr>
<tr>
<td>Matplotlib</td>
<td>Data visualization</td>
</tr>
<tr>
<td>Google Colab</td>
<td>Notebook environment</td>
</tr>
<tr>
<td>GitHub</td>
<td>Project submission and version sharing</td>
</tr>
</table>

## Project Workflow

1. Import required libraries
2. Load the dataset directly from UCI
3. Inspect dataset shape, columns, data types, sample rows, summary statistics, missing values, and duplicate rows
4. Clean and prepare the dataset
5. Create new engineered features
6. Perform grouped analysis and subgroup comparison
7. Analyze relationships between weather variables and rental demand
8. Detect unusual high demand records using NumPy z score and IQR
9. Create meaningful Matplotlib charts
10. Summarize evidence based findings
11. Discuss limitations
12. Write final conclusion

## Data Cleaning Steps

<table>
<tr>
<td><b>Issue Found</b></td>
<td><b>Action Taken</b></td>
<td><b>Reason</b></td>
</tr>
<tr>
<td>Column names had spaces and special symbols</td>
<td>Renamed columns into simple camelCase names</td>
<td>Made the code easier to write, read, and explain</td>
</tr>
<tr>
<td>Possible duplicate rows</td>
<td>Checked and removed exact duplicates</td>
<td>Prevented counting the same hourly record more than once</td>
</tr>
<tr>
<td>Date column was stored as text</td>
<td>Converted date using pd.to_datetime</td>
<td>Needed for month, day, and weekend features</td>
</tr>
<tr>
<td>Numerical columns needed correct format</td>
<td>Converted using pd.to_numeric</td>
<td>Needed for statistics, grouping, and visualizations</td>
</tr>
<tr>
<td>Text categories could be inconsistent</td>
<td>Standardized season, holiday, and functioningDay values</td>
<td>Prevented incorrect group results</td>
</tr>
<tr>
<td>Service closed rows had zero rentals</td>
<td>Separated service open and service closed records</td>
<td>Closed service zeros do not represent natural customer demand</td>
</tr>
</table>

## Feature Engineering

<table>
<tr>
<td><b>New Feature</b></td>
<td><b>How It Was Created</b></td>
<td><b>Why It Is Useful</b></td>
</tr>
<tr>
<td>year</td>
<td>Extracted from date</td>
<td>Supports date based understanding</td>
</tr>
<tr>
<td>monthNumber</td>
<td>Extracted from date</td>
<td>Keeps months in correct order</td>
</tr>
<tr>
<td>monthName</td>
<td>Extracted from date</td>
<td>Makes monthly results readable</td>
</tr>
<tr>
<td>dayName</td>
<td>Extracted from date</td>
<td>Helps understand day based patterns</td>
</tr>
<tr>
<td>weekendStatus</td>
<td>Classified Saturday and Sunday as Weekend, others as Weekday</td>
<td>Supports weekday versus weekend comparison</td>
</tr>
<tr>
<td>timePeriod</td>
<td>Grouped hour into Night, Morning, Afternoon, and Evening</td>
<td>Makes daily demand patterns easier to explain</td>
</tr>
<tr>
<td>weatherCondition</td>
<td>Created from rainfall and snowfall</td>
<td>Supports dry, rainy, snowy, and mixed weather comparison</td>
</tr>
<tr>
<td>temperatureGroup</td>
<td>Grouped temperature into Cold, Comfortable, and Hot</td>
<td>Shows demand difference by temperature level</td>
</tr>
<tr>
<td>demandLevel</td>
<td>Created using NumPy percentiles</td>
<td>Classifies low, medium, and high demand periods</td>
</tr>
<tr>
<td>weatherComfortScore</td>
<td>Created using temperature, humidity, rain, and snow penalties</td>
<td>Gives a simple riding comfort indicator</td>
</tr>
</table>

## Analysis Performed

<table>
<tr>
<td><b>Analysis Type</b></td>
<td><b>Details</b></td>
</tr>
<tr>
<td>Time Analysis</td>
<td>Demand by season, month, hour, weekend status, holiday status, and time period</td>
</tr>
<tr>
<td>Weather Analysis</td>
<td>Demand by weather condition and temperature group</td>
</tr>
<tr>
<td>Subgroup Comparison</td>
<td>Season, weekend status, holiday status, weather condition, and temperature group</td>
</tr>
<tr>
<td>Relationship Analysis</td>
<td>Correlation between weather variables and rented bike count</td>
</tr>
<tr>
<td>Outlier Analysis</td>
<td>Very high demand detection using z score and IQR</td>
</tr>
<tr>
<td>NumPy Computation</td>
<td>Percentiles, mean, standard deviation, z score, and IQR</td>
</tr>
<tr>
<td>Visualization</td>
<td>Bar charts, line charts, scatter plot, correlation chart, and heatmap</td>
</tr>
</table>

## Important Findings

<table>
<tr>
<td><b>Finding</b></td>
<td><b>Evidence</b></td>
</tr>
<tr>
<td>Summer has the highest average seasonal demand</td>
<td>1034.07 average rentals</td>
</tr>
<tr>
<td>June has the highest average monthly demand</td>
<td>1245.68 average rentals</td>
</tr>
<tr>
<td>The busiest average hour is 18:00</td>
<td>1554.02 average rentals</td>
</tr>
<tr>
<td>Dry weather has the highest average demand</td>
<td>797.28 average rentals</td>
</tr>
<tr>
<td>Temperature is the strongest original weather variable</td>
<td>Correlation value 0.5627</td>
</tr>
<tr>
<td>Weekdays have higher average demand than weekends</td>
<td>748.11 versus 682.38</td>
</tr>
<tr>
<td>Non holiday periods have higher demand than holidays</td>
<td>739.28 versus 529.15</td>
</tr>
<tr>
<td>Z score analysis found very high demand records</td>
<td>63 records</td>
</tr>
<tr>
<td>IQR analysis found high demand outliers</td>
<td>152 records</td>
</tr>
<tr>
<td>Highest single demand record</td>
<td>3556 rentals on 2018 06 19 at 18:00</td>
</tr>
</table>

## Visualizations

### Figure 1. Average Bike Rentals by Month

This figure shows that demand rises from winter to summer, peaks in June, and falls again near winter.

![Average Bike Rentals by Month](images/chart2MonthlyDemand.png)

### Figure 2. Average Bike Rentals by Hour of Day

This figure shows a clear evening peak. The highest average demand appears at 18:00.

![Average Bike Rentals by Hour of Day](images/chart3HourlyDemand.png)

### Figure 3. Average Bike Rentals by Weather Condition

This figure shows that dry weather has the highest average bike rental demand.

![Average Bike Rentals by Weather Condition](images/chart6WeatherConditionDemand.png)

### Figure 4. Correlation with Rented Bike Count

This figure shows that temperature is the strongest original weather variable associated with rented bike count.

![Correlation with Rented Bike Count](images/chartWeatherCorrelation.png)

### Figure 5. Season Hour Demand Heatmap

Stronger color means higher average bike rental demand by season and hour.

![Season Hour Demand Heatmap](images/chart7SeasonHourHeatmap.png)

## NumPy Based Computation

NumPy was used meaningfully in this project.

<table>
<tr>
<td><b>Computation</b></td>
<td><b>Purpose</b></td>
</tr>
<tr>
<td>np.percentile</td>
<td>Created demand levels and IQR limits</td>
</tr>
<tr>
<td>np.mean</td>
<td>Calculated average rented bike count</td>
</tr>
<tr>
<td>np.std</td>
<td>Calculated standard deviation</td>
</tr>
<tr>
<td>Z score calculation</td>
<td>Detected very high demand records</td>
</tr>
<tr>
<td>IQR calculation</td>
<td>Detected high demand outliers</td>
</tr>
</table>

### Z Score Logic

```text
z score = (rentedBikeCount minus mean) divided by standard deviation
