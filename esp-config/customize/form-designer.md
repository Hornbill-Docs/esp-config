# Form Designer
Hornbill provides a form designer which can be used to enhance the default forms of various entities. Features include the ability to manage the existing default fields, as well as providing the option to add custom fields.

To access the form designer, the logged in user must have the Form Designer role associated with their account. Users with this role will see a Design option on entity forms which can be edited.

Any changes to default fields or new custom fields added via the form designer are guaranteed through all updates to the Hornbill Service.

## Toolbar options
Across the top of the Editor there are some options to manage your design session.

* **Cancel**. Cancels your current editing and returns you to the previous screen without saving any changes.
* **Revert Back**. Reverts all changes made during the current edit to its previous state, and you remain within the editor.
* **Restore Defaults**. Restores all the fields and settings to the original or default state that was provided at the time of installation.
* **Apply Changes**. Any changes made during your edit will be saved and available for use.
* **+ (Add Custom Fields)**. By clicking on the `+` button, you can add custom fields to your form.

## Default Fields
Each form where the form designer can be used will have serveral default fields. Using the form designer, you can edit and manage the properties of these default fields, including dragging and dropping them to re-order them as needed, hiding default fields, and making inputs to fields mandatory.

## Custom Fields
If you would like to store some information within the form and there is no existing default Field available, you can add a Custom Field to the form. This is done by clicking on the + button in the toolbar.

* **Available Fields**. Each form will have several available custom fields which you can select from the drop-down.
* **Display Label**. Add a Display Label that will be visible to the users when viewing or editing this form.
* **Control Type**. A number of Control Types can be used. These include Single Line Text Field, Multi-line Text Area, Drop Down List Box, Radio Option List, Check List Box, 5 Star Rating, Single Check Box, Date Selector, Date Time Selector

::: tip
Some Control Types will provide additional Field Properties that will allow the defining of the options that accompany the Control Type.
:::

## Field Properties
Both Default and Custom Fields include a properties option. This is accessed by clicking on the Cog button displayed on each field. The available properties will vary on each field, depending on the type and the information held in that field.

* **Show the field in the form**. This will make this field available when in Edit mode on the form. This can also be enabled/disabled using the Eye icon located on the field.
* **The field value cannot be blank when saving**. Checking this option will make this field mandatory. As long as the field is blank, you will not be able to save any updates to the form.
* **The field cannot be edited**. When a field contains a value that you don't want changed, use this option to prevent editing.
* **Show the field in view mode even if the value is blank**. To keep a clean and uncluttered details section, if a field is empty, the label is not displayed. Once a field is populated, the Label and the content of the field are displayed. If you would like the label to be displayed even when the field is empty, tick this box.
* **Field Label**. This is the label that is displayed on the form. The label can be changed to suit the terminology that you prefer to use. In parentheses, the current language code is displayed. You can provide a translation for the language that you are currently using in your session.
* **Validate Input with RegEx Expression**. By including a RegEx Expression, you can control how the user inputs the information into the field. Use the ? button to open the RegEx Selector to help with building your Expression.
* **Test Regex Expression With Value**. This field lets you take your RegEx Expression for a test run to make sure that it works as expected.
* **Message to display to user when validation fails**. If a user enters a value that does not match the provided RegEx Expression, you can present them with a message. This can be used to guide them with the correct format that needs to be used.
