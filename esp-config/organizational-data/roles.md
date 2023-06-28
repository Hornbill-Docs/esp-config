---
layout: article-toc
---
# User Roles
A Role is a collection of rights that allow a user to perform actions in Hornbill. Hornbill comes with a range of roles ready for you to associate with your users and custom roles can be created to meet your specific needs.

In addition to platform roles, each application comes with default roles specifically designed to govern access to that application.

## Topics Covered
* Describing the different types of roles.
* The different ways to assign roles to users.
* How roles can affect application subscriptions.
* How to create a custom role.

## Before you begin
* Users with the Admin or Super User role can manage roles
* The rights Manage Role, Create Role, Delete Role, and Update Role are available for custom roles.


## Role Types
Two types of Roles exist within Hornbill, Security Roles and Assignment Roles:

* **Security Roles**<br>Are used to control access to Hornbill Applications and to the different areas within each application. Security roles have a "Privilege Level" which determines the level of access provided to users that are assigned to the role.
* **Assignment Roles**<br>Provide restrictions on the assignment of Activities. For example, when configuring a Human Task node within a Business process, it is possible to assign that task to a Role. This is especially useful if you wish to restrict the assignment of an activity to several users within a particular group or if you want to expose this activity to a selection of users across multiple groups.
It is also possible to share certain items based on an assignment Role. One example is Dashboards. Assignment Roles can only be associated with application Users"

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

## User Created Roles
If the roles that come with Hornbill do not meet your specific needs, you can create your own roles.

### Creating a Custom Role
1. Open Configuration
1. Select where the new role will be created (either Platform Configuration or a specific Hornbill App) from the drop down menu.
1. Click "Roles" under the section "User & Guest Access"
1. Select `+ Create New Role`
1. Complete Role details...
    1. Role ID - Name of new role. It must be unique and cannot be changed later.
    1. Privilege Level - For most roles this will be User
    1. Type - Security or Assignment
    1. Description - What the role has been created for
1. Click `Create Role` to Save

If you create a Platform role you can add or update the application context or tie the role to a Hornbill Shared Mailbox.

If you create an Application role you cannot assign it to other applications or mailboxes.
