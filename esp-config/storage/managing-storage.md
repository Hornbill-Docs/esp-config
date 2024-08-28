---
layout: article-toc
---

Storage over and above the instance storage quota attracts an additional monthly cost. While this is a nominal fee, regular housekeeping and some best-practice guidelines can help you manage your storage effectively.

You can review the storage consumed by your Hornbill instance in ~~Hornbill Administration > Your Subscription.~~ *??Should this be the following?* Configuration > Hornbill Solution Center > Subscription > Your Usage.

For more detail on our approach to Cloud storage, see [Data Storage](/hornbill-cloud/data-storage).

## Emails
Emails are typically the biggest contributor to storage consumption and, as the content and attachments are quite often appended to a request, their relevance and value diminishes quickly.

### Set purge thresholds
The Hornbill platform incorporates settings that purge the Sent and Deleted Items folders of email messages older than a certain number of months. The default value for these settings is 240 months (20 years of a maximum of 20 years) and 36 months (3 years of a maximum of 7 years) respectively. Any messages that are older than the purge thresholds specified in the settings will be permanently deleted from these folders.

You can find the settings in Configuration > Platform Configuration > Advanced Tools & Settings > Advanced System Settings and are called `emails.purgeDeletedItemsAfter` and `emails.purgeSentItemsAfter`.

Each shared mailbox on your Hornbill instance has a Deleted Items folder and a Sent Items folder. These settings are global; the purge threshold applies to all shared mailboxes. The background job responsible for the purge on these folders runs several times a day.

Email messages and associated attachments will be deleted from your Hornbill instance. This process has no effect on messages stored outside of Hornbill.

### Selectively delete email messages
Mailbox folders can also be managed via the main mailbox interface where messages can be selected and deleted as required. Messages will only be permanently deleted once they are moved to the deleted items folder. When using this method, messages must first be moved to the deleted items folder, and then selected and permanently deleted. Only users with the appropriate permissions to a shared mailbox will be able to permanently delete messages from the Deleted Items folder.

### Archive Email Messages and Attachments
The Email Archiver utility provides a simple, safe and secure way to archive email messages and their associated attachments from a Hornbill instance. The utility downloads the email message and attachments from a Hornbill instance and saves them in a location on a local machine of your choice.

Once downloaded, the email message and attachment will be deleted and will no longer be accessible from your Hornbill instance. Emails and their attachments will be available for reference in the location to which they were downloaded.

### Empty an Entire Email Message Folder
An entire folder can be emptied via an interface located in Hornbill Administration. This can be found in System > Email > Shared Mailboxes. Select a shared mailbox and then the tab labeled “status”. All folders which exist for that mailbox will be listed. The folder can be emptied by clicking on the red trash-can icon.

## Workflows
As System administrators come and go and your Service Delivery evolves, the number of business processes configured in your instance will inevitably grow over time. This is one area where good house keeping is important, not just from a storage perspective, but also from an administrative standpoint. Business Processes can be managed via the Hornbill Administration interface in the business process section associated with the application e.g. Service Manager Hornbill Administration > Applications > Service Manager > Business Processes.

### Ensure your Business Processes are Reliable
Failed business processes can contribute to greater storage consumption. As part of business process execution, an event log is generated so it’s actions and responses can be reviewed in the event of an issue or error. An event log is generated for every business process which is running in the application.

Assuming the business process reaches a successful conclusion (i.e. a state of “Completed”) or is canceled (a state of “Canceled”) it’s logs are purged 7 days after it entered one of these states. Logs are only maintained for business process instances with a state of “in progress”, “suspended”, or “failed”. Business process that are “in progress” or “suspended” are still active, however those that are in a failed state have encountered problems and have stalled. Logs for failed processes are retained for much longer (3 months) so action should be taken to understand the reason for failure and address this in the process design so further business process instances can avoid failure. Processes that have already failed should be dealt with appropriately either by fixing or canceling the specific business process instance.

The detail of any active business process can be inspected via the Hornbill Administration interface in the business process section associated with the application (e.g. Service Manager). There is a button located to the top right of the list of bpm processes labeled “Manage Executed Processes” which presents a list of all the active business process instances.

The “Manage Executed Processes” area should be checked periodically to ensure processes are running reliably through to completion. Any failed processes should be investigated and the root caused addressed.Ensure your Business Processes are Reliable
Failed business processes can contribute to greater storage consumption. As part of business process execution, an event log is generated so it’s actions and responses can be reviewed in the event of an issue or error. An event log is generated for every business process which is running in the application.

Assuming the business process reaches a successful conclusion (i.e. a state of “Completed”) or is canceled (a state of “Canceled”) it’s logs are purged 7 days after it entered one of these states. Logs are only maintained for business process instances with a state of “in progress”, “suspended”, or “failed”. Business process that are “in progress” or “suspended” are still active, however those that are in a failed state have encountered problems and have stalled. Logs for failed processes are retained for much longer (3 months) so action should be taken to understand the reason for failure and address this in the process design so further business process instances can avoid failure. Processes that have already failed should be dealt with appropriately either by fixing or canceling the specific business process instance.

The detail of any active business process can be inspected via the Hornbill Administration interface in the business process section associated with the application (e.g. Service Manager). There is a button located to the top right of the list of bpm processes labeled “Manage Executed Processes” which presents a list of all the active business process instances.

The “Manage Executed Processes” area should be checked periodically to ensure processes are running reliably through to completion. Any failed processes should be investigated and the root caused addressed.

### Delete Old Process Designs
Deleting old processes that are no longer used will help manage the storage consumed. Processes can be deleted using the trash can icon located to the right hand side of the process. Processes can only be deleted if there are no active instances of the design running in the application e.g. in the case of service manager business processes run against requests.

### Design Efficiently
Many business process operations have the option to post a timeline update to a request as part of performing the operation. While an individual timeline update doesn't contribute a great deal to storage consumption, these will accumulate over time. Consider whether a timeline update as part of the business process operation is really necessary before enabling it. The timeline content generated by business process nodes can be controlled in the configuration of each node by setting the “System Timeline Update” and “Manual Timeline Update” parameters to “ignore”.
xxx

## Requests
Requests are at the center of the Service Manager application and as time passes more requests will be created.

### Archive Request Attachments
The Request Attachment Archiver utility provides a simple, safe and secure way to extract file attachments from a Hornbill instance. The utility downloads attachments from a Hornbill instance and saves them in a location on a local machine of your choice.

Once downloaded, the attachment will be deleted from the request and will no longer be accessible from your Hornbill instance. The utility does not affect the request in any other way.

### Delete Selected Requests
The Hornbill Clean Utility provides a quick and easy method of removing requests, from a specified Hornbill instance. This utility allows requests to be deleted based on various criteria such as date logged, status, individual request ID, or service. Clearing out test requests periodically is good practice or some organizations may wish to delete requests older than x number of years. The utility will delete the request record, associated timeline and attachments.

<!-- esp-config/storage/managing-storage>