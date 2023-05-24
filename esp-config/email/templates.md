---
layout: article-toc
---
# Templates
Email templates can be used to pre-populate emails with information to create a standard format for outbound emails. Emails may be sent automatically from Business Process Workflows or manually from within an app.

Related Articles
Email Action Items

Template List
The list of templates is controlled by the selection of the application that will be using the template along with the entity or business object within that application for which the template will use variables to include information from the entity when an email is sent using that template.

Template Editor
The Template Editor is used to construct your email templates. Within the Editor you provide the following areas.

Name
The Name provides a reference within the list of Templates. The BPM Editor and the different Apps that use email templates will also use this name to display where email template selection is available.
Subject
Contents of the Subject of the email. Both text and variables can be used within this section.
Message
The main body of the email. When creating or modifying an email template, the Message area includes a full editor to provide options for fonts and styling within your email.
Variables
Template Variables can be used within the Subject or Message of a template in order to have information that is stored within the related entity, used in the email.

Format
Each variable starts with a double opening curly brace ( {{ ) and finishes with a double closing curly brace ( }} ). Within the curly braces, the contents can be either just a data field specified by a dot (.) followed by the field name (.H_Firstname) or the data field can be preceded by an available related entity (Contact.H_firstname). The complete variable will have the format {{.H_firstname}}
Letter Case
The letter case of the variables will determine the letter case that is used in the email. For example
{{.H_firstname}} = John
{{.h_firstname}} = john
{{.H_FIRSTNAME}} = JOHN
Global Variables
The variables are always available for use in an Email Template no matter the entity. For example
{{DATE}} = The current date in the format 2016-11-23
{{TIME}} = The current time in the format 23:53
{{instanceId}} = The id of the Hornbill instance
Modifiers
The following modifiers are used with variables and are available: For example
{{.H_firstname|upper}} = Will force the value to uppercase i.e JOHN.
{{.h_firstname|lower}} = Will force the value to lowercase i.e john.
{{.h_firstname|empty}} = Will only show the value if it exists else the variable will be removed from the output.
{{.h_firstname|html}} = Allows HTML output from a template variable instead of HTML being shown as text.
{{.h_firstname|wiki}} = Allows HTML output from a template variable that contains wiki markup, Currently only basic formatting (Bold, Italic, Ordered & Unordered lists) are supported.
{{.datetimevariable|formatLocalTime}} = Allows formatting of datetime variables using system regional settings (system.RegionalSettings.timezone & system.RegionalSettings.dateTimeFormat), without this formatting the date time will use the DB value (UTC).
Information
Modifiers do not apply for extended variables. For example, modifiers cannot be applied (they will not work) on variables like "Customer Coworker.H_first_name"
Variable Visibility
The "empty" Variable Modifier
Sometimes you may want to include a variable in your email template that you find under certain circumstances may not be populated. You will notice that when variables fail to find any corresponding information in the database they simply show themselves in their raw form: {{.variable}}. This doesn't look terribly good in your otherwise beautifully prepared email templates.

Using the "empty" modifier is a simple way to guard against this situation. Adding a vertical bar followed by the the word "empty" i.e. "|empty" within the curly braces of your variable will hide it if the system finds that there is no information to show. This results in: {{.variable|empty}}.

ESP Conditions
ESP conditions are a more advanced way of controlling the visibility of variables within your email templates and they can also be applied to blocks of text too.
An ESP expression controls whether the variable or specified text should be visible in the email being sent. i.e. If the expression evaluates to “True” then display the variable or text. If the expression evaluates to “False” then hide the variable or text completely.
Ultimately, the visibility of the variable or text is dependent purely on the condition set against it. It is not dependent on whether any data exists in the database for the variable to resolve.
What Operators can I use in my ESP Conditions?
The operators "=" (equal to) and "!=" (not equal to) are supported.
The Co-Worker Vs Contact ESP Condition Example
One common situation where the ESP expression is essential is when you want to begin your emails with “Dear [Customer]”.

As you will know by now, the customer set against a request could either be a “Co-Worker” (someone internal to your Organisation) or a “Contact” (an individual external to your organisation) and each of these types of user have a range of associated variables.

To configure an email template to cater for the possibility of the customer being a Co-worker or a Contact it should be set up as follows:

Select the desired Co-worker and Contact name variables. In this example we will be addressing the customer by first name only so we will select {{Customer Coworker.H_first_name}} and {{Customer Contact.H_firstname}}
Highlight the Co-Worker variable and click the ESP Expression button
You will see that the “Value” field is automatically populated with the highlighted variable.
In the “Expression” field, define the condition that you wish to control the visibility of this variable. Remember, the variable will only be displayed if your expression is found to be true. For the Co-worker variable, we only want this to display if the customer against the request is in fact a Co-worker. This information is stored in the main request table and can be obtained using the variable {{.h_customer_type}}. The value will be zero for a Co-worker, and one for a contact, hence the expression controlling a Co-worker variable should be: {{.h_customer_type}} = 0
Click OK
Highlight the Contact variable and click the ESP Expression button.
The controlling expression defined here needs to ensure the Contact variable only displays if the customer against a request is indeed a contact. So using the same variable as before we can set the expression as {{.h_customer_type}} = 1
Click OK

Hornbill Hint: The example described here is evaluating a variable (Customer Type) that will contain a number (0 or 1). In other situations, you might want to evaluate a variable that contains a word, such as {{.H_resolvedby_teamname}}. When doing this the variable must be surrounded by single quotes e.g. '{{.H_resolvedby_teamname}}' = 'My Team'. i.e. if resolved by team name equals "My Team", show the text bound by the ESP expression.

When viewing your email template, any variable currently under the control of an ESP expression is highlighted in Grey.
To edit an ESP Expression, highlight the variable and click the ESP Expression button.


1) Choose your variables and place them in the template.

 

2) Highlight a variable and click the ESP Expression button.

 

3) Review the ESP Expression Properties.

 

4) Adding your Customer is Co-worker expression.

 

5) Now highlight the next variable.

 

6) Adding your Customer is Contact expression.

 

7) The Grey highlighting indicates both variables now have ESP conditions controlling their visibility.