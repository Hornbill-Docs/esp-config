---
layout: article-toc
---
# Supported languages
Hornbill supports 173 different languages and provides the tools to manage the translations and the availability of these languages. 

## Topics covered
* Enabling languages
* Translating an application

## Accessing
1. Open [Configuration](/esp-config/getting-started/using-configuration)  using [Ctrl+Shift+S] on the keyboard.
1. Type *lang* in the search box, then select **Supported Languages** from the results.

or
1. Navigate to **Configuration > Platform Configuration > Internationalization > Supported Languages**.

![Supported Languages](/_books/esp-config/localization/images/supported-languages.png)

## Languages

![Languages](/_books/esp-config/localization/images/languages-button.png)

The **Languages** option allows you to turn on the languages that are available to your users. Once a language has been turned on, it will be available for users to select within their user profile under *Regional Settings*.

1. Click **Languages** on the right side of the menu bar.
1. Use the dropdown on the left side of the menu bar to filter between supported, unsupported, or all languages.
1. Toggle the languages to **ON** or **OFF** as desired.

## Translate

![Translate](/_books/esp-config/localization/images/translate-button.png)

The **Translate** option is used to provide translations for any string that is currently missing a translation for a selected application and language.  

1. Click **Translate** on the right side of the menu bar.
1. Use the dropdown on the left side of the menu bar to select the application that you wish to translate.
1. Use the language dropdown to select the language that you want to be translated.
1. Click **Translate Missing**.

A total string count shows the number of available strings, how many have been translated, and how many are missing.

When you click the **Translate Missing** button, you trigger an automatic lookup and translation of the missing strings using Google Translate. Translations that already exist will not be overwritten. 

:::note
Automatic translation of a string of text will not take its context into consideration, so not all translations will be correct. You can use [Translation Mode](/esp-config/localization/translation-mode) to make translations in context with the application's UI.
:::

<!-- https://wiki.hornbill.com/index.php?title=Manage_Languages -->