---
layout: article-toc
---
# Widgets
Widgets are provided to create plug in data that can be used to build Dashboards. Some widget types make use of existing measures and provide the ability to display them in a more appealing format. Certain widget types allow you to return and display data based on configuration carried out within the widget.

Related Articles
Application Entity Viewer
Reports
Creating a new Widget
Select the + Create New Widget button, give the new Widget a name, and choose which type of Widget you wish to create. Configuration options and an example video for each of the Widget types is given below.

Widget Types
Data Chart
Charts can be in the form of a Bar, Pie or Line Graph

Scorecard
A Scorecard widget can be used to display one or more Measures which have previously been defined.

Target Counter
This type of widget is used to display how a single measure is performing against it's target.

List of Data
Allows you to populate a widget with a list of data based on a user defined table query.

List of Counters
This widget allows you to display one or a list of metrics that are based on an aggregate value such as count, average, max, and min.

Custom
The custom widget type allows you to specify a URL and display the content as an image, in an iframe or div.

Pre-Defined Date Settings
When creating widgets within Hornbil Advanced Analytics, some widget types provide the ability to set the sampling type and the sampling period. The sample period when using predefined date settings consist of multiple options to provide you the flexibility to set the widget to report on a specific period in time. Some of these options relate to the beginning of a week (this week or last week), and because the week start day can be different for organizations based in different countries Hornbill have also provided a setting to enable this to be set per Hornbill instance within the System -> Settings -> Advanced section from your Hornbill admin portal. Search for system.regionalSettings.weekStartDay to set it for your instance. By default this setting is set to Sunday as the start of the week. There are also settings for the beginning of the calendar year - reporting.calendarYearStart which by default is set to 01/01, and a setting for the beginning of the financial year - reporting.financialYearStart which by default is set to 01/04.

The pre-defined date settings are explained here:

Start Of This Week - 00:00:00 hours on the last Sunday before today
Start Of This Month - 00:00:00 hours on the first day of the current month
Start Of Financial Year - 00:00:00 hours on the first day of the current financial year
Start Of This Year - 00:00:00 hours on the first day of the current year
Start Of Calendar Quarter - 00:00:00 hours on the first day of the current quarter. A quarter can start in January, April, July or October
Start Of Financial Quarter - 00:00:00 hours on the first day of the current financial quarter. A quarter can start in January, April, July or October
Start Of Last Week - 00:00:00 hours on last week's Sunday
Start Of Last Month - 00:00:00 hours on the first day of the last month
Start Of Last Financial Year - 00:00:00 hours on the first day of the last financial year
Start Of Last Year - 00:00:00 hours on the first day of the last year
Start Of Last Calendar Quarter - 00:00:00 hours on the first day of the last quarter
Start Of Financial Quarter - 00:00:00 hours on the first day of the last financial quarter
Last Calendar Years Samples - 00:00:00 hours on the first day of the last year to 23:59:59 hours on the last day of last year
Last Financial Years Samples - 00:00:00 hours on the first day of the last financial year to 23:59:59 hours on the last day of last financial year
Last Calendar Quarter Samples - 00:00:00 hours on the first day of the last quarter to 23:59:59 hours on the last day of the last quarter. A quarter can end in March, June, September or December
Last Financial Quarter Samples - 00:00:00 hours on the first day of the last financial quarter to 23:59:59 hours on the last day of the last financial quarter. A quarter can end in March, June, September or December
Last Months Samples - 00:00:00 hours on the first day of last month to 23:59:59 hours on the last day of last month
Last Weeks Samples - 00:00:00 hours on last week's Sunday to 23:59:59 hours on last week's Saturday

<!-- https://wiki.hornbill.com/index.php?title=Widgets -->