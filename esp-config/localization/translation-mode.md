---
layout: article-toc
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

Right-click on this text to be presented with a Translate UI option.
* **From**<br>Shows the current value for the string.
* **To**<br>Lets you manually enter a new value for this string.
* **In**<br>Lets you select an alternative language to translate this string into.
* **Default**<br> Returns the string's translation to its original default value.
* **Suggest**<br>This will perform a Google Translate to automatically populate the `To` box
* **Save**<br>This will save this translation and make it visible to everyone using that language.

![Translation Dialog Box](/_books/esp-config/localization/images/translation-dialog.png)

:::note
Under some circumstances, a string may not be presented with a green underline. In the majority of cases, these strings can still be translated in the [User Interface Translations](/esp-config/localization/user-interface-translations).
:::
<!-- References>
<!-- https://wiki.hornbill.com/index.php?title=Translation_Mode>