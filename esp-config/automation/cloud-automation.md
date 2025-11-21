# Cloud Automation
The Cloud Automation node can be invoked from the business process designer and is used to call either iBridge automations, HP Operations Orchestration Flows. or Microsoft Orchestrator Runbooks

## Adding the Cloud Automation Node

1. From an existing Node within your workflow, place your mouse pointer over this node to expose the connection arrows.
1. From a connection arrow, drag out a new connection line
1. Release you left mouse button to display the Node Selection menu
1. Select Cloud Automation

:::info
Cloud Automation Nodes are displayed in yellow to help differentiate these from other node types.

![Cloud Automation Node](/_books/esp-config/images/workflow-cloud-automation-node.png)
:::

## Configuration
Two options are available to expose the properties of the Hornbill Cloud Automation Node. You can either place your mouse pointer over the Cloud Automation node to expose the Cog icon and click on this icon or double click anywhere on the Cloud Automation Node.

![Cloud Automation Node](/_books/esp-config/images/workflow-cloud-automation.png)

### Cloud Automation
* **Language**. Select the language that you want to work in. This will default to the language set in your profile. If you have other users who will be viewing the workflow that operate in a different language, you may want to provide translations for them by selecting their language and providing the appropriate translations.
* **Display**. Give the Cloud Automation node a display name for how it will appear on the business process design canvas.

### Request
* **Connector**. This drop-down list displays the list of available connectors. By default, the Hornbill Integration Bridge connector will be available. If you have configured any Business Process Connectors using Microsoft Orchestrator or HP Operations Orchestration, these will also be available.
* **Method**. Clicking on the edit icon allows you to browse the content catalog for the selected Connector. Click and expand each item to see the available Methods, and then select the Method that you would like to use
* **Result Reference**. If you are using multiple Cloud Automation Nodes in your business process, it is good practice to give each Cloud Automation Node a unique Result Reference. With each Method having the ability to return Output parameters such as an ID, Reference number, etc you may want to use these Output parameters in other business process nodes, and they will be identified in your variable picker by their Result Reference name.If a unique name is not given, every result reference option in the variable picker will be represented with the default Integration name.
* **Continue on Error**. By default, this is set to No, and the business process will not continue if the Cloud Automation fails. Change this to Yes if you wish the business process to continue even if the Cloud Automation fails.

### Request Credentials
If using the Hornbill Integration Bridge, once a method has been selected, you will need to select a credential from the Request Credentials list.
* The available credentials are populated via KeySafe, the list is filtered based on the Authentication Type required by the Integration method.
* If the list is empty, the type of credential is shown by hovering the mouse over the i against the credential. You can go to KeySafe and create a set of credentials for the type of method you are trying to use.

#### Examples
* You would need to define in KeySafe the Twitter account credentials you want to tweet from, or the ServiceNow instance you want to create an Incident on, and which user account you want to create the Incident in the context of.
* You can create multiple sets of credentials for the same Methods, for example, if you wanted to tweet from different Twitter Accounts, you can create different request credentials for each Twitter account in KeySafe and then select which one to use from the Request Credentials for the Twitter Methods in each Cloud Automation node you configure.

### Parameters
Each Method will have a set of specific request parameters (Inputs). These are the inputs that you can pass to the solution you are integrating too.
* Request Parameters marked with the red Mandatory marker must be populated
* You can use the Variable Picker on request parameter fields to pass in variable values from request attributes such as Progressive Capture Answers, Custom Field Values, Task Outcomes, Request Service, and Customer attributes.
* Depending on the method chosen, the request parameter fields may contain Data Provider values from the solution you are integrating too, for example, in ServiceNow LogIncident, the actual State, Impact, and Urgency values from the ServiceNow Instance specified in the chosen Request Credentials will be available to you to choose from.

### Response Parameters
Most methods will return Response Parameters (Outputs) once they complete. You may wish to use these later or further down your business process. For example, if you chose to create a new Board using the Trello CreateBoard method, one of the response parameters will be the newly created board's id. This id can then be used as a request(input) parameter for another Cloud Automation, or example if you wanted to add a List or Card to the Trello Board.
* The Response Parameters will be available to use from the Variable Picker and will be listed under each Result Reference name.


## Documentation
Click on the ![Question](/_books/esp-config/images/workflow-help-button.png) icon to view information relating to the input and output parameters for the method.

More information is also available on each solution via the [iBridge Package Reference documentation](/ibridge-packages/welcome).