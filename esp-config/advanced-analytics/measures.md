---
layout: article-toc
---
# Measures

Measures help you track and visualize specific data points over time. When creating a measure, you select the data you want to sample, the frequency of those samples, and the targets you want to achieve.

Samples are stored at regular intervals to enable advanced business intelligence reporting to identify trends and performance metrics.

![An example of a measure](/_books/esp-config/images/analytics-measure-example.png)

* **Scorecard**: A scorecard displays the selected aggregate value (count, sum, average, floor, ceiling, or percentage) of data captured during each sample period.
* **Sparkline**: A sparkline is a minimalistic data visualization designed to show trends and variations in a series of data samples at a glance.
* **Target**: This widget compares the aggregate value of the data sample against the target count defined for that sample period.
* **Latest**: This displays the most recent aggregate value from the latest sample data.
* **Change**: This displays the change in the aggregate value between the latest sample and the previous sample data.

The data sampled by measures can also be used to define [widgets](/esp-config/advanced-analytics/widgets) that can be presented on a [dashboard](/esp-config/advanced-analytics/dashboards) to provide insights into your data.

## Measure configuration

### Basic Information

* **Title**: The name of the measure. This title appears in the list of defined measures and on any widgets you create based on this measure.
* **Description**: A summary of the measure. Use this field to help other users understand the purpose and logic of the measure.
* **Status**: Indicates if the measure is active.
  * **Running**: The measure currently samples data according to the defined frequency.
  * **Resampling**: The measure's data sampling has been cleared and is currently resampling fresh data.
  * **Suspended**: The measure is not currently sampling data. No new data will be collected until the measure is set back to Running.

### Measure

* **Timezone**: The time zone used to determine when to take samples for the measure. This is important for ensuring that data is collected at the correct times, especially if your organization operates across multiple time zones.
* **Frequency.** This is how often the measure will take a data sample. The options are:
  * DAILY
  * WEEKLY
  * MONTHLY
  * QUARTERLY (With optional starting months)
  * YEARLY
* **Value Aggregate.** This is the type of calculation that the measure will perform. The calculated value will be displayed on the scorecard.
  * **COUNT**: An integer that represents a count of items in a sample set that match specific criteria.
  * **SUM**: The sum of a selected *Value Column* for all the samples take during the sample period.
  * **AVERAGE**: A numeric value that represents the average value in a series of values in the data set.
  * **MIN**: A numeric value that represents the lowest value in a series of values in the data set.
  * **MAX**: A numeric value that represents the highest value in a series of values in the data set.
  * **PERCENT**: A percentage of items in a given data set that match a criterion from a larger subset. For example, the count of records where column X = 5 in a set of records in a given date range, is returned as a percentage.
* **Maximum Sample History**: This is the maximum number of samples that the system will store against this measure.
* **Scorecard Limit**: This is the number of samples shown against a scorecard.
* **Sparkline Limit**: This is the number of samples shown against a sparkline.

### Targets & Goals

* **Measure Thresholds.** This is the count that needs to be achieved in order to meet the measure's target.
* **Warning Threshold.** This is the count between the target and the breach thresholds.
* **Breach Threshold.** This is the count that needs to be achieved in order for the measure to breach its target.

:::tip
You can change the direction of the threshold by clicking the arrow to the right of the threshold targets. In terms of requests or requests logged, you would want to say that the lower the number is, the better the teams are performing. However, for the total number of resolved calls, a higher count is better.
:::

## Data source

* **Table**: The primary table where the measure collects data.
* **Key Column**: The primary key of the selected table. This column provides a unique identifier for each record.
* **Date Ranging Column**: The date column the measure uses to base its data collection. The system uses the dates in this column to count, sum, or average records based on the frequency, such as "last month" or "all records since the beginning of this year."
* **Date Ranging Column 2**: An optional field for a second date column. When you provide this, the system includes both **Date Ranging Column** and **Date Ranging Column 2** as criteria for data collection.
* **Value Column**: The column the measure uses to sum, average, or calculate percentages. This field is only available if the aggregate type selected is SUM, AVERAGE, or PERCENT.
* **Query where clause**: A filter you can apply to the measure to refine the data.
* **Percentage Sub-Query**: A filter used specifically for percentage calculations. When you select PERCENT as the aggregate type, you need to provide a SQL sub-query that defines the denominator for the percentage calculation. The main query defined by the other data source fields will be used as the numerator in the percentage calculation, while the sub-query will be used as the denominator. The system will then calculate the percentage based on these two queries.

### Saved data columns

Data columns are specific fields from the data source stored with each sample. Use these columns when [designing widgets](/esp-config/advanced-analytics/widgets#data-source-settings) and reports. You can add a maximum of 10 data columns to a measure.

The columns are named using an alias and the column name from the data source. The alias allows you to refer to the column in a more user-friendly way when creating widgets and reports.

* **Alias**: An optional alternative name for the column that can be used in reporting and analysis.
* **Column Name**: The name of the column as it appears in your data source.

![An example of data columns in a measure](/_books/esp-config/images/analytics-measure-data-columns.png)
