---
layout: article-toc
---
# Defining Working Time
Working time defines the working or operational hours for your organization. Working time can be used by the different Hornbill apps to determine when users are scheduled to work.

## Topics Covered
1. Setting a default working time zone.
1. Adding default exclusion days, such as holidays.
1. Setting the default working days and hours.
1. Creating Working Time Calendars for multiple time zones and work schedules.

## Before You Begin
This guide takes you through administrative configurations.  The following will be needed to complete this guide:
* Admin User access.
* General knowledge of using [Configuration](/esp-config/getting-started/using-configuration).

::: tip
To access any of the settings described in this document, open [Configuration](/esp-config/getting-started/using-configuration) and search by the setting name 
:::

## Working Time Zone
Hornbill can be used across multiple geographical regions and time zones. Select the time zone that represents where the users are located.  This will ensure that the correct times are stored for the activities that they perform.

|Setting Name|Description|Example|
|-|-|-|
|system.defaultWorkingTime.timezone|Sets the default time zone|GMT Standard Time|

## Exclusion Days
Add individual days that will be excluded from the working time. This is commonly used for holidays but it can also be used for any other non-operational day. Both single-day events and reoccurring events can be set.

|Setting Name|Description|Example|
|-|-|-|
|system.defaultWorkingTime.exclusions|Sets the default working time exclusion days. Each exclusion should be specified in the format "d:m:y:[comment]". For annually reoccurring exclusions, use * for the year.|1:1:*:New Year's Day|

:::tip
To exclude a day, set the working hours to 00:00-00:00
:::

## Working Time Calendars
When an organization has users that work across different schedules or in different time zones, multiple Working Time Calendars can be created.

To access Working Time Calendars

1. Open Configuration.
1. Search for Working Time Calendars.

![Working Time Calendar](_books/esp-config/images/working-time-calendar.png)

### Time Zone
Hornbill can be used across multiple geographical regions and time zones. Select the time zone that represents where the teams or users who will be using this particular Working Time Calendar are located. This will ensure that the correct times are stored for the activities that they perform.

### Day and Hour Selection
Using the grid, mouse over the days and the hours while holding down the left mouse button to select or deselect the working times. Each block highlighted in blue represents an active time.

### Holiday Exclusions
Add individual days that will be excluded from the Working Time. This is commonly used for holidays but it can also be used for any other non-operational days. Both single-day events, as well as reoccurring events, can be set.