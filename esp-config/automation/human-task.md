# Human task
When your workflow involves a manual activity, use a Human Task node. The workflow will wait for a person assigned by name or role to update the activity with one of the expected outcomes. 

You need to define the name and details of the activity, the role or individual assigned, and the expected outcomes. Optionally, you can include variables from the linked parent request that may assist in the completion of the task.

## Topics covered
* [Reference](/esp-config/automation/human-task#reference)
* [Using outcomes](/esp-config/automation/human-task#using-outcomes)
* [Using checklists](/esp-config/automation/human-task#using-checklists)

## Reference
* **Language.** You can define a human task in a single language or multiple languages. For an additional language, you create a copy of the human task in any other language enabled on your instance. This allows users working in different languages to receive the human task either in the default language or in the language defined in their profile.
* **Display.** The display name for the human task node in the Workflow Designer. This name does not appear on the human task.

### Task Settings
* **Title.** This appears as the title of the human task.
* **Category.** This appears on the human task.
* **Priority.** Set a priority to indicate the priority of the task.

### Owner
The owner can be notified about the task in reminders and also can reassign the assignee if required. The owner can be either a named user or a variable.
* **User.** Pick from a list of coworkers.
* **Variable.** You can see a list of possible variables, such as request owner if you precede the Human Task node with a Hornbill Automation node with the following settings (or any other node that outputs a user ID as a value):
    * Entity: Requests
    * Type: Get Request Information
    * Task: Request Details

### Task Assignment
Use the dropdowns to make a selection to assign the human task:
* **Assign to Role.** This is populated from the default roles and any custom roles defined on your instance. Any users who are assigned the role will receive the human task and any notifications.
* **Assign to Team.** This is populated from the default teams and any custom teams defined on your instance. Any users who are assigned the role will receive the human task and any notifications.
* **Assign to User.** Begin typing to select an individual.
* **Assign to Variable.** Use the Variable Picker.

### Lifespan Settings
You can set a start date, due date, and expiry date for the task based on either a predefined value or a variable (e.g. `respond by` or `fix by`) from the parent request.
* **Start**, **Due**, and **Expires After.** Configure each of these settings to your chosen number of days, hours, and minutes after the creation of the task. Or, you can base the lifespan on a variable such as `log date`, `resolve by`, or `fix by`. If using the variable option, you must precede the node with a Hornbill Automation node with these settings:
    * Entity: Request
    * Type: Get Request Information
    * Task: Request Details

#### About the *Expires After* setting
Expiry is a valid outcome for a human task, and setting a value here allows for --- via a Decision node following the task --- branching based on the task expiring rather than an outcome being selected.

::: tip
Variables used for lifespan settings must be in the ISO date/time format, for example 2021-11-26T11:30:00.000Z. Values from a date/time picker will be in this format, but values from a date picker will not.
:::

### Task Details
Define the details for the human task. This can be a combination of text and, if required, variables from the parent request.

The task details can comprise a summary, description fields, custom fields, or even answers to Intelligent Capture questions. See more [about inserting variables](/esp-config/automation/variable-picker).

### Task Options
* **Do not allow completion unless checklist is 100% complete.** This option becomes available if one or more checklists have been added to the task (using the **Manage Checklist** button). Select this option to make the task unable to be completed while there are outstanding checklist items.
* **Hide the completion reason field when completing the task.** Select this to set whether the Reason field is required or hidden when the completion of the task happens.
* **Show the time spent field when completing the task.** Select this to set whether the Time Spent field is hidden or shown to the user completing the task.
* **Time spent is mandatory for completion.** This option becomes available if the above option is selected. Set the default time spent.

### Outcomes
Configure the possible outcome options available for the user to choose when completing the human task. By default, two are provided: *Completed* and *Not Completed*. Use the **Add New** button to configure other possible outcomes. See [Using outcomes](/esp-config/automation/human-task#using-outcomes).

### Capture Task Fields
* **Field Properties.** Provide a title for the field, add a custom field ID, or leave the default.
* **Default Flags.** Configure whether the field is mandatory, visible on the form, in read-only view, and so on.
* **Field Type Settings.** Configure the type of capture you wish to use --- single, multi-line, static or dynamic dropdown, checkbox, radio button, label, and so on. Provide the context-based attributes as required.

For more information, see [Adding capture fields to tasks](/esp-config/automation/human-task#adding-capture-fields-to-tasks).

### Set Stage Checkpoints
Use the **Add** button to configure any stage checkpoints you want to be set on completion of the task.

## Using outcomes
You can create new options for the outcomes available to be selected. You can edit outcome settings (including adding fields), and you can delete outcomes.

You can also use outcomes and/or outcome-capture fields to branch in the workflow.

### Adding outcomes
**To add a new outcome:**
1. In the *Outcomes* section, click **Add New**.
1. Define the outcome value, a display name, and if the user completing the task is required to provide a reason when selecting this specific outcome.
1. (Optional) Provide a display color for the button.
1. (Optional) Make the outcome available in multiple languages.
1. Click **Apply Settings**.

### Adding capture fields to outcomes
1. Get to the *Edit Outcome Settings* dialog by either clicking **Edit** (the pencil icon) on an existing outcome or by adding a new outcome (using the **Add New** button).
1. In the *Capture Outcome Fields* section, click **Add Field**.
1. Configure the following fields:
    * **Field Properties.** Provide a title for the field, add a custom field ID, or leave the default.
    * **Default Flags.** Configure whether the field is mandatory, visible on the form, in read-only view, and so on.
    * **Field Type Settings.** Configure the type of capture you wish to use --- single, multi-line, static or dynamic dropdown, checkbox, radio button, label, and so on. Provide the context-based attributes as required.
1. Click **Apply Settings** to add the capture field to this specific outcome.
1. (Optional) Use the **Translate For** option to define different language versions of the capture field, which will be displayed to a user based on the language set in their profile.
1. Repeat the process for any additional capture fields that are required for the task.

### Editing and deleting outcomes
**To edit or delete outcomes:**
1. In the *Outcomes* section, use the **Edit** button (the pencil icon) or the **Delete** button (the trash can).
1. (Optional) Use the up and down arrows to reorder the outcomes.

<!--* **Expiry outcome.** You are not required to add a specific expiry outcome. This will be automatically enabled if you have configured an *Expires After* in the lifespan settings.-->
### Using outcomes to branch
**To use outcomes and/or outcome-capture fields to branch in the workflow:**
1. If you need different behavior in your workflow depending on the outcome of the human task or based on answers to capture fields tied to a chosen outcome, use a Decision node directly after the Human Task node.
1. Use the outcomes defined in the task as the branch options for the decision.
<!-- https://wiki.hornbill.com/index.php?title=Outcomes -->

<!-- 
#### Considerations
* **Default Reason field**<br>You may decide that the Reason field on the task is no longer relevant if you have added your own capture fields, and this can be hidden from the task by ticking the Hide reason option under the Task Options settings.
* **Setting Capture Fields Per Outcome**<br>It is possible to configure capture fields which are tied to the selection of an outcome on a task, and will only be presented and visible once a specific outcome has been chosen. This is covered in detail in the Outcomes wiki page.

:::tip
It is possible to use both task capture fields and outcome capture fields on the same task, but you are advised to check and ensure that none of the capture fields are using the same field id.
:::-->

<!-- 10 APR 2025 - CAMMY: I AM HIDING THIS CONTENT B/C I SEARCHED WORKSPACES AND I SEE THE allowcustomtaskfields SETTING WAS REMOVED FIVE YEARS AGO.
### Enabling Capture Outcome fields
You may have a need to record additional information against the chosen outcome of a task. In order to do this, you can enable Capture Outcome fields and use these to add additional fields to capture additional information when a specific outcome is chosen on a task.

**To enable Capture Outcome fields:**
1. In Configuration, navigate to Home > System > Settings > Advanced and enable the following setting:
* experimental.feature.bpm.allowcustomtaskfields

With this setting enabled it is now possible to configure both capture fields per outcome on a task, as well as at the task level.
-->
### Adding capture fields to tasks
1. In the *Capture Task Fields* section, click **Add Field**.
1. In the *Edit Field Settings* dialog, configure the following fields:
    * **Field Properties.** Provide a title for the field, add a custom field ID, or leave the default.
    * **Default Flags.** Configure whether the field is mandatory, visible on the form, in read-only view, and so on.
    * **Field Type Settings.** Configure the type of capture you wish to use — single, multi-line, static or dynamic dropdown, checkbox, radio button, label, and so on. Provide the context-based attributes as required.
1. Click **Apply Settings** to add the capture field to the task.
1. Repeat the process for any additional capture fields you need for the task.

<!-- ### Considerations
* **Default Reason field**<br>You may decide that the Reason field on the task is no longer relevant if you have added your own capture fields, and this can be hidden from the task by ticking the Hide reason option under the Task Options settings.-->

### Setting capture fields per outcome
You can configure capture fields that are tied to the selection of an outcome on a task, and that will only be presented and visible once a specific outcome has been chosen.

:::tip
You can use both task-capture fields and outcome-capture fields on the same task, but make sure to check that none of the capture fields are using the same field ID.
:::

### Using the answers from task-capture fields
Once a task has been completed and any task-capture fields completed, the answers from these fields are available to be used elsewhere in the lifecycle of the workflow.

* You can branch and make decisions on the answers using the Custom Expression builder. Select the relevant task and capture field to evaluate.
* You can inject the answers from task-capture fields into request fields or other tasks. Use the variable picker in a node following the task, but make sure it is in the same stage of the workflow.
* The task-capture field answers will be written to the timeline of the entity the task has been completed against.

## Using checklists
You can add to-do items in checklists for a task.

**To add a checklist to a human task:**
1. In the *Task Options* section, click **Manage Checklist** and then **Add Group**.
1. Give the checklist group a name.
1. Click the **+** button to add one or more checklist items.
1. (Optional) Use the arrows to re-order the checklist items in the checklist group.
1. (Optional) To remove checklist items or the checklist group, click **Delete** (the trash can icon).
1. (Optional) Use **Add Group** to add subsequent checklist groups to the same task.
1. (Optional) Use the arrows to re-order the checklist groups on the task.
1. When finished, click **Apply** to add the checklist group or groups to the task.

**To edit or delete checklists:**<br>
Click **Manage Checklist** to edit or delete the checklists associated to the task.

### About the task-progress percentage
When a user marks a checklist item as complete on a task, the **% progression** through the checklist items will be indicated on the task.

![Task Progression](/_books/esp-config/images/task-progression.png)

**To prevent the completion of the task while one or more outstanding checklist items remain:**
1. In the *Task Options* section, select **Do not allow completion unless checklist is 100% complete**.

<!-- https://wiki.hornbill.com/index.php?title=BPM_Human_Tasks-->
<!-- https://wiki.hornbill.com/index.php?title=Checklists -->
<!-- https://wiki.hornbill.com/index.php?title=Capture_Task_Fields -->
