---
layout: article-toc
---
# Widgets

Widgets allow you to create plug-in data for[dashboards](/esp-config/advanced-analytics/dashboards). You can use widgets to display existing [measures](/esp-config/advanced-analytics/measures) in a visual format or to return data based on specific configurations within the widget itself.

## General settings

Use the **General settings** dialog to manage widget properties and select the widget type. To help you choose the right visualization for your data, review the following options:

* **Data chart**: Displays data based on specific data source configurations. For more information, see [Data source settings](#data-source-settings).
* **Scorecard**: Displays one or more measures that you have previously defined.
* **Target counter**: Shows how a single measure performs against a specific target.
* **List of data**: Populates the widget with a list of data based on a table query that you define.
* **List of counters**: Displays one or more metrics based on aggregate values such as count, average, maximum, or minimum.
* **Custom**: Allows you to specify a URL to display content as an image, an iframe, or a div.

![Widget properties dialog](/_books/esp-config/images/widget-general-settings-properties.png)

## General look and feel

Use the **General look and feel** dialog to style your widget. You can customize the following elements:

* Background and element colors
* Transparency levels
* Border styles

## Data source settings

When you create data charts, you must specify a data type to define how the chart generates information. You can select from the following data types:

* **Measured Samples**: Use this type to add data from multiple measures to a single chart. This type displays history and uses definable sample intervals. You can display this data as a bar chart or a line chart.
* **Measure Group By**: Use this type to display data from a single measure grouped by [Saved Data Columns](/advanced-analytics/measures#saved-data-columns). You can display this data as a bar chart or a pie chart.
* **Measure Samples Group By**: Use this type to group and display sampled data from a single measure. You can group this data by [Saved Data Columns](/advanced-analytics/measures#saved-data-columns) and by definable sample periods. You can display this data as a bar chart or a line chart.
* **SQL Group By**: Use this type to specify a database table, a grouping column, and a counting column. You can also define filter conditions and the sample history duration. You can display this data as a bar chart or a pie chart.

## Widget settings

Use the **Widget settings** dialog to adjust chart options. In this section, you can configure:

* Axis and grid properties
* Legend placement
* Target lines

## Pre-defined date settings

When you create widgets in Hornbill Advanced Analytics, you can set the sampling type and the sampling period.

The sample period includes several options to help you report on specific points in time. Some options relate to the start of a week. Because the start of the week varies by region, you can configure this globally for your Hornbill instance. By default, the start of the week is Sunday.

### Set the start of the week

To customize which day your organization considers the start of the week, follow these steps:

**Steps**

1. Select the **Configuration** gear icon at the bottom of the left navigation menu.
2. In the navigation dropdown, select **Platform Configuration**.
3. Navigate to **Advanced Tools & Settings** > **Advanced System Settings**.
4. Search for the setting `system.regionalSettings.weekStartDay`.
5. Enter the preferred day for your instance.

**Expected Result**

The system updates the start of the week for all widgets using predefined date settings.

::: tip
You can also configure the start of the calendar year using `reporting.calendarYearStart` (default is 01/01) and the start of the financial year using `reporting.financialYearStart` (default is 01/04).
:::

### Available date settings

Refer to the following table for definitions of each predefined date setting:

| Date Setting | Definition |
| :--- | :--- |
| Start Of This Week | 00:00:00 hours on the last Sunday before today |
| Start Of This Month | 00:00:00 hours on the first day of the current month |
| Start Of Financial Year | 00:00:00 hours on the first day of the current financial year |
| Start Of This Year | 00:00:00 hours on the first day of the current year |
| Start Of Calendar Quarter | 00:00:00 hours on the first day of the current quarter (January, April, July, or October) |
| Start Of Financial Quarter | 00:00:00 hours on the first day of the current financial quarter (January, April, July, or October) |
| Start Of Last Week | 00:00:00 hours on last week's Sunday |
| Start Of Last Month | 00:00:00 hours on the first day of the last month |
| Start Of Last Financial Year | 00:00:00 hours on the first day of the last financial year |
| Start Of Last Year | 00:00:00 hours on the first day of the last year |
| Start Of Last Calendar Quarter | 00:00:00 hours on the first day of the last quarter |
| Start Of Last Financial Quarter | 00:00:00 hours on the first day of the last financial quarter |
| Last Calendar Years Samples | 00:00:00 hours on the first day of the last year to 23:59:59 hours on the last day of last year |
| Last Financial Years Samples | 00:00:00 hours on the first day of the last financial year to 23:59:59 hours on the last day of last financial year |
| Last Calendar Quarter Samples | 00:00:00 hours on the first day of the last quarter to 23:59:59 hours on the last day of the last quarter |
| Last Financial Quarter Samples | 00:00:00 hours on the first day of the last financial quarter to 23:59:59 hours on the last day of the last financial quarter |
| Last Months Samples | 00:00:00 hours on the first day of last month to 23:59:59 hours on the last day of last month |
| Last Weeks Samples | 00:00:00 hours on last week's Sunday to 23:59:59 hours on last week's Saturday |