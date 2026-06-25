# Auto Assign Authorization

This node is used to invoke authorization tasks from a predefined list of authorizers. This helps remove the need for named authorizers being stored within the configuration of the workflow. As employee's roles change or people leave the organization, this will minimize having to update workflows as the authorizers change.

![Auto Assign Authorizers](/_books/esp-config/automation/images/auto-assign-authorizers.png)

## Prerequisites

The **Auto Assign Authorizers** node cannot work in isolation.  It must be preceded by a node that collects the users that will participate in the authorization. These nodes include the following:

* **[Wait for List of Request Authorizers](/servicemanager-config/customize/workflows/requests-automation#suspend)**
* **Get Authorizers by Group**
* **Get Authorizers by Role**

## Example workflow

![Auto Assign Authorizers Workflow Example](/_books/esp-config/automation/images/auto-assign-workflow.png)
