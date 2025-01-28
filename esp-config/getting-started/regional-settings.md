---
layout: article-toc
---
# Configuring Regional Settings
Hornbill allows you to configure regional settings, such as time zone, language, and date and time formats, to better fit your organization's location. This guide will provide an overview of the regional settings that can be adjusted. 

## Topics Covered
* Setting the default date and time formats.
* Selecting the default time zone.
* How to enable and disable the languages that are available to users.

## Before You Begin
This guide takes you through administrative configurations.  The following will be needed to complete this guide:
* Admin User access.
* General knowledge of using [Configuration](/esp-config/getting-started/using-configuration).

::: tip
To access any of the settings described in this document, open [Configuration](/esp-config/getting-started/using-configuration) and search by the setting name 
:::

## Date and Time Formats
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

## Default Time Zone
The default time zone allows you to select the time zone where your main business operations are located.
|Setting Name|Description|Default|
|-|-|-|
|system.regionalSettings.timezone|Sets the timezone that Hornbill is operating in|GMT Greenwich Mean Time|

::: note
All time entries are saved to Hornbill using the GMT time zone.  Time zone settings provide an offset from the stored GMT time, to determine how they are displayed in the UI. 
:::

## Languages
Hornbill is a multi-language environment that includes the translation of the user interface and the ability to translate communications between users.

### Default Language
|Setting Name|Description|Default|
|-|-|-|
|system.regionalSettings.language|Sets the language that Hornbill would use when formatting language-specific text|en-GB|

### Enabling / Disabling Available Languages
Within Hornbill, you can enable over 400 languages.  

[Enabled languages](/esp-config/localization/supported-languages) are available for users to choose from within their profiles.  When selected, users will view all areas of Hornbill in that language. By disabling languages, you control which languages users can select from. 

#### Language Translations
Enabled languages require a level of regular maintenance to ensure that all translations are in place. [Language translations](/esp-config/localization/supported-languages#translate) are done by Google Translate and are not verified by Hornbill. You are responsible for verifying and maintaining the translations provided by Google Translate across your instance. 

Configure languages by opening [Configuration](/esp-config/getting-started/using-configuration) and search `manage system languages`.