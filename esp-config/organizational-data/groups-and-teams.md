---
layout: article-toc
---
# Groups and teams
The Hornbill platform allows for the creation of a hierarchical structure that represents your organization. Create and manage your organization's groups, teams and functions, and the members that belong to them. Some examples of the different group types include companies, divisions, departments, and cost centers. 

## Topics covered
* How groups are used
* Manually adding groups
* Planning the group structure
* Adding users to groups

## Before you begin
* Admin user access is required
* Knowledge of the existing structure of your organization
* You should fully understand how the Hornbill Platform supports [Organizational an Team Structure](/esp-fundamentals/core-capabilities/organization-and-teams)
* You should fully understand how the Organizational and Team Structure works with [Human Tasks](/esp-fundamentals/core-capabilities/human-tasks)

## How groups are used
 The organizational data is used by the different Hornbill apps to identify groups of users for a number of purposes. Some examples of these include

* Email notifications to group members within a Business Process Automation
* Authorization by group within a Business Process Automation
* Service subscriptions within Service Manager
* Knowledge base access within Service Manager
* Group based reporting
* Home Groups for unique user experience in the Employee Portal

## Deciding on your organization and team structure in Hornbill

Generically, Organizational structures define the way in which an organization arranges its people, resources, and communication lines to achieve its goals.  Hornbill has the facility to model your entire organization structure if you wanted to, but, in most cases this will not be desirable as it will most likely over-complicate setting up Hornbill for your initial needs. 

Learn more about [Common organizational structures](/core-capabilities/organization-and-teams#common-types-of-organizational-structure)

It is critical to understand your companies organizational structure (or part thereof) in the context of what you are using Hornbill for, especially in the context of how you will be using Hornbill to orchestrate and manage the flow of work in relation to your people. 

How you organize your Functional/Assignment teams are important to the way in which you will work, and especially for the way in which you want your workflow automation's to work. 

In the case where you are using Hornbill for workloads that support others within your organization, then setting up an Organizational structure that you can place your end (supported) users into, in order that your teams recognize your internal people and company structure.

As a general rule, you should aim to keep your organizational and team structures as simple as possible, and favor flatness over a complicated hierarchy. It's not a requirement that you model your organizations actual structure in Hornbill, its only a requirement you model what makes sense to the way you want to work with Hornbill in the context of your organization.

:::warning
Once you have defined your organizational structure, many other parts Hornbill depend on that structure to function. Using that structure will store data (things like assignments, ownership, sharing, access controls etc) that all depend on that structure.  You should keep in mind that the structure you choose is not easily malleable once defined, and substantially changing this structure after the fact can be difficult, time consuming and error-prone, and things may not work as expected after poorly planned changes. 
:::

<br>

:::warning
GERRY: James, can you re-align this content in accordance with [Organization and Teams](https://docs-internal.hornbill.com/esp-fundamentals/core-capabilities/organization-and-teams), refer back to platform documentation instead of any duplication
:::

## Groups vs Teams/Functions
* **Groups** <br> Use `groups` to build your organizational structure along with the associated people that belong to each group.
* **Teams** <br> Use `teams` for associating subscribed users that work together within the different Hornbill apps.

|Feature|Group|Team|Function|
|-|-|-|-|
|Can contain sub-groups|Yes|No|No|
|Associate Basic Accounts|Yes|No|No|
|Associate User Accounts|Yes|Yes|Yes|
|Allow Task Assignment|No|Yes|Yes|

## Adding a group

From the organization view click on the `+ Create New Group` button.

* **Organization Id**<br>This is the unique identifier for this group. 
    * This value can only contain letters, numbers, and underscores
    * It cannot begin with a numeric digit
    * Must be at least two characters long and is limited to a maximum of 160 characters
    :::note  
    Please be aware, that once the ID has been saved, it cannot be amended. If this new group has a parent, then the ID will be constructed using the ID that you specify as well as being prefixed with the ID(s) of any parent groups.
    :::
* **Name**<br>This is the user-friendly name for the group. This can be amended at any time after the group has been created.
* **Parent**<br>This is how the hierarchy is defined. Here, the direct parent of the group should be specified. For example, if creating a division, a company group may be selected as a parent. Be aware, that once the parent has been saved, it cannot be amended.
* **Type**<br>This is a drop-down list, specifying the type of group that is being created (Company, Division, Department, Costcenter, Team, or General)
* **Attributes 1 to 9**<br>These fields can be used to store additional information. 
* **Notes**<br>A free text field to record any additional information regarding the group.

:::tip
**Reporting** - Groups are stored in the table h_sys_groups and the types described above are represented by an integer value between 0 and 5 in a column called h_type. These are as follows: 0=general, 1=team, 2=department, 3=costcenter, 4=division, 5=company. The group type may be useful when creating measures, widgets, and reports.
:::

## Associated users
Once a group has been created, users can be associated to the group.

1. Click the group in which the user(s) need to be associated with
1. Click the `Associated Users` Tab
1. Click the `Associate User` button. A form is displayed with the following options:

* **Search Users**,<br>Begin typing the name of an individual user to assign to the group, and click the name to select them
* **By Organization**<br>If the assigned users of the group need to be the same as another existing group, use this field to search and select the group. This will add all the members of that existing group to your new group.
* **By Role**<br>If the members of the group can be selected based on a common Hornbill Security Role, use this field to search and select the role. Any user who possesses that role will be added to your new group.
* **Membership** Select whether the user is a Member, Team Leader, or Manager of the group.

:::tip
BPM Automations can be used to add and remove users from groups. This can be useful as part of any workflow that manages new or leaving staff.
:::

## Allow task assignments
This option is only available for Teams.  Having the Allow Task Assignments set to `Yes` on a team makes the team name available on the task form for assignment.

### Associated user task management
* **Allow task view**<br>From the Task View, users with this option can see tasks that are assigned to their group.
* **Allow task action**<br>From the Task View, users with this option can action the tasks that are assigned to their group, such as assigning the task to themselves or completing the task.

## Advanced settings
|Setting Name|Description|
|-|-|
|task.onlyManagerCanAssignGroupUser|If this is set to true then only group manager can assign a task to a user which is already assigned to group.|
