---
layout: article-toc
---
# Measures

To get the most value from your business intelligence reporting, you must define measures that the system samples and stores at regular intervals. As you collect and store these measures over time, you can access more advanced reporting capabilities.

These capabilities include:

* **Trending**: View how your data changes over a specific period.
* **Performance measurement**: Compare your current results against defined goals and thresholds.

Measures help you track and visualize specific data points over time.When creating a measure, you select the data you want to sample, the frequency of those samples, and the targets you want to achieve.

![An example of a measure](/_books/esp-config/images/analytics-measure-example.png)

* **Scorecard**: A scorecard displays the total count of data recorded during each sample period.
* **Sparkline**: A sparkline is a minimalistic data visualization designed to show trends and variations in a series of data samples at a glance.
* **Target**: This widget compares the count of recorded data against the target count defined for that sample period.
* **Latest**: This displays the most recent count of recorded data.
* **Change**: This widget shows the change in the count of recorded data compared to the previous sample period.

The data captured by measures can be used in [widgets](/esp-config/advanced-analytics/widgets) on your [dashboards](/esp-config/advanced-analytics/dashboards) to provide insights into your data and help you make informed decisions.

## Creating a Measure

### Basic Information

* **Title**: The name of the measure. This title appears in the list of defined measures and on any widgets you create based on this measure.
* **Description**: A summary of the measure. Use this field to help other users understand the purpose and logic of the measure.
* **Status**: Indicates if the measure is active. A **Running** status means the measure currently samples data according to the defined frequency.

### Measure

* **Frequency.** This is how often the measure will take a data sample. The options are:
  * DAILY
  * WEEKLY
  * MONTHLY
  * QUARTERLY (Please choose the starting quarter)
  * YEARLY
* **Value Aggregate.** This is the type of calculation that the measure will perform.
  * **COUNT.** An integer that represents a count of items in a result set that match specific criteria.
  * **AVERAGE.** A numeric value that represents the average value in a series of values in the data set.
  * **MIN.** A numeric value that represents the lowest value in a series of values in the data set.
  * **MAX.** A numeric value that represents the highest value in a series of values in the data set.
  * **SUM.** A numeric value that represents the sum of a series of values in the data set.
  * **PERCENT.** A percentage of items in a given data set that match a criterion from a larger subset. For example, the count of records where column X = 5 in a set of records in a given date range, is returned as a percentage.
* **Scorecard Limit.** This is the number of samples shown against a scorecard.
* **Sparkline Limit.** This is the number of samples shown against a sparkline.
* **Maximum Sample History.** This is the maximum number of samples that the system will store against this measure.

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
* **Query where clause**: A filter you can apply to the measure to refine the data.
* **Percentage Sub-Query**: A filter used specifically for percentage calculations.

### Saved Data Columns

Data columns are the specific fields from your data source that you want to include in your measure. These columns are stored with each sample and can be used when [designing widgets](/esp-config/advanced-analytics/widgets#data-source-settings) and reports. A maximum of 10 data columns can be added to a measure.

The columns are named using an alias and the column name from the data source. The alias allows you to refer to the column in a more user-friendly way when creating widgets and reports.

* **Alias**: An optional alternative name for the column that can be used in reporting and analysis.
* **Column Name**: The name of the column as it appears in your data source.

![An example of data columns in a measure](/_books/esp-config/images/analytics-measure-data-columns.png)