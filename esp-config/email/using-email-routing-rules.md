---
layout: article-toc
---

# Inbound Routing Rules
The Routing Rules provide a way of automating the delivery and triggering automated actions that occur on receipt of an email received into Hornbill.  When an email is received, and a matching rule is found, the rule can perform an action, essentially allowing you to hook the mail router and perform a more customized action. This may be simply redirecting the email message to a particular shared mailbox and/or a folder, or triggering more advanced email routing rule extensions that are provided by the different Hornbill applications. 

## Before You Begin
* You should be generally familiar with the way an email flows through Hornbill, in particular the shared mailbox functionality. 
* At least one [Shared Mailbox](/esp-config/email/shared-mailboxes) needs to be setup.
* Be familiar with [ExpressLogic Expressions](/esp-fundamentals/reference-guides/express-logic).

## Routing Rule List

### Switching On or Off
At the top of the list, a toggle button is provided to turn the Routing Rules on or off. This setting applies to all rules in this list. For any rules to be processed, this option must be set to `ON`.

![On/Off Toggle](/_books/esp-config/email/images/on-off-toggle.png)

### Creating a Rule
Clicking on the + in the toolbar will allow you to create a new rule.

### Ordering
Routing rules are processed in the order that they are listed, starting at the top. Once a rule is matched, the rule action is carried out, and then rule processing for this message completes. 

:::note
Only the first rule that matches the incoming message will be fired, this is why it is important that you have control over the order of the rules.
:::

* The order can be changed by dragging and dropping a rule to a different position. 
* If a rule doesn't match it will then check the next rule in the list. 
* If no rules match, the email will be sent to the inbox of the [Shared Mailbox](/esp-config/email/shared-mailboxes) that matches the `To` address.

:::tip
If a rule matches, but its action fails to to execute, no further rules will be checked, and the rule's fail action will be followed.
:::

### Deleting a Rule
The Delete option in the tool bar becomes available when one or more rules are selected in the list. Deleting a rule will permanently remove the rule.


## Rule Expression Syntax
Each rule uses an expression to match information found within the email message being processed. Information from the email message is made accessible to the expression processor as variables. For convenience, these variables are available in the editor when typing, you will see matching variable names being presented.  You can also look up the variable names in the popup help next to the expression field.  

Selecting any of these variables from the list by clicking or using the arrow keys, will insert that variable into the Rule Expression field. 

The following table lists the available variables and their purpose: -

|Variable|Description|
|:--|:--|
|`toAddress`|The email address(es) to which the message was sent.<br><br>If the email was sent to multiple recipients, this variable will contain a comma-separated list of all the addresses (e.g. support@hornbill.com, info@hornbill.com). When including the toAddress variable in an expression, the LIKE operator should be used. For example, the expression `toAddress LIKE '%support@hornbill.com%'` would match, even if there are multiple addresses.|
|`toDomain`|The email domain(s) to which the message sent.<br><br>If the email was sent to multiple recipients, this variable will contain a comma-separated list of all the domains (e.g. `hornbill.com, google.com`).  When including the toDomain variable in an expression, the LIKE operator should be used. For example, the expression `toDomain LIKE '%hornbill.com%'` would match, even if there are multiple domains.|
|`ccAddress`|The CC email address(es) to which the message was sent.<br><br>If the email was sent to multiple CC recipients, this variable will contain a string of comma-separated addresses (e.g. `support@hornbill.com, info@hornbill.com`).  When including the ccAddress variable in an expression, the LIKE operator should be used. For example, the expression `ccAddress LIKE '%support@hornbill.com%'` would match, even if there are multiple addresses.|
|`ccDomain`|The CC email domain(s) to which the message was sent.<br><br> If the email was sent to multiple CC recipients, this variable will contain a string of comma-separated domains (e.g.  `hornbill.com, google.com`). When including the ccDomain variable in an expression, the LIKE operator should be used. For example, the expression`ccDomain LIKE '%hornbill.com%'` would match, even if there are multiple domains.|
|`fromAddress`|The full email address of the person who sent the message, for example `joe.bloggs@hornbill.com`|
|`fromDomain`|The email domain of the person who sent the message, for example `hornbill.com`|
|`subject`|The message subject text|
|`body`|The message body text. If the message was sent as HTML, this will be a html-stripped text string.|
|`mailbox`|The name of the mailbox on Hornbill to which the toAddress email was matched|

:::important
These variable names are case-sensitive when you reference them in your expressions. 
:::

### Simple Example Expressions

|Operator|Example|
|-|-|
|LIKE|subject LIKE '%abc'<br>subject LIKE 'xyz%'<br>subject LIKE '%mno%'|
|NOT LIKE|subject NOT LIKE '%abc'<br>subject NOT LIKE 'xyz%'<br>subject NOT LIKE '%mno%'|
|NOT|subject != 'abc'|
|NOT IN|subject NOT IN ('abc', 'zyx')|
|IN|subject IN ('abc', 'mno', 'xyx')|
|=|subject = 'abcd'|

### ExpressLogic
Routing rules use Hornbill's ExpressLogic Expression engine for evaluating the rule expressions. You can see a detailed [ExpressLogic Reference Guide](/esp-fundamentals/reference-guides/express-logic) to learn more about the syntax, functions, and general expression capabilities used in Hornbill.

In addition to the standard helper functions made available by the ExpressLogic expression engine its self, the following additional email-specific functions are available to help with rule expressions.
|Function|Description|
|:--|:--|
|MESSAGE_HEADER|Return the value of any email message header present in the email message being evaluated. If header is not present this will return NULL. <br><br>`MESSAGE_HEADER('X-Header-Name')`<br><br>For example:-<br><br>`MESSAGE_HEADER('MessageID') LIKE '%hornbill.com%`|


## Routing Rule Action
When a rule is triggered it can perform an action. The following actions are available for use

### Action: Disabled
The rule is disabled and will not be processed, and no action will be triggered.

### Action: Forward to Mailbox/Folder
You can control which mailbox and which folder the email message is delivered to.  When you select this Action option, the following action-specific fields will be available: -

* __Mailbox__:  A drop down list of available shared mailboxes
* __Folder__: Once a 'mailbox' is presented, this field will provide a drop-down list of folders available. 

### Action: Trigger Application Logic
You can trigger a specific function provided by any application that implements email routing rule custom logic to process the message in a way that is specific to that application. When this option is selected the following fields will be available: -

* __Application__: A drop down list of applications that have Email Routing Rule actions defined
* __Operation__: A dropdown list of available inbound routing rule functions available for the selected application
* __Target Folder Success__: The specified folder to deliver the message to if the operation was successful (see note below about setting the folder name here).
* __Target Folder Failure__: The specified folder to deliver the message to if the operation failed. (see note below about setting the folder name here).
* __Custom Field__: The field called Resource is a field that is customized by different operations, this is not really describable here, you need to refer to the application-specific documentation for more details.
* __Mark as Read on Success__: If enabled, this will mark the message as read if the FlowCode action completes successfully.  

:::note
__Folder Names__: The Trigger Application Logic action, at configuration time, does not know what the name of the target mailbox will be, the mailbox is determined at runtime based on the incoming email To address and the target mailbox that matches that address. For this reason, its not possible to select specific folders, instead you need to type in the name of the folder, and the system will resolve that name to the correct folder in the mailbox that will receive the message.  If you leave this field blank, or, if the folder name you specify does not match a folder (an exact folder name match must occur), then the default target folder will be used.  This means for successful processing the message will be moved to the __Deleted Items__ folder, and for failed actions, the message will be delivered to the __Inbox__ folder.
:::  
