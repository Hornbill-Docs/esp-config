---
layout: article-toc
---
# Workflow Designer

The Workflow Designer lets you define and build workflows that can then be used to standardize and automate your processes. You can define a logical sequence of activities and automated tasks in a workflow that can then be repeated reliably.

## Tool Bar

* **Filter**: Filter the list of workflows by typing text that will match against the following fields: Workflow name, Category, Created By, and Updated By.
* **Status Filter**: Filter the list of workflows by status using the options `Show All Workflows`, `Show Active Workflows`, and `Show De-Activated Workflows`.
* **Search workflows for a set value**: This option will search all of your existing workflows for a string of text. For example, you can search on a User ID to locate all the workflows where that User ID has been set within the workflow options.
* **Create New**: Select this option to create a new workflow.
* **Delete**: Delete one or more workflows that have been selected in the list of workflows. This option will only be available once a workflow has been selected.

## List

* **Column Headings**: Each heading can be clicked on to change the order in which the workflows are displayed.
* **Workflow**: Column that displays the name of each individual workflow. This can be clicked on to view and edit the selected workflow within the Workflow Designer.
* **Actions**: Some quick access options are available in the last column for each workflow.
* **Process Publishing & Activation**: Clicking this option will allow you to publish the workflow, using the latest draft version. You are also able to activate one of the previous 10 versions of the workflow or copy them back to the draft version.
* **Copy process**: Create an identical copy of this workflow.
* **Rename process**: Rename this workflow. This can only be done when the workflow has no executed processes with a status of active or suspended. Use the Manage Executed Processes option to identify and manage these executed processes.
* **Delete process**: Delete this workflow. This can only be done when the workflow has no executed processes with a status of active or suspended. Use the Manage Executed Processes option to identify and manage these executed processes.

## Stages

A stage is a container for a set of actions or tasks that fulfill a particular aspect of a workflow.  

* Each workflow can have one or more stages.
* The workflow cannot go back to a previous stage.
* A stage can be skipped.
* The output of a node is only available within the stage where it is located.

## Manage Workflow Options

### Access Granted to

In situations where it is necessary to regulate access to workflows, this feature provides the capability to designate specific individuals who are permitted to access the workflow directly from the workflow list.

:::important
Before access control can be applied to workflows, this feature must be enabled by an administrator. The [platform setting](/esp-config/advanced-tools-and-settings/advanced-system-settings) **security.bpm_access_controls.enabled** must be set to `ON`. Before setting to `ON` access control should be reviewed on all existing workflows to ensure appropriate access is in place.
:::

* Access is automatically granted to the person who created the workflow and the Hornbill admin (superuser).
* If access has not been granted to anyone, only the creator and the Hornbill admin will see the workflow.
* Access can be granted to individual users, roles, or groups.
* Any user that requires access to a workflow must also have the **Business Process Manager** [role](/esp-config/organizational-data/roles).

![Access Granted to](/_books/esp-config/images/access-granted-to.png)

## Navigation Nodes

A stage contains a series of nodes that make up the workflow.

* **Via**: The via node serves no functional purpose, but can be used in the designer, between nodes to better align the layout of the workflow on the design canvas.
* **Start**: The Start Node indicates the starting point of the workflow. There are no parameters and you can only have one per stage.
* **End**: This stage will terminate the workflow. You can only use this node in the final stage.
* **Next Stage**: This will take you either to the next sequential or a later stage and will only be available when you have 2 stages or more. You cannot go to a previous stage.
* **Abort**: This node will end the workflow and will cause the heads up display to show as red.
* **Set Checkpoint**: This node will allow you to set a visible indicator that a task / or important milestone in the workflow has been met - In order to use this node, checkpoints must have been defined for the stage of the workflow (Stage Properties). It is also possible to mark a checkpoint as having been met on the all the above nodes as a configuration option.


## Functional nodes

* **[Hornbill Automations](/esp-config/automation/hornbill-automations)**: Hornbill Automations are definable automated actions that will occur within the workflow. The available Hornbill Automations are provided by each application that utilizes workflows. Each application can provide automated tasks.
* **[Authorization](/esp-config/automation/authorization)**: Used to define the decision makers for authorizations, set their approval weightings, add expiry options on the decision, and if required include useful variables from the parent request to assist with the decision making in the authorization task information.
* **[Auto Assign Authorization](/esp-config/automation/auto-assign-authorization)**: This node is used to invoke authorization tasks from a list of predefined users.
* **[External Authorization](/esp-config/automation/external-authorization)**: This node is used to request an authorization decision from an external party via email.
* **[Decision](/esp-config/automation/decision)**: These nodes can be used after a number of other nodes including, Human Tasks, or Automated tasks where multiple outcomes are possible.
* **[Human Tasks](/esp-config/automation/human-task)**: This is for assigning a manual activity that needs to be carried out. The workflow will wait for someone to complete the activity before continuing.
* **[Cloud Automation](/esp-config/automation/cloud-automation)**: This node is used to invoke automated actions in a workflow using either integrations with 3rd party solutions using Hornbill's Integration Bridge, or by invoking automations defined in 3rd party tools like Microsoft Orchestrator or HP OO.
* **[IT Automation](/esp-config/automation/it-automation)**: This allows for the selection of a specific package and operation as in an ad-hoc IT Automation Job or as used within a Runbook.
* **Runbook Process**: This allows one to select an ITOM Runbook with the input and output parameters.

