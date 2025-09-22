# Custom Buttons
Custom Buttons can be added to the user interface on several entities, such as contact and company records, to extend the available options and perform unique actions on the entity.

Custom buttons can be configured to allow one of three options. 

* Open a URL.
* Open a pop-up.
* Run an Auto Task Process.

Custom Buttons can be personalized with descriptions, icons, tooltips, and optionally can be set to only show if a set of rules is met.

## Before you begin
To work with custom buttons the following roles need to be considered.
* **Form Designer**. A user will need this role to be able to configure and manage custom buttons. 
* **Business Process Manager**. A user will need this role to be able to link an Auto Task process to a custom button.

## Configuring Custom Buttons
### Creating a Custom Button
Entities that support a custom button will include a cog icon on the left-hand side of the title bar.  Click on this cog to add a new custom button.
* **Label**. Provide a label for the new custom button.
* **Icon**. Optionally choose an icon to represent and sit alongside the custom button label on the entity form.
* **Color**. Choose a background color for the custom button.
* **Tooltip**. Optionally provide a more detailed explanation for the custom button. This will be displayed when a user hovers over the custom button.

#### Show button if...
By default, the custom button will appear on all forms used by the entity. Rules can be added to the *The Show button if* option to control when the button is displayed.  
* The available rules will be relevant to the entity against which you are adding the custom button.
* When multiple rules are used, all rules must be met for the button to be displayed.

### Action
Each custom button can be configured to be one of the following:

### Open URL
* Add a URL that you wish to launch from the custom button. 
* Include variables from the entity to help construct the URL.
* The URL will open a new browser tab to display the page.

### Popup
* Add a URL that contains embeddable content.
* A popup (iframe) containing the content will be displayed, keeping the user on the page from where it was opened.

:::tip
3rd party websites are available to test if a URL can be embedded in an iframe.
:::

### Auto Task
* Select the Auto Task Process that you wish to be invoked and executed when the custom button is selected.

#### Response
* **Display Autotask progress in timeline**. Select this option if you want a post to be added to the entity's timeline to audit the running of the Auto Task process and its progress and success.
* **Open popup with Autotask progress**. Select this option if you want a popup to display when the custom button is selected, and to show the user the progress of the executed Auto Task process.

## Custom Button Groups
Custom button groups allow you to group together related custom buttons that will appear together in a drop-down. 

![Custom Button Groups](/_books/esp-config/images/custom-button-groups.png)

* **Adding groups**. Click on `Add Button Group` and a new group will be added.
* **Naming a group**. Click on the edit icon for the group, modify the name, and press `Enter` on the keyboard.
* **Moving groups**.  The order that the groups are displayed can be changed by using the drag and drop option to the left of the group title.
* **Moving buttons**. Each button can be moved between groups by using the drag and drop option to the left of the button title.

If the number of buttons and drop-down groups exceed the available space, a single drop-down menu containing all the groups and non-grouped buttons will be used.

:::tip
The label *Custom Buttons* that is displayed when button groups are collapsed into a single drop-down menu or when grouping is not used can be renamed using [translations](/esp-config/localization/user-interface-translations). Changing this will apply to all entities where custom buttons are used. Ideas for naming this button may include *Menu*, *Options*, *Actions*, or *Advanced Actions*.
:::  