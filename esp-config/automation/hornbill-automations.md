# Hornbill Automations
A Hornbill Automation is a definable automated task that will occur within the workflow. The available Hornbill Automations are provided by each application that uses Workflows.

## Adding a Hornbill Automation
When viewing a workflow canvas, there are a couple of ways to add a Hornbill Automation.

* **Add after existing node**. Drag an arrow from an existing workflow node. When you let go of the mouse button, you are presented with a list of nodes that you can select from. Select Hornbill Automation

* **Add between existing nodes**. Click on an arrow between two existing nodes. Once the arrow is selected, right-click on the arrow and select Add node between connected nodes. Select Hornbill Automation from the list of available nodes.

Hornbill Automations can be easily identified in a workflow as a light blue rectangular node.

## Utility
### Get Email Addresses For Group Members
This utility will output a list of email addresses for users that belong to an organizational group. This list can then be used in other automations such as sending an email.
:::note
Any user who is part of the group but doesn't have an email address set on their profile will be excluded from the output.
:::

![Get Email Addresses For Group Members](/_books/esp-config/images/workflow-utility-get-group-email-addresses.png)

#### Options
* **Group**. This is a mandatory option that needs to be set to Manual or Variable.  Setting to manual provides a picklist to select from.  Setting to variable requires a variable that contains the group ID.
* **User Type**.  You can select between User, Basic, or All.  If a group contains both Full and Basic users, this will allow you to be selective of which user type you want to include.

#### Output
* **Email Addresses**. This output provides a comma seperated list of email addresses.
