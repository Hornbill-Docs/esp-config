---
layout: article-toc
---

# Inbound Routing Rules
The Routing Rules provide a way of automating the delivery and actions that occur on emails that are received into Hornbill. This may be simply redirecting the email message to a particular shared mailbox or applying advanced operations that are provided by the different Hornbill apps. 

Each Routing rule allows you to define expressions to verify the content of the incoming emails in order for that rule to apply. 

## Before You Begin
* At least one [Shared Mailbox](/esp-config/email/shared-mailboxes) needs to be setup.
* Be familiar with [ExpressLogic Expressions](/esp-fundamentals/reference-guides/express-logic).

## Routing Rule List
### Switching On or Off
At the top of the list, a toggle button is provided to turn the Routing Rules on or off. This setting applies to all rules in this list. For the rules to be processed, this must be set to `ON`.

![On/Off Toggle](_books/esp-config/email/images/on-off-toggle.png)

### Creating a Rule
Clicking on the + in the toolbar will allow you to create a new rule.

### Ordering
Routing rules are processed in the order that they are listed, starting at the top.
* The order can be changed by dragging and dropping a rule to a different position. 
* If a rule doesn't match it will then check the next rule in the list. 
* If no rules match, the email will be sent to the inbox of the [Shared Mailbox](/esp-config/email/shared-mailboxes) that matches the `To` address.

:::tip
If a rule matches, but its action fails to complete, no further rules will be checked and the rule's fail action will be followed.
:::

### Deleting a Rule
The Delete option in the tool bar becomes available when one or more rules are selected in the list. Deleting a rule will permanently remove the rule.


## Rule Expression Syntax
Each rule requires an expression which is used to validate information held within the email. To help with setting up the rule expression a number of parameters have been provided in the Rule Parameters selector located at the top right of the Rule Expression field. 

Selecting any of these items from the list will insert that parameter into the Rule Expression field.

|Name|Description|
|:--|:--|
|`toAddress`|The full email address to which the message being processed was sent to, for example `support@hornbill.com`. <br><br>It is possible that the email was sent to more than one recipient, in this case, this variable will contain a string of comma-separated addresses, for example `support@hornbill.com, info@hornbill.com`.  In this case you may want to adopt a simple wildcard matching approach using the LIKE operator, for example `toAddress LIKE '%support@hornbill.com%'` would match, even if there are multiple addresses present.|
|`toDomain`|The email domain to which the message being processed was sent to, for example `hornbill.com`. <br><br>It is possible that the email was sent to more than one recipient, in this case this variable may contain a string of comma-separated domains, for example `hornbill.com, google.com`.  In this case you may want to adopt a simple wildcard matching approach using the LIKE operator, for example `toDomain LIKE '%hornbill.com%'` would match, even if there are multiple domains.|
|`ccAddress`|The full email address to which the message being processed was cc'd to, for example `support@hornbill.com`.  <br><br>It is possible that the email was cc'd to more than one recipient, in this case this variable will contain a string of comma-separated addresses, for example `support@hornbill.com, info@hornbill.com`.  In this case you may want to adopt a simple wildcard matching approach using the LIKE operator, for example `toAddress LIKE '%support@hornbill.com%'` would match, even if there are multiple addresses.|
|`ccDomain`|The email domains to which the message being processed was cc'd to, for example `hornbill.com`. <br><br>It is possible that the email was sent to more than one recipient, in this case this variable may contain a string of comma-separated domains, for example `hornbill.com, google.com`.  In this case you may want to adopt a simple wildcard matching approach using the LIKE operator, for example `toDomain LIKE '%hornbill.com%'` would match, even if there are multiple domains.|
|`fromAddress`|The full email address of the person who sent the message, for example `joe.bloggs@hornbill.com`|
|`fromDomain`|The full email domain of the person who sent the message, for example `hornbill.com`|
|`subject`|The message subject text|
|`body`|The message body text. If the message was sent as HTML, this will be html-stripped text string.|
|`mailbox`|The name of the mailbox on Hornbill to which the toAddress email was matched|

:::important
These parameter names are case-sensitive. 
:::

### Example Expressions

|Operator|Example|
|-|-|
|LIKE|subject LIKE '%abc'<br>subject LIKE 'xyz%'<br>subject LIKE '%mno%'|
|NOT|subject != 'abc'|
|NOT IN|subject NOT IN ('abc', 'zyx')|
|IN|subject IN ('abc', 'mno', 'xyx')|
|=|subject = 'abcd'|

### ExpressLogic
Routing rules use Hornbill's ExpressLogic Expression engine for performing logical expressions for rule matching. You can see a detailed [ExpressLogic Reference Guide](/esp-fundamentals/reference-guides/express-logic) to learn more about the syntax, functions, and general expression capabilities used in Hornbill.

In addition to the standard expression functions made available by the ExpressLogic expression engine, the following functions are available to help with rule expressions.
|Function|Description|
|:--|:--|
|MESSAGE_HEADER|Return the value of any email message header present in the email message being evaluated. If header is not present this will return NULL. <br><br>`MESSAGE_HEADER('X-Header-Name')`<br><br>For example:-<br><br>`MESSAGE_HEADER('MessageID') LIKE '%hornbill.com%`<br><br><small>*Available in platform build 3801 onwards</small>|

## Use Mailbox
This option provides the simple routing of incoming emails to a particular Shared Mailbox.

### Mailbox
From the list of available Shared Mailboxes, select the mailbox that you wish emails that match the Rule Expression to be routed to.

### Folder
Select the folder within the selected Shared Mailbox for email to be stored in. This list of folders include the Inbox, Deleted Items, and any custom folder that has been added to the selected Shared Mailbox.

## Use Operation
Each Hornbill App can provide Operations that provide advanced processing of emails.

### Application
Select an App to view the available operations for that particular App

### Operation
Select the operation that you wish to perform if your Rule Expression matches

### Target Folder Success
On a successful Rule Expression match the folder you would like the email routed to

### Target Folder Failure
In the case of a rule match but action failure the folder you would like the email routed to

### Reference
This field can be used by the selected operation in order to correctly process the selected Operation. Refer to the application specific documentation to determine if this is required.

## Service Manager Settings
When setting up Operations in the context of Service Manager you will need to set up default values for calls to be logged against.


What Actions Can be Performed based on a Matching Rule?
Within Hornbill you can automate the following actions

Routing of an email to a specified Mailbox and folder within that mailbox
Log a new Incident
Update an existing Incident
Log a new Service Request
Update an existing Service Request
::: note
For logOrUpdateIncident, logOrUpdateServiceRequest and updateRequest operations the Reference field is a mandatory parameter. You will need to specify the Regex Syntax that matches your (call) reference in the email's Subject. E.g. for the standard out-of-the-box reference use: [a-zA-Z]{2}[0-9]{8}
:::