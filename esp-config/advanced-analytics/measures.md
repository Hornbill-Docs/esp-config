---
layout: article-toc
---
# Measures
A key requirement of providing strategic business intelligence through reporting is to define measures that are sampled and stored periodically. Once these measures are stored over a period of time, the type of reporting possible is expanded considerably. It includes trending, performance measurement against goals and thresholds, and predictions based on historical trends.

The creation of a measure includes selecting the data you wish to sample, the frequency that the samples are taken, and the targets and goals you wish to achieve.

The information provided by measures can be used to build widgets for display on dashboards. The output consists of numerical values that enable the population of:
* **Scorecards.** This is a count of the data that the measure has recorded per period.
* **Sparklines.** This is a count of the data that the measure has recorded per period shown in a chart format.
* **Actual vs Target.** This is a count of the data recorded versus the target count of the measure per period.

## Features

### Basic Information
* **Title.** The title is visible from within the list of defined measures. It is also used when creating a widget based on a measure.
* **Description.** You can provide details of the measure so that other users with the ability to view and edit this measure can understand more about it.
* **Status.** A "running" measure is currently active and sampling data based on the frequency.

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

### Data Source

* **Table.** This is the primary table from which the measure will collect its data.
* **Key Column.** This is the primary key of the named table. Being the primary key, this provides a unique identifier for each record.
* **Date Ranging Column.** Here you select a date column that the measure will base its data collection on. The dates held in this column will be used to count/sum/average the records based on frequency, such as last month, last year, or all records since the beginning of this year.
* **Date Ranging Column 2.** This is an optional field where you can provide a second date column to be included as part of the criteria for data collection. This will be used to count/sum/average the records where the collected data for the selected frequency will be based on both Date Ranging Column AND Date Ranging Column 2.
* **Query where clause.** Here you can add a filter to the measure.
* **Percentage Sub-Query.** Here you can add a percentage filter to the measure.
* **Saved Data Columns.** Here you can specify which columns are available to be drilled down on and grouped by. Unless columns are defined against the measure, they will not be available to group by or drill down when configuring widget content based on the measure.

<!-- https://wiki.hornbill.com/index.php?title=Measures -->
