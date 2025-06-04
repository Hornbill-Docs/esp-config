# Authorization
This workflow automation allows you to add authorizations to a workflow. One or more Hornbill Users can be added to a single authorization and the workflow is suspended until an outcome for the authorization has been provided.

## Authorization Owner
The owner of an authorization is someone that may not be participating in the authorization, but require visibility and control of the authorization. An example of this may be the manager of the person that is providing the authorization or someone who is overseeing the authorization and requires the ability to authorize on behalf of the authorizers.

* **User**<br>Use this option to select from available users that have access to authorizations. Basic Users are not available to be selected.
* **Variable**<br>Using variables can be a great way to allocate authorizers where the participants are not static. It is still important to remember that only Users with a Collaboration Subscription can participate and you need to assure that users that don't have a subscription are not accidentally allocated as an authorizer. The provided variable must contain the User's ID

## Authorizers
In order for someone to participate in an authorization, they must be set up as a User and have a Collaboration subscription.

* **User**<br>Use this option to select from available users that have access to authorizations. Basic Users are not available to be selected.
* **Variable**<br>Using variables can be a great way to allocate authorizers where the participants are not static. It is still important to remember that only Users with a Collaboration Subscription can participate and you need to assure that users that don't have a subscription are not accidentally allocated as an authorizer. The provided variable must contain the User ID.
* **Weighting Level**<br>This is a powerful option to allow you to allocate the level that each individual contributes to the overall authorization. For each authorizer, a default 100% weight level is given. Independent of the number of authorizers, someone with a 100% weight level is able to complete the authorization on their own. If you have two authorizers, and both are set to a 50% weight level, then both authorizers must provide a response. When including multiple authorizers, you must assure that any combination of weighting levels must total up to 100% in order for the authorization to proceed.

## Task
* **Title**<br>The title of the Authorization is displayed in a number of places and will typically be a short descriptive title that clearly describes to the user what the authorization is for. This title will be available on the Hornbill Notifications, Email Notifications, Task View, and on the different apps that use authorizations.
* **Category**<br>Set a category for the authorization, which can be viewed by the user within their Task List View.
* **Priority**<br>Setting a priority will allow users to view and filter their authorizations from their Task List View.

## Outcome Settings
Outcome options come with three different types of outcomes, with the Tentative outcome being optional. Authorize and Reject are required outcomes. Additional outcomes cannot be added to an authorization.

* **Enable Tentative Authorization**<br>This will enable the Tentative option and make it visible within the list of available outcomes.
* **Authorize**<br>This outcome is provided for authorizers to approve the authorization. Weighting levels will apply when this outcome is selected.
* **Reject**<br>This outcome is provided for authorizers to reject the authorization. It only takes one authorizer to reject an authorization. Weighting levels do not apply. When there are multiple authorizers participating in the authorization, independent of their weighting level, a single rejection will reject the entire authorization. The authorizations sent to the other authorizers will be canceled.
* **Tentative**<br>A tentative outcome provides a 3rd optional outcome which may be used for scenarios such as an authorizer wanting additional criteria to be completed before continuing. It only takes one authorizer to select a tentative outcome. Weighting levels do not apply. When there are multiple authorizers participating in the authorization, independent of their weighting level, a single tentative outcome will apply to the entire authorization. The authorizations sent to the other authorizers will be canceled.

:::tip
Within your workflow an Authorization can be followed by a Decision Node where you can branch on the outcome of your authorization. This allows you to take different actions or paths based on the outcome. Please note that the Decision Node must immediately follow to the Authorization node in order to have access to the outcomes.
:::

## Life Span Settings
The Life Span Settings allow you to place an expiry on the authorization. Once an authorization has expired, any pending authorizations will be canceled and the authorization node will provide an outcome of expired

* **Start**<br>This option places the authorization into the user's task calendar with the provided start time. The start time is defined by the number of Days, Hours, or Minutes from the time the authorization was created.
* **Due After**<br>This option works with the Start option where it adds a start/due range on the authorization within the Task Calendar. The Due After is defined by the number of Days, Hours, or Minutes from the Start. When set, an additional option to send a reminder is made available. Reminders can be sent to the owner and assignee(s), just the owner, or just the assignee(s)
* **Expires After**<br>This option allows you to limit how long the Authorization is available for. Once this time has passed, the authorization(s) will be canceled. An outcome will be set to Expired

## Authorization Details
The Authorization Details are the content of the authorization task that is being sent to the different authorizers. This will allow you to present information about the authorization to the assignee so that it is clear what they are authorizing. Outcomes from previous BMP nodes can provide information in the form of variables that can be used to populate the details.

## Set Stage Checkpoints
You are able to select stage checkpoints that are met when this node is reached. Checkpoints must first be defined under the Manage Current Stage button located in the BPM designer toolbar.

## Service Manager Authorizations
A Hornbill user that does not have a subscription to Service Manager has the opportunity to view the Change or Service Request that requires their authorization in a View Only mode. The Authorization task provides a link to the request which will open the request via the Employee Portal.

<!-- https://wiki.hornbill.com/index.php?title=BPM_Authorization -->