---
layout: article-toc
---
# User Availability Status
These states are available to a user who can select a suitable state from their User Profile menu to make other users aware of their availability.

## Tool Bar
* **Language**<br>From the language selector, you can chose a language that you would like to view or provide translations for. Translations are displayed in the UI Display column.
* **Add**<br>Use this button to add a new state to the list
* **Settings**<br>Control the visibly of this feature
    * **Enable - Without Time Recording**<br>Only display the state
    * **Enable - With Time Recording**<br>Include the time that the state was selected
    * **Disable Feature**<br>Turn off the ability for users to select their availability state

## Availability State List
* **Status**<br>The name of each of the available states
* **UI Display**<br>Shows the translation for the currently selected language. To update the translation, simply click on the text and provide a new translation to match the language selected in the tool bar.
* **In Use**<br>Enable or disable any of the available states. Default States cannot be deleted, but they can be disabled if they are not required
* **Present At Work**<br>if set, the user is present at work in your normal working environment, as opposed to being, for example, out in their car traveling to a client site.
* **Is Working Time**<br>This status indicates the user is in normal working time or not. They can be present at work, but out of working time, for example, They are staying late for some non-work-related reason.
* **On Call**<br>The user is on call, meaning they are available for on-call duties, they may or may not be present in their normal working environment, and they may or not be in their normal working time
* **Do Not Disturb**<br>The user might be at work, in working time, on-call or any combination thereof, but they are not to be disturbed. Having this selected will display the availability status in red

:::tip
**Reporting** - The above information regarding the changes in state and the types of states can be found in the h_sys_accounts_status_log table
:::