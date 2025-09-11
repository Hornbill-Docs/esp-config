# Intelligent Capture Designer
Intelligent Capture is a graphical workflow tool that provides a simple way to define the capturing of information. Intelligent Capture includes several types of forms for collecting information. These forms can be added, ordered, and have different paths defined that can be taken depending on the information being captured.

## Before you begin
* Be familiar with using [Configuration](/esp-config/getting-started/using-configuration).
* Users require either the Admin Role or the Progressive Capture Manager role to access the designer in Configuration.

## Nodes
When building a capture workflow, there are a few different nodes that are available to use when considering your design.

![Intelligent Capture Nodes](/_books/esp-config/images/capture-nodes.png)

* **Start**<br>Every capture workflow must have a Start node. This is the entry point for all capture workflows.
* **Form**<br>You can choose from several pre-configured forms (in Form Properties) and place them in the sequence you need.
* **Custom Form**<br>Allows you to create a form complete with custom fields and values.
* **Decision Node**<br>Allows a capture workflow to take alternative paths within the script based on defined expressions.
* **Switch Capture**<br>Allows you to link capture workflows together and seamlessly switch from one to another.
* **End**<br>Every capture workflow must have at least one of these to end the workflow.
* **Cancel**<br>The Cancel node allows the capture workflow to exit without any further processing. This behaves the same as if the user had selected the cancel button that is available when filling out a capture. The user will be returned to where the Intelligent Capture was initiated from.

    :::tip
    Any form that precedes a Cancel node will display a `Cancel` button in place of the `Finish` button.
    ![Cancel Capture](/_books/esp-config/images/capture-cancel-button.png)
    :::

### Decision node
The decision node allows the workflow designer to send the user down different paths to collect information based on the choices that are made on the previous forms or based on session and global variables.

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

#### Custom expressions
Custom Expressions allow you to define a *Goto if* statement based on the preceding nodes' outcomes, global variables, or session variables.

![Custom Expression](/_books/esp-config/images/custom-expression.png)

* You can use outcome values from any form that has been used in the capture workflow before the decision node. 
* You can use a global variable in the custom expression to change the path. For example, if the customer is being completed by a support user in the user app, you may want to follow a different path compared to if the same capture was being completed by a user or contact on either the employee or customer portals.
* You can use session variables that take into consideration information about the user who is using the capture.

### Switch capture
The Switch Capture node provides the ability to seamlessly move to or link capture workflows together. 

Using this node replaces the previous behavior of jumping from an initial capture workflow to another, and in essence, any forms used in both are evaluated and reused when jumping. It also removes the need to evaluate which forms in the second capture workflow to use, and any issues associated with capture forms being skipped.

Using this node will in effect, continue from the initial capture workflow into the next capture workflow rather than replace it. This means it does not need to evaluate which forms to skip; it simply ignores any forms already used in the initial capture.

**Advantages of using the switch capture node**
* When switching captures, the user experience for the analyst is smooth as you are linking one process to another, not replacing one with another.
* The ability to return to the forms in the initial capture, once you have switched or linked to a second capture to change choices or even change which capture to switch to.
* You don't need to include the same forms in both captures. 

## Sharing and visibility
Intelligent Capture owners will be able to view their own captures scripts as well as capture scripts that have been shared with them from the capture workflow list.

When creating or editing a capture, it is possible via the Manage Process Settings and Grant Access To option to share your process with:

* Roles
* Users
* Groups

It is possible to share captures with multiple users, roles, and groups. Once a capture has been shared, the user will be able to view the capture from the Intelligent Capture list.

To remove visibility to a specific User, Role, or Group, click **Delete** (the trash can icon) next to the item you wish to stop sharing the capture with.

To enforce the above sharing and visibility controls, ensure the system setting security.bpm_access_controls.enabled is set to ON from the Platform Configuration.

## Intelligent capture options
Each capture workflow has a number of configuration options:

* **Download**<br>Download the definition file. It downloads to a .txt file a copy of the current capture workflow.
* **Upload**<br>Upload a pcf.txt file to the capture workflow. This will replace the current capture workflow content.
* **Print**<br>Print out a document that provides a graphical representation of the capture workflow.
* **Save** (Validate, Activate, De-activate)<br>After the creation or editing of a capture workflow, your workflow needs to be saved and then activated to make it available for use. Any capture workflow that you wish to keep but do not have available for use can be deactivated.

## Global variables
Global variables are available throughout the Intelligent Capture workflow. These allow custom expressions on decision nodes to be used based on the following values:

* **Portal Type**<br>This global variable lets you determine the path based on one of two entry points. This could either be from one of the customer portals (Portals) or the main Hornbill client (Service Desk).

* **Source**<br>This global variable lets you determine the path of an Intelligent Capture script based on the provided sources. The options for source include Analyst, Chat, Email, Post, Request, and Self Service.

Personalize Intelligent Capture forms based on the logged-in user. The variables listed below can be used within the Custom Forms on the Form Prompt, Field Labels, and Field Descriptions. Each variable is placed within a double set of curly brackets. For example: {{user.fName}}.

* **user.fName**<br>Displays the first name of the logged-in user.
* **user.lName**<br>Displays the last name of the logged-in user.
* **user.accountRefUrn**<br>Displays the URN ID of the logged-in user.
* **user.currentTimeZoneOffset**<br>Displays the current time based on the user's time zone setting.
* **user.userId**<br>Displays the User ID of the logged-in user.
* **user.userName**<br>Displays the full name (first and last) of the logged-in user.
* **user.jobTitle**<br>Displays the job title of the logged-in user.
* **user.mobile**<br>Displays the mobile phone number of the logged-in user.
* **user.email**<br>Displays the email of the logged-in user.
* **user.phone**<br>Displays the work phone number of the logged-in user.
* **user.managerName**<br>Displays the name of the manager of the person raising the request.
* **user.siteName**<br>Displays the name of the user's site as set on their profile.
