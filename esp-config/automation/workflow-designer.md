---
layout: article-toc
---
# Workflow Designer
The Workflow Designer lets you define and build workflows that can then be used to standardize and automate your processes. You can define a logical sequence of activities and automated tasks in a workflow that can then be repeated reliably.

## Tool Bar
* **Filter**<br>Filter the list of workflows by typing text that will match against the following fields: Workflow name, Category, Created By, and Updated By.
* **Status Filter**<br>Filter the list of workflows by status using the options `Show All Workflows`, `Show Active Workflows`, and `Show De-Activated Workflows`.
* **Search workflows for a set value**<br>This option will search all of your existing workflows for a string of text. For example, you can search on a User ID to locate all the workflows where that User ID has been set within the workflow options.
* **Create New**<br>Select this option to create a new workflow.
* **Delete**<br>Delete one or more workflows that have been selected in the list of workflows. This option will only be available once a workflow has been selected.

## List
* **Column Headings**<br>Each heading can be clicked on to change the order in which the workflows are displayed.
* **Workflow**<br>Column that displays the name of each individual workflow. This can be clicked on to view and edit the selected workflow within the Business Process Designer.
* **Actions**<br>Some quick access options are available in the last column for each workflow.
* **Process Publishing & Activation**<br>Clicking this option will allow you to publish the workflow, using the latest draft version. You are also able to activate one of the previous 10 versions of the workflow or copy them back to the draft version.
* **Copy process**<br>Create an identical copy of this workflow.
* **Rename process**<br>Rename this workflow. This can only be done when the workflow has no executed processes with a status of active or suspended. Use the Manage Executed Processes option to identify and manage these executed processes.
* **Delete process**<br>Delete this workflow. This can only be done when the workflow as no executed processes with a status of active or suspended. Use the Manage Executed Processes option to identify and manage these executed processes.

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

## Nodes
A stage contains a series of nodes that make up the workflow.
### Via
The via node serves no functional purpose, but can be used in the designer, between nodes to better align the layout of the workflow on the design canvas.
### Start
The Start Node indicates the starting point of the workflow. There are no parameters and you can can only have one per stage.
### Hornbill Automation
Hornbill Automations are definable automated actions that will occur within the workflow. The available Hornbill Automation are provided by each application that utilizes workflows. Each application can provide automated tasks.
### Authorization
Used to define the decision makers for authorizations, set their approval weightings, add expiry options on the decision, and if required include useful variables from the parent request to assist with the decision making in the authorization task information.

### Auto Assign Authorization
This node is used to invoke authorization tasks for approvers which have been predefined using the Service Manager > Entity > Request > Suspend > Wait for List of Request Authorizers node or the Core > Application > Utility > Get Authorizers by Group. This node has no requirement to define approval weightings etc as these will have been configured in the preceding node. Options do include the configuration of outcomes, the authorization task details and lifespan setting including optional due and expiry dates.
### External Authorization
This node is used to request an authorization decision from an external party via email. The node allows for a single email recipient, definable outcomes, and the option to inject variable content into a hardcoded email which will be sent to the email address (static or using a variable). The recipient of the email will receive a link to a web page; from where they can review the authorization decision, choose an outcome , and if configured provide a supporting reason. Where the node is used, the workflow will be suspended awaiting an outcome and will resume once the recipient has submitted their response. This node would typically be followed by a decision node, like any other type of authorization, with branches configured to reflect the outcome choices of the node.
The recipient of the email does not need to log into any interface when accessing the web page link.
### Decision
These nodes can be used after a number of other nodes including, Human Tasks, or Automated tasks where multiple outcomes are possible. The Decision node can be used to facilitate the drawing of multiple outcome lines to other nodes, and for each outcome to be individually set. It is also possible to join decision nodes, to other decision nodes through the use of a No Match outcome. This caters for situations where multiple outcomes per decision are needed and not simply the three which are available from a single decision node.
Note: It is strongly advised that all Decision nodes have a No Match outcome to avoid the potential of a No Matching GotoIf error when none of the criteria are met.
### Human Tasks
This is for a synchronous manual activity that needs to be carried out. The workflow will wait for someone to update the activity with one of the expected outcomes. You need to define the name and details of the activity, allocate a role or an individual co-worker, and expected outcomes, as well as optionally including variables from the linked parent request which may assist in the completion of the task.

### Cloud Automation
This node is used to invoke automated actions in a workflow using either integrations with 3rd party solutions using Hornbill's Integration Bridge, or by invoking automations defined in 3rd party tools like Microsoft Orchestrator or HP OO. options will include choosing the connector to use, selecting the Method (automation) you wish to invoke and then supplying the required input parameters relevant to the connector and method you have chosen.
### IT Automation
This allows for the selection of a specific package and operation as in an ad-hoc IT Automation Job or as used within a Runbook
### Runbook Workflow
This allows one to select a Runbook with the input and output parameters.
### End
This stage will terminate the workflow. You can only use this node in the final stage.
### Next Stage
This will take you either to the next sequential or a later stage and will only be available when you have 2 stages or more. You cannot go to a previous stage.
### Abort
This node will end the workflow and will cause the heads up display to show as red.
### Set Checkpoint
This node will allow you to set a visible indicator that a task / or important milestone in the workflow has been met - In order to use this node, checkpoints must have been defined for the stage of the workflow (Stage Properties). It is also possible to mark a checkpoint as having been met on the all the above nodes as a configuration option.
### Start Parallel Processing
This node can be used when there is a need to invoke more than one stream of processing at the same time. This is commonly used with [human tasks](/servicemanager-config/customize/workflows/workflow-designer#human-tasks) that can be assigned and worked on independantly, but they must all be completed before the workflow can continue.

![Parallel Processing](/_books/esp-config/images/parallel-processing.png)

:::tip
The use of [Suspend automations](/servicemanager-config/customize/workflows/service-manager-workflows#suspend) is not recommended within a parallel process. Suspend automations are designed to suspend the entire workflow and not an individual stream within a parallel process.
:::

#### Settings
Open the settings by clicking on the node and selecting the cog icon or double-click on the node. 

Two settings are available: 
* **Positioning**. Lets you change the orientation of the node.
* **Size**.  Change the size to better accommodate the number of streams.

![Parallel Processing Settings](/_books/esp-config/images/parallel-processing-settings.png)

### Finish Parallel Processing
Use this node to bring together and finish the individual process streams that had been initiated from a Start Parallel Processing node.

* The workflow will not progress past this node until all process streams have reached this point. 
* When designing a parallel process it is important to design each stream with a successful path or outcome to reach the Finish Parallel Processing node. 

    :::important
    If a human task fails due to an error in one stream, all other tasks within the parallel processing will be canceled. 
    :::
* Each stream should be kept separate from other streams.  Do not connect one stream to another stream.

#### Settings
Open the settings by clicking on the node and selecting the cog icon or double-click on the node. 

Two settings are available: 
* **Positioning**. Lets you change the orientation of the node.
* **Size**.  Change the size to better accommodate the number of streams.

![Parallel Processing Settings](/_books/esp-config/images/parallel-processing-settings.png)

<!--https://wiki.hornbill.com/index.php?title=Business_Process_Designer -->