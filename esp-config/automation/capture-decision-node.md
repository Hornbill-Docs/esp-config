# Capture Decision Node

The decision node allows the intelligent capture designer to send the user down different paths to collect information based on the choices that are made on the previous forms or based on session and global variables.

![Branch Form](/_books/esp-config/images/decision-node.png)

A decision node inherits the outcomes from all of the preceding forms. These outcomes can determine which path is taken.

* Each decision node connector includes a *Goto if* statement that determines if that path will be taken.
* To define the *Goto if* statement, you must first connect the decision node to the next node in the workflow.
* The first connector will automatically have the *Goto if* statement set to *No Match*.
* Subsequent connectors will require a *Goto if* statement to be set up before the workflow can be validated.
* Click on the connector's label to change the *Goto if* statement.
* There must always be a valid *Goto if* statement for all possible outcomes; otherwise, the capture could potentially have nowhere to go and result in an error. It is recommended to always have a *Goto if* statement on one of the paths set to *No Match*.

:::tip
There is a maximum of three paths on a decision node.  Additional paths can be achieved by daisy-chaining more than one decision node.
:::

## Custom expressions

Custom Expressions allow you to define a *Goto if* statement based on the preceding nodes' outcomes, global variables, or session variables.

![Custom Expression](/_books/esp-config/images/custom-expression.png)

* You can use outcome values from any form that has been used in the capture workflow before the decision node.
* You can use a global variable in the custom expression to change the path. For example, if the customer is being completed by a support user in the user app, you may want to follow a different path compared to if the same capture was being completed by a user or contact on either the employee or customer portals.
* You can use session variables that take into consideration information about the user who is using the capture.

### Global variables

* **Portal Type** - Use this to determine if the capture is being completed on one of the portals or from within the service desk.  This variable will have the value of `Portal` if running on one of the portals  or `Service Desk` if running from within the main Service Manager app.
* **Source** - Used to determine the exact source of where the capture is being completed.  This variable will be set to one of the following values: Analyst, Chat, Email, Post, Request, or Self Service.

### Session variables

Decisions can be made based on who is responding to the questions on the capture script.

* User ID
* Login ID
* User Name
* Users Manager Name
* Location Name
* Job Title
* User Has Role
