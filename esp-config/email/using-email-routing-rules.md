---
layout: article-toc
---

# Inbound Email Routing
The Email Routing Rules provide a way of automating the delivery and actions that occur on emails that are received into Hornbill. This may be simply redirecting the email message to a particular shared mailbox or applying advance operations that are provided by the different Hornbill Apps. Each Email Routing rules allow you to define expressions to verify the content of the incoming emails in order for that rule to apply.


## Email Routing Rule Form
From the list of Routing Rules there a few actions and some considerations to keep in mind.

## Switching On or Off
At the top of the list a toggle button is provided to turn the Routing Rules to being either On or Off. This setting applies to all rules in this list. For the rules to be processed, this must be set to On.

## Creating a Rule
Clicking on the + in the tool bar will allow you to create a new rule.

## Ordering
Once more than one rule has been created, the order of the rules can be changed by using the up and down arrows located on the right side of each rule. When an email is received, the routing rules will be processed in the order that they are listed, starting at rule 1. If a rule doesn't match it will then check the next rule. If no rules match the email will simply reside in the Inbox.
Note: If a rule matches, but its action fails to complete, no further rules will be checked and the rule's Fail action will be followed.

## Deleting a Rule
The Delete option in the tool bar becomes available once one or more Rules are selected in the list

## Rule Expression
Each Routing Rule requires a Rule Expression which is used to validate information held within the email. To help with setting up the Rule Expression a number of parameters have been provided in the Rule Parameters selector located at the top right of the Rule Expression field. Selecting any of these items from the list will insert that Rule Parameter into the Rule Expression field.

toAddress
toDomain
fromAddress
fromDomain
subject
body
mailbox
Information If you are manually adding Rule Parameters it is important that the correct letter case is used and it matches those provided in the Rule Parameters selector

## Rule Expression Syntax
The syntax used in the Rule Expression is similar to standard SQL syntax. String and numeric comparisons, and parentheses are all supported.

A few basic expressions to get you started can be found by showing the list of functions.

### Special Functions
Hornbill supports a number of functions that are useful for more complex expressions.


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