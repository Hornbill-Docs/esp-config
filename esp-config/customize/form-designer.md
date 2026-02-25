# Form designer

Hornbill provides a form designer to customize the default forms of various entities. You can use this tool to manage existing default fields and add custom fields.

To use the form designer, your account must have the Form Designer role. When you have this role, a **Design** option appears on entity forms that you can edit.

Any changes to default fields or new custom fields persist through all Hornbill updates.

## Toolbar options

The toolbar at the top of the editor contains options to manage your design session.

* **Cancel**: Discards your current edits and returns you to the previous screen.
* **Revert Back**: Undoes all changes made during the current session while keeping the editor open.
* **Restore Defaults**: Resets all fields and settings to the original state provided during installation.
* **Apply Changes**: Saves your edits and makes them available for use.
* **+ (Add Custom Fields)**: Opens the menu to add new custom fields to your form.

## Default fields

Every form includes several default fields. You can use the form designer to manage these fields by performing the following actions:

* Drag and drop fields to reorder them.
* Hide default fields that you do not need.
* Set fields as mandatory.

## Custom fields

If you need to store information that does not fit into a default field, you can add a custom field. To start, select the **+** button in the toolbar.

* **Available Fields**: Select a field from the drop-down menu. Each form has a specific set of available custom fields.
* **Display Label**: Enter the label that users see when they view or edit the form.
* **Control Type**: Select the interface element for the field. Options include:
  * Single Line Text Field
  * Multi-line Text Area
  * Drop Down List Box
  * Radio Option List
  * Check List Box
  * 5 Star Rating
  * Single Check Box
  * Date Selector
  * Date Time Selector

Note: Some control types provide additional field properties to define specific options for that element.

## Field properties

Both default and custom fields have a properties menu. To access these settings, select the **Cog** icon on the specific field. Available properties vary based on the field type and the data it holds.

* **Show the field in the form**: Displays the field when the form is in Edit mode. You can also toggle this using the **Eye** icon on the field.
* **The field value cannot be blank when saving**: Makes the field mandatory. Users cannot save the form if this field is empty.
* **The field cannot be edited**: Prevents users from changing the value in the field.
* **Show the field in view mode even if the value is blank**: Displays the field label even if the field contains no data. By default, Hornbill hides empty fields to keep the interface clean.
* **Field Label**: Sets the text displayed on the form. You can customize this to match your preferred terminology. The current language code appears in parentheses. You can provide translations for the language used in your current session.
* **Validate Input with RegEx Expression**: Restricts user input based on a Regular Expression. Select the **?** button to open the RegEx Selector for assistance.
* **Test Regex Expression With Value**: Allows you to test your RegEx Expression to ensure it functions correctly.
* **Message to display to user when validation fails**: Sets the error message a user sees if their input does not match the RegEx Expression. Use this to guide users toward the correct format.
