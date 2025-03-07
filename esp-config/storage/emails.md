---
layout: article-toc
---

Storage over and above the instance storage quota attracts an additional monthly cost. While this is a nominal fee, regular housekeeping and some best-practice guidelines can help you manage your storage effectively.

You can review the storage consumed by your Hornbill instance in Configuration > Hornbill Solution Center > Subscription > Your Usage.

For more detail on our approach to Cloud storage, see [Data Storage](/hornbill-cloud/data-storage).

## Emails
Emails are typically the biggest contributor to storage consumption and, because their content and attachments are quite often appended to a request, their relevance and value diminishes quickly.

### Set purge thresholds
The Hornbill platform incorporates settings that purge the Sent and Deleted Items folders of email messages older than a certain number of months. The default value for these settings is 240 months (20 years of a maximum of 20 years) and 36 months (3 years of a maximum of 7 years) respectively. Any messages that are older than the purge thresholds specified in the settings will be permanently deleted from these folders.

You can find the settings in Configuration > Platform Configuration > Advanced Tools & Settings > Advanced System Settings and are called `emails.purgeDeletedItemsAfter` and `emails.purgeSentItemsAfter`.

::: important 
Each shared mailbox on your Hornbill instance has a Deleted Items folder and a Sent Items folder. These email-purge settings are global; the purge threshold applies to all shared mailboxes. The background job responsible for the purge on these folders runs several times a day.
::: 

Email messages and associated attachments will be deleted from your Hornbill instance. This process has no effect on messages stored outside of Hornbill.

### Selectively delete email messages
Mailbox folders can also be managed via the main mailbox interface where messages can be selected and deleted as required. Messages will only be permanently deleted once they are moved to the Deleted Items folder. When using this method, first move messages to the Deleted Items folder, then select and permanently delete them. Only users with the appropriate permissions to a shared mailbox will be able to permanently delete messages from the Deleted Items folder.

### Archive email messages and attachments
The Email Archiver utility provides a simple, safe, and secure way to archive email messages and their associated attachments from a Hornbill instance. The utility downloads the email message and attachments from a Hornbill instance and saves them in a location on a local machine of your choice.

Once downloaded, the email message and attachment will be deleted and will no longer be accessible from your Hornbill instance. Emails and their attachments will be available for reference in the location to which they were downloaded.

### Empty an entire email message folder
To empty an entire folder, navigate to Configuration > Platform Configuration > Email > Shared Mailboxes. All folders that exist for that shared mailbox will be listed. 

Click a shared mailbox, then in the Status tab, find the folder you want to empty and click its red **Empty Folder** button. 

<!-- esp-config/storage/emails>