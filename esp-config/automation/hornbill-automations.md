# Hornbill Automation

A Hornbill automation is a definable node that can be added to a workflow to perform a number of tasks. Additional Hornbill automations are provided by each installed application. Any application that utilizes workflows can access and use the Core Hornbill automations.

## Adding a Hornbill automation

When viewing a workflow canvas, there are a couple of ways to add a Hornbill automation.

* **Add after an existing node** - Drag an arrow from an existing workflow node. When you let go of the mouse button, you are presented with a list of nodes that you can select from. Select Hornbill automation.
* **Add between existing nodes** - Click on an arrow between two existing nodes. Once the arrow is selected, right-click on the arrow and select Add node between connected nodes. Select Hornbill automation from the list of available nodes.

Hornbill automations can be easily identified in a workflow as a light blue rectangular node.

![Hornbill Automation](/_books/esp-config/images/workflow-hornbill-automation.png)

### Attributes

* **Display** - The text displayed within the node on the canvas.  This text is also used in the [variable picker](/esp-config/automation/variable-picker). Use text that describes the purpose of the node.
* **Application** - The name of the application that provides the automation.
* **Scope** - Application or Entity. Automations are broken down between general application automations and those that are for a specific entity.
* **Type** - Each type contains a collection of related tasks.
* **Task** - The task that will be automated. Each task contains several options that are used to fulfill the automation.
* **Result Reference** - This is a unique identifier for the node. This is used in the construction of a variable that is selected using the [variable picker](/esp-config/automation/variable-picker). If there are multiple nodes in a workflow that perform the same task, the result reference makes sure that the correct node is being referenced.

## Hornbill automation help

Each automation includes a help option ![Help Button](/_books/esp-config/images/workflow-help-button.png) that provides information on all of the inputs, outputs, and outcomes for the selected task.

![Workflow Automation Help](/_books/esp-config/images/workflow-automation-help.png)

## Contact

The contact automation provides the ability to create and update [contact records](/esp-config/guest-access/contacts). This can be used in environments where the creation and management of contacts is required through automated workflows rather than being done manually. Automating the creation and management of contacts can help assure consistency.

![Contact Automation](/_books/esp-config/images/workflow-contact.png)

### Contact tasks

* **Create Contact** - Create a new contact record.
* **Archive Contact** - Archive an existing contact record.
* **Get Contact** - Get information that is stored in the contact's record so that it can be used elsewhere in the workflow.
* **Portal Access** - Set the status of the contact's access to the [Customer Portal](/esp-config/customize/customer-portal/configure-customer-portal) to approved, suspended, or none.
* **Set Contact Two-Factor Authentication** - Enable two-factor authentication for a contact and specify if email or the Microsoft Authenticator app is used.
* **Unarchive Contact** - Make an archived contact record active again.
* **Update Contact** -  Update the information held in a contact record.

## Location

The location automation provides the ability to create and update [locations](/esp-config/organizational-data/locations).

![Location Automation](/_books/esp-config/images/workflow-location.png)

### Location tasks

* **Create** - Add a new location.  
* **Update** - Update an existing location.
* **Delete** - Delete an existing location.

### Options

#### Mandatory Options

* **Name** - A name must be provided for both the create and update automations. The name is the full display name of the location and not the numerical ID.  The name is a unique value so that no two locations can be named the same.  

## Groups & Teams

The Groups & Teams automation can be used to bring back information about a single [group or team](/esp-config/organizational-data/organization#how-groups-are-used).  This can be particularly useful for accessing information held in the custom attributes. 

![Groups & Teams Automation](/_books/esp-config/images/workflow-groups-and-teams.png)

### Available tasks

* **Get Group/Team Details** - Retrieve information held in a particular group or team.

### Options

#### Mandatory Options

* **ID**. Either the ID or URN of a group or team needs to be provided.

## Email

![Email Automation](/_books/esp-config/images/workflow-direct-message.png)

### Email tasks

* **Direct Message Send** - This automation is used to send a mail message directly to one or more recipients without going through a shared or personal mailbox. For this to be used, an [Email Domain](/esp-config/email/email-domains) must be set up. Emails that have been sent using this automation can be viewed in the list of [Direct Outbound](/esp-config/email/direct-outbound) emails.

### Options

#### Mandatory options

* **From Address**. As a direct send email does not go through a mailbox, a sender address is not automatically applied, and one must be provided.  Direct send emails are commonly used for notifications or one-way communications, and a noreply email address is often used.
* **Subject** - The subject of the email.
* **Body** - The body of the email.

## Users

![Users Automation](/_books/esp-config/images/workflow-user-automation.png)

### User tasks

* Add User to Organization
* Add User to a Public Workspace
* Add Role to User
* Archive User
* Create New User
* Create New User From Template
* Delete User
* Get User Details
* Get User Custom Attributes
* Get User Groups
* Get User Manager Details
* Update User Profile
* Remove User From All Organizations
* Remove User From Organization
* Remove User from a Public Workspace
* Remove Role from User
* Update User Status
* Update User Account

## Utility

### Get Email Addresses For Group Members

This utility will output a list of email addresses for users who belong to an organizational group. This list can then be used in other automations, such as sending an email.
:::note
Any user who is part of the group but doesn't have an email address set on their profile will be excluded from the output.
:::

![Get Email Addresses For Group Members](/_books/esp-config/images/workflow-utility-get-group-email-addresses.png)

#### Options

* **Group** - This is a mandatory option that needs to be set to Manual or Variable.  Setting to manual provides a picklist to select from.  Setting to variable requires a variable that contains the group ID.
* **User Type** -  You can select between User, Basic, or All.  If a group contains both Full and Basic users, this will allow you to be selective of which user type you want to include.

#### Output

* **Email Addresses** - This output provides a comma-separated list of email addresses.
