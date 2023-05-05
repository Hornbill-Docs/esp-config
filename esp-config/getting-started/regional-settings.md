---
layout: article-toc
---
# Configuring Regional Settings
With Hornbill, you can configure regional setting settings, such as time zone, language, and date and time formats. This guide describes some of the regional settings that can be changed to reflect your organization's location. 

## Topics covered
* Setting the default date and time formats
* Selecting the default time zone
* How to enable and disable the languages that are available to users

## Before you begin
This guide takes you through administrative configurations.  The following will be needed to complete this guide:
* Admin User access
* General knowledge of using [Configuration](/esp-config/getting-started/using-configuration)

::: tip
To access any of the settings described in this document, open [Configuration](/esp-config/getting-started/using-configuration) and search by the setting name 
:::

## Date and time formats
These settings are used to apply default date and time formats in areas such as reporting and outgoing emails when regional settings defined in a user's profile can not be used.

|Setting Name|Description|Default|
|-|-|-|
|system.regionalSettings.dateFormat|Sets the date format the server may use when formatting date/time values|yyyy-MM-dd|
|system.regionalSettings.dateTimeFormat|Sets the date/time format the server may use when formatting date/time values|yyyy-MM-dd HH:mm:ss|
|system.regionalSettings.timeFormat|Sets the time format the server may use when formatting date/time values|HH:mm:ss|
|system.regionalSettings.weekStartDay|Sets the day of the week that a calendar week is considered to start on, when calculating start of week/end of week times and dates|sunday|

::: note
All dates and times are saved to Hornbill in the ISO format yyyy-MM-dd HH:mm:ss. This is important to know when it comes to integrations, automation, reporting, exports, and other interactions that require direct access to Hornbill.  The Hornbill user interface may have a different format displayed compared to what is stored.
:::

## Default time zone
The default time zone allows you to select the time zone of where your main business operations are located.
|Setting Name|Description|Default|
|-|-|-|
|system.regionalSettings.timezone|Sets the timezone that the server is operating in|GMT Greenwich Mean Time|

::: note
All time entries are recorded in the database using the GMT time zone.  Time zone settings provide an offset from the stored GMT time, to determine how they are displayed in the UI. 
:::

## Languages

### Default language
|Setting Name|Description|Default|
|-|-|-|
|system.regionalSettings.language|Sets the language the server would use when formatting language-specific text|en-GB|

### Enabling / disabling available languages
Hornbill provides support for using over 400 different languages.  Enabled languages are available to users, allowing them to select their preferred language from their profile.  By disabling languages, you can control which languages you don't want to support. Enabled languages do require a level of regular maintenance to ensure that all translations are in place.

::: tip
Configure languages by opening [Configuration](/esp-config/getting-started/using-configuration) and search `manage system languages`
:::