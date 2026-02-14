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

* **Security roles:** Security roles are used to control access to Hornbill through the use of rights. Security roles include a [Privilege Level](/esp-config/organizational-data/roles#privileges) which determines the level of access provided to users that are assigned to the role.
* **Assignment roles:** Assignment roles provide restrictions on the assignment of activities. For example, when configuring a Human Task node within a workflow, it is possible to assign that task to a role. This is especially useful if you wish to restrict the assignment of an activity to several users within a particular group or if you want to expose this activity to a selection of users across multiple groups.
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

|Role|Description|Privilege Level|
|-|-|-|
|Activities Template Manager|This role grants the rights to manage activities templates.|user|
|Admin Role|This role provides administrative functionality to the Hornbill platform and should only be granted to an administrator.|user|
|Advanced Reporting Admin|This role grants the ability to manage, create, edit and delete reporting measures, widgets, dashboards, slideshow and advanced reporting using tables and entities. Advanced reporting relies on standard SQL SELECT statements for the report definition, so requires a comfortable knowledge of SQL and underlying database schema.|user|
|Anonymous Guest|This role grants the rights limited guest access without a registered account. Used for integrations.|none|
|Authorized Guest|This role grants the rights to guest users that have been authenticated.|guest|
|Basic User Role|This role provide very limited, mostly read-only access to the system to support co-worker self-service users.|basic|
|Business Process Manager|This role grants the rights to define business process workflows.|user|
|Contacts Admin|This role grants the rights to add, edit and delete contacts as well as customize portals.|user|
|Coworker Lifecycle|This role grants the rights to design and use the lifecycle button on the coworkers page.|user|
|Dashboard Viewer|This role grants the rights to view dashboards and slideshow.|user|
|Form Designer|This role grants the rights to design existing forms including adding additional fields as well as changing the default layouts.|user|
|HAi Manager|This role should only be used for managing HAi configurations.|user|
|Home Page Manager|This role grants the rights to manage the Home Page.|user|
|Hornbill Authorized Guest|This role grants the rights to guest users that have been authenticated.|guest|
|Locations Manager|This role grants the rights to manage Locations.|user|
|Organizations Admin|This role grants the rights to add, edit and delete organizations.|user|
|Page Manager|This role grants the rights to manage pages.|user|
|Progressive Capture Manager|This role grants the rights to define Intelligent Capture workflows.|user|
|Reporting Admin|This role grants the ability to manage, create, edit and delete reporting measures, widgets, dashboards and slideshow.|user|
|Reporting User|This role grants the ability to view reporting and preview/run reports.|user|
|Service Domain Administrator|This role grants the rights to manage Service Catalogs and Domains.|user|
|Sites Manager|This role grants the rights to manage Sites.|user|
|Super User Role|This role provides super user functionality to the system as it overrides all rights and permissions. A super user should never log into the user application, and the role should only ever be used when first setting up the system, or in an emergency to recover the system.|admin|
|Translator|This role grants the rights to define translations for application strings between different languages.|user|
|User Import|This role should only be used for User Import Tool. user
|User Role|This role provides all standard platform user functionality.|user|

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

### System rights

All roles have the option to add system rights. The system rights include the following categories: Accounts, Data, Configuration, System Settings, Collaboration, and Reporting.

![Role System Rights](/_books/esp-config/images/roles-system-rights.png)

### Application Rights

Application rights are only available if the role is associated to an application. The available categories and rights will depend on the associated application.

![Role Application Rights](/_books/esp-config/images/roles-application-rights.png)
