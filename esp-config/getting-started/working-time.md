---
layout: article-toc
---
# Working time
Working time defines the working or operational hours for your organisation. Working time can be used by the different Hornbill apps to determine when users are scheduled to work.

## Topics covered
1. Setting a default working time zone
1. Adding default exclusion days, such has holidays
1. Setting the default working days and hours
1. Creating Working Time Calendars for multiple time zones and work schedules

## Before you begin
This guide takes you through administrative configurations.  The following will be needed to complete this guide:
* Admin User access
* General knowledge of using [Configuration](/esp-config/getting-started/using-configuration)

::: tip
To access any of the settings described in this document, open [Configuration](/esp-config/getting-started/using-configuration) and search by the setting name 
:::

## Working time zone
Hornbill can be used across multiple geographical regions and time zones. Select the time zone that represents where the users are located  This will ensure that the correct times are stored for the activities that they perform.

|Setting Name|Description|Example|
|-|-|-|
|system.defaultWorkingTime.timezone|Sets the default timezone|GMT Standard Time|

## Exclusion days
Add individual days that will be excluded from the working time. This is commonly used for holidays but it can also be used for any other non-operational day. Both single-day events and reoccurring events can be set.

|Setting Name|Description|Example|
|-|-|-|
|system.defaultWorkingTime.exclusions|Sets the default working time exclusion days. Each exclusion should be specified in the format "d:m:y:[comment]". For annually reoccurring exclusions, use * for the year.|1:1:*:New Year's Day|

## Default working time
The system working time defines the default operational days and hours that users of Hornbill will be working within.  

|Setting Name|Description|Example|
|-|-|-|
|system.defaultWorkingTime.week.fri|Sets the default start/end working time for Friday (format hh:mm-hh:mm). Times will rounded down to the nearest 15 minute boundary|09:00-17:00|
|system.defaultWorkingTime.week.mon|Sets the default start/end working time for Monday (format hh:mm-hh:mm). Times will rounded down to the nearest 15 minute boundary|09:00-17:00|
|system.defaultWorkingTime.week.sat|Sets the default start/end working time for Saturday (format hh:mm-hh:mm). Times will rounded down to the nearest 15 minute boundary|09:00-17:00|
|system.defaultWorkingTime.week.sun|Sets the default start/end working time for Sunday (format hh:mm-hh:mm). Times will rounded down to the nearest 15 minute boundary|09:00-17:00|
|system.defaultWorkingTime.week.thu|Sets the default start/end working time for Thursday (format hh:mm-hh:mm). Times will rounded down to the nearest 15 minute boundary|09:00-17:00|
|system.defaultWorkingTime.week.tue|Sets the default start/end working time for Tuesday (format hh:mm-hh:mm). Times will rounded down to the nearest 15 minute boundary|09:00-17:00|
|system.defaultWorkingTime.week.wed|Sets the default start/end working time for Wednesday (format hh:mm-hh:mm). Times will rounded down to the nearest 15 minute boundary|09:00-17:00|

:::tip
To exclude a day, set the working hours to 00:00-00:00
:::

## Working Time Calendars
When an organisation has users that work across different schedules or in different time zones, multiple Working Time Calendars can be created.

### Day and hour selection
Using the grid, mouse over the days and the hours while holding down the left mouse button to select or deselect the working times. Each block highlighted in blue represents an active time.