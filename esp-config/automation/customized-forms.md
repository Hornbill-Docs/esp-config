# Customized Forms

As well as standard capture forms that are provided with each application, customized forms can also be created. With custom forms, you can create multiple questions using different field types to capture specific information.

![Example custom capture form](/_books/esp-config/automation/images/example-custom-capture-form.png)

## Adding a customized form

To add a new customized form to a capture:

1. From an existing node, drag a new connector from one of its connection points.
1. When the left mouse button is released, a popup menu is displayed.
1. Select **Customized Form** from the popup menu.

or

1. Select an existing connector.
1. Right click on the selected connector.
1. Select **Customized Form** from the popup menu.

![Adding a customized form](/_books/esp-config/automation/images/adding-a-custom-form.png)

The new customized form will be displayed as a purple node with the label *Customized Form*. You can either double-click on the node or select the cog when hovering the mouse over the node to configure the form.

![Customized Form Node](/_books/esp-config/automation/images/custom-capture-node.png)

## Custom form properties

![Custom Form Properties](/_books/esp-config/automation/images/custom-form-properties.png)

* **Display**: The display name for the node in the intelligent capture designer.
* **Purpose**: A text field to record the purpose of the custom form (optional).

### Form Settings

* **Language**: A default language version of the custom form is provided, but you can opt to create different language versions of the custom form by selecting another available language and populating the labels and answers in different languages.
* **Form Id**: This is the unique identifier for the custom form, this can be used later to identify the answers to your questions when using the Hornbill Business Process Workflow engine. The Form Id must be at least 3 characters in length.
  :::note
  When using the [Switch Capture](/esp-config/automation/intelligent-capture-designer#switch-capture) node, Form IDs must be unique across the different captures that could be switched to. Consider naming the forms in a way that includes a reference to the capture that the form is on.
  :::
* **Form Prompt**: This is any text you wish to appear with the custom form to help identify its purpose.
* **Never Skip Form**: Setting to True will ensure that this form is never bypassed in your capture flow, even if custom questions have default values set and the questions are not set to mandatory. This will ensure the user will always be presented with the form to at least validate the default choices, or change them if required.

### Form Fields

The form fields are the questions you wish to ask on the custom form.

* You can add new questions by selecting the 'add field' button
* You can edit an existing question by selecting the note and pencil icon of an existing question
* You can delete an existing question by using the trash can icon of an existing question
* You can re-order how the questions will appear by using the up and down arrows to move the questions into the required order.

:::note
There is a maximum of 200 questions across all forms within a single capture flow that can be stored and used.
:::

#### Edit Field Settings

* **Properties Language**: If you require the questions of the custom form to be available in more than the default English language, use the **Properties Language** option to switch the configuration into the additionally required languages and set the values accordingly.  The translated values will then be presented to the user based on the language set in their profile.

##### Field Properties

Field settings are specific for each field on the custom form.

There are various field options and settings and these are explained below.

* **Field Id**: This is the unique id for the question on the custom form. This can normally be left, unless you are wanting to map the answer from this question to a custom field on a request, where a field mapping needs to be given. Read about field mappings. The Field Id must be at least 3 characters in length.
* **Data Binding**: The data binding property allows you to specify another custom form field that you want to overwrite when setting this field’s value. For example if you have a custom form with the ID *FormA* and in it a field with the ID *CustomerID*, to overwrite the value captured in that form you would set the data binding in this field to *FormA.CustomerID*.
* **Label**: This will be the label used to represent the question on the custom form.
* **Description**: You can use this field to provide hints / tips or advice on how to complete the answer to this specific question.

###### Default Flags

* **Show this field in summary panel once form is completed**: Select this option if you want the question and answer to appear on the right hand side confirmation panel during the Intelligent Capture flow.
* **This field requires a value to be provided**: Select this option if you want to make the answering of this question mandatory.
* **This field will be visible on the form**: Select this option if you want the field to be visible on the form - sometimes this is not needed, if you are passing a fixed value into a field and you want to hide this from the user.
* **This field will be read only**: Select this option if you wish to use the field to be for information only.
* **This field will be visible in read mode if it has no value**: Select this option if you would like this field to be displayed, even if there is no value stored in it. Just the label will be shown.

###### Override Flags

The **Override Flags** allows you to set the conditions under which this field will be displayed. This can be based on the answer to a question from a previous field.

* Set Flags To
  * This field requires a value to be provided
  * This field will be visible on the form
  * This field will be read only.
  * This field will be visible in read mode if it has no value.

* **If The Following Is True**: This is the section where you define your conditions. It is divided into three parts: the first is the field you want to evaluate, the second is the comparison operator, and the third is the actual value you want to use with the operator.

:::note
The list of conditions is evaluated in the order they are listed and it stops at the first condition that is evaluated as true.
:::

* Comparison operators

|Operator|Description|Expected type of value|Example values
|-|-|-|-|
|**==**|equal|number or string|"**yes**", "**5**"|
|**!=**|not equal|number or string|"**yes**", "**5**"|
|**<**|less than|number|"**5**"|
|**>**|bigger than|number|"**5**"|
|**<=**|less or equal|number|"**5**"|
|**= >**|bigger or equal|number|"**5**"|
|**is in**||comma separated number or string|"**any,of,it**", "**1,2,3**"|
|**is not in**||comma separated number or string|"**any,of,it**", "**1,2,3**"|
|**is set**||true if any value is present|
|**is not set**||true if not value present|
|**starts with**||number or string|"**Hello**", "**0**"|
|**ends with**||number or string|"**Bye!**"|
|**contains**||number or string|"**specific**", "**10**"|
|**doesn't contain**||number or string|"**specific**", "**10**"|

:::tip
Please note that not every type of value makes sense to compare with every operator. For example, for values like numbers, it's appropriate to use < or >, whereas for strings, it is better to use "starts with" or "contains."
:::

##### Field Type Settings

Select the field type that you want to use:

* **Single line text field**: Use this option if you want to present the user with a single line input box.
* **Multi line text field**: Use this option if you want to present the user with a multi-line input box.
* **Static checkbox group**: Use this option if you want the user to select one or multiple values from a definable checkbox list.
* **Dynamic checkbox group**: Use this option if you want the user to select one or multiple values from a pre-defined checkbox list, select a data provider and optionally filter the returned results.
* **Simple List**: Choose an existing simple list as your Data Provider.
* **Data Query**: Choose from a list of supplied data queries as your Data Provider (All Sites, My Sites, All Assets, Assets by Class, Assets by Type, All Users, Co-Workers, Basic Users).
* **Static drop down select box**: Use this option if you want the user to select one option from a definable select box list.
* **Dynamic drop down select box**: Use this option if you want the user to select one option from a pre-defined select box list, select a data provider and optionally filter the returned results.
* **Simple List**: Choose an existing simple list as your Data Provider.
* **Data Query**: Choose from a list of supplied data queries as your Data Provider (All Sites, My Sites, All Assets, Assets by Class, Assets by Type, All Users, Co-Workers, Basic Users).
* **Static Radioset**: Use this option if you want the user to select one option from a definable radio button set.
* **Dynamic radioset**: Use this option if you want the user to select one option from a pre-defined radio button set. Select a data provider and optionally filter the returned results
  * Simple List - Choose an existing simple list as your Data Provider
  * Data Query - Choose from a list of supplied data queries as your Data Provider (All Sites, My Sites, All Assets, Assets by Class, Assets by Type, All Users, Co-Workers, Basic Users)
* **Date Control**: Use this option if you only require the user to provide a date.
* **Date & Time Control**: Use this option if you require the user to provide both a date and time.
* **Between Date Control**: Use this option if you require the user to provide date range. This feature allows you to restrict the range to a specific set of dates using the following options:
  * "Max Allowed Days Between": This allows you to set the maximum number of days between the start and end date. For example, a value of 2 means that the end date cannot be more than 2 days after the start date.
  * "Date Range Start": This option allows you to set a relative date from the current date. For instance, a value of 0 means starting from today, 1 means starting from tomorrow, and 7 means starting from next week. Negative values can also be used to go backwards in time, such as -1 for yesterday.
  * "Date Range End": This option follows the same rules as the start date, allowing you to set a relative date from the current date.
* **Between Date & time Control**: Use this option if you require the user to provide both a date and time.
* **User group picker**: Use this option if you want the user to select a group or groups from the pre-defined organizational groupings.
* **Label**: Use this option if you want to add a separator into the questions being asked, or on the answers section of the request.
* **File Upload**: Include a field on a form that allow a user to upload a file.  Options include being able to add multiple file for a single field and allowing a user to paste content.

Different field types will have different configuration options available to them, including:

* Ability to set default values.
* Ability to define values for static checkbox, static select box, static radio set options (display name and value).
* Regex Field Validation.
