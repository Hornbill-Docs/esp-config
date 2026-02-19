# IT Automation

Introduction The **IT Automation** node is used to execute an ITOM package operation in a similar way to that of creating an IT Automation Job. Each time the node is used, a new Job will appear in the Job queue where it can be monitored/managed in the same manner as other ITOM jobs.

## Adding the IT Automation Node

* From an existing Node within a workflow

1. Place the mouse pointer over the node to expose the connection arrows.
2. From a connection arrow, drag out a new connection line
3. Select _IT Automation_

* From a Connection Line between to nodes

1. Select the Connection Line and Right Click
2. Select _Add node between connected nodes_ from the context menu
3. Select _IT Automation_

> IT Automation nodes are displayed in Tan; to help differentiate from other node types.

## Configuration

Two options are available to expose the properties of the IT Automation process node, place the mouse pointer over the node to expose the **Cog** icon and click on this icon or double click anywhere on the node.

### IT Automation

* **Language**

Select the language to work in, this defaults to the language set in the user's profile. If other users require viewing the workflow in a different language, translations can be provided by selecting the language and entering the appropriate translations.

* **Display**

Provide the node with a display name that will appear on the workflow design canvas

* **Description**

Optional text area that can be used to provide a description detailing the node's function

### Job Request

* **Package**

Package used to provide the IT Automation payload

* **Operation**

Operation to perform using the package

* **Priority**

Set the Jobs Priority which ranges from Urgent - Execute the Job as soon as possible, pushing the Job to the top of the queue to Only execute the Job when the server is in idle mode, and will also push the Job to the bottom of the queue

* **Site Target**

Specify the SIS Server or Group that will facilitate the Automation Job

* **Target Machine**

Select the Device(s) that the Operation will target

* **_List_**

Target Machines are sourced from a pre-created Inventory List

* **_Inventory_**

Select a Machine from the ITOM Inventory

* **_Manual_**

Manually entered Machine name(s), that must already exist in the ITOM Inventory and is marked as a Managed device

* **Credentials**

Sourced from the KeySafe, provides the security context to be used for package deployment and execution

* **_Admin Credentials_**

Security Context used to deploy the package onto the target device(s)

* **_Run As Credentials_**

Security Context used to execute the package on the target device(s) (if not provided then Admin Credentials are used)

* **Extra Credentials**

Optional credentials used as part of the functionality within the package

* **Operation Parameters**

Once a package and a Run Operation has been selected, any related parameters will be displayed; mandatory fields are highlighted and hints may be provided in the input box.

* **Result Reference**

A variable that refers to an object that enables access to the output parameters returned by a node anywhere within a process. Each node can be given a unique variable name allowing for the output of multiple nodes to be accessed. Where a unique name is not given, the output from the current node will overwrite all output from a previously executed node with the same result reference variable.

* **Continue on Error**

When this option set to _No_ (default), the workflow will not continue if the IT Automation fails. Setting the option to _Yes_ enables the workflow to continue execution after the failed IT Automation node.
