# Variable picker
The variable picker is available to use in most workflow nodes and their fields, including:
* Human Tasks
* Custom expressions following Decision nodes
* Integration calls
* Automated tasks
* Authorizations

You can use the variable picker to inject or overwrite variable values into node fields.

## Using the variable picker
While you can manually insert variables into node fields (see [Request Variables](/servicemanager-config/customize/workflows/request-variables)), you also have the option of using the variable picker.

You can open the variable picker in multiple ways:
* In most fields in workflow nodes, click the variable picker icon --- the epsilon, or ε.
* When the variable picker is available but not displayed, use CTRL (or CMD) with a left mouse click.

The variables that are available to use are governed by the nodes preceding the node you want to use the variable picker on in your workflow.

Available variables:
* **Global Inputs.** This option will contain any globally available variables such as `requestId`.
* **Flowcodes.** This will list any variable data related to the entity in which the variable picker is being used. In order to have options presented here, you must use the relevant workflow Get Information nodes in the workflow stage prior to the node you want to make the variables available in.

    The variable containers that can be used, and their related Get Information nodes, are the following:
    * **Customer Details.** Automated Tasks > Requests > Get Request Information > Customer Details
    * **Organization Details.** Automated Tasks > Requests > Get Request Information > Organization Details
    * **Owner Details.** Automated Tasks > Requests > Get Request Information > Owner Details
    * **Request Details.** Automated Tasks > Requests > Get Request Information > Request Details
    * **Intelligent Capture Answers.** Automated Tasks > Requests > Get Request Information > Progressive Capture Answers
    * **Service Details.** Automated Tasks > Requests > Get Request Information > Service Details
    * **Site Details.** Get Request Information > Site Details
* **Tasks.** This will contain any tasks that precede the node into which you are looking to use the variable picker in the current stage of the workflow.

    Task variables that can be used include the following:
    * Outcomes
    * Completion Details
    * Completion Date
    * Owner
    * Custom Field Answers
* **Integrations.** This will contain any output parameter variables that are returned from any integration nodes preceding the node in which you are looking to use the variable picker in the current stage of the workflow.

## Inject or overwrite
With the variable picker open and having navigated to the variable you wish to insert, you have two options to choose from:

* **Inject.** This adds the variable to any other content that is currently in the node field (other variables, manually added content, etc.).
* **Overwrite.** This removes any existing content in the node field and replaces it with the variable you have chosen.  

The variable picker allows for the adding of one variable at a time. When you need to add multiple variables to the same node field, the above process would need to be repeated, using the inject option rather than the overwrite option.

## Raw value or display value
When choosing to inject a variable or overwrite with a variable, you can choose to use either the raw value or the display value of the variable.

A good example of this is when you are configuring your Intelligent Capture custom questions, you may define a possible answer with both a value and a display value. These values may be the same or they may differ. If you are creating different language versions of the question, you may want the raw value to remain the same while the display value is different depending on the different language versions you have created. As such, you may choose to inject or overwrite with the display value rather than the raw value. The raw value will still be important elsewhere.

You may make branching decisions in your workflow based on the raw value, because this value will always remain constant regardless of whether the display value changes. This may be the case depending on the user's language settings, or if you wish to edit how the display name is presented to users.