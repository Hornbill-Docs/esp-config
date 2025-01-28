---
layout: article-toc
---
# Supported languages
Hornbill supports 173 different languages and provides the tools to manage the translations and the availability of these languages. 

## Topics Covered
* Enabling languages
* Translating an application

## Accessing
* Open [Configuration](/esp-config/getting-started/using-configuration) and search for ***Supported Languages***

or

1. Open [Configuration](/esp-config/getting-started/using-configuration) and select `Platform Configuration`
1. In the navigation panel locate the section titled ***Localization***
1. Select `Supported Languages`


![Supported Languages](/_books/esp-config/localization/images/supported-languages.png)

## Languages

![Languages](/_books/esp-config/localization/images/languages-button.png)

The `Languages` option allows you to turn on the languages that are available to your users. Once a language has been turned on it will be available for users to select within their user profile under Regional Settings.

1. Select `Languages` on the right side of the menu bar.
1. Use the filters to select between Supported, Unsupported, or All languages.
1. Toggle the languages to `ON` or `OFF` as desired.

## Translate

![Translate](/_books/esp-config/localization/images/translate-button.png)

The `Translate` option is used to provide translations for any string that is currently missing a translation for a selected application and language.  

1. Select `Translate` on the right side of the menu bar.
1. Select the application that you wish to translate.
1. Select the language that you want to be translated.
1. Select `Translate Missing`.

A total string count shows the number of available strings, how many have been translated, and how many are missing. Clicking on the `Translate Missing` button will perform an automatic lookup and translate the missing strings using Google Translate. Translations that already exist will not be overwritten. 

:::tip
Automatic translation of a string of text will not take its context into consideration and not all translations will be 100% accurate. Using [Translation Mode](/esp-config/localization/translation-mode) you are able make translations in context with the application's UI.
:::

<!-- https://wiki.hornbill.com/index.php?title=Manage_Languages -->