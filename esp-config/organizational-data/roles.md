---
layout: article-toc
---
# User roles
A Role is a collection of rights that allow a user to perform actions in Hornbill. Hornbill comes with a range of roles ready for you to assign to your users and custom roles can be created to meet your specific needs.

In addition to platform roles, each application comes with roles specifically designed to govern access to that application.
* [Service Manager User Roles](/servicemanager-config/setup/service-manager-roles)

## Topics covered
* Describing the different types of roles.
* The different ways to assign roles to users.
* How roles can affect application subscriptions.
* How to create a custom role.

## Before you begin
* Users with the Admin or Super User role can manage roles
* The rights Manage Role, Create Role, Delete Role, and Update Role are available for custom roles.


## Role types
Two types of Roles exist within Hornbill, Security Roles and Assignment Roles:

* **Security roles**<br>Security roles are used to control access to Hornbill through the use of rights. Security roles include a [Privilege Level](/esp-config/organizational-data/roles#privileges) which determines the level of access provided to users that are assigned to the role.
* **Assignment roles**<br>Assignment roles provide restrictions on the assignment of activities. For example, when configuring a Human Task node within a workflow, it is possible to assign that task to a role. This is especially useful if you wish to restrict the assignment of an activity to several users within a particular group or if you want to expose this activity to a selection of users across multiple groups.
It is also possible to share certain items based on an assignment role. One example is Dashboards. Assignment roles can only be associated with application Users.

## Privileges
Security roles use the following privileges to control the level of access for a user that has been assigned to the role.

|Privilege Level|Description|
|-|-|
|None|This privilege level has no privileges assigned.|
|Guest|This is the privilege level applied to any guest account login via a customer/external portal session.|
|Basic|This privilege level is associated with basic user accounts. The basic user privilege level provides very limited access to the Hornbill platform, typically this type of user would be an employee that does not use Hornbill on a day-to-day basis, but uses the Employee portal to access services being provided.|
|User|This privilege level is typically associated with a normal user account.|
|Admin|This privilege level is in effect a ‘super user’ account. This privilege level is used sparingly, and should not be used for day to day user accounts.|

:::tip
A user's overall privilege level is determined by the highest privilege level of all their combined roles.
:::

## System roles
There are a number of roles that are provided with Hornbill.  These roles are read-only and contain a set rights for performing a particular set of tasks.  Additional rights cannot be added.    

System roles can be easily identified in the list of roles by the closed padlock icon.

## User created roles
If the roles that come with Hornbill do not meet your specific needs, you can create your own roles.

### Creating a custom role
1. Open Configuration
1. Select where the new role will be created (either Platform Configuration or a specific Hornbill App) from the drop down menu.
1. Select `Roles` in the left-hand navigation panel.
1. Select `+ Create New Role` from the top right-hand toolbar.
1. Provide a Role ID (must be unique), Privilege Level (only required when creating a security role), Type, and description.

:::tip
1. If you create a role under the platform configuration, you can add or update the application context or tie the role to a Hornbill Shared Mailbox.
1. If you create a role under an application configuration you cannot assign it to other applications or mailboxes.
1. Users can be allocated subscriptions through role assignments. If you assign a user to an application role that has a privilege level of `user` a subscription will be allocated to that user when they next log in.
:::

### System and application rights
* **System Rights**<br>All roles have the option to add system rights.
* **Application Rights**<br>This will only be available if the role is associated to an application. Only the rights for the associated application will be available.

<!--
## System Rights
### Accounts
|Name|Description|
|-|-|
|Manage Roles||
|Create Role||
|Update Role|| 
|Delete Role|| 
|Manage Users|| 
|Create Users|| 
|Update Users|| 
|Delete Users|| 
|Manage Groups|| 
|Create Groups||
|Update Groups|| 
|Delete Groups|| 
|Manage Portal Accounts||
|Create Portal Accounts|| 
|Update Portal Accounts|| 
|Delete Portal Accounts|| 
|Manage Notifications|| 
|Register Channels|| 
|Deregister Channels|| 
|Manage Working Time Calendars||
|Create Working Time Calendars|| 
|Update Working Time Calendars|| 
|Delete Working Time Calendars|| 
|Manage Timers|| 
|Create Timers|| 
|Update Timers|| 
|Delete Timers|| 
|Execute Stored Queries|| 
|Run Data Imports|| 
|Can Spawn Business Process|| 
|canCancelProcess|| 
|changeDocumentOwner|| 
-->
### Data
|Name|Description|
|-|-|
|Manage Lists|Provides read access to the [Simple Lists](/esp-config/data/simple-lists) under Platform Configuration and with each application where the user has a subscription.  Additional rights are required to be able to create, update, and delete lists| 
|Add Lists|Add a new simple list. Requires the `Manage Lists` right|
|Update Lists|Update an existing simple list. Requires the `Manage Lists` right|
|Delete Lists|Delete a simple list. Requires the `Manage Lists` right| 
|Manage Scheduled Jobs|Allows the user to view their own scheduled jobs within the user app. Users that have a privilege level of admin will also be able to view all users' scheduled jobs from within Configuration and reassign the owner of a job|
<!--
|Create Scheduled Jobs||
|Update Scheduled Jobs|| 
|Delete Scheduled Jobs||
|Manage Auto Sequences||
|Create Auto Sequences||
|Update Auto Sequences||
|Delete Auto Sequences||
|Manage Tasks||
|Create Tasks||
|Update Tasks||
|Delete Tasks||
|manageEntityRules||
|Add Documents||
|Update Documents||
|Delete Documents||
|Manage Indexer|| 
|Create Indexes||
|Delete Indexes||
|searchIndex||-->

<!--
### Configuration
|Name|Description|
|-|-|
|Manage Business Processes|| 
|Manage System Settings||
|Manage Application Settings||
|Manage Application Strings||
|Manage System Support||
|Manage CAFS||
|manageImageShare||
|Manage REGEX||
|Manage Background Jobs||
|Manage Secret Keys||
|Manage Sessions||
|Manage Progressive Capture||
|Manage Webhooks||
|manageEmail||
|manageSsoProfiles||
|manageKeysafe||
|manageIntegrations||
|manageServiceCatalogs||
|Manage Office Location Integration Services||
|Manage Office Location Integration Packages||
|Manage Runbooks||
|Manage Automation Jobs||
|Manage Inventory||
|manageForms||
|manageSecurityAudit||
|manageNetworkRules||
|manageAssetDiscoveryUploads||
-->
<!--
### System Settings
|Name|Description|
|-|-|
|Manage Applications||
|Install Applications|| 
|Switch Applications|| 
|Update Applications|| 
|Refresh Applications|| 
|Uninstall Applications|| 
|Get Database Schema|| 
|Apply Database Schema|| 
|Add Records|| 
|Get Records|| 
|Update Records|| 
|Delete Records||
-->
<!--
### Collaboration
|Name|Description|
|-|-|
|Post Messages||
|Deregister Activity Streams||
|Follow Activity Streams||
|Unfollow Activity Streams|| 
|Like Activities||
|Unlike Activities|| 
|Query Activity Streams|| 
|Post Comments||
|Edit Comments||
|Delete Comments|| 
|Create Workspaces|| 
|Get Workspaces|| 
|Join Workspaces|| 
|Leave Workspaces|| 
|Add Workspace Members|| 
|Remove Workspace Members|| 
|Update Workspaces|| 
|Change Workspace Owner|| 
|Delete Workspaces|| 
|Start Conversations|| 
|Get Conversations|| 
|Post Conversations|| 
|Search Conversations|| 
|Add Conversations Members|| 
|Delete Conversations|| 
|Remove Conversation Members||
|Manage Profile Images||
|Search Activities||
-->
<!--
### Reporting
|Name|Description|
|-|-|
|View Measures||
|Create Measures|| 
|Update Measures||
|Delete Measures||
|View Widgets||
|Create Widgets|| 
|Update Widgets||
|Delete Widgets||
|View Dashboards & Slideshows||
|Create Dashboards & Slideshows|| 
|Update Dashboards & Slideshows||
|Delete Dashboards & Slideshows||
|View Reports||
|Create Reports|| 
|Update Reports|| 
|Delete Reports||
-->
<!--https://wiki.hornbill.com/index.php?title=Roles -->
