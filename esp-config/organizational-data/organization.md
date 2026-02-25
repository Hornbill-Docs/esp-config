---
layout: article-toc
---
# Groups and Teams

The Hornbill platform allows for the creation of a hierarchical structure that represents your organization. Create and manage your organization's groups and teams, and the members that belong to them. Some examples of the different group types include companies, divisions, departments, and cost centers.

## Topics covered

* How groups are used
* Manually adding groups
* Planning the group structure
* Adding users to groups

## Before you begin

* Admin user access is required
* Knowledge of the existing structure of your organization
* You should fully understand how the Hornbill Platform supports a [group and team structure](/esp-fundamentals/core-capabilities/internal-groups-and-teams)
* You should fully understand how the organizational and team structure works with [Human Tasks](/esp-fundamentals/core-capabilities/human-tasks)

## How groups are used

 The organizational data is used by the different Hornbill apps to identify groups of users for several purposes. Some examples of these include

* Email notifications to group members within a workflow automation.
* Authorization by a group within a workflow automation.
* Service subscriptions within Service Manager.
* Knowledge base access within Service Manager.
* Group based reporting.
* Home Groups for unique user experience in the Employee Portal.

## Groups vs Teams

* **Groups** :  Use `groups` to build your organizational structure along with the associated people that belong to each group.
* **Teams** :  Use `teams` for associating subscribed users that work together within the different Hornbill apps.

|Feature|Group|Team|[Function](/esp-fundamentals/core-capabilities/internal-groups-and-teams#functional-organizational-unit-ou-types)|
|-|-|-|-|
|Can contain sub-groups|Yes|No|No|
|Associate Basic Accounts|Yes|No|No|
|Associate User Accounts|Yes|Yes|Yes|
|Allow Task Assignment|No|Yes|Yes|

## Groups

### Adding a group

From the groups and teams view click on the `+ Create New Group` button.

* **Id**: This is the unique identifier for this group.
  * This value can only contain letters, numbers, and underscores
  * It cannot begin with a numeric digit
  * Must be at least two characters long and is limited to a maximum of 160 characters
    :::note  
    Please be aware, that once the ID has been saved, it cannot be amended. If this new group has a parent, then the ID will be constructed using the ID that you specify as well as being prefixed with the ID(s) of any parent groups.
    :::
* **Name**: This is the user-friendly name for the group. This can be amended at any time after the group has been created.
* **Parent**: This is how the hierarchy is defined. Here, the direct parent of the group should be specified. For example, if creating a division, a company group may be selected as a parent. Be aware, that once the parent has been saved, it cannot be amended.
* **Type**: This is a drop-down list, specifying the type of group that is being created (Company, Division, Department, Costcenter, Team, or General)
* **Attributes 1 to 9**: These fields can be used to store additional information.
* **Notes**: A free text field to record any additional information regarding the group.

:::tip
**Reporting** - Groups are stored in the table h_sys_groups and the types described above are represented by an integer value between 0 and 5 in a column called h_type. These are as follows: 0=general, 1=team, 2=department, 3=costcenter, 4=division, 5=company. The group type may be useful when creating measures, widgets, and reports.
:::

### Associated users

Once a group has been created, users can be associated to the group.

1. Click the group in which the user(s) need to be associated with
1. Click the `Associated Users` Tab
1. Click the `Associate User` button. A form is displayed with the following options:

* **Search Users**,: Begin typing the name of an individual user to assign to the group, and click the name to select them
* **By Organization**: If the assigned users of the group need to be the same as another existing group, use this field to search and select the group. This will add all the members of that existing group to your new group.
* **By Role**: If the members of the group can be selected based on a common Hornbill Security Role, use this field to search and select the role. Any user who possesses that role will be added to your new group.
* **Membership** Select whether the user is a Member, Team Leader, or Manager of the group.

:::tip
Workflow Automations can be used to add and remove users from groups. This can be useful as part of any workflow that manages new or leaving staff.
:::

## Teams

### Allow task assignments

This option is only available for Teams and not available on Groups.  Having the Allow Task Assignments set to `Yes` on a team makes the team name available on the task form for assignment when manually creating a task.

![Allow team task assignment](/_books/esp-config/images/team-allow-task-assignment.png)

### Member management

When adding members to a team, there are some additional options related to task assignment.

* **Allow task view**: From the [My Activities View](/esp-user-guide/my-activities/overview), users with this option can see tasks that are assigned to their group.
* **Allow task action**: From the [My Activities View](/esp-user-guide/my-activities/overview), users with this option can action the tasks that are assigned to their group, such as assigning the task to themselves or completing the task. When this is turned off, they can see this teams tasks in the Activities view, but they can't be opened.

## Advanced settings

|Setting Name|Description|
|-|-|
|task.onlyManagerCanAssignGroupUser|If this is set to true then only group manager can assign a task to a user which is already assigned to group.|
|system.groups.mode|The the mode this instance's internal user org structure operates in. Information about the modes can be found here [organizational team structure](/esp-fundamentals/core-capabilities/organization-and-teams)
