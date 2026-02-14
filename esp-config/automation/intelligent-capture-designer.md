# Intelligent Capture Designer

Intelligent Capture is a graphical workflow tool that lets you define a script that is used to gather information from users. Using a visual interface, you can build custom workflows that guide users through a series of questions or data entries.

## Before you begin

* Be familiar with using [Configuration](/esp-config/getting-started/using-configuration).
* You will need either the Admin or the Intelligent Capture Manager [system role](/esp-config/organizational-data/roles#system-roles) to access the designer in Configuration.

## Nodes

In the development of a capture workflow, several distinct nodes are available for use in your design.

![Intelligent Capture Nodes](/_books/esp-config/images/capture-nodes.png)

* **Start** - Every capture workflow must have a Start node. This is the entry point for all capture workflows.
* **Form** - You can choose from several pre-configured forms and place them in the sequence you need.
* **[Customized Form](/esp-config/automation/customized-forms)** - Create a form with custom fields and values.
* **[Decision Node](/esp-config/automation/capture-decision-node)** - Take alternative paths within the script based on defined expressions.
* **Switch Capture** - Allows you to link capture workflows together and seamlessly switch from one to another.
* **End** - Every capture workflow must have at least one End node. When the end is reached, the responses to the forms will be processed.
* **Cancel** - The Cancel node allows the capture workflow to exit without being  processed. This behaves the same as if the user had selected the cancel button that is available when filling out a capture. The user will be returned to where the Intelligent Capture was initiated from.

    :::tip
    Any form that precedes a Cancel node will display a `Cancel` button in place of the `Finish` button.
    ![Cancel Capture](/_books/esp-config/images/capture-cancel-button.png)
    :::

### Switch capture

The Switch Capture node provides the ability to seamlessly move to or link capture workflows together.

Using this node replaces the previous behavior of jumping from an initial capture workflow to another, and in essence, any forms used in both are evaluated and reused when jumping. It also removes the need to evaluate which forms in the second capture workflow to use, and any issues associated with capture forms being skipped.

Using this node will in effect, continue from the initial capture workflow into the next capture workflow rather than replace it. This means it does not need to evaluate which forms to skip; it simply ignores any forms already used in the initial capture.

#### Advantages of using the switch capture node

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

* **Download** - Download the definition file. It downloads to a .txt file a copy of the current capture workflow.
* **Upload** - Upload a pcf.txt file to the capture workflow. This will replace the current capture workflow content.
* **Print** - Print out a document that provides a graphical representation of the capture workflow.
* **Save** - (Validate, Activate, De-activate) After the creation or editing of a capture workflow, your workflow needs to be saved and then activated to make it available for use. Any capture workflow that you wish to keep but do not have available for use can be deactivated.

### Session variables

You can make your forms feel more personal by automatically pulling in the user's information. To do this, place the variable inside double curly brackets in any field label or description.

* **user.fName** - Displays the first name of the logged-in user.
* **user.lName** - Displays the last name of the logged-in user.
* **user.accountRefUrn** - Displays the URN ID of the logged-in user.
* **user.currentTimeZoneOffset** - Displays the current time based on the user's time zone setting.
* **user.userId** - Displays the User ID of the logged-in user.
* **user.userName** - Displays the full name (first and last) of the logged-in user.
* **user.jobTitle** - Displays the job title of the logged-in user.
* **user.mobile** - Displays the mobile phone number of the logged-in user.
* **user.email** - Displays the email of the logged-in user.
* **user.phone** - Displays the work phone number of the logged-in user.
* **user.managerName** - Displays the name of the manager of the person raising the request.
* **user.siteName** - Displays the name of the user's site as set on their profile.
