# Hornbill Automations
A Hornbill automation is a definable automated task that will occur within the workflow. The following Hornbill automations are included with the Hornbill platform.  Additional automations are provided by each installed application that uses workflows. 

## Adding a Hornbill automation
When viewing a workflow canvas, there are a couple of ways to add a Hornbill automation.

* **Add after existing node**. Drag an arrow from an existing workflow node. When you let go of the mouse button, you are presented with a list of nodes that you can select from. Select Hornbill automation.

* **Add between existing nodes**. Click on an arrow between two existing nodes. Once the arrow is selected, right-click on the arrow and select Add node between connected nodes. Select Hornbill automation from the list of available nodes.

Hornbill automations can be easily identified in a workflow as a light blue rectangular node.

![Hornbill Automation](/_books/esp-config/images/workflow-hornbill-automation.png)

## Hornbill automation help
![Help Button](/_books/esp-config/images/workflow-help-button.png)

Each automation includes a help option  that provides information on all of the inputs and outputs for each of the available tasks. 
 
## Location
The location automation provides the ability to create and update [locations](/esp-config/organizational-data/locations).

![Location Automation](/_books/esp-config/images/workflow-location.png)

### Available tasks
* **Create**. Add a new location.  
* **Update**. Update an existing location.

### Options
#### Mandatory Options
* **Name**. A name must be provided for both the create and update automations. The name is the full display name of the location and not the numerical ID.  The name is a unique value so that no two locations can be named the same.  


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
