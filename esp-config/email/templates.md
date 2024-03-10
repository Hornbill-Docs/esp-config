---
layout: article-toc
---
# Email Templates
Email templates can be used to pre-populate emails with information to create a standard format for outbound emails. Emails may be sent automatically from Business Process Workflows or manually from within an app.

## Template List
The list of templates is controlled by the selection of the application that will be using the template along with the entity or business object within that application for which the template will use fields to include information from the entity when an email is sent using that template.

### Grouping
Email templates can be assigned a group using up to 3 levels. The Grouping option allows you to filter the list by these groups. When selecting a group, the list will display all templates for that group and any sub-group. The group names and assignments are all mananged within the Template Editor.

## Template Editor
The Template Editor is used to construct your email templates. Within the Editor you provide the following areas.

* **Group**<br>The Group option provides a way of organizing email templates using up to 3 levels. You can either add the template to an existing group or you can create a new group name. Groups can be used to filter the Email Template list and can help with template selection when using certain application features.

* **Name**<br>The Name provides a reference within the list of Templates. The BPM Editor and the different Apps that use email templates will also use this name to display where email template selection is available.
* **Subject**<br>Contents of the Subject of the email. Both text and fields can be used within this section.
* **Message**<br>The main body of the email. When creating or modifying an email template, the Message area includes a full editor to provide options for fonts and styling within your email.


## Fields
Each application, through the use of entity definitions defines the specific fields that are available for any given template.  Field names are generally descriptive and self-evident, and often include a short description of their purpose which you can see at the point of choosing the field(s). However, if you do need more detailed information, you should see the documentation for the specific application, as each application's entities and published email template fields are different. 

### Global Fields
As well as the application-specific fields, there are a number of general purpose fields that are always available regardless of the application or entity context, these fields are general purpose fields relating to the session of the user making use of the template.

|Field ID|Field Name|Field Group|Description|
|:--|:--|:--|:--|
|`{{DATE}}`|Current Date|-|The users unique account ID on your Hornbill instance|
|`{{TIME}}`|Current Time|-|The users unique account ID on your Hornbill instance|
|`{{instanceId}}`|Instance ID|-|The users unique account ID on your Hornbill instance|
|`{{session.userId}}`|User ID|Session|The users unique account ID on your Hornbill instance|
|`{{session.firstName}}`|First|Session|The users first name|
|`{{session.lastName}}`|Last Name|Session|The users last name|
|`{{session.name}}`|Full Name|Session|The users full name|
|`{{session.jobTitle}}`|Jon Title|Session|The users Job Title|
|`{{session.profileIcon}}`|Profile Icon|Session|The users profile Icon|
|`{{session.email}}`|E-Mail Address|Session|The users primary email address|
|`{{session.phone}}`|Phone Number|Session|The users primary contact phone number|
   

### Field Formats & Modifiers
Template Fields can be used within the Subject or Message of a template in order to have information that is stored within the related entity and be injected into the email being created from the template, as well as a number Fields related to the user making use of the template when sending a message.

* **Format**<br>Each field starts with a double opening curly brace ( {{ ) and finishes with a double closing curly brace ( }} ). Within the curly braces, the contents can be either just a data field specified by a dot (.) followed by the field name (.H_Firstname) or the data field can be preceded by an available related entity (Contact.H_firstname). The complete field will have the format {{.H_firstname}}
* **Letter Case**<br>The letter case of the fields will determine the letter case that is used in the email. For example
    * `{{.H_firstname}}` = John
    * `{{.h_firstname}}` = john
    * `{{.H_FIRSTNAME}}` = JOHN
* **Modifiers**<br>The following modifiers are used with fields and are available: For example:
    * `{{.H_firstname|upper}}` = Will force the value to uppercase i.e JOHN.
    * `{{.h_firstname|lower}}` = Will force the value to lowercase i.e john.
    * `{{.h_firstname|empty}}` = Will only show the value if it exists else the field will be removed from the output.
    * `{{.h_firstname|html}}` = Allows HTML output from a template field instead of HTML being shown as text.
    * `{{.h_firstname|wiki}}` = Allows HTML output from a template field that contains wiki markup, Currently only basic formatting (Bold, Italic, Ordered & Unordered lists) are supported.
    * `{{.datetimefield|formatLocalTime}}` = Allows formatting of datetime fields using system regional settings (system.RegionalSettings.timezone & system.RegionalSettings.dateTimeFormat), without this formatting the date time will use the DB value (UTC).

    :::tip
    Modifiers do not apply for extended fields. For example, modifiers cannot be applied (they will not work) on fields like "Customer Coworker.H_first_name"
    :::

### Controlling Field Visibility - The "empty" field Modifier
Sometimes you may want to include a field in your email template that you find under certain circumstances may not be populated. You will notice that when fields fail to find any corresponding information in the database they simply show themselves in their raw form: `{{.field}}`. This doesn't look terribly good in your otherwise beautifully prepared email templates.

Using the "empty" modifier is a simple way to guard against this situation. Adding a vertical bar followed by the the word "empty" i.e. "|empty" within the curly braces of your field will hide it if the system finds that there is no information to show. This results in: `{{.field|empty}}`.

### Field Conditions
ESP conditions are a more advanced way of controlling the visibility of fields within your email templates and they can also be applied to blocks of text too.

An ESP expression controls whether the field or specified text should be visible in the email being sent. i.e. If the expression evaluates to “True” then display the field or text. If the expression evaluates to “False” then hide the field or text completely.
Ultimately, the visibility of the field or text is dependent purely on the condition set against it. It is not dependent on whether any data exists in the database for the field to resolve.

* **What Operators can I use in my ESP Conditions?**<br>The operators "=" (equal to) and "!=" (not equal to) are supported.
* **The Co-Worker Vs Contact ESP Condition Example**<br>One common situation where the ESP expression is essential is when you want to begin your emails with “Dear [Customer]”.

As you will know by now, the customer set against a request could either be a “Co-Worker” (someone internal to your Organization) or a “Contact” (an individual external to your organization) and each of these types of user have a range of associated fields.

To configure an email template to cater for the possibility of the customer being a Co-worker or a Contact it should be set up as follows:

1. Select the desired Co-worker and Contact name fields. In this example we will be addressing the customer by first name only so we will select `{{Customer Coworker.H_first_name}}` and `{{Customer Contact.H_firstname}}`
1. Highlight the Co-Worker field and click the ESP Expression button
You will see that the “Value” field is automatically populated with the highlighted field.
1. In the “Expression” field, define the condition that you wish to control the visibility of this field. Remember, the field will only be displayed if your expression is found to be true. For the Co-worker field, we only want this to display if the customer against the request is in fact a Co-worker. This information is stored in the main request table and can be obtained using the field `{{.h_customer_type}}`. The value will be zero for a Co-worker, and one for a contact, hence the expression controlling a Co-worker field should be: `{{.h_customer_type}}` = 0
1. Click OK
1. Highlight the Contact field and click the ESP Expression button.
1. The controlling expression defined here needs to ensure the Contact field only displays if the customer against a request is indeed a contact. So using the same field as before we can set the expression as `{{.h_customer_type}}` = 1
1. Click OK

:::tip
The example described here is evaluating a field (Customer Type) that will contain a number (0 or 1). In other situations, you might want to evaluate a field that contains a word, such as `{{.H_resolvedby_teamname}}`. When doing this the field must be surrounded by single quotes e.g. `{{.H_resolvedby_teamname}}` = 'My Team'. i.e. if resolved by team name equals "My Team", show the text bound by the ESP expression.
:::

When viewing/editing and email template, any field that has a Field Expression applied is highlighted in gray.
To edit Field Expression, highlight the field and click the Edit Expression button.

1. Choose your fields and place them in the template.
1. Highlight a field and click the ESP Expression button.
1. Review the ESP Expression Properties.
1. Adding your Customer is Co-worker expression.
1. Now highlight the next field.
1. Adding your Customer is Contact expression.
1. The Gray highlighting indicates both fields now have ESP conditions controlling their visibility.