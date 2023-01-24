---
layout: article-toc
---
# Regional settings
This guide covers how to set up regional settings and features which will be used by Hornbill and its apps.
## Topics covered
* Setting the default date and time formats
* Selecting the default time zone that Hornbill will use
* How to enable and disable the languages that are available to users
* Defining a default working time for your users

## Before you begin
This guides takes you through administrative configurations.  The following will be needed to complete this guide:
* Admin User access
* General knowledge of using [Hornbill Configuration](/esp-config/guides/using-configuration)

## Steps to access and update settings
1. Login to Hornbill with an admin account
1. In the left-hand menu bar, select the cog icon at the bottom or optionally use **[Ctrl + Shift + S]** on the keyboard
1. Click on the Configuration search icon
1. Enter part or all of the name of the setting
1. Select the setting from the results list to view the setting
1. Set the setting to the desired value

## Time and date formats
The following settings are used to apply a default format for how both the time and date are displayed.  User Profiles also have an option to set a format for each individual user which will supercede these settings.  The settings covered here are used when there is no user context such as workflow automation email templates, and the Customer Portal.

|Setting|Description|Example|
|-|-|-|
|system.regionalSettings.dateFormat|Sets the date format the server may use when formatting date/time values|yyyy-MM-dd|
|system.regionalSettings.dateTimeFormat|Sets the date/time format the server may use when formatting date/time values|yyyy-MM-dd HH:mm:ss|
|system.regionalSettings.timeFormat|Sets the time format the server may use when formatting date/time values|HH:mm:ss|
|system.regionalSettings.weekStartDay|Sets the day of the week that a calendar week is considered to start on, when calculating start of week/end of week times and dates|sunday|

## Default time zone
The default time zone allows you to select the time zone of the data centre where your Hornbill is located or where your main business operations are located.
|Setting|Description|Example|
|-|-|-|
|system.regionalSettings.timezone|Sets the timezone that the server is operating in|GMT Greenwich Mean Time|

## Languages

|Setting|Description|Example|
|-|-|-|
|system.regionalSettings.language|Sets the language the server would use when formatting language-specific text|en-GB|

### Enabling / disabling available languages

## Working Time Calendars
Create a Working Time Calendar
setting: system.defaultWorkingTime.timezone
