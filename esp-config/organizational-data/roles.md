---
layout: article-toc
---
# User Roles
A Role is a collection of rights that allow a user to perform actions in Hornbill. Hornbill comes with a range of roles ready for you to associate with your users and custom roles can be created to meet your specific needs.

In addition to platform roles, each application comes with default roles specifically designed to govern access to that application.

## Topics Covered
* Describing the different types of roles.
* How to create a custom role.
* The different ways to assign roles to users.
* How roles can affect application subscriptions.

## Before you begin
* Users with the Admin or Super User role can manage roles
* The rights Manage Role, Create Role, Delete Role, and Update Role are available for custom roles.


## Role Types
Two types of Roles exist within Hornbill, Security Roles and Assignment Roles:

* **Security Roles**<br>Are used to control access to Hornbill Applications and to the different areas within each application. Security roles have a "Privilege Level" which determines whether they can be given to a basic user or full user.
* **Assignment Roles**<br>Provide restrictions on the assignment of Activities. For example, when configuring a Human Task node within a Business process, it is possible to assign that task to a Role. This is especially useful if you wish to restrict the assignment of an activity to several users within a particular group or if you want to expose this activity to a selection of users across multiple groups.
It is also possible to share certain items based on an assignment Role. One example is Dashboards. Assignment Roles can only be associated with application Users"

## Custom Roles
If the roles that come with Hornbill do not meet your specific needs, you can create your own Security and Assignment roles.

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
