---
layout: article-toc
---
# User roles
A Role is a collection of rights that allow a user to perform particular actions in Hornbill.

Hornbill comes with a range of roles ready to associate to your users. Each app is installed with a set of default roles specifically designed to govern access to that application. Manage Role assignments to your users or create some of your own.

In order for Users to access various parts of Hornbill they need to be given the appropriate roles. This is done via the Configuration.

## Role Types
Two types of Role exist within Hornbill, Security Roles and Assignment Roles:

* **Security Roles**<br>Are used to control access to the different Hornbill Applications and also to the different areas within each application. Security roles posses a "Privilege Level" which affects whether they can be given to a basic user or full user.
* **Assignment Roles**<br>As the name suggests, are primarily there to provide restrictions on the assignment of Activities. For example, when configuring a Human Task node within a Business process, it is possible to assign that task to a Role. This is especially useful if you wish to restrict the assignment of an activity to a number of Users within a particular Group (but not all users) or if you want to expose this activity to a selection of Users across multiple Groups.
It is also possible to share certain items based on an assignment Role. One example is Dashboards. Assignment Roles can only be associated to "Application Users"

## Custom Roles
If the supplied roles that come with Hornbill do not cater for your specific needs, it is possible to create your own Security and Assignment roles.

### Creating a Custom Role
1. Open Configuration
1. Select where the new role will be created (either Platform Configuration or a specific Hornbill App) from the drop down menu.
1. Click "Roles" under the section "User & Guest Access"
1. Select '+ Create New Role'
1. Complete Role details...
    1. Role ID - Name of new role. It must be unique and cannot be changed later.
    1. Privilege Level - For most roles this will be User
    1. Type - Security or Assignment
    1. Description - What the role has been created for
1. Click "Create Role" to Save

Once created, if the role was created in the context of Platform Configuration it's possible to add or update the application context or tie the role to a Hornbill Shared Mailbox. If the role was created in the context of a specific app, the application context cannot be amended.
