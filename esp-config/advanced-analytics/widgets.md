---
layout: article-toc
---
# Widgets
With widgets, you can create plug-in data for use in building dashboards. Some widget types make use of existing measures and provide the ability to display them in a more appealing format. Certain widget types allow you to return and display data based on configuration carried out within the widget.

## Topics covered
* [General settings](/advanced-analytics/widgets#general-settings)
* [General look and feel](/advanced-analytics/widgets#general-look-and-feel)
* [Data source settings](/advanced-analytics/widgets#data-source-settings)
* [Widget settings](/advanced-analytics/widgets#widget-settings)
* [About pre-defined date settings](/advanced-analytics/widgets#about-pre-defined-date-settings)


## General settings
Use this dialog to manage widget properties.
* **Data chart.** See [Data source settings](/advanced-analytics/widgets#data-source-settings).
* **Scorecard.** A scorecard widget can be used to display one or more measures that have previously been defined.
* **Target counter.** This type of widget is used to display how a single measure is performing against its target.
* **List of data.** This widget allows you to populate a widget with a list of data based on a user defined-table query.
* **List of counters.** This widget allows you to display one metric or a list of metrics that are based on an aggregate value such as count, average, max, and min.
* **Custom.** The custom widget type allows you to specify a URL and display the content as an image, in an iframe or div.

## General look and feel
Use this dialog to style the widget according to your preferences. You can set colors, transparency, and border styles. 

## Data source settings
When creating data charts, you specify data types to define how the data for the chart will be created. Select from the following data types:
* **Measured Samples.** This type allows you to add multiple measures' data to a single chart, to display the data using definable sample intervals, and to display history.
* **Measure Group By.** This type allows a single measure's data to be displayed and grouped by Saved Data Columns.
* **Measure Samples Group By.** This type allows a single measure's sampled data to be grouped and displayed by Saved Data Columns and by definable sample periods (manual or predefined date settings).
* **SQL Group By.** This type allows you to specify a database table, which column to group on, which column to count on, as well as to define filter conditions for the data and the sample history duration.

## Widget settings
Use this dialog to adjust the chart settings, as well as the options for axis, grid, and legend. Here you can also adjust settings for target lines.

## About pre-defined date settings
When creating widgets within Hornbill Advanced Analytics, you can use some widget types to set the sampling type and the sampling period.

The sample period, when using predefined date settings, consists of multiple options to provide you the flexibility to set the widget to report on a specific period in time. Some of these options relate to the beginning of a week (this week or last week), and because the week start day can be different for organizations based in different countries, Hornbill have also provided a setting to enable this to be set per Hornbill instance within Configuration. By default, this setting is set to Sunday as the start of the week. 

**To customize the beginning of the week start:**
1. Select the **Configuration** cog at the bottom of the left-hand application menu bar.
1. In Configuration, from the navigation dropdown, select **Platform Configuration**.
1. Navigate to Advanced Tools & Settings > Advanced System Settings.
1. Search for `system.regionalSettings.weekStartDay` to set it for your instance.

::: tip
There are also settings for the beginning of the calendar year (`reporting.calendarYearStart`)  which by default is set to 01/01, and for the beginning of the financial year (`reporting.financialYearStart`) which by default is set to 01/04.
:::

Pre-defined date settings are as follows:
|Date Setting|Definition|
| - | - |
|Start Of This Week|00:00:00 hours on the last Sunday before today|
|Start Of This Month|00:00:00 hours on the first day of the current month|
|Start Of Financial Year|0:00:00 hours on the first day of the current financial year|
|Start Of This Year|00:00:00 hours on the first day of the current year|
|Start Of Calendar Quarter|00:00:00 hours on the first day of the current quarter. A quarter can start in January, April, July or October|
|Start Of Financial Quarter|00:00:00 hours on the first day of the current financial quarter. A quarter can start in January, April, July or October|
|Start Of Last Week|00:00:00 hours on last week's Sunday|
|Start Of Last Month|00:00:00 hours on the first day of the last month|
|Start Of Last Financial Year|00:00:00 hours on the first day of the last financial year|
|Start Of Last Year|00:00:00 hours on the first day of the last year|
|Start Of Last Calendar Quarter|00:00:00 hours on the first day of the last quarter|
|Start Of Financial Quarter|00:00:00 hours on the first day of the last financial quarter|
|Last Calendar Years Samples|00:00:00 hours on the first day of the last year to 23:59:59 hours on the last day of last year|
|Last Financial Years Samples|00:00:00 hours on the first day of the last financial year to 23:59:59 hours on the last day of last financial year|
|Last Calendar Quarter Samples|00:00:00 hours on the first day of the last quarter to 23:59:59 hours on the last day of the last quarter. A quarter can end in March, June, September or December|
|Last Financial Quarter Samples|00:00:00 hours on the first day of the last financial quarter to 23:59:59 hours on the last day of the last financial quarter. A quarter can end in March, June, September or December|
|Last Months Samples|00:00:00 hours on the first day of last month to 23:59:59 hours on the last day of last month|
|Last Weeks Samples|00:00:00 hours on last week's Sunday to 23:59:59 hours on last week's Saturday|

<!-- https://wiki.hornbill.com/index.php?title=Widgets -->
<!-- there is still additional information that needs to be brought over from the wiki page -->