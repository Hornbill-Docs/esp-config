---
layout: article-toc
keywords: translate strings in the UI
---
# Translation mode
Throughout every application within the Hornbill user interface, you are presented with forms containing text to describe labels, messages, hints, and more. The Hornbill environment provides an in-app ability to translate this text so you can make sure the translation is in context with how it is being used.

## Rights and roles
A role called Translator is provided to allow selected users to be assigned the right to configure in-app translations. 

**To assign a user the Translator role:**
1. Navigate to **[Configuration](/esp-config/getting-started/using-configuration) > Platform Configuration > Roles**.
1. In the Search field, search for *tran* and then in the Roles list, click **Translator**.
1. Go to the *Assigned Users* tab, then click **Add Users**.
1. In the User field, search for a user and click **Save**.

## Start Translation Mode
A user that has been assigned the Translator role  will have an option within their [Profile toolbar](/esp-user-guide/navigation#profile-toolbar) (at the top right).

![Start Translation Mode](/_books/esp-config/localization/images/start-translation-mode.png)

Translations can serve two purposes:

* To provide an alternative translation to the English text that has been provided by default.
* To translate the default text to another language that you wish to provide for users.

## Translate UI
Once translation mode is enabled, each string that allows for a translation to be applied is presented with a green underline.

![Translate Mode Underline](/_books/esp-config/localization/images/translation-mode-underline.png)

**To translate a UI string:**
1. In the Profile toolbar, click **Start Translation Mode**. (If instead, you see **Stop Translation Mode**, then you are already in translation mode.)
1. In the Hornbill UI, find a string that you want to translate and right-click on it.
1. In the Translate dialog, add your translation and then click **Save**. The options available to you are the following:

    * **From.** Shows the current value for the string.
    * **To.** Lets you manually enter a new value for the string.
    * **In.** Lets you select an alternative language to translate this string into.
    * **Reset.** Returns the string's translation to its original default value.
    * **Suggest Translation.** Performs a Google Translate to automatically populate the `To` box.

Once you have saved the translation, and it will be visible to everyone using that language.

![Translation Dialog Box](/_books/esp-config/localization/images/translation-dialog.png)

:::note
Under some circumstances, a string may not be presented with a green underline. In the majority of cases, these strings can still be translated in the [User Interface Translations](/esp-config/localization/user-interface-translations).
:::
<!-- References>
<!-- https://wiki.hornbill.com/index.php?title=Translation_Mode>